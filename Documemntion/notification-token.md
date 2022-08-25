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
    
    `device_info:[object]`

    **Sample input:**
    
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
        
        {
          "user_id": "Required and string",
          "token": "Required and string",
          "device": "Required , string and value should be web or ios or android",
          "device_info": "Optional object data for web {browser:'Browser name',version:'Browser version'}"
        }

      OR 

      `Unauthorized`



* **Sample Call:**

  ```
    curl --location --request POST '{host}/api/notification-message/token' \
    --header 'Authorization: Bearer {login token}' \
    --header 'Content-Type: application/json' \
    --data-raw '{
        "user_id": "nTZ4xpIpGnNZtqnrfofOieRp7M72",
        "token": "eSxDSyIMJNwxEM9qk9vxca:APA91bHv-d7BtOr_C1788fr0CMmiBDMgQeVWl1dO79j2ItV8UxNlnVuLJEEZMkHDH417LBlwqhPzjAiloWGaWlu88KFZUJYbZ8VR2nIiL4EZpF5tod5iWdGnkwvKFMZStmwK_q5pi1Rg1",
        "device": "web",
        "device_info": {"browser":"Chrome","version":"104.0.0.0"}
    }'
  ```

----


**Delete Notification token**
----
   Returns json data about success message as status true or false.

* **URL**

  /api/notification-message/token

* **Method:**

  `DELETE`
  

* **Raw json Data Params**

    **Header:**

    `Authorization:Bearer [logintoken]`

    **Required:**

    `user_id:[string]`

    `token:[string]`

    **Sample input:**

      ```
      {
      "user_id": "nTZ4xpIpGnNZtqnrfofOieRp7M72",
      "token": "eSxDSyIMJNwxEM9qk9vxca:APA91bHv-d7BtOr_C1788fr0CMmiBDMgQeVWl1dO79j2ItV8UxNlnVuLJEEZMkHDH417LBlwqhPzjAiloWGaWlu88KFZUJYbZ8VR2nIiL4EZpF5tod5iWdGnkwvKFMZStmwK_q5pi1Rg1"
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
      
      {
        "user_id": "Required and string",
        "token": "Required and string"
      }

    OR 

    `Unauthorized`

* **Sample Call:**

  ```
   curl --location --request DELETE '{host}/api/notification-message/token' \
    --header 'Authorization: Bearer {login token}' \
    --header 'Content-Type: application/json' \
    --data-raw '{
        "user_id": "nTZ4xpIpGnNZtqnrfofOieRp7M71",
        "token": "eSxDSyIMJNwxEM9qk9vxca:APA91bHv-d7BtOr_C1788fr0CMmiBDMgQeVWl1dO79j2ItV8UxNlnVuLJEEZMkHDH417LBlwqhPzjAiloWGaWlu88KFZUJYbZ8VR2nIiL4EZpF5tod5iWdGnkwvKFMZStmwK_q5pi1Rg2"
    }'
  ```
