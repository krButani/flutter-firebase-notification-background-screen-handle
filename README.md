# flutter-firebase-notification-background-screen-handle


1 If you want to navigate without context use a GlobalKey.

Define a Globalkey //not inside any class

```
final GlobalKey<NavigatorState> navigatorKey = GlobalKey<NavigatorState>();
```

and inside your MaterialAppWidget()

```
MaterialApp(
       navigatorKey: navigatorKey,
...
);
```

From firebase you'll receive some data in _firebaseMessagingBackgroundHandler(){} based on that data you can navigate to any screen.

//if you are creating a notification using that data then put required data in payload of that notification. so you can receive that payload when you tap on that notification that will help you to navigate to a specific screen.

so navigate without context like this.

```
navigatorKey.currentState
        ?.pushNamed(AnotherScreen.routeName);
```

if you want to pass arguments

```
navigatorKey.currentState
        ?.pushNamed(IOSNotificationIntentScreen.routeName, arguments: {
      "arg1": "hello arg 1",
      "arg2": "hello arg 2",
    });
```


[Visit More](https://stackoverflow.com/questions/77314116/how-to-open-a-specific-page-within-pageview-of-flutter-when-a-push-notification)
