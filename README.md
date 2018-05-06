### 把PATCH打到自己的CM13分支

此PATCH适合场景：本地的CM13分支不是最新的并且你对git patch有了解，如果不是，可以直接同步已经基于最新CM13分支打过PATCH的仓库 [传送门](https://github.com/OneStep-CM13/android)

OneStep新增两个本地没有的仓库，故需要先下载：
```sh
    $ git clone https://github.com/OneStep-CM13/android_frameworks_smartisanos-base.git /the/path/of/your/cm13_root_dir/frameworks/smartisanos-base
    $ git clone https://github.com/OneStep-CM13/android_packages_apps_OneStep.git /the/path/of/your/cm13_root_dir/packages/apps/OneStep
```

下载此仓库所有PATCH：
```sh
    $ git clone https://github.com/OneStep-CM13/patch.git ~/patch
```

以打frameworks_base为例：
```sh
    $ cd /the/path/of/your/cm13_root_dir
    $ cd frameworks/base
    $ git am ~/patch/frameworks/base/*.patch
```

再来一个例子，打OneStep：
```sh
    $ cd /the/path/of/your/cm13_root_dir
    $ cd packages/apps/OneStep
    $ git am ~/patch/packages/apps/OneStep/*.patch
```

如果你的分支落后官方CM13很多，可能出现冲突，需要查阅git patch文档自行解决
成功打完所有PATCH后开始编译测试，Good Luck!
此次移植基于OnePlus One CM13，运行良好，不排除在其他机型上出现BUG的情况
关注OneStep最新进展 [传送门](https://github.com/SmartisanTech/android)
