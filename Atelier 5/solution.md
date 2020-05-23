-- 5.1 SELECT Name FROM `pieces`;

-- 5.2 SELECT \* FROM `providers`;

-- 5.3 SELECT Piece,AVG(Price) FROM `provides` GROUP BY Piece

-- 5.4 SELECT Name FROM `providers` WHERE Code IN(SELECT Provider FROM `provides` WHERE Piece = 1);
-- 5.4 SELECT Providers.Name FROM Providers INNER JOIN Provides ON Providers.Code = Provides.Provider AND Provides.Piece = 1;

-- 5.5 SELECT Name FROM `pieces` WHERE Code IN(SELECT piece FROM `provides` WHERE Provider = 'HAL');

-- 5.6 SELECT Pieces.Name, Providers.Name, Price FROM Pieces INNER JOIN Provides ON Pieces.Code = Piece INNER JOIN Providers ON Providers.Code = Provider WHERE Price = (SELECT MAX(Price) FROM Provides WHERE Piece = Pieces.Code)

-- 5.6 SELECT Pieces.Name, Providers.Name, Price FROM Pieces INNER JOIN Provides ON Pieces.Code = Piece INNER JOIN Providers ON Providers.Code = Provider WHERE Price = ( SELECT MAX(Price) FROM Provides WHERE Piece = Pieces.Code );

-- 5.7 INSERT INTO Provides VALUES (1, 'TNBC', 7);

-- 5.8 UPDATE Provides SET Price = Price + 1;

-- 5.9 DELETE FROM Provides WHERE Provider = 'RBT' AND Piece = 4;

-- 5.10 DELETE FROM Provides WHERE Provider = 'RBT';
