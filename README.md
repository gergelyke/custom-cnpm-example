custom-cnpm-example
===========

Use cnpmjs.org and your own nfs to build your own npm

## Mysql

From [here](https://github.com/cnpm/cnpmjs.org/blob/master/docs/db.sql), you can get the mysql table and create your own mysql database.

## Samples

### Simple

The most simple way to use `cnpmjs.org` is in [custom-cnpm-example/simple](https://github.com/cnpm/custom-cnpm-example/tree/master/simple).

Just custom your own config, then:

```
var cnpm = require('cnpmjs.org');
var config = require('./config');

cnpm.startWorker(config);
cnpm.startSync(config);
```

Then you get a single-process cnpm server.

### Culster

To make your system more **stable** and **reliable**, mabey you need to enable cluster mode. Just look at [custom-cnpm-example/cluster](https://github.com/cnpm/custom-cnpm-example/tree/master/cluster). You also can run `cnpmjs.org` in cluster with other cluster modules.

### Simple File System

Maybe you do not have a private file system to replace the `qn file store`, we also provider a [simple file system](https://github.com/cnpm/sfs), which support cluster server. Just check out the example here: [custom-cnpm-example/sfs](https://github.com/cnpm/custom-cnpm-example/tree/master/sfs).

## Try it

```
$ cnpm install

# start simple sample
$ node simple

# start cluster sample
$ node cluster

# start sfs sample
$ node sfs
```

## More File system store support

You can replace the default `qn file store` by any other file store system, only need to follow [this guide](https://github.com/cnpm/cnpmjs.org/wiki/NFS-Guide).
We provide aliyun oss and taobao tfs support. Just check it out.

* [oss](https://github.com/cnpm/oss-cnpm)
* [tfs](https://github.com/cnpm/tfs-cnpm)

## License
MIT
