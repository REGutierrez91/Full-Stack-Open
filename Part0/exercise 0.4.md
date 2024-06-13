```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server

    Note over browser: The browser sends the user's input <br/> "Full Stack Open 0.4" to the server

    server-->>browser: HTML document
    deactivate server

    Note over browser: The server send an URL redirection <br/> requesting the browser to make <br/> a new HTTP GET to "/notes"

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: main.css
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: main.js
    deactivate server

    Note over browser: The browser starts executing <br/> the JavaScript code that <br/> fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "Full Stack Open 0.4", "date": "2024-6-12" }, ... ]
    deactivate server

    Note over browser: The browser executes the callback <br/> function that renders the notes <br/> with the new item added









```
