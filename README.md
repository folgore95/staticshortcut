# Static Shortcut Example
<img src="https://github.com/folgore95/media/blob/master/staticshortcut.png"/>

## About

This app is a demonstration of google's static app shortcuts, which were introduced with API 25 and Android Nougat 7.1.

## How can i add a static shortcut?

In your app manifest, `AndroidManifest.xml` add these lines:

```xml
<meta-data
                android:name="android.app.shortcuts"
                android:resource="@xml/shortcuts"/>

```

You can look at my <a href="https://github.com/folgore95/staticshortcut/blob/master/app/src/main/AndroidManifest.xml">AndroidManifest</a>, if you need an example.

After you have added these lines, simply create in `res` path a new folder `xml`. Here create an xml file called `shortcuts`. Copy and paste these lines and adapt them for your own app.

```xml
<?xml version="1.0" encoding="utf-8"?>
<shortcuts xmlns:tools="http://schemas.android.com/tools"
    xmlns:android="http://schemas.android.com/apk/res/android">

    <shortcut
        android:icon="@drawable/ic_shortcut"
        android:enabled="true"
        android:shortcutId="static-shortcut-1"
        android:shortcutShortLabel="@string/static_shortcut_message"
        android:shortcutLongLabel="@string/static_shortcut_message"
        tools:targetApi="n_mr1">

        <intent
            android:targetPackage="it.gosha98.shortcut"
            android:action="android.intent.action.VIEW"
            android:targetClass="it.gosha98.shortcut.MainActivity"
            android:data="http://example.com/data" />

        <!-- You can find more categories here https://developer.android.com/guide/topics/ui/shortcuts.html -->
        <categories android:name="android.shortcut.conversation" />

    </shortcut>

</shortcuts>
```

You can find an example <a href="https://github.com/folgore95/staticshortcut/blob/master/app/src/main/res/xml/shortcuts.xml">here.</a>

Then you need to go into `res/values/strings.xml` and add this string:

```xml
<string name="static_shortcut_message">Example of shortcut</string>


