Getting Started
===============

Setting up
^^^^^^^^^^
Setting up the rights Variables

config.php & config2.php, 
::
   $SERVER="localhost:3306"; 	// database server Host
   $USER="root";  				// Database user
   $PASS="";      				// Database Password
   $BBDD="konieapp"; 			// Database Name


conn.php
This code establishes the connection with Protrack
::
   $dsn = "Driver={SQL Server};Server=10.1.1.80,1433;Database=Protrack;Integrated Security=SSPI;User ID=koniecupsinternationalinc.local\Protrack;Password=Proabc123$$;";
   $conn = odbc_connect( $dsn, 'sa', 'B1Admin' );

connex.php
This code establishes the connection with our local database
::
   $dsn = "Driver={SQL Server};Server=10.1.1.80,1433;Database=Protrack;Integrated Security=SSPI;User ID=koniecupsinternationalinc.local\Protrack;Password=Proabc123$$;";
   $conn = odbc_connect( $dsn, 'sa', 'B1Admin' );


Deprecated Functions
^^^^^^^^^^^^^^^^^^^^
This Module is running in a old php version lower than 5.5, so to be able to test this module you have to make a few changes:

- mysql_connect => **mysqli_connect**
- mysql_connect_errno => **mysqli_connect_errno**
- mysql_query($sqlref) => **mysqli_query($conex,$sqlref)**
- mysql_fetch_array => **mysqli_fetch_array**



.. note::
   $resultref=mysql_query($sqlref) or die(mysqli_error());
   // REPALCE WITH
   $resultref=mysqli_query($conex,$sqlref) or die(mysql_error());

This directory represents a complete module. The main file is **index.php** and it is used to initialize the module.


Database Connections
^^^^^^^^^^^^^^^^^^^^
- Uses an SQL Database
- PROTRACK is a third party framework that uses SQL Server, the connection is required.