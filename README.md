# JDBC-Example
CRUD operations, performed against a MySql DB table using JDBC

## How to use:
1. Create an empty MySql database, called EMP, using PhpMyAdmin or another DB manager
2. Import the .SQL file
3. Set DB username & pass to "root" in your config.inc.php (for PhpMyAdmin) or modify the credentials for every Java class to match your DB credentials
4. Import the JDBC project into your workspace and configure the build path to include the JDBC jar
5. Start the DB on Localhost
6. Before calling the function getEmpName, execute the following stored proceedure in your PhpMyAdmin:

DELIMITER $$

DROP PROCEDURE IF EXISTS `EMP`.`getEmpName` $$
CREATE PROCEDURE `EMP`.`getEmpName` 
   (IN EMP_ID INT, OUT EMP_FIRST VARCHAR(255))
BEGIN
   SELECT first INTO EMP_FIRST
   FROM Employees
   WHERE ID = EMP_ID;
END $$

DELIMITER ;

## TIP:
You can use XAMPP as a convinient way to setup your DB on local server
