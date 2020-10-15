# expression-validation-project
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Expression Validation</title>
    <!-- Latest compiled and minified CSS -->
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">

<!-- jQuery library -->
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>

<!-- Popper JS -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js"></script>

<!-- Latest compiled JavaScript -->
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
</head>
<body>
    <div class="container">
        <br>
        <form onsubmit="return validation()">
            <div class="form-group">

                <!-- Username -->
                <label for="">Username : </label>
                <input type="text" name="" id="username" class="form-control" required>
                <span id="userError" class="text-danger font-weight-bold"></span>
            </div>

            <!-- Email -->

            <div class="form-group">
                <label for="">Email : </label>
                <input type="text" name="" id="email" class="form-control" required>
                <span id="emailError" class="text-danger font-weight-bold"></span>
            </div>

            <!-- Phone Number -->

            <div class="form-group">
                <label for="">Phone Number : </label>
                <input type="text" name="" id="phoneNumber" class="form-control" required>
                <span id="phnNumError" class="text-danger font-weight-bold"></span>
            </div>

            <!-- Post Code -->

            <div class="form-group">
                <label for="">Post Code : </label>
                <input type="text" name="" id="postCode" class="form-control" required>
                <span id="postCodeError" class="text-danger font-weight-bold"></span>
            </div>

            <input type="submit" name="" class="btn btn-primary">

        </form>
    </div>

    <script type="text/javascript">
    function validation() {
        var username = document.getElementById('username').value;
        var email = document.getElementById('email').value;
        var phoneNumber = document.getElementById('phoneNumber').value;
        var postCode = document.getElementById('postCode').value;

        var usercheck = /^[A-Za-z. ]{3,30}$/;
        var emailcheck = /^([a-zA-Z0-9].?)+[^.]@([a-zA-Z0-9].?)+[^.]$/ ;
        var phnNumcheck = /^(+)?(88)?01[0-9]{9}$/;
        var postCodecheck = /^[0-9]{4}$/;

// Username check

        if(usercheck.test(username)) {
            document.getElementById('userError').iinnerHTML = "";
        } else {
            document.getElementById('userError').innerHTML = "**Username is invalid";
            return false;
        }

        // Email check

        if(emailcheck.test(email)) {
            document.getElementById('emailError').innerHTML = "";
        } else {
            document.getElementById('emailError').innerHTML = "**Email is invalid";
            return false;
        }

        // Phone Number check

        if(phnNumcheck.test(phoneNumber)) {
            document.getElementById('phnNumError').innerHTML = "";
        } else {
            document.getElementById('phnNumError').innerHTML = "**Phone number is invalid";
            return false;
        }

        // Post code check

        if(postCodecheck.test(postCode)) {
            document.getElementById('postCodeError').innerHTML = "";
        } else {
            document.getElementById('postCodeError').innerHTML = "**Post Code is invalid";
            return false;
        }



   
   
    }

    
   


    </script>






</body>
</html>
