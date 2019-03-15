# rn-059-stacktrace-mess-demo-app
This is a demo React Native application to showcase a stacktrace bug with the debugger on Android

# Steps to reproduce the issue
1. Clone this repo and
2. `yarn install`
3. `yarn start:reset` to clean up all caches and start Metro
4. Connect a physical Android device or start an Android emulator
5. In a new terminal window, run `yarn android` to build and launch the Android app
6. Notice the app has started OK
7. Open the debug menu in the app and select "Debug JS Remotely". This will restart the app in debug mode and connect to a debugger (perhaps Chrome opened for this).
8. Notice how the debugger has stopped to a file, but that file is not the App.js [where the `debugger` statement is](https://github.com/hypest/rn-059-stacktrace-mess-demo-app/blob/8d2d757bb1785899731d647dd1d96b75bf7ddb23/App.js#L23).
9. Notice the debugger console output and verify that the `Before the debugger statement` log is there. That's a log line printed right before the `debugger` statement is encountered, verifying that we are indeed in the App.js file anyway.
