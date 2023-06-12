---
layout: layouts/base.njk
eleventyNavigation:
  key: Contact Us
  order: 6
---

<html>
  <head>

		<!-- <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous"> -->
        <h2> Contact Us Form </h2>
        <br>  
  </head>
  <body>

<form name = "contact" method = "POST" data-netlify = "true">
  <label for="fname">First Name </label>
  <input type="text" id="fname" name="fname" required
       minlength="4" maxlength="12" size="10">
  
  <br>  <br>
    
      <label for="sname">Surname </label>
  <input type="text" id="sname" name="sname" required
       minlength="4" maxlength="12" size="10">
  
  <br>  <br>
  
  <label for="email">Email (gmail): </label>
  <input type="email" id="email"
       pattern=".+@gmail\.com" size="30" required>
  
   <br>  <br>
  
  <label for="phone">Phone number (000-000-0000): </label>
  <input type="tel" id="phone" name="phone"
       pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}"
       required>
  
  <br>  <br>
  
   <label for="message">Message </label>
    <br>
   <textarea id="message" name="message" rows="4" cols="50">Type your message here</textarea>
  
   <br>
  <button class = "form_submit" type = "submit" > Submit </button>

   
  <br>  <br>
  

  <br> 

   <input type="checkbox" id="tnc" name="tnc" >
   <label for=tnc> Please accept terms and conditions</label><br>

  
</form>
    <footer class = "text-center">
      <p>&copy; 2023 My nature Web</p>
    </footer>

		<script>
        //get default border colours (to use on input when validation passes)
    var borderStylePass = document.querySelector('#fname').style.border;
    //set fail border colours (to use on input when validation fails)
    var borderStyleFail = '1px solid red';
    //get the form submit button
    var submitButton = document.querySelector(".form_submit");

submitButton.addEventListener("click", function(event){
  var fname = document.querySelector("#fname");
  var sname = document.querySelector("#sname");
  var email = document.querySelector("#email");
          //all validation is assumed to be passed until tested
        blnValidated = true;
        //change the border as it the validation passed
        fname.style.border = borderStylePass;
        sname.style.border = borderStylePass;
       //if validation fails change the bln to false and change the input border colour
        if(!fname.value){
            blnValidated = false;
            fname.style.border = borderStyleFail;
        }
        if(!sname.value){
            blnValidated = false;
            sname.style.border = borderStyleFail;
        }
          //if validation fails change the bln to false and change the input border colour
        email.style.border = borderStylePass;
        if(!email.value){
            blnValidated = false;
            email.style.border = borderStyleFail;
        }
        //if validation failed do not allow the form to submit the data
        if(!blnValidated){
            event.preventDefault();
        }
}, false);
    </script>

  
</body>
</html>