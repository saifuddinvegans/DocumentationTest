**OnCreate**
----
  Function triggred whan a new data added to path user/{userId}

* **call aws api function**
  * **Header**

      `x-channel` vallue should be `MOBILE` or `WEB`
      
  * **sample curl call**
  ```
  curl --location --request POST 'https://api.dev.claire.health/account/new' \
  --header 'x-channel: WEB' \
  --header 'x-caller_id: BACKOFFICE' \
  --header 'x-app_language: IT' \
  --header 'x-app_version: 1.0.0' \
  --header 'x-nonce: e8801deb-5e29-4016-b4a3-f2ae39b8f231' \
  --header 'x-hmac: TBD' \
  --header 'Content-Type: application/json' \
  --data-raw '{"id":"2efa5dee-33b4-461d-af2f-123e0cc34ea6"}'
  ```