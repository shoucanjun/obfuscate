#常规混淆出现的一些问题集合

先附上混淆格式 [传送门] (http://proguard.sourceforge.net/manual/examples.html)这里的例子绝对够你用了


*案例1、混淆后图片变67字节被损坏变黑。
just like this  -->  
![aaa](https://cdn.monetizejs.com/resources/button-32.png)

解决：

```java
public class aaa{
  System.out.println("....");
}
```
