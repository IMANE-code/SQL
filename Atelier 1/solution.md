1/CREATE DATABASE boutique;

2/CREATE TABLE Manufacturers (
  Code INTEGER PRIMARY KEY,
  Name varchar(255) NOT NULL
);
CREATE TABLE Products (
  Code INTEGER PRIMARY KEY,
  Name varchar(255) NOT NULL,
  Price decimal NOT NULL ,
  Manufacturer INTEGER NOT NULL,
  foreign key (Manufacturer) references Manufacturers(Code) 
);

3/ INSERT INTO `manufacturers`(`Code`, `Name`) VALUES (1,'sony');
   INSERT INTO `manufacturers`(`Code`, `Name`) VALUES (2,'Creative Labs');
   INSERT INTO `manufacturers`(`Code`, `Name`) VALUES (3,'Hewlett-Packard');
   INSERT INTO `manufacturers`(`Code`, `Name`) VALUES (4,'Iomega');
   INSERT INTO `manufacturers`(`Code`, `Name`) VALUES (5,'Fujitsu');
   INSERT INTO `manufacturers`(`Code`, `Name`) VALUES (6,'Winchester');
   
4/ Insérer dans le tableau Products : 
INSERT INTO `Products`(`Code`, `Name`,`Price`, `Manufacturer`) VALUES (1,'Hard drive',240,5);
INSERT INTO `Products`(`Code`, `Name`,`Price`, `Manufacturer`) VALUES (2,'Memory',120,6);
INSERT INTO `Products`(`Code`, `Name`,`Price`, `Manufacturer`) VALUES (3,'ZIP drive',150,4);
INSERT INTO `Products`(`Code`, `Name`,`Price`, `Manufacturer`) VALUES (4,'Floppy disk',5,6);
INSERT INTO `Products`(`Code`, `Name`,`Price`, `Manufacturer`) VALUES (5,'Monitor',240,1);
INSERT INTO `Products`(`Code`, `Name`,`Price`, `Manufacturer`) VALUES (6,'DVD drive',180,2);
INSERT INTO `Products`(`Code`, `Name`,`Price`, `Manufacturer`) VALUES (7,'CD drive',90,2);
INSERT INTO `Products`(`Code`, `Name`,`Price`, `Manufacturer`) VALUES (8,'Printer',270,3);
INSERT INTO `Products`(`Code`, `Name`,`Price`, `Manufacturer`) VALUES (9,'Toner cartridge',66,3);
INSERT INTO `Products`(`Code`, `Name`,`Price`, `Manufacturer`) VALUES (10,'DVD burner',180,2);

5/ SELECT Name FROM `products` ;

6/ SELECT Name,Price FROM `products`;

7/ SELECT Name FROM `products` WHERE Price <= 200;

8/ SELECT Name FROM `products` WHERE Price BETWEEN 60 AND 120;

9/ SELECT Name,Price*100 FROM `products`;

10/ SELECT AVG(Price) FROM `products` ;

11/ SELECT AVG(Price) FROM `products` WHERE Manufacturer = 2;

12/ SELECT COUNT(Name) FROM `products` WHERE Price >= 180

13/ SELECT Name,Price FROM products WHERE Price >= 180 ORDER BY Price DESC;

14/ SELECT a.*,b.Name FROM products a JOIN Manufacturers b on(a.Manufacturer=b.Code);

15/ SELECT a.Name ,a.Price, b.Name FROM products a JOIN Manufacturers b on(a.Manufacturer=b.Code);

16/ SELECT AVG(Price),Manufacturer FROM products GROUP BY Manufacturer;

17/ SELECT AVG (a.Price), b.Name FROM products a JOIN Manufacturers b on(a.Manufacturer=b.Code)GROUP BY b.Name;

18/ SELECT AVG (a.Price), b.Name FROM manufacturers b JOIN products a ON a.Manufacturer=b.Code GROUP BY b.Name
    HAVING AVG(a.Price)>=150;

19/ SELECT Name,Price FROM products WHERE Price=(SELECT min(Price) FROM products);

20/ Sélectionnez le nom de chaque fabricant ainsi que le nom et le prix de son produit le plus cher.

21/ INSERT INTO `products`(`Code`, `Name`, `Price`, `Manufacturer`) VALUES (11,'Loudspeakers',70,2);

22/ UPDATE `products` SET `Name`='laser Print' WHERE CODE=8;

23/ UPDATE `products` SET `Price`=Price-(Price*0.1);

24/ UPDATE `products` SET `Price`=Price-(Price*0.1) WHERE Price>=120