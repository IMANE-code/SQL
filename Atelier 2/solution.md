-- 2.1 SELECT LastName FROM `employees`;

-- 2.2 SELECT DISTINCT LastName FROM `employees`

-- 2.3 SELECT * FROM `employees` WHERE LastName='smith';

-- 2.4 SELECT * FROM `employees` WHERE LastName='smith' or LastName='Doe';

-- 2.5 SELECT * FROM `employees` WHERE Department=14

-- 2.6 SELECT * FROM `employees` WHERE Department=37 or Department=77;

-- 2.7 SELECT * FROM `employees` WHERE LastName LIKE 's%';

-- 2.8 SELECT SUM(Budget) FROM `departments`;

-- 2.9 SELECT DISTINCT Department,COUNT(*) FROM `employees` GROUP BY Department;

-- 2.10 SELECT * FROM `employees` AS e 
        INNER JOIN `Department` as d 
        on e.Department = d.Code;

-- 2.11 SELECT a.name, a.lastname, b.name Department_name, b.Budget FROM `employees` a JOIN `departments`   b ON    a.department = b.code;

-- 2.12 SELECT Name,LastName FROM `employees` WHERE `Department` IN(SELECT CODE FROM `departments` WHERE `Budget`>60000 );

-- 2.13 SELECT * FROM `departments` WHERE Budget>(SELECT AVG(Budget) FROM `departments`)

-- 2.14 SELECT Name FROM `departments` WHERE Code IN (SELECT Department FROM `employees` GROUP BY Department HAVING COUNT(*) > 2);
SELECT Departments.Name FROM `employees` INNER JOIN `departments` ON Department = Code GROUP BY Departments.Name HAVING COUNT(*) > 2;

-- 2.15 SELECT name, lastname FROM `employees` WHERE department =(SELECT temp.code FROM (SELECT * FROM `departments` ORDER BY budget limit 2) temp ORDER BY temp.budget DESC limit 1);

-- 2.16 INSERT INTO `departments`(`Code`, `Name`, `Budget`) VALUES (11,'Quality assurance',40000);
        INSERT INTO `employees`(`SSN`, `Name`, `LastName`, `Department`) VALUES (847219811,'Mary','Moore',11);

-- 2.17 UPDATE `departments` SET `Budget`= Budget - (Budget*0.1);

-- 2.18 UPDATE `employees` SET `Department`=14 WHERE `Department`=77;

-- 2.19 DELETE FROM `employees` WHERE `Department`=14;

-- 2.20 DELETE FROM `employees` WHERE `Department` IN(SELECT CODE FROM `departments` WHERE Budget>60000);

-- 2.21 DELETE FROM `employees`;
