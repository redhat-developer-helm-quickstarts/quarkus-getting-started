# Getting started with Quarkus

This is a minimal CRUD service exposing a couple of endpoints over REST.

Under the hood, this demo uses:

- RESTEasy to expose the REST endpoints
- REST-assured and JUnit 5 for endpoint testing

In this demo, you will learn how to build a basic Quarkus application using the [Quarkus Helm Chart](https://github.com/redhat-developer/redhat-helm-charts/tree/master/alpha/quarkus-chart).

## Add the Red Hat Helm Chart Repository

Be sure to add the Red Hat Helm Chart Repository if deploying via the Helm CLI:
```
helm repo add redhat https://redhat-developer.github.io/redhat-helm-charts
```

This repository is already configured if you are installing via the OpenShift UI.

## Run Quarkus in JVM mode

The Quarkus Helm Chart is configured to run Quarkus in JVM mode by default. Simply install the Helm chart to build and deploy your Quarkus application:
```
helm install quarkus-app redhat/quarkus
```

To configure your installation beyond the defaults, take a look at the [Quarkus chart's values](https://github.com/redhat-developer/redhat-helm-charts/tree/master/alpha/quarkus-chart#values).

## Run Quarkus as a native executable

To run Quarkus as a native executable, change the `build.mode` value to `native` in a values file:
```
build:
  mode: native
```

This will generate an inline Dockerfile to compile your application in native mode.

To install, simply run the following command:
```
helm install quarkus-app redhat/quarkus --values values.yaml
```

To configure your installation beyond the defaults, take a look at the [Quarkus chart's values](https://github.com/redhat-developer/redhat-helm-charts/tree/master/alpha/quarkus-chart#values).