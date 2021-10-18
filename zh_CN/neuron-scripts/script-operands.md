# 脚本操作数

## 局部变量

局部变量是一个只有当前脚本才能使用的变量，必须用 "DECLARE" 注释声明。当启动程序时，该变量得到的值为 0。当 Neuron 脚本结束（返回）时，所有的局部变量都会被断开，所以下次这个脚本再次启动时，其所有的局部变量都是 0。为了将数据保存到下次执行时，应该使用全局变量。

局部变量是一个小写的字母名。\_和数字（除了第一个字符）也可以作为名称的一部分。名称最多可以包含 30 个字符。

## 全局变量

全局变量是所有 Neuron 脚本都可以使用的变量，必须在全局变量设置环境中定义。当启动 Neuron 程序时，该变量得到的值为 0。当 Neuron 程序结束时，所有的全局变量都会被断开，所以下次启动 Neuron 程序时，其所有的全局变量又是 0。为了将数据保存到下次执行时，应该使用数据基础变量。

一个全局变量的开头是大写字母 G，后面是一个点和一个小写字母名称。全局变量以大写字母 G 开头，后面跟着点和小写字母名称，\_和数字（除第一个字符外）也可以作为名称的一部分。名称最多可以由 20 个字符组成(前导符 G 除外)。

全局变量可以和索引一起使用。声明全局变量时，也要输入字数。如果试图在数组外寻址，将会失败。

## 对象变量

对象变量是对象的属性，它可以用于所有的 Neuron 子程序。它可以在所有的 Neuron 子程序中使用。当启动 Neuron 实例时，变量得到的是之前的值，当 Neuron 实例结束时，所有的标签变量都保存在硬盘上，以便下次启动。

一个对象变量由三个元素组成。第一个元素是对象名称。例如，温度对象可以使用 "SENSORA" 作为它的对象名，湿度对象可以使用 "SENSORB" 作为它的对象名。

第二，[] 里面有一个常量，叫做对象索引，可以是一个局部变量。这个数字代表对象的项目索引。

最后一个元素是对象的属性。一个对象可以有多达多个属性字段。每个字段包含一个唯一的字段名，称为属性名。例如，温度对象 SENSORA 的实际温度可以使用 "TEMPERATURE" 作为属性名。

因此，温度对象的实际温度为 SENSORA[ix].TEMPERATURE。这就是对象变量。

## 常量

常量是指范围为 -2,147,483,648 至 2,147,483,647 的数值。常量可以是有符号的十进制（如上所述）、无符号的十六进制（如果是前面的 0x（0x0 到 0xffffffff））或无符号的八进制（如果是前面的 0 （0 到 03777777777））。在脚本中，带小数点的常数也被接受为双值。例如，pi 是 3.1415。脚本常量支持两种值类型。

## 系统变量

在系统中，有一些系统全局变量被系统使用。系统全局变量就是一个有自己语法的全局变量。每次在启动主程序之前，都要准备/使用这些变量。

| 变量        | 描述                                                                                    |
| ----------- | --------------------------------------------------------------------------------------- |
| G.time      | 这个变量返回当前的时间。该值是标准的 UNIX 时间（自 1970 年 1 月 1 日 00:00 起的秒数）。 |
| G.year      | 该变量返回当前年份。                                                                    |
| G.month     | 该变量返回当前月份。                                                                    |
| G.day       | 该变量返回当前月份的日期。                                                              |
| G.hour      | 该变量返回一天中的当前时间。                                                            |
| G.min       | 该变量返回小时的当前分钟。                                                              |
| G.dayofweek | 该变量返回当前是星期几（1-7，1 是星期一等）。                                           |
| G.mode      | 该变量返回当前机器的运行模式（1 - auto，2 - manu，3 - serv）。                          |