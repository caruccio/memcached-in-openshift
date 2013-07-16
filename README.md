Embedded Memcached Cartridge
============================

This git repository helps you get up and running quickly w/ a embedded Memcached installation on OpenShift.
It was based on code form https://github.com/zfdang/memcached-in-openshift.

Running on OpenShift
----------------------------

Create an account at http://getupcloud.com/

Create your application

```
rhc app create -a myapp -t <type>
```

Add this upstream memcached repo

```
cd myapp/
git remote add memcached -m master git://github.com/caruccio/openshift-memcached-embedded.git
git pull -s recursive -X theirs upstream master
```

Then push the repo upstream

```
git push
```

Note that on a scallable app, each gear has it's own memcached instance.
To connect to local gear's memcached use env var ```$OPENSHIFT_INTERNAL_IP``` on port 22322 (edit ```.openshift/action_hooks/post_deploy``` to change it).

That's it, you can now checkout your application at:

```
http://myapp-<namespace>.getup.io
```

Please note it's only a first version.
