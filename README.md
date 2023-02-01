# streaming-03-rabbitmq

Get started with RabbitMQ, a message broker, that enables multiple processes to communicate reliably through an intermediary

## Before You Begin

1. Fork this starter repo into your GitHub.
1. Clone your repo down to your machine.
1. In VS Code with Python extension, click on emit_message_v1.py to get VS Code in Python mode.
1. View / Command Palette - then Python: Select Interpreter
1. Select your conda environment. See the references below for more.
1. Use the terminal to install pika into your active environment. 

`conda install -c conda-forge pika`

## Read

1. Read the [RabbitMQ Tutorial - Hello, World!](https://www.rabbitmq.com/tutorials/tutorial-one-python.html)
1. Read the code and comments in this repo.
    -->I tried recreating that code and running, but ran into errors regarding the declaration of "channel" 

## Execute about,py

1. Run about.py.
1. Read about.txt. 
1. Verfiy you have exactly one active, one None env.

## Version 1 - Execute the Producer/Sender

1. Read v1_emit_message.py (and the tutorial)
1. Run the file. 

You'll need to fix an error in the program to get it to run.
Once it runs and finishes, we can reuse the terminal.

## Version 1 - Execute the Consumer/Listener

1. Read v1_listen_for_messages.py (and the tutorial)
1. Run the file.

You'll need to fix an error in the program to get it to run. --> Yes had to fix the spelling of localhost.
Once it runs successfully, will it terminate on its own? How do you know?  --> I thought it had termined on it's own because it printed 'Hellow World!'; however, there was no close to the program in the code. When ctrl+c was pressed, then saw a message "interrupted" which indicated it was now completed due to manual intervention.

As long as the process is running, we cannot use this terminal for other commands. --> Correct - would need to open another terminal to feed additional information to the same queue. 

## Version 1 - Open a New Terminal / Emit More Messages

1. Open a new terminal window.
1. Use this new window to emit more messages
1. In v1_emit_message.py, modify the message. 
1. Execute the script. 
1. Watch what happens in the listening window.
1. Do this several times to emit at least 3 different messages.

## Version 1: Don't Repeat Yourself (DRY)

1. Did you notice you had to change the message in two places? --> Yes
    1. You update the actual message sent. 
    1. You also update what is displayed to the user. --> Hello Earth, Hello Mars, Hello Jupiter were the three messages.
1. Fix this by introducting a variable to hold the message. 
    1. Use your variable when sending.  --> created a variable called message and called it when declaring the body within the channel and when printing the message.
    1. Use the variable again when displaying to the user. --> used the variable in the print message

To send a new message, you'll only make one change.
Updating and improving code is called 'refactoring'. 
Use your skills to keep coding enjoyable. 

## Version 2

Now look at the second version of each file.
These include more graceful error handling,
and a consistent, reusable approach to building code.

Each of the version 2 programs include an error as well. --> fixed lllocalhost - but ran it first to read the error code that was generated. The v2_listen code also has a mispelled word, and ran it to find the error which is also a mispelling of localhost. 

1. Find the error and fix it. --> fixed spelling of localhost
1. Compare the structure of the version 2 files.  --> also uses variables. Defined functions and used the try, except two times with a finally block to close the connection.
1. Modify the docstrings on all your files. -->done
1. Include your name and the date. -->done
1. Imports always go at the top, just after the file docstring. --> fixed this on the v1_listen file
1. Imports should be one per line - why? --> not recommended so it is more easily read and understood
1. Then, define your functions. -->blocks of code that can be reused to define variables and send messages
1. Functions are reuable logic blocks.
1. Everything the function needs comes in through the arguments.
1. A function may - or may not - return a value. 
1. When we open a connection, we should close the connection. 
1. Which of the 4 files will always close() the connection? -->The sender (emit) closes the connection. The listener remains open until Ctrl+C is entered by user.
1. Search GitHub for if __name__ == "__main__": 
1. How many hits did you get? --> >15 Million
1. Learn and understand this common Python idiom. -->Found an article here: https://github.com/abhisheku1/C-Python/blob/f0a680007f345a46bcd187b952a929c7068c1da8/Doc/library/__main__.rst#id3

## Reference

- [RabbitMQ Tutorial - Hello, World!](https://www.rabbitmq.com/tutorials/tutorial-one-python.html)
- [Using Python environments in VS Code](https://code.visualstudio.com/docs/python/environments)

## Multiple Terminals
Screenshot 2023-01-31 193851 v2_exercise.jpg

Also ran through additional send.py/receive.py exercises and the v1 terminal
Screenshot 2023-01-31 193431 v1_exercise.jpg
Screenshot 2023-01-31 193217.jpg

