# Intro to Red Hat Advanced Cluster Management and Advanced Cluster Security

## Demo Setup

### Management Cluster Setup: ACM

First, login via CLI as a `cluster-admin`.

Once logged in, deploy the ACM Operator:

```
oc apply -k https://github.com/redhat-cop/gitops-catalog/advanced-cluster-management/operator/overlays/release-2.5
```

Once the Operator is deployed, create an ACM instance:

```
oc apply -k https://github.com/redhat-cop/gitops-catalog/advanced-cluster-management/instance/base
```

This will take a few minutes to deploy.

### Management Cluster Setup: ACM Policies

Now that ACM is deployed, we will let ACM deploy the rest of the demo with Poicies.

Apply everything in the `01-acm-policies` directory to load up the policies required for this demo.

```
oc apply -k 01-acm-policies
```

### Management Cluster Setup: ACM Applications

Apply everything in the `02-acm-applications` directory to load up the applications required for this demo.

```
oc apply -k 02-acm-applications
```
