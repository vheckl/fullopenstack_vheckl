sequenceDiagram
    participant browser
    participant server

    Note right of browser: User writes a note and clicks Save

    Note right of browser: JS prevents default form submission and renders the note immediately using DOM-API

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    Note right of server: Server saves the new note
    server-->>browser: 201 Created
    deactivate server

    Note right of browser: No redirect — browser stays on the same page
