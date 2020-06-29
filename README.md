<!DOCTYPE html>
<html lang="en">

  <head>
    <meta charset="UTF-8">
    <title>Send An E-Mail!</title>
    <style>
      body {
        margin: 0;
        padding: 0;
        text-align: center;
        background: linear-gradient(rgba(0, 0, 50, 0.5), rgba(0, 0, 50, 0.5)), url("https://i.pinimg.com/originals/eb/af/65/ebaf654ad48105230ba6149331bbd4a2.jpg");
        background-size: cover;
        background-position: center;
        font-family: sans-serif;
      }



      .contact-title {
        margin-top: 100px;
        color:#fff;
        text-transform: uppercase;
        transition: all 4s ease-in-out;
      }
      
      
      .contact-title h1{
        font-size: 32px;
        line-height: 10px;
      }
      
      
      .contact-title h2{
        font-size:16px;
      }
      
      form{
        margin-top: 50px;
        transition: all 4s ease-in-out;
      }
       
       
      .form-control{
        width:600px;
        background:transparent;
        border: none;
        outline:none;
        border-bottom: 1px solid gray;
        color:#fff;
        font-size:18px;
        margin-bottom:16px;
      } 
      
      input {
        height:45px;
      }
      
      form .submit{
        background: #ff5722;
        border-color: transparent;
        color:#fff;
        font-size:20px;
        font-weight: bold;
        letter-spacing: 2px;
        height:50px;
        margin-top: 20px;
      }
      
      form .submit:hover{
        background-color: #f44336;
        cursor:pointer;
      }
       
    </style>
  </head>

  <body>

    <div class="contact-title">
      <h1>
        Say Hello
      </h1>
      <h2>
        Send An Email To Annyone You Want!
      </h2>
    </div>


<div class="contact-form">
<form id="contact-form" method="post" action="contact-form-handeler.php">
<input name="name" type="text" class="form-control" placeholder="Your Name" required>
<br>

<input name="email" type="email"  class="form-control" placeholder="Your Email" required>
<br>

<textarea name="message" class="form-control" placeholder="message" row="4" required></textarea><br>

<input type="submit" class="form-control submit" value="SEND MESSAGE">
</form>
</div>



 <?php
$name = $_POST['name'];
$visitor_email = $_POST['email'];
$message = $_POST['message'];


$email_from = 'jaay8338@student.harmonytx.org';

$email_subject = "New Form Submition";

$email_body = "User NAme: $name.\n".
                "User Email: $visitor_email.\n".
                "User Message:$message.\n";
                
     $to = "5312016@student.harmonytx.org";           
                
                
     $headers = "From: $email_ from \r\n";   
     
     $headers .= "Reply-To: $visitor_email\r\n";
     mail($to,$email_subject,$email_body,$headers);
     
     header("Location: index.html");
              ?>
  </body>

</html>
