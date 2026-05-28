# Confirm Continue 
A posix compatible shell script to ask boolean questions in a [Y/n] style. 

# Features
1. Ubuntu / Debian Style confirmation with default option capitalized
2. Default Option Selection
3. Invoke Scripts according to Y / N or cancel
2. Quiet Mode for automatic default selection
3. Customizable Confirmation messages
4. Ready for automated testing

# Parameters

| Parameter | Description | Example |
|---|---|---|
| `-y` | Set default answer to yes. Pressing Enter confirms. | `confirm_continue -y` |
| `-n` | Set default answer to no. Pressing Enter aborts. | `confirm_continue -n` |
| `-q` | Quiet mode — skips prompt and auto-applies the default. Activates automatically when no TTY is available. | `confirm_continue -q` |
| `-t <seconds>` | Timeout in seconds. Timer pauses when the user starts typing. Aborts on expiry. | `confirm_continue -t 30` |
| `-startmsg=<text>` | Message printed before the prompt. Defaults to `Do you want to continue? [Y/n]` or `[y/N]` depending on default. | `confirm_continue -startmsg="About to delete all files."` |
| `-endmsg=<text>` | Message printed after a successful yes. Not printed on no or timeout. | `confirm_continue -endmsg="Deployment complete."` |
| `msg_yes=<text>` | Message printed on confirmation. | `confirm_continue msg_yes="Starting backup..."` |
| `msg_no=<text>` | Message printed on rejection. | `confirm_continue msg_no="Backup cancelled."` |
| `msg_timeout=<text>` | Message printed when the timer expires. | `confirm_continue -t 10 msg_timeout="No response. Skipping."` |
| `msg_invalid=<text>` | Message printed when the input is not recognised. | `confirm_continue msg_invalid="Please type y or n."` |
| `on_yes=<cmd>` | Function or command called on confirmation. Return code propagates to caller. | `confirm_continue on_yes=deploy` |
| `on_no=<cmd>` | Function or command called on rejection or timeout. Return code propagates to caller. | `confirm_continue on_no=rollback` |
| `CONFIRM_TTY=<path>` | Environment variable overriding `/dev/tty`. Used for automated testing. | `CONFIRM_TTY="$tmp" confirm_continue` |
