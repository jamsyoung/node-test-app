# Node Test App

```bash
$ npm install
$ node server.js

$ curl http://localhost:8080
{"welcome":"oblivion"}

$ curl http://localhost:8080/hello/jamie
{"hello":"jamie"}
```

## Deployment via Docker/Dokku
These specific commands only work for me.  You will need to setup your own
[Docker][docker]/[Dokku][dokku] box.

```bash
$ git remote add dokku dokku@git.nodev.code:node-test-app
$ git push dokku master
Counting objects: 5, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 308 bytes | 0 bytes/s, done.
Total 3 (delta 2), reused 0 (delta 0)
-----> Cleaning up ...
remote: Cloning into '/tmp/tmp.qxLns7rofZ'...
-----> Building node-test-app ...
remote: done.
remote: HEAD is now at 74a8d41... .
       Node.js app detected
-----> Requested node range:  0.10.32
-----> Resolved node version: 0.10.32
-----> Downloading and installing node
-----> Restoring node_modules directory from cache
-----> Pruning cached dependencies not specified in package.json
-----> Installing dependencies
-----> Caching node_modules directory for future builds
-----> Cleaning up node-gyp and npm artifacts
-----> No Procfile found; Adding npm start to new Procfile
-----> Building runtime environment
-----> Discovering process types
       Procfile declares types -> web
-----> Releasing node-test-app ...
-----> Deploying node-test-app ...
=====> Application deployed:
       http://node-test-app.nodev.club

To dokku@git.nodev.club:node-test-app
   a222015..74a8d41  master -> master

$ curl http://node-test-app.nodev.club
{"welcome":"oblivion"}
```




[docker]: http://docs.docker.com
[dokku]: http://progrium.viewdocs.io/dokku/index
