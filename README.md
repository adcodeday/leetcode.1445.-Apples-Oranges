# leetcode.1445.-Apples-Oranges
力扣.1445. 苹果和桔子
![lik](https://github.com/adcodeday/leetcode.1445.-Apples-Oranges/assets/130963605/14b2a794-779b-4045-9234-88d4daaadc0a)
SELECT a.sale_date, (a.sold_num - b.sold_num) AS diff  
FROM Sales a  
JOIN Sales b ON a.sale_date = b.sale_date  
WHERE a.fruit = 'apples' AND b.fruit = 'oranges'  
ORDER BY a.sale_date;  

这个查询使用了自连接（self-join）的概念。自连接是指将表与自身进行连接操作，以便在表中的不同行之间建立关联关系。在这种情况下，我们使用自连接来匹配具有相同日期的苹果和桔子的销售记录。

首先，我们使用两个表别名 a 和 b 来表示 Sales 表的两个副本。然后，我们通过以下条件将这两个副本连接起来：a.sale_date = b.sale_date。这样，我们就将具有相同日期的销售记录匹配起来了。

在连接之后，我们使用 WHERE 子句来筛选出表中只包含苹果和桔子销售记录的行。条件是 a.fruit = 'apples' 和 b.fruit = 'oranges'，这样我们就只保留了那些既有苹果销售记录又有桔子销售记录的行。

最后，我们使用 SELECT 子句选择了两个列：a.sale_date 和 (a.sold_num - b.sold_num) AS diff。第一个列是销售日期，第二个列是苹果销售数量减去桔子销售数量的差异。我们使用别名 diff 来表示这个差异列。

最后，我们使用 ORDER BY 子句按照 sale_date 的格式对结果进行排序，以确保查询结果按照日期的升序排列。
