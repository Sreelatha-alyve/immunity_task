**login api:**

1. login_email(Request $request):
    
   firstly the the email_encrypt in the users table is matched with the hash of the $request->email field generated        by MD5 algorithm. If it is matched then it's evident that the user already exists else an otp is sent to the the
   $request->email.

2. login_verify_email(Request $request):
  
    a. prepare the details of the request object like trimming the white spaces of email/ converting all the letters in        email to lower case, and pass the modified request object to a method called verify_otp_global() method,that            validates the user provided otp with the email.
   
    b. If the OTP verification is successful, the code retrieves the user by searching for the MD5 hash of the email in        the users table.

    c. The function processes user data, including setting the profile image URL based on conditions and fetching user         permissions.It checks if the user belongs to any communities and retrieves the relevant role mappings.


  
