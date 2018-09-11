isAdmin = _spPageContextInfo.isSiteAdmin

var ctx = new SP.ClientContext.get_current();
var web = ctx.get_web();
var ob = new SP.BasePermissions();
ob.set(SP.PermissionKind.fullMask);
var per = web.doesUserHavePermissions(ob);

ctx.executeQueryAsync(function () {
    isAdmin = per.get_value();
})
