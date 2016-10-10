1 位置变量
> ```$* 包含参数列表```

> ```$@包含参数列表```

> ```$#包含参数的个数```

2 $[]的使用方式非常灵活 对于[]里面的表达式求值
> ```expr命令也可以对表达式执行求值操作```

> ```let命令用于计算整数表达式的值```

3 脚本执行命令和控制语句

1 if选择结构
```
if test-commands
then 
    commands
fi

ps: 用于条件测试的语句[ $password = "password" ] 在]左右边上必须带空格
```
2 while循环
```
while read n
do
   ===程序块===
done
```

3 for 循环
```
for i in 1 2 3 4 5 6 7 8 9
do 
   echo $i
done 
```

用于数字比较的选项
选项 | 对应的英语单词 | 描述
---|---|---
-eq | equal | 如果相等,返回真
-ne | not equal | 如果不相等,返回真
-lt | lower than|如果int1小于int2,返回真
-le |lower or equal|如果int1小于或等于int2,返回真
-gt | greater than |如果int1大于int2 ,返回真
-ge | greater or equal|如果int1大于或等于int2,返回真


常用shell命令


命令 | 描述
---|---
cut | 以指定的方式分割行,并输出特定的部分
diff | 找到两个文件的不同点
sort | 对输入的行进行排序
uniq | 删除已经排好序的输入中的重复行
tr   | 转换或删除字符
wc   | 统计字符.单词和行的数量
substr| 提取字符串中的一部分
seq | 生成整数数列

4 查看

