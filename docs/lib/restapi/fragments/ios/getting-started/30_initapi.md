To initialize the Amplify API and Authentication categories, we are required to use the `Amplify.addPlugin()` method for each category we want.  When we are done calling `addPlugin()` on each category, we finish configuring Amplify by calling `Amplify.configure()`.

**Add the following imports** to the top of your `AppDelegate.swift` file:
```swift
import Amplify
import AmplifyPlugins
```

**Add the following code** to your AppDelegate's `application:didFinishLaunchingWithOptions` method:
```swift
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
    do {
        try Amplify.add(plugin: AWSCognitoAuthPlugin())
        try Amplify.add(plugin: AWSAPIPlugin())
        try Amplify.configure()
        print("Amplify configured with API and Auth plugin")
    } catch {
        print("Failed to initialize Amplify with \(error)")
    }

    return true
}
```
Upon building and running this application you should see the following in your console window:

```console
Amplify configured with API and Auth plugin
```