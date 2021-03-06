# 锐X笔试

## 1.选择题（共十题，只记起来七道题）

1. 下列中哪个是属于传输层协议（<font color=red>B</font>）

   A. FTP

   B. TCP

   C. IP

   D. HTTP

   <font color = red>解答：网络有七层协议（自上向下）：应用层 、表示层 、会话层 、传输层 、网络层 、数据链路层、物理层。A. FTP属于应用层。 B. TCP属于传输层协议。 C. IP属于网络层协议。 D. HTTP属于应用层协议。</font>

2. 下列程序的输出语句应该为（<font color=\#7CFC00>D</font>）

   ```java
   int x = 3, y = 8, z = 15;
   switch (y % x) {
       case 1:
           z = x + y;
       case 2:
           z = x / y;
       case 3:
           z = x - y;
       default:
           z = x * y - y;
   }
   System.out.println(z);
   ```

   A. 0.375

   B. 0

   C. -5

   D. 16

   <font color = red>解答：当switch case中没有break或return时，程序会跳到符合条件的语句中然后不管后面是否符合条件都会一直往下执行。</font>

3. 下列中属于运算符的是（<font color=\#7CFC00>C</font>）

   A. =

   B. <<<

   C. >>

   D. <>

   <font color = red>解答：java的运算符分为4类：算数运算符、关系运算符、逻辑运算符、位运算符。A. =在java中不属于运算符。B. 在java中只存在>>>（无符号右移），不存在<<<。C. >>（有符号右移）属于位运算符。 D.  java中不存在<> ，而在sql中表示不等于（在 SQL 的一些版本中，该操作符可被写成 !=）。</font>

4. 下列关于>>和>>>的解释正确的是（<font color = red>C</font>）

   A. >>是带符号左移，>>>是无符号左移。

   B. >>是无符号左移，>>>是带符号左移。

   C. >>是带符号右移，>>>是无符号右移。

   D. >>是无符号右移，>>>是带符号右移。

   <font color = red>解答：>>表示是带符号的右移：按照二进制把数字右移指定数位，高位如符号位为正补零，符号位负补一，低位直接移除。>>>表示无符号的右移：按照二进制把数字右移指定数位，高位直接补零，低位移除。</font>

5. 若进栈序列为1,2,3,4,5,6,且进栈和出栈可以穿插进行,则不可能出现的出栈序列为（<font color=\#7CFC00>C</font>）

   A. 3 2 4 1 6 5

   B. 5 6 4 3 2 1

   C. 3 2 6 1 4 5

   D. 4 5 3 6 2 1

   <font color = red>解答：此题考查的是栈这种数据结构，该数据结构为只能从栈顶中插入，而拿取数据也只能从栈顶中获取。</font>

6. 下列SQL语句中哪个能实现查找Person表中所有FirstName为LiHua的全部数据（<font color=\#7CFC00>D</font>）

   A. select [all] from Person where FirstName like 'LiHua'

   B. select * from Person where FirstName like 'LiHua'

   C. select [all] from Person where FirstName = 'LiHua'

   D. select * from Person where FirstName = 'LiHua'
   
7. 下列关于内存回收的说法正确的是（<font color = green>B</font>）

   A. 程序员必须创建一个线程来释放内存

   B. 内存回收程序负责回收无用内存

   C. 内存回收程序允许程序员直接释放内存

   D. 内存回收程序可以在指定时间释放内存对象



## 2.简答题（共三题）

1. 简述同步和异步的区别，分别用在什么情况下，请举例说明。

   <font color = green>同步：就是说某一临界资源在某一时刻只能有一个线程访问，比如数据库里某字段，如果多人同时修改该字段必然引起混乱。<br/>异步：就是同时做几件事（当然，如果是单核的话，无法实现真正意义上的同时做几件事，只是时间片切换很快造成这种感觉，双核可以实现），比如迅雷看看，一边下载，一边播放。</font>

2. 简述int和Integer的区别。

   * <font color = green>Integer是int的包装类，int则是java的一种基本数据类型</font>
   * <font color = green>Integer变量必须实例化后才能使用，而int变量不需要</font>
   * <font color = green>Integer实际是对象的引用，当new一个Integer时，实际上是生成一个指针指向此对象；而int则是直接存储数据值</font>
   * <font color = green>Integer的默认值是null，int的默认值是0</font>

3. 简述JDBC调用数据库的步骤。

   1. <font color = green>加载JDBC驱动程序</font>
   2. <font color = green>提供JDBC连接的URL</font>
   3. <font color = green>创建数据库的连接</font>
   4. <font color = green>创建一个Statement</font>
   5. <font color = green>执行SQL语句 </font>
   6. <font color = green>处理结果</font>
   7. <font color = green>关闭JDBC对象</font>

   

## 3.编程题（共两题）

1. 某位将军打完胜仗归来，皇帝要奖赏这名将军，带来一些奖品。奖品的重量分别为2,2,6,5,4，而每种奖品的价值也不一样，分别为6,3,5,4,6。但是由于这位将军的马车最多只能装下重量为10的物品，请设计程序算出将军所能带走的最大奖品价值。

   输入示例：

   ```
   5 10
   2 2 6 5 4
   6 3 5 4 6
   ```

   输出示例：

   ```
   15
   ```

   

   > <font color = green size = 5>思路:</font>
   >
   > <font color = green>假设放入n件物品，背包最大承重为m，物品的总重为w，其最大价值为v[n,m]</font>
   >
   > <font color = green>当背包的承重为0，或者不将物品放入背包时，背包中的最大总价值均为0，即v[n,0]=v[0,m]=0。</font>
   >
   > <font color = green>当放入第n件物品前超过背包的最大承重时，则无法将该物品放入背包中，即v[n,m]=v[n-1,m]。</font>
   >
   > <font color = green>放入当前物品n不超过背包的最大承重时，则当前物品放入背包时的最大价值为vn+v[n-1,m-wn]，不放入背包时的最大价值为v[n-1,m]，因此对于当前物品是否放入背包中所能获得的最大价值为v[n,m]=max{ v[n-1,m],vn+v[n-1,m-wn] }。</font>

   

   分析上面的输入输出示例可构建如下的表格：

   |      |  0   |  1   |  2   |  3   |  4   |  5   |
   | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
   |  0   |  0   |  0   |  0   |  0   |  0   |  0   |
   |  1   |  0   |  0   |  0   |  0   |  0   |  0   |
   |  2   |  0   |  6   |  6   |  6   |  6   |  6   |
   |  3   |  0   |  6   |  6   |  6   |  6   |  6   |
   |  4   |  0   |  6   |  9   |  9   |  9   |  9   |
   |  5   |  0   |  6   |  9   |  9   |  9   |  9   |
   |  6   |  0   |  6   |  9   |  9   |  9   |  12  |
   |  7   |  0   |  6   |  9   |  9   |  10  |  12  |
   |  8   |  0   |  6   |  9   |  11  |  11  |  15  |
   |  9   |  0   |  6   |  9   |  11  |  13  |  15  |
   |  10  |  0   |  6   |  9   |  14  |  14  |  15  |

   由表便知从这5个物品中选择放入容量为10的背包，所能得到的最大价值为15

   ``` java
   import java.util.Scanner;
   
   public class Main {
       public static void main(String[] args) {
           Scanner scanner = new Scanner(System.in);
           // 物品数量
           int count = scanner.nextInt();
           // 背包总承重
           int maxWeight = scanner.nextInt();
           // 物品重量数组
           int[] weight = new int[count+1];
           // 物品价值数组
           int[] value = new int[count+1];
           weight[0] = 0;
           value[0] = 0;
           for (int i = 1; i <= count; i++) {
               weight[i] = scanner.nextInt();
           }
           for (int i = 1; i <= count; i++) {
               value[i] = scanner.nextInt();
           }
           scanner.close();
           System.out.println(maxValue(weight, value, count, maxWeight));
       }
   
       private static int maxValue(int[] weight, int[] value, int count, int maxWeight) {
           int n,m;
           // 下面这个数组表示n个物品放入背包剩余空间为m的最大价值
           int[][] v = new int[count+1][maxWeight+1];
           for (n = 1; n < count+1; n++) {
               for (m = 1; m < maxWeight+1; m++) {
                   if (n == 0) {
                       v[n][m] = 0;
                   } else if (m == 0) {
                       v[n][m] = 0;
                   } else {
                       if (weight[n] > m) {
                           v[n][m] = v[n - 1][m];
                       } else {
                           v[n][m] = Math.max(v[n - 1][m], v[n - 1][m - weight[n]] + value[n]);
                       }
                   }
               }
           }
           return v[count][maxWeight];
       }
   }
   ```

2. 输入一行字符，分别统计出其中英文字母、空格、数字和其他字符的个数

   输入示例：

   ```
   sdaohoh% / sa112312rAsafnoF
   ```

   输出示例：

   ```
   英文:17
   数字:6
   空格:2
   字符:2
   ```

   > <font color = green size = 5>思路:</font>
   >
   > <font color = green>将字符串拆分成字符数组，然后遍历这个数组，然后判断属于字母、空格、数字或者字符然后统计起来</font>

   ``` java
   import java.util.Scanner;
   
   public class Main {
       public static void main(String[] args) {
           Scanner scanner = new Scanner(System.in);
           String s = scanner.nextLine();
           scanner.close();
           char[] chars = s.toCharArray();
           //字母个数
           int letter = 0;
           //数字个数
           int num = 0;
           //空格个数
           int space = 0;
           //其他字符个数
           int character = 0;
           for (char aChar : chars) {
               // 字母
               if ((63 <= aChar && aChar <= 90) || (97 <= aChar && aChar <= 122)) {
                   letter++;
               } else if (48 <= aChar && aChar <= 57) {
                   num++;
               } else if (aChar == 32) {
                   space++;
               } else {
                   character++;
               }
           }
           System.out.println("字母:" + letter);
           System.out.println("数字:" + num);
           System.out.println("空格:" + space);
           System.out.println("字符:" + character);
       }
   }
   ```
