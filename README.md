# Tinker-Fix
tinker热修复简单demo,在官方demo基础上精简，参考这个demo了解tinker的工作流程，方便快速集成到自己的项目中
![Tinker](https://github.com/hiliving/Tinker-Fix/blob/master/app/screenshot/tinker.gif)

#Demo使用步骤
  1.首先执行clean，以清除build历史，先执行一次assembleRelease,在build目录下bakApk文件夹里会生成三个文件，将其名字拷贝到build.gradle中对应位置
  2.试验修改一行代码，我修改的是布局文件中的hello world，修改为“修改了一个BUG”，然后执行tinkerPatchRelease命令，之后build目录下outPuts文件夹里
    会生成tinkerPatch文件夹，其中就有补丁文件，把patch_signed_7zip.apk拷贝或者push到手机内置SD卡根目录，这里注意不是外置sd存储卡。
  3.好了，打开应用，点击path按钮，应用会退出，重新进入，会发现文本已修改成功，点show按钮看到补丁生效了。
