---
title: "Terraform"
date: 2020-05-06T11:13:46+02:00
---

## Install terraform

```
cd /tmp
curl https://releases.hashicorp.com/terraform/0.12.24/terraform_0.12.24_linux_amd64.zip -o terraform_0.12.24_linux_amd64.zip
unzip terraform_0.12.24_linux_amd64.zip
sudo mv terraform /usr/local/bin/
[jroussel@nephtys tmp]$ terraform --version
Terraform v0.12.24
```

## Install terraform-libvirt-provider

The github project for this provider is available [here](https://github.com/dmacvicar/terraform-provider-libvirt#downloading).

```
sudo dnf install libvirt-devel
mkdir -p $GOPATH/src/github.com/dmacvicar; cd $GOPATH/src/github.com/dmacvicar
git clone https://github.com/dmacvicar/terraform-provider-libvirt.git
cd $GOPATH/src/github.com/dmacvicar/terraform-provider-libvirt
make install
mkdir -p $HOME/.terraform.d/plugins
cp $GOPATH/bin/terraform-provider-libvirt $HOME/.terraform.d/plugins
```

## Test terraform provider

```
cd /tmp
mkdir terraform-test && cd terraform-test
cat<<EOF > test.tf
provider "libvirt" {
    uri = "qemu:///system"
}
resource "libvirt_domain" "terraform_test" {
  name = "terraform_test"
}
EOF
terraform init
terraform plan
terraform apply
terraform destroy
```
