# OpenShift artifactory-oss

This repository contains a dockerized version of [artifactory-oss](https://www.jfrog.com/open-source)
to be used on OpenShift by running as a non-priviledged user.

## Run

    docker run -v $(pwd)/artifactory:/artifactory -p 8080:8080 -it widerin/openshift-artifactory-oss:latest

## Create on openshift

    oc login https://<your-master-node>:8443
    oc new-project artifactory-oss
    oc create -f openshift/deployment.yaml
    oc create -f openshift/service.yaml

If you want to expose your artifactory-oss server you have to create a route.
