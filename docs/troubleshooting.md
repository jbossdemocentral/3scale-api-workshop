# Troubleshooting

This document will help you check for common issues, and how to avoid them. We've provided some troubleshooting tips based on issues users have seen. Please open an issue if you need help troubleshooting and it is not covered here.

## Check for common issues

* Double-check you don't have **typos** (typographical error, mistake when typing) in your fields, files, or repository branches and tag names.

## Installation Troubleshooting

> TODO

## Lab 01

### Know Networking Issue (Timeout)

There is a timeout when using the Apicurio Studio after a couple minutes of being working in the tool. Looks like after some minutes of idle time the websocket connection from the graphical user interface to the websocket API times out. There is no reconnect function in the Studio to recover the connection.

**Workaround:** Refresh your browser tab/window, don't worry everything was saved up to the time out and should be recovered after the GUI refresh.

## Lab 02

### Too Many Connections

In this lab, if there is a lot of concurrent users working at the same time you might find an error when trying to query the Location API Service. If you checked the log of the pod, might find the following error: *Too Many Connections*.

**Workaround:** Kill the MySQL pod in the International Inc namespace. This will release all the pending connections and allow the clients to reconnect. Also you will need to kill your service pod to create a new one.

### Accessing the service URL shows empty screen

The provided API does not have a mapping for `/` (root) path. 

**Workaround:** Try using `/locations` to test.

## Lab 06

Most of the problems you find in this lab can be discovered and analyzed using the included browser developer tools. Check this links on how to enable the tools for [Chrome](https://developers.google.com/web/tools/chrome-devtools/) and [FireFox](https://developer.mozilla.org/en-US/docs/Tools/Tools_Toolbox).

### Invalid redirect uri

You will receive this error from Red Hat Single Sign On if you didn't register or mistyped the *Valid redirect uri* when editing the application in RH SSO.

**Fix:** Check the value of in Red Hat Single Sign On under *Clients* and your client id. Also be sure it includes `/*` a the end of your URI.

### Red Hat Single Sign On CORS error

If you didn't specify the *Valid origins* to call your SSO endpoint you will get a CORS error.

**Fix:** Be sure to add `*` (star) under *Web Origins* in the client application configuration in Red Hat Single Sign On.

### CORS error in Browser

You will see this error when doing the pre-flight check for the Ajax call.

**Fix:**

1. Be sure you followed the steps to add the policies in *Lab 03*. If not, you will need to enable the CORS policy in your APIs 3scale integration page.

1. This error in FireFox can also be related to the self signed certificate. Check the next issue fix on how to correct this problem. 

### NET::ERR\_CERT\_AUTHORITY\_INVALID

If using Chrome, you will see this error when trying to call the backend service.

**Fix:** Be sure to accept the self-signed certificate from the API gateway. Copy the 3scale endpoint url and paste it in another browser tab/window to naviage to it. Accept/Add Exception of the self-signed certificate.

## Something else doesn't work

Ask around on the sme-apis list, or create an issue.

If you figure it out, edit this document as a courtesy to the next person having the same problem.