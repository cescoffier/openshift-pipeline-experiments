# Experimentations with Openshift Pipelines

This project is a very simple Vert.x application that can be deployed to Openshift using:

1. The fabric8 maven plugin
2. A pipeline build

## Prerequisites

You need to have the `oc` client, and you need to be logged in:

```
oc login ...
```

## Fabric8 Maven Plugin

Just use:

```
mvn fabric8:deploy -Popenshift
```

## Using pipelines

When using a pipeline, the application is built on Openshift using the following steps:

1. Checkout the source from this repository
2. Build and deploy the application

Commands:

```
oc process -f src/openshift/template.yaml | oc create -f -
oc start-build vertx-rest
```