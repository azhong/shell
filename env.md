# shell 环境变量的作用域理解

牢记几点即可：
* 执行一个脚本文件，比如 sh test.sh，则是在子shell窗口完成操作，内部各种export都不会污染当前环境，执行完即可退出；
* source 一个脚本文件，比如 source test.sh，则在当前窗口完成操作，内部各种export都会污染当前环境；
* 当打开一个子窗口执行shell时，父窗口的环境变量可以被子窗口使用；

# 测试代码
 ```
 #!/bin/bash
 
 export abc="abc"
 echo $abc
 ```
 ## sh test.sh
 执行完之后，再次执行echo "$abc"，输出为空
 
 ## source test.sh 
 执行完之后，再次执行echo "$abc"，输出为abc
