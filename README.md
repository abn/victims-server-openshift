victims-server-openshift
========================

This repo allows you to deploy a new instance of the victims-web server on openshift.

## Running on OpenShift
### Prerequisites
1. You have a valid account with OpenShift
2. You have followed the instructions at https://www.openshift.com/get-started
3. You have *rhc* installed and ready

### Creating the app
This is pretty straight forward, run the following command. The app should be deployed to http://victims-NAMESPACE.rhcloud.com
```sh
rhc app create victims mongodb-2.2 python-2.6 --from-code git://github.com/abn/victims-server-openshift.git
```
A sample output would be:
```sh
$ rhc app create victims mongodb-2.2 python-2.6 --from-code git://github.com/abn/victims-server-openshift.git
Application Options
-------------------
  Namespace:   abn
  Cartridges:  mongodb-2.2, python-2.6
  Source Code: git://github.com/abn/victims-server-openshift.git
  Gear Size:   default
  Scaling:     no

Creating application 'victims' ... done

Waiting for your DNS name to be available ... done

Downloading the application Git repository ...
Cloning into 'victims'...
Warning: Permanently added the RSA host key for IP address '**.***.***.**' to the list of known hosts.

Your application code is now in 'victims'

victims @ http://victims-abn.rhcloud.com/ (uuid: **********************)
--------------------------------------------------------------------------
  Created:         7:33 PM
  Gears:           1 (defaults to small)
  Git URL:         ssh://$UID@victims-abn.rhcloud.com/~/git/victims.git/
  Initial Git URL: git://github.com/abn/victims-server-openshift.git
  SSH:             $UID@victims-abn.rhcloud.com

  python-2.6 (Python 2.6)
  -----------------------
    Gears: Located with mongodb-2.2

  mongodb-2.2 (MongoDB NoSQL Database 2.2)
  ----------------------------------------
    Gears:          Located with python-2.6
    Connection URL: mongodb://$OPENSHIFT_MONGODB_DB_HOST:$OPENSHIFT_MONGODB_DB_PORT/
    Database Name:  victims
    Password:       ***********
    Username:       admin

RESULT:
Application victims was created.
MongoDB 2.2 database added.  Please make note of these credentials:
   Root User:     admin
   Root Password: ***********
   Database Name: victims
Connection URL: mongodb://$OPENSHIFT_MONGODB_DB_HOST:$OPENSHIFT_MONGODB_DB_PORT/

```
