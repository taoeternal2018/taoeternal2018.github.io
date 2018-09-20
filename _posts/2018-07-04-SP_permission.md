---
layout:     post
title:      SP_permission
subtitle:   SP_permission
date:       2018-09-04
author:     Taoeternal
header-img: img/post-bg-coffee.jpeg
catalog: true
tags:
    - Xcode
    - 开发技巧
---

isAdmin = _spPageContextInfo.isSiteAdmin

var ctx = new SP.ClientContext.get_current();
var web = ctx.get_web();
var ob = new SP.BasePermissions();
ob.set(SP.PermissionKind.fullMask);
var per = web.doesUserHavePermissions(ob);

ctx.executeQueryAsync(function () {
    isAdmin = per.get_value();
})
