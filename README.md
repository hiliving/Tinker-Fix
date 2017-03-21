# Tinker-Fix

###### tinker热修复简单demo,在官方demo基础上精简，参考这个demo了解tinker的工作流程，方便快速集成到自己的项目中

![Tinker](https://github.com/hiliving/Tinker-Fix/blob/master/app/screenshot/tinker.gif)

# Demo使用步骤
1. 首先执行clean，以清除build历史，先执行一次assembleRelease,在build目录下bakApk文件夹里会生成三个文件，将其名字拷贝到build.gradle中对应位置。

2. 试验修改一行代码，我修改的是布局文件中的hello world，修改为“修改了一个BUG”，然后执行tinkerPatchRelease命令，之后build目录下outPuts文件夹里会生成tinkerPatch文件夹，其中就有补丁文件，把patch_signed_7zip.apk拷贝或者push到手机内置SD卡根目录，这里注意不是外置sd存储卡.

3. 好了，打开应用，点击path按钮，应用会退出，重新进入，会发现文本已修改成功，点show按钮看到补丁生效了。  
  
##总的来说:
AndFix作为native解决方案，首先面临的是稳定性与兼容性问题，更重要的是它无法实现类替换，它是需要大量额外的开发成本的；
Robust兼容性与成功率较高，但是它与AndFix一样，无法新增变量与类只能用做的bugFix方案；
Qzone方案可以做到发布产品功能，但是它主要问题是插桩带来Dalvik的性能问题，以及为了解决Art下内存地址问题而导致补丁包急速增大的。
特别是在Android N之后，由于混合编译的inline策略修改，对于市面上的各种方案都不太容易解决。而Tinker热补丁方案不仅支持类、So以及资源的替换，它还是2.X－7.X的全平台支持。利用Tinker我们不仅可以用做bugfix,甚至可以替代功能的发布。Tinker已运行在微信的数亿Android设备上，那么为什么你不使用Tinker呢？
