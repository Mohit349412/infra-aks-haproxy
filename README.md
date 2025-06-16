# AKS + HAProxy Ingress Terraform Example

This repository provisions an Azure Kubernetes Service (AKS) cluster using Terraform and deploys the latest HAProxy ingress controller via the Helm provider.

## Prerequisites

- [Terraform](https://www.terraform.io/downloads.html)
- Azure CLI authenticated (`az login`)
- Helm (for inspecting charts, optional)

## Usage

1. **Clone this repo**
   ```sh
   git clone https://github.com/Mohit349412/infra-aks-haproxy.git
   cd infra-aks-haproxy
   ```

2. **Initialize Terraform**
   ```sh
   terraform init
   ```

3. **Apply the configuration**
   ```sh
   terraform apply
   ```

   You will be prompted for confirmation before resources are provisioned.

4. **Output**
   - AKS cluster is created.
   - HAProxy ingress controller is installed using the latest chart version.

## Customization

Edit `variables.tf` or supply variables via CLI to customize node count, region, cluster names, etc.

## Cleanup

```sh
terraform destroy
```

---

**Note:** This will install the latest version of the HAProxy ingress Helm chart by default. If you want to pin to a specific version, set the `version` attribute in the `helm_release` resource in `main.tf`.
