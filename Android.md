1.Fragment和Activity的生命周期
2.Viewpager,fragment预加载
3.fragment懒加载
4.ListView和RecyclerView的区别，缓存
5.Java的内存模型
6.GC回收机制
7.RxJava
8.HashMap原理
9.数组实现原理
10.Android内存泄露
11.Handler原理
12.自定义控件，流程，刷新方法的区别invalidate，requestLayout
13.Serializable和Parcelable区别
14.intent传递数据最大限制，超出限制如何解决
15.LruCache和DiskLruCache
16.JVM类加载机制
17.ANR和OOM解决方案，如何解决
18.Java软引用和弱引用
19.MVP
20.Java内存区域与内存溢出
21.垃圾回收算法
22.线程池
23.多线程中安全使用使用集合API
24.快速排序
25.冒泡排序
26.链表的反转
27.AsyncTask中线程是串行还是并行
28.java是值传递还是引用传递
29.java装箱
30.性能优化
31.如何解决界面的卡顿
32.retrofit原理
33.rxjava原理，执行流程，线程池调度
34.数据库表，sql相关的优化
35.HandlerThread，asyncTask原理并行还是串行，内部的线程池如何调度
36.ThreadLocal
37.同步，锁相关
38.HTTPS,对称秘钥，非对称秘钥，数字签名
39.ormLite，greenDao框架
40.启动activity相关
41.java的原子和非原子操作
42.应用上线了之后如何定位错误和崩溃，so里面的错误等问题如何定位
43.二分查找
44.flutter与RN的区别（因技术栈而异）
45.归并排序
46.序列化与反序列化之后对应的两个引用指向的不是同一个地址

47.

    public class TryCatchFinally {

    public static void main(String[] args) {

        int n = fun();
        System.out.println(n);
    //打印结果：B  C  ，
    n = 2（执行finally的return结果）
    }

    private static int fun() {
        try {
            int x =3;
            int b = x / 0;
            System.out.println("A");
            return 0 ;
        } catch (Exception e) {
            System.out.println("B");
            return 1;
        }finally {
            System.out.println("C");
            return 2;
        }
    }
    }

  48.
    public class ReferenceSwap {

    public static void main(String[] args) {
        Student s1 = new Student("a");
        Student s2 = new Student("b");

        fun(s1,s2);

        System.out.println(s1.name + s2.name);  
    //打印结果为 : ab(上面的操作跟这里没有任何关系，并没有改变引用a，b指向的内存空间)
    }

    


    static void fun(Student s1,Student s2) {
        Student temp = s1;
        s1 = s2;
        s2 = temp;
        System.out.println(s1.name + s2.name);  
    //打印结果为: ba（做了一次引用传递）
    }

    static class Student {
        String name;

        public Student(String name) {
            this.name = name;
        }
    }
    }

49.

    public class TestString {

    public static void main(String[] args) {
    ==比较的是引用，equals比较的是内存中存储的字面值，
    此时内存中只有一份“abc”，所有a，b两个都是指向了“abc”的内存空间
        String a = "abc";
        String b = "abc";
        System.out.println(a == b);  true
        System.out.println(a.equals(b)); true

    内存中已经有了一份“mn”，但是通过new 重新开辟了一块空间放置另一份“mn”
        String c = "mn";
        String d = new String("mn");
        System.out.println(c == d);  false
        System.out.println(c.equals(d)); true


        String ss = "abdcedf";
        char[] array = ss.toCharArray();
        for (char aa : array) {
         System.out.println(aa);
        }
    }
}


50.A a = new A();描述过程
51.动画：视图，帧，属性动画
52.Java运行时数据区