# Troubleshooting

This document will help you check for common issues, and how to avoid them. We've provided some troubleshooting tips based on issues users have seen. Please open an issue if you need help troubleshooting and it is not covered here.

## Check for common issues

* Double-check you don't have **typos** (typographical error, mistake when typing) in your fields, files, or repository branches and tag names.

## Installation Troubleshooting

> TODO

## Lab 01

### Know Networking Issue (Timeout)

There is a timeout when using the Apicurio Studio after a couple minutes of being working in the tool. Looks like after some minutes of idle time the websocket connection from the graphical user interface to the websocket API times out. There is no reconnect function in the Studio to recover the connection.

**Workaround:** Refresh your browser tab/window, don't worry everything was saved up to the time out and should be recovered after the GUI refresh.

## Something else doesn't work

Ask around on the sme-apis list, or create an issue.

If you figure it out, edit this document as a courtesy to the next person having the same problem.