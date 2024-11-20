# Linux Keylogger

A simple keylogger written in Python for Linux systems. This project demonstrates how to capture and log keyboard events using the `pyxhook` library.  

## Overview

The keylogger captures all key presses and saves them to a specified log file. This project is intended for educational purposes to learn about how keyboard events can be intercepted on Linux systems.

> ⚠️ **Disclaimer**: This keylogger is for educational purposes only. Unauthorized use of keyloggers is illegal and unethical. Always ensure you have proper permissions before using such software.

## Features

- Captures keyboard events on Linux systems.
- Saves key presses to a log file.
- Configurable log file location through environment variables.
- Option to clear the log file at startup.
- Customizable cancellation key to stop the keylogger.

## Technologies Used

- **Python**: The main programming language used for this project.
- **pyxhook**: A Python library to interact with the X server for capturing keyboard events on Linux.

## How It Works

1. The script uses `pyxhook` to create a keyboard hook that listens for keypress events.
2. When a key is pressed, the `OnKeyPress` function is triggered, which logs the key to the specified file.
3. Environment variables allow configuration of:
   - Log file location (`pylogger_file`).
   - Cancellation key (`pylogger_cancel`).
   - Whether to clear the log file at startup (`pylogger_clean`).

## Setup and Usage

### Prerequisites
- A Linux-based system.
- Python 3 installed on your machine.
- `pyxhook` library installed. You can install it using `pip`:
  ```bash
  pip install pyxhook
  ```

### Running the Keylogger
1. Clone this repository to your local machine:
   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```
2. Configure optional environment variables:
   - `pylogger_file`: Path to the log file.
   - `pylogger_cancel`: Key to cancel the keylogger (default: `` ` ``).
   - `pylogger_clean`: If defined, clears the log file at startup.
   
   Example:
   ```bash
   export pylogger_file=~/Desktop/log.txt
   export pylogger_cancel=~
   export pylogger_clean=1
   ```

3. Run the script:
   ```bash
   python keylogger.py
   ```

4. Stop the keylogger by pressing the cancel key (default: `` ` ``).

### Log File
The default log file location is `~/pythonprojects/keylogger/file.log`. You can change this by setting the `pylogger_file` environment variable.

### Handling Errors
If an error occurs, it will be logged in the same log file for later analysis.

## Customization

- **Log File Location**: Change the environment variable `pylogger_file` to specify a different path for the log file.
- **Cancel Key**: Customize the cancel key by setting `pylogger_cancel` to a different key (e.g., `~` or `ESC`).
- **Clear Log File**: To start with a fresh log file, set the `pylogger_clean` environment variable before running the script.

## Example Output
Here is an example of a log file:
```
a
b
c
Enter
Shift_L
```

## Contributing
Contributions are welcome! Feel free to fork this repository and submit a pull request with any improvements or additional features.

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.
