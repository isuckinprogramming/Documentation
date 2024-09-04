# Networking 2 Final Project

Application for Real Time Messaging between different users accross the network. As part of the final requirement of Networking 2.

## Process when user enters the application

Flow of Overall Process of using Real Time Messaging Application  
::: mermaid
graph TD;
  user --> enter-application[User Lands in home page of real time messaging application]
  
  enter-application --> homepage{choose actions}

  homepage --> |User is not registered| register[user registration to application]
  homepage --> |User has registered account| log-in[user log-in with account]

  log-in --> messaging-app[User can use application]
  register --> messaging-app

  messaging-app --> stop-using-app{User Stops using Application}

  stop-using-app --> |user chooses to log out account| log-out[User log out of the application]

  stop-using-app --> |user closes tab or browser, or unexpectedly close browser| web-browser-close[User Closes Web Browser or Unexpectedly quits]

:::

## User Actions in Real Time Messaging Application

::: mermaid 
graph TD;
  User --> message
  message --> continue[continue chat]
  message --> start-new[start new chat with other users]

  continue --> single-user[single user chat]
  continue --> group-message[multiple user chat room]

  start-new --> find-users[search for user name or contact]
  find-users --> single-user 
  find-users --> create-group-chat[find multiple users to create a group chat room]
  create-group-chat --> group-message

  User --> manage-chats[Management of Chats]
  manage-chats --> terminate-contact[remove user contact in chat room]
  
  manage-chats --> reconnect[User regains connection to chat room]

  reconnect --> |If user has previously terminated contact| single-user-2[single user chat]
  reconnect --> |If user has previously terminated contact| group-message-2[multiple user chat room]

  single-user-2 --> reconnect-done[establish connection with chat - allow user to send messages and receive new messages]
  group-message-2 --> reconnect-done

  terminate-contact --> single-user-3[single user chat]
  terminate-contact --> group-message-3[multiple user chat room]

  User --> logout[User Log out of 
  
  Application]

:::