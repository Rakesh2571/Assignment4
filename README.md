
<!DOCTYPE html>
<html>
	<head>
		<link rel="Stylesheet" type="text/css" href="css/style.css">
	</head>
	<body>
			<header>
				<ul>
					<li><a href="index.html">Home</a></li>
				</ul>
				<ul>
					<li><a href="register.html">Back</a></li>
				</ul>
	<?php
		$servername = "localhost";
		$username = "root";
		$password = "";
		$database = 'classic_autostore';

		// Create a connection		

		$connection = mysqli_connect($servername, $username, $password, $database);

		// Check the connection

		if ($connection->connect_error)
			{
				die("The Connection failed: " . $connection->connect_error);
			}
		$message="The data has been  successfully ! Thank you";
		echo"<script> type='text/javascript'alert('$message');</script>";
		$query="INSERT INTO classic_table (seller_name,address,city,phone_number,email,year,make,model) VALUES ('".$_POST['sellername']."','".$_POST['Address']."','".$_POST['City']."','".$_POST['phone']."','".$_POST['Email']."','".$_POST['Year']."','".$_POST['Make']."','".$_POST['Model']."')";
		/*$addDB="INSERT INTO classic_table (displaylink) VALUES ('".$addlink."')";*/
		$execute=$connection->query($query);
		
		$sellerssname=$_POST['sellername'];
		$sellersaddress=$_POST['Address'];
		$sellersCity=$_POST['City'];
		$sellersphonenumber=$_POST['phone'];
		$sellerssemail=$_POST['Email'];
		$sellersyear=$_POST['Year'];

		$sellersmake=str_replace(' ','-',$_POST['Make']);
		$sellersmodel=str_replace(' ','-',$_POST['Model']);
		$addlink="https://www.jdpower.com/Cars/".$sellersyear."/".$sellersmake."/".$sellersmodel;

		$addDB="INSERT INTO classic_table (displaylink) VALUES ('".$addlink."')";
		$execute=$connection->query($addDB);
		echo"<table><ul><tr><td><h1>Vehicle Information</h1></td></tr></ul></table>";
		echo"<table><tr><th>Seller's Name:</th>   <td>$sellerssname</td></tr></table>";
		echo"<table><tr><th>Address:</th>  	<td>$sellersaddress</td></tr></table>";
		echo"<table><tr><th>City:</th>  	<td>$sellersCity</td></tr></table>";
		echo"<table><tr><th>Phone number:</th>   <td>$sellersphonenumber</td></tr></table>";
		echo"<table><tr><th>Email:</th>   <td>$sellerssemail</td></tr></table>";
		echo"<table><tr><th>Year:</th>   <td>$sellersyear</td></tr></table>";
		echo"<table><tr><th>Make:</th>   <td>$sellersmake</td></tr></table>";
		echo"<table><tr><th>Model:</th>  <td>$sellersmodel</td></tr></table>";
		echo"<table><tr><th>Hyperlink:</th><td><a href='$addlink'>    $addlink</font></a></td></tr></table>";		
		
		mysqli_close($connection)
	?>
		</header>
	</body>
</html>

