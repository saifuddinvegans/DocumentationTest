**Add new notification token**
----
  Returns json data about success message as status true or false.

* **URL**

  /api/notification-message/token

* **Method:**

  `POST`
  

* **Raw json Data Params**

    **Header:**

    `Authorization:Bearer [logintoken]`

    **Required:**

    `user_id:[string]`

    `token:[string]`

    `device:[string][web or ios or android]`


    **Oprional:**
    
    `device_info:[string]`

    **Sample input**
    ```
    {
    "user_id": "nTZ4xpIpGnNZtqnrfofOieRp7M72",
    "token": "eSxDSyIMJNwxEM9qk9vxca:APA91bHv-d7BtOr_C1788fr0CMmiBDMgQeVWl1dO79j2ItV8UxNlnVuLJEEZMkHDH417LBlwqhPzjAiloWGaWlu88KFZUJYbZ8VR2nIiL4EZpF5tod5iWdGnkwvKFMZStmwK_q5pi1Rg1",
    "device": "web",
    "device_info": {"browser":"Chrome","version":"104.0.0.0"}
    }
    ```

  

* **Success Response:**

  * **Code:** 201 <br />
    **Content:** 
    
    `{ status: true }` 
    
    status value is Boolean
 
* **Error Response:**

  * **Code:** 200  <br />
    **Content:** 
    
    `{ status: false , message:''}` 
    
    status value is Boolean message is optional 

    OR 

  * **Code:** 400  <br />
    **Content:** 
    
    `{
    "user_id": "Required and string",
    "token": "Required and string",
    "device": "Required , string and value should be web or ios or android",
    "device_info": "Optional object data for web {browser:'Browser name',version:'Browser version'}"
}`



* **Sample Call:**

  ```
    curl --location --request POST '{host}/api/common_otp/create' \
    --header 'Content-Type: application/x-www-form-urlencoded' \
    --data-urlencode 'email=example@example.com' \
    --data-urlencode 'phone=+1xxxxxxxxxxx'
  ```
----


**Resend OTP**
----
 Returns json data about success message to OTP sent or error.

* **URL**

  /api/common_otp/resend

* **Method:**

  `POST`
  

* **Data Params**

    **Required:**
    `email:[string]`

    **Oprional:**
    `phone:[string]`

  If phone is given the the OTP will send to phone number. If not then then OTP will send to email

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ success: 'OTP sent' }`
 
* **Error Response:**

  * **Code:** 200  <br />
    **Content:** `{
                    error: {
                        "message": "OTP sent failed!",
                        "error": { object of original server error}
                    }
                }`
    
    OR

  * **Code:** 200  <br />
    **Content:** `{"error":{"message":"Error","error":{"message":"nitCommon: error initializing","error":{}}}}`

* **Sample Call:**

  ```
    curl --location --request POST '{host}/api/common_otp/resend' \
    --header 'Content-Type: application/x-www-form-urlencoded' \
    --data-urlencode 'email=example@example.com' \
    --data-urlencode 'phone=+1xxxxxxxxxxx'
  ```
----
  

**Verify OTP**
----
 Returns json data about success message to OTP verification or error.

* **URL**

  /api/common_otp/verify

* **Method:**

  `POST`
  

* **Data Params**

    **Required:**
    `email:[string]`
    `otp:[number]`

    **Oprional:**
    `phone:[string]`

  If phone is given the the OTP will send to phone number. If not then then OTP will send to email

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ success: 'OTP verified' }`
 
* **Error Response:**

  * **Code:** 200  <br />
    **Content:** `{"error":{"message":"OTP not found!"}}`


    OR

  * **Code:** 200  <br />
    **Content:** `{"error":{"message":"Error","error":{"message":"nitCommon: error initializing","error":{}}}}`

* **Sample Call:**

  ```
    curl --location --request POST '{host}/api/common_otp/verify' \
    --header 'Content-Type: application/x-www-form-urlencoded' \
    --data-urlencode 'otp=000000' \
    --data-urlencode 'email=example@example.com' \
    --data-urlencode 'phone=+1xxxxxxxxxxx'
  ```
