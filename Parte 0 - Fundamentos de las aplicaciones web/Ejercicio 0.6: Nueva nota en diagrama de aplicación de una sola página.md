```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{"content": "wassup", "date": "2026-03-08T11:02:24.535Z"}, ...]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa - Payload: {"content":"Fullstack ar","date":"2026-03-08T21:36:03.370Z"}
    activate server
    server-->>browser: {"message":"note created"}
    deactivate server

    Note right of browser: The SPA version of the application doesn't send form data in the traditional way; instead, it uses JavaScript code retrieved from the server. An event handler is created that generates a new note, adds it to the notes list, re-renders the notes list on the page, and sends the new note to the server. The code determines that the data will be sent with an HTTP POST request and that the data type will be JSON. The data type is determined by a Content-type header. The data is then sent as a JSON string.The SPA version of the application doesn't send form data in the traditional way; instead, it uses JavaScript code retrieved from the server. An event handler is created that generates a new note, adds it to the notes list, re-renders the notes list on the page, and sends the new note to the server. The code determines that the data will be sent with an HTTP POST request and that the data type will be JSON. The data type is determined by a Content-type header. The data is then sent as a JSON string.The SPA version of the application doesn't send form data in the traditional way; instead, it uses JavaScript code retrieved from the server. An event handler is created that generates a new note, adds it to the notes list, re-renders the notes list on the page, and sends the new note to the server. The code determines that the data will be sent with an HTTP POST request and that the data type will be JSON. The data type is determined by a Content-type header. The data is then sent as a JSON string.The SPA version of the application doesn't send form data in the traditional way; instead, it uses JavaScript code retrieved from the server. An event handler is created that generates a new note, adds it to the notes list, re-renders the notes list on the page, and sends the new note to the server. The code determines that the data will be sent with an HTTP POST request and that the data type will be JSON. The data type is determined by a Content-type header. The data is then sent as a JSON string.    
```
