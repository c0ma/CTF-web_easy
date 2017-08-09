# CTF-web_easy
```
<html>
<head>
<title>VoiceTech Sweden AB</title>
<head>
<body>
<?php
	error_reporting(E_ERROR);
    function ip_in_range($lower_range_ip_address, $upper_range_ip_address, $needle_ip_address)
    {
        $min    = ip2long($lower_range_ip_address);
        $max    = ip2long($upper_range_ip_address);
        $needle = ip2long($needle_ip_address);            
        return (($needle >= $min) AND ($needle <= $max));
    }    
	$headers = apache_request_headers();
	
	$ip = $headers['X-Forwarded-For'];
	$custip = (ip_in_range("31.44.224.0" , "31.44.239.255",$ip)); 

	if($custip == true)
		echo "flag{I'm_s0_G0ddamn_horny_+he_cr4ck_0f_d4wn_be++er_b3_car3ful_4round_m3}";
	else
		echo "You are not allowed to view this content.<br>Only for VoiceTech Sweden AB customers.";
?>
</body>
</html>
```
