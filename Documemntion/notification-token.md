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
    
    `overwrite:[Boolean]`

    `device_info:[object]`

    **Sample input:**

    ```
    {
      "user_id": "nTZ4xpIpGnNZtqnrfofOieRp7M72",
      "token": "eSxDSyIMJNwxEM9qk9vxca:APA91bHv-d7BtOr_C1788fr0CMmiBDMgQeVWl1dO79j2ItV8UxNlnVuLJEEZMkHDH417LBlwqhPzjAiloWGaWlu88KFZUJYbZ8VR2nIiL4EZpF5tod5iWdGnkwvKFMZStmwK_q5pi1Rg1",
      "device": "web",
      "overwrite": true,
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
          "overwrite": "Optional Boolean value",
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
      
      `{
        "user_id": "Required and string",
        "token": "Required and string"
      }`

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

----

**Send Notification to All**
----
  Returns json data about success message as status true or false.

* **URL**

  /api/notification-message/send/all

* **Method:**

  `POST`
  

* **Raw json Data Params**


    **Required:**

    `title:[string]`

    `message:[string]`    


    **Oprional:**
    
    `data:[object]`

    **Sample input:**

    ```
    {
      "title": "Claire dev",
      "message": "Test message from dev",
      "data":{
          "type":"scheduling",
          "metadata":"ewoib3JkZXJfaWQiOiAiMTc1OTU4OTMwMjkiCn0="
        }
    }
    ```

  

* **Success Response:**

  * **Code:** 201 <br />
    **Content:** 
    
    `
    {
        "status": true,
        "results": [
            {
                "error": {
                    "code": "messaging/registration-token-not-registered",
                    "message": "The provided registration token is not registered. A previously valid registration token can be unregistered for a variety of reasons. See the error documentation for more details. Remove this registration token and stop using it to send messages."
                }
            },
            {
                "messageId": "28c19300-4b5d-411b-988f-f93916b45f64"
            }
        ],
        "failureCount": 1,
        "successCount": 1
    }
    ` 


    status value is Boolean
 
* **Error Response:**

  * **Code:** 200  <br />
      **Content:** 
      
        ` {
            "status": false,
            "results": [],
            "failureCount": 0,
            "successCount": 0
        }` 
      
      status value is Boolean 

    OR 

  * **Code:** 400  <br />
      **Content:** 
        
        `{
            "title": "Required and string",
            "message": "Required and string",
            "data": "Optional object data"
        }`

     



* **Sample Call:**

  ```
    curl --location --request POST '{host}/api/notification-message/send/all' \
  --header 'Content-Type: application/json' \
  --data-raw '{
      "title": "Claire dev",
      "message": "Test message from dev",
      "data":{
          "type":"scheduling",
          "metadata":"ewoib3JkZXJfaWQiOiAiMTc1OTU4OTMwMjkiCn0="
      }
  }'
  ```

----

**Send Notification to User**
----
  Returns json data about success message as status true or false.

* **URL**

  /api/notification-message/send/{userId}

* **Method:**

  `POST`
  

* **Raw json Data Params**


    **Required:**

    `title:[string]`

    `message:[string]`    


    **Oprional:**
    
    `data:[object]`

    **Sample input:**

    ```
    {
      "title": "Claire dev",
      "message": "Test message from dev",
      "data":{
          "type":"scheduling",
          "metadata":"ewoib3JkZXJfaWQiOiAiMTc1OTU4OTMwMjkiCn0="
        }
    }
    ```

  

* **Success Response:**

  * **Code:** 201 <br />
    **Content:** 
    
    `
    {
        "status": true,
        "results": [
            {
                "error": {
                    "code": "messaging/registration-token-not-registered",
                    "message": "The provided registration token is not registered. A previously valid registration token can be unregistered for a variety of reasons. See the error documentation for more details. Remove this registration token and stop using it to send messages."
                }
            },
            {
                "messageId": "28c19300-4b5d-411b-988f-f93916b45f64"
            }
        ],
        "failureCount": 1,
        "successCount": 1
    }
    ` 


    status value is Boolean
 
* **Error Response:**

  * **Code:** 200  <br />
      **Content:** 
      
        ` {
            "status": false,
            "results": [],
            "failureCount": 0,
            "successCount": 0
        }` 
      
      status value is Boolean 

    OR 

  * **Code:** 400  <br />
      **Content:** 
        
        `{
            "title": "Required and string",
            "message": "Required and string",
            "data": "Optional object data"
        }`

     



* **Sample Call:**

  ```
    curl --location --request POST '{host}/api/notification-message/send/G2vp9iWKpxNhXiNhnw8EQ4k4ti03' \
  --header 'Content-Type: application/json' \
  --data-raw '{
      "title": "Claire dev",
      "message": "Test message from dev",
      "data":{
          "type":"scheduling",
          "metadata":"ewoib3JkZXJfaWQiOiAiMTc1OTU4OTMwMjkiCn0="
      }
  }'
  ```

----
**Note**
----
  * Android device are not able to get both notification and Data in the same time so we put title and message in the data.
  * To save time for sending notification with FCM for same request all user token are grouped to sended in single call.
  * In firestore the data are storing with doc name userId and as a map as format of {web:array, ios:array, android:array} 