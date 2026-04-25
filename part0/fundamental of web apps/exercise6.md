sequenceDiagram
    participant browser
    participant server

    Note right of browser: User writes a note and clicks "Save"

    Note right of browser: JS handles the event (no page reload)

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    Note right of server: Server stores the new note
    server-->>browser: JSON response (created note)
    deactivate server

    Note right of browser: Browser updates UI using JS

    Note right of browser: New note is added to the list without reloading the page