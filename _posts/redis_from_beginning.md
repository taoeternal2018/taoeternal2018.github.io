---
layout:     post
title:      redis from beginning？
subtitle:   redis
date:       2018-10-19
author:     BY
header-img: img/post-bg-ios9-web.jpg
catalog: 	 true
tags:
    - redis
---
Step1: install redis server:             sudo apt-get install redis-server

Step2: install redis python client:      pip install redis
(启动 Redis
$ redis-server
查看 redis 是否启动？
$ redis-cli
以上命令将打开以下终端：

redis 127.0.0.1:6379>
127.0.0.1 是本机 IP ，6379 是 redis 服务端口。现在我们输入 PING 命令。

redis 127.0.0.1:6379> ping
PONG)

Step3: a redis hello world:

import redis
redis_host = "localhost"
redis_port = 6379
redis_password = ""

def hello_redis():
    """Example Hello Redis Program"""
    
    # step 3: create the Redis Connection object
    try:
    
        # The decode_repsonses flag here directs the client to convert the responses from Redis into Python strings
        # using the default encoding utf-8.  This is client specific.
        r = redis.StrictRedis(host=redis_host, port=redis_port, password=redis_password, decode_responses=True)
    
        # step 4: Set the hello message in Redis 
        r.set("msg:hello", "Hello Redis!!!")

        # step 5: Retrieve the hello message from Redis
        msg = r.get("msg:hello")
        print(msg)        
    
    except Exception as e:
        print(e)
