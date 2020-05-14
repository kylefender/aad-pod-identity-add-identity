# aad-pod-identity

This was copied from the [Azure/aad-pod-identity](https://github.com/Azure/aad-pod-identity) repository. We'll use this to deploy the per environment/instance pieces (AzureIdentity and AzureIdentityBinding).

[aad-pod-identity](https://github.com/Azure/aad-pod-identity) enables Kubernetes applications to access cloud resources securely with [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory/) (AAD).

## Introduction

A simple [helm](https://helm.sh/) chart for setting up the components needed to use [Azure Active Directory Pod Identity](https://github.com/Azure/aad-pod-identity) in Kubernetes.

This helm chart will deploy the following resources:

* AzureIdentity instance
* AzureIdentityBinding instance

## Configuration

The following tables list the configurable parameters of the aad-pod-identity chart and their default values.

| Parameter | Description | Default |
| --- | --- | --- |
| `azureIdentity.enabled` | Create azure identity and azure identity binding resource | `false` |
| `azureIdentity.name` | Azure identity resource name | `azure-identity` |
| `azureIdentity.namespace` | Azure identity resource namespace. Default value is release namespace | |
| `azureIdentity.type` | Azure identity type - type 0: MSI, type 1: Service Principal | `0` |
| `azureIdentity.resourceID` | Azure identity resource ID | |
| `azureIdentity.clientID` | Azure identity client ID | |
| `azureIdentityBinding.name` | Azure identity binding name | `azure-identity-binding` |
| `azureIdentityBinding.selector` | Azure identity binding selector. The selector defined here will also need to be included in labels for app deployment. | `demo` |
