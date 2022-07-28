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
    **Content:** `{ id : 12, name : "Michael Bloom" }`
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "User doesn't exist" }`

  OR

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

* **Sample Call:**

  ```javascript
    $.ajax({
      url: "/users/1",
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```