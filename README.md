# PermissionX
第一行代码的封装库实战，最后一章是推送到jcenter，由于学习时jcenter已经停止服务了，所以没有跟着做。

PermissionX是一个用于简化Android运行是权限用法的开源库。
添加如下配置将PermissionX引入到你的项目中：
```groovy
dependencies {
    ...
    implementation 'com.permissionx.guolindev:permissionx:1.0.0'
}
```

然后就可以使用如下语法结构来申请运行时权限了：
```kotlin
PermissionX.request(
    this,
    Manifest.permission.CALL_PHONE,
    Manifest.permission.READ_CONTACTS
) { allGranted, deniedList -> 
    if (allGranted) {
        Toast.makeText(this, "All permissions are granted", Toast.LENGTH_SHORT).show()
    } else {
        Toast.makeText(this, "You denied $deniedList", Toast.LENGTH_SHORT).show()
    }
}
```
