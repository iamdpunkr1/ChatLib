---
{"dg-publish":true,"permalink":"/backend/"}
---


# Introduction
The backend is built using Node.js with Express, Redis, and MongoDB or MySQL.

### Prerequisites
- Node.js (version 14.x or higher)
- npm (version 6.x or higher) or yarn
- MongoDB (local or Atlas)
- MySQL
- Redis

### Installation
```
git clone https://github.com/iamdpunkr1/chat-app

%% For MongodDB %%
cd backend

%% For MySQL %%
cd  backend_mySQL

npm install
```


### Running the Backend
In the `backend` directory:
1. Open the terminal and run the command `npx tsc`. This will create a `dist` folder containing all the compiled files.
2. Copy the `.env` file to the `dist` folder.
3. Copy the entire backend folder to the server or use `git pull` if the code is updated in GitHub.
4. (Optional) Depending on the server and the type of deployment, run the `NAME.service` file. Note: use Node version `16.20.2` or above.

### Environment Variables (MongoDB)
Create a `.env` file in the `backend` directory and add the following variables:
```
EMAIL_PASSWORD=your-gmail-app-password
EMAIL_ID=your-email
DB=chats
USERS_COLLECTION=users
CHAT_COLLECTION=chat-details
MONGO_URI=your-mongodb-uri
ACCESS_TOKEN_SECRET=your-accesstoken-secret-key
ACCESS_TOKEN_EXPIRY=1h
REFRESH_TOKEN_SECRET=your-refreshtoken-secret-key
REFRESH_TOKEN_EXPIRY=12h
SOCKET_AUTH_CODE=your-secret-code-distinguishing-between-users-and-agents
FILE_URL="your-path-to-the-stored-files"
PORT=5005
```

### Environment Variables (MySQL)
Create a `.env` file in the `backend` directory and add the following variables:
```
EMAIL_PASSWORD=your-gmail-app-password
EMAIL_ID=your-email
DB_HOST=your-hosted-mysql-url
DB_USER=mysql-user-id
DB_PASSWORD=mysql-user-password
DB_NAME=chatpp
ACCESS_TOKEN_SECRET=your-accesstoken-secret-key
ACCESS_TOKEN_EXPIRY=1h
REFRESH_TOKEN_SECRET=your-refreshtoken-secret-key
REFRESH_TOKEN_EXPIRY=12h
SOCKET_AUTH_CODE=your-secret-code-distinguishing-between-users-and-agents
FILE_URL="your-path-to-the-stored-files"
PORT=5005
```

### API Endpoints
The backend provides the following API endpoints:

- `POST /api/user/login` - User login.
- `POST /api/admin/login` - Agent/Admin login.
- `POST /api/admin/register` - New Agent/Admin registration.
- `GET /api/logout` - User/Admin logout.
- `POST /api/refresh-token` - Refresh access token.
- `POST /api/send-transcript` - Send chat transcript.
- `POST /api/upload` - Upload files.
- `GET /api/logs` - Check console logs of the file.