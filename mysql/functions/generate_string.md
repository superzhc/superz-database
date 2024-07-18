# 随机生成字符串

```sql
CREATE FUNCTION `generate_string`(n int) RETURNS varchar(255) CHARSET utf8
BEGIN
	declare chars_str varchar(100) default 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890~!@#$%^&*()_+=-[]{}\\|:;"\',.\<\>/?';
    declare return_str varchar(255) default '';
    declare i int default 0;
    while i < n do
        set return_str = concat(return_str, substring(chars_str, floor(1+rand()*94), 1));
        set i=i+1;
    end while;
    return return_str;
END
```