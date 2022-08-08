**OnCreate**
----
  Function triggred whan a new data added to path user/{userId}

* **call aws api function**

    This function get the api setting for header from the firestore `project_configurations/keys/aws_api`. 

  * **Header**

      `x-channel` vallue should be `MOBILE` or `WEB`. [this data can be change from setting of firestore]
      `x-channel` vallue should be `BACKOFFICE` or `DR_PORTAL` or `CUSTOMER_PORTAL`. [this data can be change from setting of firestore]
      `x-app_language` vallue should be `IT`. [this data can be change from setting of firestore]
      `x-app_version` vallue should be `1.0.0`. [this data can be change from setting of firestore]
      `x-nonce` vallue should be uuid. 
      `x-hmac` vallue should be `TBD`. 

  * **Data**
      `'{"id":"[uid from firestore user collection]"}'`

  * **sample curl call**
  ```
  curl --location --request POST '{host}/account/new' \
  --header 'x-channel: WEB' \
  --header 'x-caller_id: BACKOFFICE' \
  --header 'x-app_language: IT' \
  --header 'x-app_version: 1.0.0' \
  --header 'x-nonce: e8801deb-5e29-4016-b4a3-f2ae39b8f231' \
  --header 'x-hmac: TBD' \
  --header 'Content-Type: application/json' \
  --data-raw '{"id":"2efa5dee-33b4-461d-af2f-123e0cc34ea6"}'
  ```