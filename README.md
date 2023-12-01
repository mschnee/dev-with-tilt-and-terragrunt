Development with Tilt and Terragrunt
====================================

This repository presents an example of developing applications and infrastructure using Tilt as the CI/CD tool, and terragrunt to manage the resources.


# Categories
There are two __Categories__ of environments provided as examples: `localhost` and `aws`.

The `localhost` category is a kubernetes cluster run on your localhost.  Setting that up is outside of the scope of this project: but there are lots of options, including [Rancher Desktop](), [Docker Desktop](), [kind](kind), [minikube](), to name a few.

The `aws` category represents infrastructure in AWS.

# Environments
In each category, there are three __Environments__: `localdev`, `development`, and `production`.

Consider **Production** to be, well, production.  This is what you expect your end-users to interact with.

The **Development** environment is the place where QA and integration work would be represented.  

The **localdev** environment is where the real magic happens: in both the `localhost` and `aws` __categories__, the infrastructure defined for "localdev" is what is managed by Tilt.  This infrastructure is namespaced to a specific developer in every way possible: everything from the FQDN of URIs to the kubernetes namespaces to resource names are prefixed to the developer's given name.  These resources are created with `tilt up`, and they are destroyed with `tilt down`de