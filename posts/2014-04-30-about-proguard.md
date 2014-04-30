About code proguard
=====================

Decompile apk 
---------

(1) get classes.dex from the apk;         
(2) download dex2jar_xpgod.rar and run 
    
    >dex2jar.bat classes.dex

   output is classes_dex2jar.jar
(3) open the jar with jd-gui

ApkTool 
---------
(1) download apktool1.5.2, see [more][1]
(2) download framework-res.apk , see [more][2],[more][3]
(3) run 

    apktool if framework-res.apk
(4) rename the apk with 123.apk
(5) run
    
    apktools.cmd

Proguard 
---------

see [more][4]
see [more][5]
see [more][6]


----------

  [1]: http://www.smzy.com/smzy/down95937.html
  [2]: http://bbs.gfan.com/android-5137173-1-1.html
  [3]: http://www.20864.com/201333/315.html
  [4]: http://nobugs.sinaapp.com/?p=403
  [5]: http://www.eoeandroid.com/thread-209210-1-1.html
  [6]: http://www.cnblogs.com/classic/archive/2011/04/27/2030234.html
  
