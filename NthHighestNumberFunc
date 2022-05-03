create FUNCTION getNthHighestSalary(@n INT) 
RETURNS INT 
as
begin
declare @ans int
declare @rows int
set @rows = (select count(s.salary) from (select row_number() over (order by salary) as rownum, salary from employee
group by salary) s)
set @n = @rows - @n + 1
set @ans = (select s.salary from (select row_number() over (order by salary) as rownum, salary from employee
group by salary) s
where s.rownum = @n)
return @ans
end
