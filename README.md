# PROCEDURE
mysql 存储过程


MySQL 的存储过程 procedure 与 函数 function 的区别和使用方法
</br>
https://blog.csdn.net/xlxxcc/article/details/52485322
</br>

MySQL知识（十五）——存储过程的调用、查看、修改和删除
</br>
https://blog.csdn.net/Zen99T/article/details/50751100
</br>
phpMyAdmin添加存储过程
</br>
http://pixy.iteye.com/blog/1166862

</br>
CREATE DEFINER=`root`@`localhost` PROCEDURE `SelectAEmptyasinOut`( OUT today VARCHAR(1000) )
BEGIN

SELECT  `external_product_id` 
FROM  `inventoryloadercreator` 
WHERE  `zhendianAsin` IS NULL 
ORDER BY  `id` ASC 
LIMIT 1 
INTO today;

UPDATE  `inventoryloadercreator` SET  `zhendianAsin` =  "searching" WHERE  `external_product_id` = today;


END

语句定界符 //
