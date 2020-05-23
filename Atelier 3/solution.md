--3.1 SELECT * FROM `warehouses`

--3.2 SELECT `Contents`, `Value` FROM `boxes` WHERE VALUE > 150
select * from boxes where Value>150;

--3.3 SELECT DISTINCT Contents FROM `boxes`;

--3.4 SELECT AVG(Value) FROM `boxes`;

--3.5 SELECT AVG(Value), warehouse FROM boxes GROUP BY warehouse;

--3.6 SELECT AVG(Value), warehouse FROM boxes GROUP BY warehouse HAVING AVG(Value) > 150;

--3.7 SELECT boxes.Code , warehouses.Location FROM boxes INNER JOIN warehouses ON boxes.Warehouse = warehouses.Code;

--3.8 SELECT Warehouse , COUNT(*) FROM boxes GROUP BY Warehouse;

--3.9 SELECT Code FROM warehouses WHERE Capacity < ( SELECT COUNT(*) FROM boxes WHERE Warehouse = warehouses.Code );

--3.10 SELECT Code FROM `boxes` WHERE Warehouse IN ( SELECT Code FROM warehouses WHERE Location = ('Chicago') );

--3.11 INSERT INTO `warehouses`(`Code`, `Location`, `Capacity`) VALUES (6, 'New York' , 3);

--3.12 INSERT INTO `boxes`(`Code`, `Contents`, `Value`, `Warehouse`) VALUES ("H5RT" ,"Papers", 200 ,2 );

--3.13 UPDATE `boxes` SET `Value`= Value * 0.85;

--3.14 DELETE FROM `boxes` WHERE Value < 100;

-- 3.15 DELETE FROM `boxes` WHERE Warehouse IN ( SELECT Code FROM warehouses WHERE Capacity < ( SELECT COUNT(*) FROM boxes WHERE Warehouse = warehouses.Code ) );

-- 3.16 CREATE INDEX `index_nom` ON `table` (`colonne1`);
        CREATE INDEX `index_Warehouse` ON boxes (Warehouse);

-- 3.17 SHOW INDEX FROM `boxes`;
