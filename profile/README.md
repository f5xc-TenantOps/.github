<p align="center">
  <img src="https://github.com/f5xc-TenantOps/.github/blob/main/xcTenantOps-logo.jpg?raw=true" height="256"/>
</p>

# F5 Distributed Cloud Tenant Operations

## 👋 About
This repository stores all tooling used to handle operations across a fleet of F5 Distributed Cloud tenants.
This includes demos, labs, reporting, and internal tenant operations used by F5ers (and others) to learn about the platform.

## 🌈 Contribution Guidelines
<ul style="list-style-type:square">
    <li>Code updates must be made via PRs. Thou shalt not commit directly to <code>main</code>.</li>
    <li>Use Github issues to request updates and report bugs.</li>
    <li>Be nice ♥️</li>
</ul>


## 👩‍💻 Useful resources
<img src="https://www.f5.com/content/dam/f5/f5-logo.svg" alt="" height="25"/> [F5 Distributed Cloud Knowledge Hub](https://docs.cloud.f5.com/docs-v2)

<img src="https://www.f5.com/content/dam/f5/f5-logo.svg" alt="" height="25"/> [F5 Distributed Cloud Services API](https://docs.cloud.f5.com/docs-v2/api)

<img src="https://argo-cd.readthedocs.io/en/stable/assets/logo.png" alt="" height="25"/> [ArgoCD](https://argo-cd.readthedocs.io/en/stable/)

<img src="https://www.crossplane.io/_next/static/media/icecream-icon.0e89f4c8.svg" alt="" height="25"/> [CrossPlane](https://www.crossplane.io)


## 🤔 Philosophy
<ul style="list-style-type:square">
    <li><b>All</b> infrastructure is expressed in code</li>
    <li>Infrastructure components are deployed using GitOps and continuous delivery principals</li>
    <li>Code is executed in containers or in serverless infrastucture</li>
    <li>State is stored in cloud native tooling</li>
    <li>No bespoke components</li>
</ul>

## 🏛️ Architecture
- [ ] Component Arch
- [ ] Event Flow
- [ ] Log/reporting system

## 🗂️ Repositories

### <img src="https://s3.dualstack.us-east-2.amazonaws.com/pythondotorg-assets/media/files/python-logo-only.svg" alt="" height="25"/> f5xc-tops-py-client
Python library for interacting with the F5 Distributed Cloud API.

### <img src="https://s3.dualstack.us-east-2.amazonaws.com/pythondotorg-assets/media/files/python-logo-only.svg" alt="" height="25"/> f5xc-tops-py-common
Python library of common components used by workers. 
This helps keep things DRY.

### <img src="https://raw.githubusercontent.com/kubernetes/kubernetes/d88b4e3b6e34a85f58778b7ef96e64edffff6823/logo/logo.svg" alt="" height="25"/> f5xc-tops-mgmt-cluster
- [x] ArgoCD
- [x] Crossplane
- [x] Grafana stack - (grafana, prometheus, loki)

Cluster Bootstrap (ArgoCD, secrets managment) and core components needed to deploy tenantOps cloud infra and jobs.
ArgoCD, once bootstrapped, deploys core components.

### <img src="https://raw.githubusercontent.com/kubernetes/kubernetes/d88b4e3b6e34a85f58778b7ef96e64edffff6823/logo/logo.svg" alt="" height="25"/> f5xc-tops-infra
Repo container cloud infrastrucuture components (crossplane CRDs) and tenantOps infrastucture jobs (k8s jobs/crons).
ArgoCD deploys these resources against the mgmt cluster.

### <img src="https://github.com/kubernetes/community/blob/master/icons/png/resources/unlabeled/pod-128.png?raw=true" alt="" height="25"/> f5xc-tops-job-workers
Containers and Lambdas used for tenantOps jobs.

### <img src="https://www.vectorlogo.zone/logos/grafana/grafana-icon.svg" alt="" height="25"/> f5xc-tops-dashboards
Grafana dashboards and alerting components.
