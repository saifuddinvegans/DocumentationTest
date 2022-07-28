**Create OTP**
----
  Returns json data about success message to OTP sent or error.

* **URL**

  /api/common_otp/create

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
    curl --location --request POST '{host}/api/common_otp/create' \
    --header 'Content-Type: application/x-www-form-urlencoded' \
    --data-urlencode 'email=example@example.com' \
    --data-urlencode 'phone=+880xxxxxxxxxxx'
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
    --data-urlencode 'phone=+880xxxxxxxxxxx'
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
    --data-urlencode 'phone=+880xxxxxxxxxxx'
  ```
