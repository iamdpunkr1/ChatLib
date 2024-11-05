---
{"dg-publish":true,"permalink":"/frontend/"}
---


## Installation
## Agent Panel installation

```sh
     cd frontend
     npm install
     ```

### Icon and Title
To update the icon, title, and other metadata of the application, go to the `./src/config.tsx` file in the frontend folder and make the necessary changes.

### Deployment
To deploy the frontend , follow these steps:

1. Set the `baseUrl` of the frontend project. For example, if the base URL is `https://www.alegralabs.com/PATH_TO_FOLDER`, then the `baseUrl` will be `PATH_TO_FOLDER`.
2. Add `base: "PATH_TO_FOLDER"` in the `vite.config.ts` file and in `./src/config.tsx`, add the basename to the Router tag: `<Router basename='PATH_TO_FOLDER'>`.
3. Open the terminal and run `npm run build` to build the app for production, which will create the `dist` folder.
4. Copy the contents of the `dist` folder to the `PATH_TO_FOLDER` or the desired folder on the server.



## User Panel installation 

### Step 1: Download and Include ChatLib 

In the head tag of your document include the Tailwindcss.
```html
<script src="https://cdn.tailwindcss.com"></script>
```

Add or download ChatLib.js, then include it in your project. Add this script tag at the bottom of the body tag.

```html
<script src="https://cdn.socket.io/4.7.5/socket.io.min.js" integrity="sha384-2huaZvOR9iDzHqslqwpR87isEmrfxqyWOF7hr7BY6KG0+hVKLoEXMPUJw3ynWuhO" crossorigin="anonymous"></script>
<script src="https://alegralabs.com/dipankar/awwards/assets/ChatLib.js"></script>  
```


### Step 2: Initialize ChatLib in Your Web App

Create a JavaScript file or add the following code to your main script file to initialize ChatLib.

```js

<script> 

document.addEventListener('DOMContentLoaded', async () => {  

    const chatLib = new ChatLib({  

        websocketUrl: 'wss://your-websocket-server.com',  

        chat_button_id: 'chat-button', // ID of the chat button element  

        chatTitle: 'Support Chat',  

        chatDescription: 'Chat with our support team.',  

        chatIconUrl: 'https://your-icon-url.com/icon.png',  

        chatIconSize: 50,  

        chatFileTypes: ['image/jpeg', 'image/png', 'image/gif'],  

        chatFileSize: 5 * 1024 * 1024, // Maximum file size in bytes  

        position: 'bottom-right', // Position of chatbox  

        chatPrimaryColor: '#3b82f6', // Primary color for the chat UI  

        chatTextColor: '#fff', // Text color for the chat UI  

    });



    await chatLib.init(); // Initialize and connect the chat  

});  
</script>

```



## Customizing ChatLib

### Options

Pass the following options to customize ChatLib:

| **Option**       | **Description**                        | **Default Value**                        |
| ---------------- | -------------------------------------- | ---------------------------------------- |
| websocketUrl     | WebSocket server URL                   | 'wss://your-websocket-server.com'        |
| chat_button_id   | Button ID for the chat toggle          | null                                     |
| chatTitle        | Chat window title                      | 'ChatApp'                                |
| chatDescription  | Chat window description                | 'Chat description'                       |
| chatIconUrl      | URL for the chat icon                  | 'https://via.placeholder.com/50'         |
| chatIconSize     | Size of the chat icon in pixels        | 50                                       |
| chatFileTypes    | Allowed file types                     | ['image/jpeg', 'image/png', 'image/gif'] |
| chatFileSize     | Maximum file size for uploads in bytes | 2 * 1024 * 1024 (2 MB)                   |
| position         | Position of chat box                   | 'bottom-right'                           |
| chatPrimaryColor | Primary color for chat interface       | '#3b82f6'                                |
| chatTextColor    | Text color for chat interface          | '#fff'                                   |

## Example Usage

To implement ChatLib in your application, call init() after setting up the instance:

```js
const chatLib = new ChatLib({  

    websocketUrl: 'wss://your-websocket-server.com',  

    chat_button_id: 'chat-button',  

    // Other options...  

});  

chatLib.init();
```
