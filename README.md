# TicTacToe Game

## Collaborators
- Anusheel Solanki - 2020B3A70541G (f20200541@goa.bits-pilani.ac.in)
- Nandish Chokshi - 2020B1A72031G (f20202031@goa.bits-pilani.ac.in)

## Version of Android Studio Used
Android Studio Giraffe|2022.3.1 Patch 1

## App Description
This application is a multiplayer Tic Tac Toe game. It uses Android Navigation Component, Firebase, Fragments and various parts of UI. There are two options, log in and sign up respectively. In order to play the game a user needs to enter login id and password. There is also an option to sign up if account has not been created. User stays logged in until he logs out using log out button in app. Next the user gets displayed a dashboard screen in which his username, wins and losses are displayed. It also shows a list of players who are waiting for the second player to join and have created a two player game. There is a floating button that lets the current user create a new one player or two player game by showing an alert dialog. If the user selects the option for single player, then he can play it with the computer. If he selects two player, a new two player game is created. If he presses back button before the result of game is decided, an alert dialog pops up to giving an option to forfeit the game. Some known bugs occur when two users try to open the same game at the same time. Also, it takes some time to fetch data from firebase and therefore the message on the screen gets delayed by some seconds.

---
## Task-1
Firstly, the authentication method is set to email and password from firebase. After, that two buttons are created, log in and sign up respectively. Both the actions are achieved by using the inbuilt authentication functions by firebase. If a user is logged in, it will be shown dashboard directly. This was done by checking whether a current user is present or not at the dashboard fragment. Also, an on click listener is added to the log out button to successfully log out the user. On successful creation, a field is stored in realtime database which stores wins, losses and username of that particular user.

## Task-2
The user now gets navigated to the game fragment using nav controller. Firstly a text view is added to both top and bottom. The text view at the top is the name of the game and the below one is used to show the result. Now, firstly it should be checked whether the game is one player or two player. Now, there are two players, the first one being the user itself and the second player is the computer. We've enabled click listeners for all of the buttons, and we've configured it such that the computer only moves when one of the buttons is pressed. We constantly wait for the user to make the first move and go first. The computer takes a turn as soon as the user moves. To determine its turn, the computer utilises a random function. We created the checkResult() function to determine if the user or the machine is the winner. We display a text that states WIN or LOSE as soon as the user wins or loses. The back button returns us to the dashboard component, which now displays the total wins and losses.

## Task-3
The player can create a two player game by selecting the two player option. Here we open the game fragment with a string as an argument in the nav graph that represents the Id of the first player who created the game. User can also open a multiplayer game by clicking on one of the available games in the dashboard. For implementing this we have made a new child for the firebase database that has all available online games. We extract data from this database for every other user and display it in the dashboard using recycler view. There is a string which stores the current state of the game and that is displayed on both the screen. The game in firebase stores the value of player1, player2, gameState and gameResult respectively. When we are in the Two Player game, the creator is notified by a toast that the second user is ready to play. Now if we press the back button for both the users we remove that game from database so that it is not seen further. The same alert dialog is used which was used in one player mode that pops to ask for forfeit or returning back to game.

---
## Time Taken to develop the app
- Approximately 50-60 hours were spent on developing the app.
---
