###  2017-11-11

# 第三届上海市大学生网络安全大赛wp



## Some Words
#### 0x00 [原理]
     布尔盲注
#### 0x01 [目的]
     了解kali系统下的脚本，盲注
#### 0x02 [环境]
     kaki
#### 0x03 [工具]
     FireFox,python
#### 0x04 [步骤]

1.首先打开题目，在url栏注入，有回显。是布尔盲注

![](/files_for_wp/words_1.png)

2.尝试更多的注入，发现过滤了很多东西。如and，union，=之类的</br>
  and被过滤，使用or</br>

3.尝试布尔盲注,可参考[布尔盲注](http://blog.csdn.net/squeen_/article/details/52767887)</br>
  ①.获取数据库的长度：为5</br>
  ![](/files_for_wp/words_2.png)</br>
  数据库长度为0，正常回显</br>
  ![](/files_for_wp/words_3.png)</br>
  数据库长度为4，正常回显</br>
  ![](/files_for_wp/words_4.png)</br>
  数据库长度为5，不报错，无回显</br>
  ②.获取数据库名称:为</br>
  ![](/files_for_wp/words_5.png)</br>
  正常回显</br>
  ![](/files_for_wp/words_6.png)</br>
  不报错，无回显</br>
  所以第一个位为ascii值为119的值：w</br>
  依次尝试，数据库名为：words</br>
  ③.获取表长度：为4</br>
  ![](/files_for_wp/words_7.png)</br>
  表长度为0，正常回显</br>
  ![](/files_for_wp/words_8.png)</br>
  表长度为3，正常回显</br>
  ![](/files_for_wp/words_9.png)</br>
  表长度为4，不报错，无回显</br>
  ④.获取表名:为f14g（方法同②）</br>
  ![](/files_for_wp/words_10.png)</br>
  不报错，无回显</br>
  所以第一个位为ascii值为119的值：w</br>
  依次尝试，数据库名为：f14g</br>

4.使用python脚本注入</br>
 脚本如下：</br>
 ![](/files_for_wp/words_11.png)</br>
 运行的flag</br>

5.flag：flag{1781c958-e46d-4722-b637-503cf7b2b7ca}


#### 0x05 [总结]
    布尔盲注
</br>
</br>
</br>
</br>
</br>






