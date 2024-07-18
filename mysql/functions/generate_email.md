# 随机生成邮箱

```sql
CREATE FUNCTION `generate_email`() RETURNS varchar(255) CHARSET utf8
BEGIN
	declare email varchar(255);
	set email=CONCAT(FLOOR(UNIX_TIMESTAMP()+10000000000*rand()),'@',ELT(CEILING(RAND( ) * 4) ,  "qq.com","163.com","sina.com","gmail.com"));
    return email;
END
```