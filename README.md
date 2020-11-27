# Overwatcher
A simple app for sending telegram notification on completion of a long-running command.
## Setting up
Install package:
```shell script
pip install overwatcher
```
Setup environment variables (at least two required):
```shell script
export OVERWATCHER_TOKEN=...
export OVERWATCHER_CHAT=...
```
The former should contain token of a telegram bot which could be obtained from `@BotFather`, the latter can be requested from `@chatid_echo_bot`. 
Other env variables are not necessary:
```shell script
export OVERWATCHER_BASE_FILE_PATH=... # base filepath from which to start searching mentioned files (default value is /home)
export OVERWATCHER_N_FILES=... # the number of last files from the log to push (default value is 3)
export OVERWATCHER_N_LINES=... # the number of lines from command output to forward (default value is 20)
export OVERWATCHER_MAX_LINE_LENGTH=... # max number of characters on a single line (default value is 100)
```
## Usage
Example:
```shell script
python -m overwatcher notify "ls -alh && sleep 10"
```
Response is sent to a telegram chat:
```shell script
Command echo nice is completed in 0.003 seconds. Result:
nice
```
