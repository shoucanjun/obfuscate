#常规混淆出现的一些问题集合

先附上混淆格式 [传送门] (http://proguard.sourceforge.net/manual/examples.html)这里的例子绝对够你用了


### 案例1、混淆后图片变67字节被损坏变黑。</br>
just like this
<img src="https://github.com/shoucanjun/obfuscate/raw/master/image/obfuscate.png" height="200" width="400"/>
<!-- ![](https://github.com/shoucanjun/obfuscate/raw/master/image/obfuscate.png) -->

原因:</br>
开启了shrinkResources又开启了minifyEnabled。至于原因的话我也不是很清楚，我也是乱试一通的。本来混淆的话只是对java代码有效果，对资源文件是没有影响的，shrinkResources和minifyEnabled的设置应该是独立的才对，想不到同时设置也会影响到。
以下是错误的写法:
```gradle
buildTypes {
       release {
           shrinkResources true  // 移除无用资源
           minifyEnabled true   //混淆
           proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
       }
   }
```
解决方案：</br>
只需要把shrinkResources关闭就行了
```gradle
buildTypes {
       release {
           shrinkResources false  // 移除无用资源
           minifyEnabled true   //混淆
           proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
       }
   }
```
