<html>
 <head>
 <title>Aliens Abducted me-Report an Abduction </title>
</head>

<body> 
 
 <h2>Aliens Abducted me-Report an Abduction</h2>
 
 <?php
 $when_it_happened = $_POST['whenithappened'];
 $how_long = $_POST['howlong'];
 $alien_description = $_POST['aliendescription'];
 $how_many = $_POST['howmany'];
 $fang_spotted = $_POST['fangspotted'];
 $email = $_POST['email'];
 $first_name = $_POST['firstname'];
 $last_name= $_POST['lastname'];
 $whattheydid = $_POST['whattheydid'];
 $otherinfo = $_POST['other'];
 $to = 'agbachiabel@gmail.com';
 $subject = 'Aliens Abducted Me - Abduction Report';
 $msg = "$first_name was abducted $when_it_happened and was gone for $how_long.\n" .
        "Number of Aliens: $how_many\n" .
		"Alien Description: $alien_description\n" .
		"What they did: $whattheydid\n" .
		"Fang spotted: $fang_spotted\n" .
		"Other comments: $otherinfo"; 
	$dbc = mysqli_connect('localhost', 'root','', 'aliendatabase') or die('Error connecting to Mysql server');
    $query = "INSERT INTO aliens_abduction(first_name,last_name,when_it_happened,how_long,how_many,alien_description,what_they_did,fang_spotted,other,email)".
	"VALUES('$first_name','$last_name','$when_it_happened','$how_long','$how_many',".
	"'$alien_description','$whattheydid','$fang_spotted','$otherinfo','$email')";
 $result = mysqli_query($dbc,$query) or die('Error querying database');
 mysqli_close($dbc);
echo 'Thanks for submitting the form.<br/>';
echo 'You were abducted '.$when_it_happened;
echo ' and were gone for '.$how_long.'<br/>';
echo 'Describe them: '.$alien_description.'<br/>';
echo 'Was fang there? ' .$fang_spotted.'<br/>';
echo 'Your email address is '.$email.'<br/>';
echo 'What they did: ' . $whattheydid.'<br/>';
echo 'Other comments: ' .$otherinfo.'<br/>';
echo 'Thanks once again '.$first_name;
?>
 
</body>
</html>
