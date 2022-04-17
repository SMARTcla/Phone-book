Write a console helper bot that will recognize commands entered from the keyboard and respond according to the command entered.

The helper bot should become our prototype assistant application. The assistant application, as a first approximation, should be able to work with the contact book and calendar. In this homework, we will focus on the interface of the bot itself. The simplest and most convenient interface at the initial stage of development is the CLI (Command Line Interface) console application. The CLI is fairly easy to implement. Any CLI consists of three main elements:

Command parser. The part that is responsible for parsing the strings entered by the user, extracting keywords and command modifiers from the string.
Command handler functions are a set of functions that are also called handler, they are responsible for the direct execution of commands.
Request-response cycle. This part of the application is responsible for receiving data from the user and returning the response from the handler function to the user.
At the first stage, our assistant bot must be able to save the name and phone number, find the phone number by name, change the recorded phone number, display all the records that it has saved to the console. To implement such simple logic, we will use a dictionary. In the dictionary, we will store the username as the key and the phone number as the value.

Conditions#
The bot should be in an infinite loop, waiting for the user's command.
The bot ends its work if it encounters the words: .
The bot is not case sensitive to the input commands.
The bot accepts commands:
"hello", replies to the console "How can I help you?"
"add...". By this command, the bot saves a new contact in memory (in a dictionary, for example). Instead of ..., the user enters a name and phone number, necessarily separated by a space.
"change ..." With this command, the bot saves a new phone number for an existing contact in memory. Instead of ..., the user enters a name and phone number, necessarily separated by a space.
"phone ...." By this command, the bot displays the phone number for the specified contact in the console. Instead of ..., the user enters the name of the contact whose number is to be shown.
"show all". By this command, the bot displays all saved contacts with phone numbers to the console.
"good bye", "close", "exit" for any of these commands, the bot ends its robot after it displays "Good bye!" in the console.
All user input errors must be handled with the input_error decorator. This decorator is responsible for returning messages like "Enter user name", "Give me name and phone please", etc. to the user. The input_error decorator should handle exceptions that occur in handler functions (KeyError, ValueError, IndexError) and return an appropriate response to the user.
The command logic is implemented in separate functions, and these functions take one or more strings as input and return a string.
All user interaction logic is implemented in the main function, all print and input occur only there.
