1 - authentication screen mockups
=================================

![Authentication-flow](/flow.png)

Functional stories
------------------

All screens have a Help tooltip that provides information on the screen.

### 1.1 - Login Picker

- User launches app and lands on *1.1 Login Picker* screen, the screen checks
  if the user is logged in and sends the user onto other pages or stays active
- User pushes Email login button and is taken to the *1.3 E-mail login* screen
- User pushes G+ or Facebook Login and *OAuth authentication flow* is activated

Mockup:

    +-----------------------+
    | (SN) SincroNET        |
    |                       |
    | Sign in with          |
    | +-------------------+ |
    | | Google Plus       | |
    | +-------------------+ |
    | +-------------------+ |
    | | Facebook          | |
    | +-------------------+ |
    | +-------------------+ |
    | | Email             | |
    | +-------------------+ |
    |  Register       Help  |
    +-----------------------+

1.2 - Registration
------------------

- User lands in *1.2 registration* screen, screen stays active waiting for user
  input
- User picks G+ or Facebook registration and *OAuth Registration flow* is
  started

  or

- User fills in e-mail and pushes register button, screen checks for existing
  account, and sends user to *1.8 Email Registration with account registered*

Mockup:

    +-----------------------+
    | (SN) SincroNET        |
    |                       |
    | +-----+  +----------+ |
    | | G+  |  | Facebook | |
    | +-----+  +----------+ |
    |    or use e-mail      |
    | +-------------------+ |
    | | me@example.com    | |
    | +-------------------+ |
    | +-------------------+ |
    | | Register          | |
    | +-------------------+ |
    |                 Help  |
    +-----------------------+

1.3 - Email Login
-----------------

- User lands in *1.3 E-mail login* and screen stays active waiting for user
- User fills in e-mail address and password pushes login
- Screen *Checks Login* with server and either:
- Screen sends user to *Authenticated State*

  or

- Screen Sends user to *1.4 Email Login on Failed login* screen

Mockup:

    +-----------------------+
    | (SN) SincroNET        |
    |                       |
    | Enter your e-mail     |
    | and password          |
    | +-------------------+ |
    | | me@example.com    | |
    | +-------------------+ |
    | +-------------------+ |
    | | Password          | |
    | +-------------------+ |
    | +-------------------+ |
    | | Login             | |
    | +-------------------+ |
    |  Register       Help  |
    +-----------------------+

1.4 - Email Login on Failed login
---------------------------------

- User lands on *1.4 Email Login on Failed login* screen and screen waits for
  user input
- User tries again and login is checked once more.
- User choses to recover password and is taken to *1.5 Password Recovery*
  screen

Mockup:

    +-----------------------+
    | (SN) SincroNET        |
    |                       |
    | Enter your e-mail     |
    | and password          |
    | +-------------------+ |
    | | me@example.com    | |
    | +-------------------+ |
    | +-------------------+ |
    | | Password          | |
    | +-------------------+ |
    | Authentication failed |
    | Recover password      |
    | +-------------------+ |
    | | Login             | |
    | +-------------------+ |
    |  Register       Help  |
    +-----------------------+

1.5 - Password Recovery
-----------------------

- User lands in *1.5 Password Recovery*, screen waits for input
- User fills in e-mail address and pushes Recover password button, screen
  sends RPC request to *Send Recovery Link*, fires a *notification about link*
  and kills the application

  or

- User pushes Register link and is taken to *1.2 Registration* screen

Mockup:

    +-----------------------+
    | (SN) SincroNET        |
    |                       |
    | Enter your e-mail     |
    | +-------------------+ |
    | | me@example.com    | |
    | +-------------------+ |
    | +-------------------+ |
    | | Recover password  | |
    | +-------------------+ |
    |  Register       Help  |
    +-----------------------+

1.6 - Set Password
------------------

- User lands in *1.6 Set password* screen, screen waits for input
- User enters password and password confirmation and pushes set password.
- Screen checks passwords match fires  *RPC for setting password on server*
  and takes user to *1.3 Email login* screen

Mockup:

    +-----------------------+
    | (SN) SincroNET        |
    |                       |
    | Enter password twice  |
    | +-------------------+ |
    | | Password          | |
    | +-------------------+ |
    | +-------------------+ |
    | | Password          | |
    | +-------------------+ |
    | +-------------------+ |
    | | Set password      | |
    | +-------------------+ |
    |                 Help  |
    +-----------------------+

1.7 - Email Registration
------------------------

- User lands in *1.7 Email Registration* and screen waits for input.
- User fills in e-mail address and pushes register button, screen fires
  RPC for *Check if email is registered* and either:

- User is taken to *1.8 Email Registration with account registered* screen

  or

- Server has updated application about registration link and screen sends
  fires off *notification about registration link* and exits application.

Mockup:

    +-----------------------+
    | (SN) SincroNET        |
    |                       |
    | Enter your e-mail     |
    | +-------------------+ |
    | | me@example.com    | |
    | +-------------------+ |
    | +-------------------+ |
    | | Register          | |
    | +-------------------+ |
    |                 Help  |
    +-----------------------+

1.8 - Email Registration with account registered
------------------------------------------------

- User lands in *1.8 Email Registration with account registered* and screen
  waits for user input. Either:
- User fills in password and pushes login button, screen fires RPC for
  *Check login*

  or

- User pushes recover button, screen fires RPC for *Send recovery link* and
  fires a *notification for recovery email sent* application terminates

Mockup:

    +-----------------------+
    | (SN) SincroNET        |
    |                       |
    |  Account for          |
    |  me@example.com       |
    |  already exists!      |
    |                       |
    |  Enter the password   |
    | +-------------------+ |
    | | Password          | |
    | +-------------------+ |
    | +-------------------+ |
    | | Login             | |
    | +-------------------+ |
    |  or                   |
    | +-------------------+ |
    | | Recover           | |
    | +-------------------+ |
    |                 Help  |
    +-----------------------+
