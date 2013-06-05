victims-server-openshift
========================

This repo allows you to deploy a new instance of the victims-web server on openshift.

## Running on OpenShift
### Prerequisites
1. You have a valid account with OpenShift
2. You have following the instructions at https://www.openshift.com/get-started
3. You have *rhc* installed and ready

### Creating the app
This is pretty straight forward, run the following command:
```sh
rhc app create victims mongodb-2.2 python-2.6 --from-code git://github.com/abn/victims-server-openshift.git
```

The app should now be deployed on https://victims-NAMESPACE.rhcloud.com
