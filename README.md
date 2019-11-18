姓名：张嘉诚
班级：大数据181
学号：2018310998

实验四 字符串实验
1.实验目的
 掌握字符串String及其方法的使用
 掌握异常处理结构
 业务要求
 内容：利用已学的字符串处理知识编程完成《长恨歌》古诗的整理对齐工作，写出功能函数，并运行。达到如下功能：
2.要求
1.每7个汉字加入一个标点符号，奇数时加“，”，偶数时加“。”
2.允许提供输入参数，统计古诗中某个字或词出现的次数
3.考虑操作中可能出现的异常，在程序中设计异常处理程序

输入：汉皇重色思倾国御宇多年求不得杨家有女初长成养在深闺人未识天生丽质难自弃一朝选在君王侧回眸一笑百媚生六宫粉黛无颜色春寒赐浴华清池温泉水滑洗凝脂侍儿扶起娇无力始是新承恩泽时云鬓花颜金步摇芙蓉帐暖度春宵春宵苦短日高起从此君王不早朝承欢侍宴无闲暇春从春游夜专夜后宫佳丽三千人三千宠爱在一身金屋妆成娇侍夜玉楼宴罢醉和春姊妹弟兄皆列士可怜光采生门户遂令天下父母心不重生男重生女骊宫高处入青云仙乐风飘处处闻缓歌慢舞凝丝竹尽日君王看不足渔阳鼙鼓动地来惊破霓裳羽衣曲九重城阙烟尘生千乘万骑西南行<未完，待续>
输出：
汉皇重色思倾国，御宇多年求不得。
杨家有女初长成，养在深闺人未识。
天生丽质难自弃，一朝选在君王侧。
回眸一笑百媚生，六宫粉黛无颜色。
春寒赐浴华清池，温泉水滑洗凝脂。
侍儿扶起娇无力，始是新承恩泽时。
云鬓花颜金步摇，芙蓉帐暖度春宵。
春宵苦短日高起，从此君王不早朝。
…………

注意： 输入的内容，利用main方法中的args数组传递
3.过程：
 首先先创建和声明一个字符串对象，其内容为没有加标点符号的长恨歌内容。再创建一个字符数组，将之前的字符串对象转换到一个字符数组中。然后利用for循环遍历字符数组中的每个字符，进行判断，由于加完标点符号的古诗一共有33个标点，所以可以令for循环中变量i<34进行加标点符号的判断，而且i从i=0开始算起，并且没经历一次循环i+1,即i++.再利用java的Scanner类next()方法完成获取已经打出标点符号的字符串。最后在创建一个方法countString(),其作用是用来统计长恨歌中出现的某个字出现的次数。
4.流程图：

![imag](https://github.com/curry301999/changhenge/blob/master/liuchengtu.png)
5.核心代码：
public static void main(String args[]) {
  String str = new String("汉皇重色思倾国御宇多年求不得杨家有女初长成养在深闺人未识天生丽质难自弃一朝选在君王侧回眸一笑百媚生六宫粉黛无颜色春寒赐浴华清池温泉水滑洗凝脂侍儿扶起娇无力始是新承恩泽时云鬓花颜金步摇芙蓉帐暖度春宵春宵苦短日高起从此君王不早朝承欢侍宴无闲暇春从春游夜专夜后宫佳丽三千人三千宠爱在一身金屋妆成娇侍夜玉楼宴罢醉和春姊妹弟兄皆列士可怜光采生门户遂令天下父母心不重生男重生女骊宫高处入青云仙乐风飘处处闻缓歌慢舞凝丝竹尽日君王看不足渔阳鼙鼓动地来惊破霓裳羽衣曲九重城阙烟尘生千乘万骑西南行");
  char a[];
  a = str.toCharArray();
  for (int i=0; i<34; i++) {
   System.out.print(a[(i*7)]);
   System.out.print(a[(i*7)+1]);
   System.out.print(a[(i*7)+2]);
   System.out.print(a[(i*7)+3]);
   System.out.print(a[(i*7)+4]);
   System.out.print(a[(i*7)+5]);
   System.out.print(a[(i*7)+6]);
   if (i % 2 == 0) 
       System.out.print('，');
   else
       System.out.println('。');
  }
  Scanner curry=new Scanner(System.in);
  String b=curry.next();
        countString(str,b);
  
 }
 public static void countString(String str,String s) {
     int length=str.length();
     int count = 0;
     int k = 0;
     for(int i= 0; i<=length; i++){
         if(str.indexOf(s) == (i-k)){
             str = str.substring(i-k+1,str.length());
             count++;
             k = i+1;
         }
     }
     System.out.println(s+"出现的次数为"+count+"次");
 }
}
6.运行截图：

![imag](https://github.com/curry301999/changhenge/blob/master/1.png)
![imag](https://github.com/curry301999/changhenge/blob/master/2.png)
![imag](https://github.com/curry301999/changhenge/blob/master/3.png)
![imag](https://github.com/curry301999/changhenge/blob/master/4.png)
7.编程感想：通过此次实验明白了String及其使用方法，明白了如何声明与创建一个字符串对象。学会了使用String类中常用的成员方法的使用。最后利用之前c++学过的遍历来完成标点符号的增加以及数字出现次数的统计。而我认为这次实验是目前做过的实验当中最简单的一个实验，相比较于之前的两个来说所用到的知识点的范围没之前的广，只局限与了字符串方面的知识。虽然这次不难，但是仍不能掉以轻心，还需要我们今后的大量练习方可达到日后的熟能生巧！
