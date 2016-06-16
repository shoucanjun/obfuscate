#常规混淆出现的一些问题集合

先附上混淆格式 [传送门] (http://proguard.sourceforge.net/manual/examples.html)这里的例子绝对够你用了


*案例1、混淆后图片变67字节被损坏变黑。
just like this  -->  
![](https://github.com/shoucanjun/obfuscate/blob/master/D1AB1FF6-74E9-44FE-A534-B3E47A8EC4E5.png?raw=true)

解决：

```java
public class aaa{
  System.out.println("....");
}
```
