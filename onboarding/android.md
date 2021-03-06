## Installation

Update your `app/build.gradle` to include the following `compile` call:
```
compile('com.rollbar:rollbar-android:1.0.0@aar'){transitive=true}
```

## Initialization

Make sure to add the following permissions to your `AndroidManifest.xml`:
```xml
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```



Import `com.rollbar.android.Rollbar` and call `Rollbar.init()` in `onCreate()`:
``` java
import com.rollbar.android.Rollbar;

public class MainActivity extends Activity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        Rollbar.init(this, "{{ client_access_token }}", "development");
        // Rest of onCreate() method ....
    }
}
```

## Send Test Data

Add the following anywhere in your application after the `init()` call to send test data:
``` java
Rollbar rollbar = Rollbar.instance();
rollbar.error(new Exception("This is a test error"));      
```

## Further configuration

For additional configuration information, see the documentation for the <a href="https://rollbar.com/docs/notifier/rollbar-android " target="_blank" rel="noopener">rollbar-android</a> SDK.
