# lua-resty-ceph

A simple Lua wrapper for ceph with s3 and swift based on OpenResty.

More: 

1. <http://docs.ceph.org.cn/radosgw/s3/>
2. <http://docs.ceph.org.cn/radosgw/swift/>


# API

* [new](#new)
* [get_all_buckets](#get_all_buckets)
* [create_bucket](#create_bucket)
* [del_bucket](#del_bucket)
* [get_all_buckets](#get_all_buckets)
* [get_all_objs](#get_all_objs)
* [get_buckets_location](#get_buckets_location)
* [get_buckets_acl](#get_buckets_acl)
* [create_obj](#create_obj)
* [get_obj](#get_obj)
* [del_obj](#del_obj)
* [check_for_existance](#check_for_existance)
* [get_obj_acl](#get_obj_acl)
* [set_obj_acl](#set_obj_acl)


## Synopsis

``` lua
local cephs3 = require("resty.ceph.s3")
local app = cephs3:new(config.access_key, config.secret_key, config.host)

local data = app:create_bucket(bucket)
ngx.say(data)
app:get_all_objs(bucket)
    
```

# Usage

## new

    local app = cephs3:new(access_key, secret_key, host)

## get_all_buckets

    app:get_all_buckets()

## create_bucket

    app:create_bucket(bucket, acl)

## del_bucket

    app:del_bucket(bucket)

## get_all_buckets

    app:get_all_buckets()

## get_all_objs

    app:get_all_objs(bucket)
    app:get_all_objs(bucket, 'marker=3&max-keys=25')

## get_buckets_location

    app:get_buckets_location(bucket)

## get_buckets_acl(bucket)

    app:get_buckets_acl(bucket)

## create_obj

    app:create_obj(bucket, file, content)

## del_obj

    app:del_obj(bucket, file)

## get_obj

    app:get_obj(bucket, file)

## check_for_existance

    app:check_for_existance(bucket, file)

## get_obj_acl

    app:get_obj_acl(bucket, file)

## set_obj_acl

    app:set_obj_acl(bucket, file)

# TODO

* Upload operations.
* Simpe wrapper based on  **Lua-rados** <https://github.com/noahdesu/lua-rados>.

# Author

Linsir: <https://github.com/linsir>


# Licence

BSD license.

All rights reserved.
