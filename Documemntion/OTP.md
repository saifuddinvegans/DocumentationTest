**Create OTP**
----
  Returns json data about a single user.

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
    **Content:** ` {
          error: {
            message: `OTP sent failed!`
          }
        }`
 
* **Error Response:**

  * **Code:** 200  <br />
    **Content:** `{
                    error: {
                        "message": "OTP sent failed!",
                        "error": { object of original server error}
                    }
                }`



* **Sample Call:**

  ```
    curl --location --request POST '{host}/api/common_otp/create' \
    --header 'Content-Type: application/x-www-form-urlencoded' \
    --data-urlencode 'email=saifuddin+001@govegans.it'
  ```