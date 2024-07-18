# 随机生成前 N 年日期

```sql
CREATE FUNCTION `generate_date`(n int) RETURNS date
BEGIN
	DECLARE rand_date DATE;
	SET rand_date=DATE_SUB(CURRENT_DATE() , interval rand()*365*n  day);
	RETURN rand_date;
END
```