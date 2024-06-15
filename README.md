# part0
Create a sequence diagram depicting the situation where the user creates a new note on the page https://studies.cs.helsinki.fi/exampleapp/notes by writing something into the text field and clicking the Save button.

```mermaid
sequenceDiagram
  participant Browser
  participant Server
  
  Browser->>Server: Request POST https://studies.cs.helsinki.fi/exampleapp/new_note
  activate Server
  Server-->>Browser: HTML document new_note
  deactivate Server
  
  Browser->>Server: Request GET https://studies.cs.helsinki.fi/exampleapp/notes
  activate Server
  Server-->>Browser: HTML document notes
  deactivate Server
  
  Browser->>Server: Request GET https://studies.cs.helsinki.fi/exampleapp/main.css
  activate Server
  Server-->>Browser: CSS file main.css
  deactivate Server
  
  Browser->>Server: Request GET https://studies.cs.helsinki.fi/exampleapp/main.js
  activate Server
  Server-->>Browser: JavaScript file main.js and Browser starts running JS script
  deactivate Server
  
  Browser->>Server: Request GET https://studies.cs.helsinki.fi/exampleapp/data.json
  activate Server
  Server-->>Browser:  [{ "content": "", "date": "2024-06-15" }, ... ] and Browser executes callback function that renders the notes
  deactivate Server
```
Create a diagram depicting the situation where the user goes to the single-page app version of the notes app at https://studies.cs.helsinki.fi/exampleapp/spa.

```mermaid
sequenceDiagram
  participant Browser
  participant Server
  
  Browser->>Server: Request GET https://studies.cs.helsinki.fi/exampleapp/spa
  activate Server
  Server-->>Browser: HTML document spa
  deactivate Server
  
  Browser->>Server: Request GET https://studies.cs.helsinki.fi/exampleapp/main.css
  activate Server
  Server-->>Browser: CSS file main.css
  deactivate Server
  
  Browser->>Server: Request GET https://studies.cs.helsinki.fi/exampleapp/spa.js
  activate Server
  Server-->>Browser: JavaScript file main.js and Browser starts running JS script
  deactivate Server
  
  Browser->>Server: Request GET https://studies.cs.helsinki.fi/exampleapp/data.json
  activate Server
  Server-->>Browser:  [{ "content": "", "date": "2024-06-15T10:45:40.012Z" }, ... ] and Browser executes callback function that renders the notes
  deactivate Server
```

Create a diagram depicting the situation where the user creates a new note using the single-page version of the app.
```mermaid
sequenceDiagram
  participant Browser
  participant Server

  Browser->>Server: Request POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
  activate Server
  Server-->>Browser: { "content": "helliijhjjdodo", "date": "2024-06-15T20:10:56.214Z"} and Browser runs js code to parse json data and populate it in the notes list
```
