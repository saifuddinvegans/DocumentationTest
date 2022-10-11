**Send email varification link to a user**
----
  Returns json data about success message as status true or false.

* **URL**

  /auth/emailvarification

* **Method:**

  `POST`
  

* **Raw json Data Params**

    **Header:**

    `Authorization:Bearer [logintoken]`

    **Required:**

    `email:[string]`



    **Sample input:**

    ```
    {
      "email": "saifuddin+0016@govegans.it"
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
      
      `{ status: false , error:[{...}]}` 
      
      status value is Boolean message is optional 

    OR 

  * **Code:** 400  <br />
      **Content:** 
        
        {
          "email": "Required and valid email"
        }

      OR 

      `Unauthorized`
    

  * **Code:** 506  <br />
      **Content:** 
        
        {
            "error": {
                "code": "auth/user-not-found",
                "message": "There is no user record corresponding to the provided identifier."
            }
        }




* **Sample Call:**

  ```
    curl --location --request POST '{host}/api/auth/emailvarification' \
    --header 'Content-Type: application/json' \
    --header 'Authorization: Bearer {login token}' \
    --data-raw '{
        "email": "saifuddin+0016@govegans.it"
    }'    
  ```

----