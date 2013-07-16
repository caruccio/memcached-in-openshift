Embedded Memcached Cartridge
============================

This git repository helps you get up and running quickly w/ a embedded Memcached installation on OpenShift.


Running on OpenShift
----------------------------

Create an account at http://getupcloud.com/

Create your application

```sh
rhc app create -a memcached -t python-2.6
```

Add this upstream memcached repo

```sh
cd memcached
git remote add upstream -m master git://github.com/caruccio/openshift-memcached-embedded.git
git pull -s recursive -X theirs upstream master
```
Then push the repo upstream

```sh
git push
```

That's it, you can now checkout your application at:

```sh
http://memcached-$yournamespace.getup.io
```
