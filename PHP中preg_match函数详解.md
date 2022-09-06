链接：https://editor.csdn.net/md/?articleId=124201990

@[toc](目录)
## 函数形式
```php
preg_match(string $pattern, string $subject, array &$matches);
```

## 函数功能
匹配正则表达式.
## 参数详解
#### pattern
要搜索的模式串，字符串类型
#### sbuject
输入的字符串，字符串类型
#### matches
可选，用来存放搜索结果，```$matches[0]```存放所有匹配的字符串，```$matches[1]```用来存放第一个匹配的字符串，```$matches[2]```用来存放第三个匹配的字符串，以此类推

### 返回值
如果没有匹配,返回值为0
如果有匹配，返回值为1
## 例子
```php
<?php
preg_match('/(foo)(bar)(baz)/', 'foobarbaz', $matches);
print_r($matches);
?>
/**结果
Array
(
    [0] => foobarbaz
    [1] => foo
    [2] => bar
    [3] => baz
)
**/
```
