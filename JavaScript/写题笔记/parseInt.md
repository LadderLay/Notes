`parseInt(string,radix)`
parseInt解析一个字符串并返回指定基数的十进制整数。
radix的取值范围： 2-36
若radix不在2-36这个范围内，或者第一个非空字符不能转换成数字，则返回`NaN`
若radix未指定、0、undefined 会有几种不同的处理情况：  
- string以**'0X'、'0x'**开头 => radix  = 16
- string以**'0'**开头 => radix  = 8或10
- string以**其他值**开头 => radix  = 10

若parseInt遇到的字符不是指定radix参数中的数字，则它将忽略该字符以及所有后续字符，返回到该点为止已解析的整数值。