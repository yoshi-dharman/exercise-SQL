1.Tampilkan semua Customer yang tinggal di Negara German atau Mexico\
SELECT * FROM Customers\
WHERE Country = "Germany" OR Country = "Mexico"\

2.Tampilkan semua Product yang Harganya kurang dari 15\
SELECT * FROM Products\
WHERE Price < 15\

3.Tampilkan semua Product yang range Harganya dari 10 - 30\
SELECT * FROM Products\
WHERE Price > 10 AND Price < 30\

4.Tampilkan semua Customer yang tinggal di Europa\
SELECT * FROM Customers\
WHERE Country NOT IN ('Argentina', 'Brazil', 'Canada', 'Mexico', 'USA', 'Venezuela')\

5.Hitung jumlah total Order Customer dengan Nama Rattlesnake Canyon Grocery\
SELECT COUNT(OrderID) \
FROM Orders as O \
INNER JOIN Customers as C\
ON C.CustomerName = "Rattlesnake Canyon Grocery" AND O.CustomerID = C.CustomerID\

6.Tamplikan Orderan dari Federal Shipping dengan OrderDate kurang dari bulan 12\
SELECT ShipperName, OrderDate \
FROM Shippers as S\
Inner Join Orders as O\
ON NOT OrderDate LIKE "%-12-%" AND S.ShipperID = O.ShipperID\

7.Tampilkan Semua Nama Barang yang dibeli oleh Save-a-lot Markets\
SELECT DISTINCT  ProductName\
FROM Customers as C\
INNER JOIN Orders as O\
ON C.CustomerName = "Save-a-lot Markets" AND C.CustomerID = O.CustomerID\
INNER JOIN OrderDetails as OD\
ON OD.OrderID = O.OrderID\
INNER JOIN Products as P\
ON P.ProductID = OD.ProductID \

8.Hitung total keseluruhan barang yang dibeli oleh B's Beverages\
SELECT CustomerName, Sum(Quantity) \
FROM Customers as C\
INNER JOIN Orders as O\
ON C.CustomerID = O.CustomerID AND C.CustomerName = "B's Beverages"\
INNER JOIN OrderDetails as OD\
ON OD.OrderID = O.OrderID\

9.Hitung total pengiriman yang dilakukan oleh United Package pada bulan 8\
SELECT Count(S.ShipperID) \
FROM Shippers as S\
INNER Join Orders as O\
On S.ShipperName = "United Package" AND O.OrderDate Like '%-08-%' AND S.ShipperID = O.ShipperID\

10.Tampilkan Product dengan Category Beverages\
SELECT * \
FROM Products as P\
INNER JOIN Categories as C\
ON C.CategoryID = P.CategoryID AND C.CategoryName = 'Beverages'\