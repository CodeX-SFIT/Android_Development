# Binding the UI With the Code

After Making any great User-Interface with the layout Editor and manually editing the xml to your liking, its now time to link it to the code that actually does something with that UI and displays meaningful Info

Before we jump in and start Writing code there are a few basic essential things to understand in 

- Activities
- oncreate() method inside Activities
- setContentView inside onCreate()
- linking components in the layout to variables in java file

Basically we are just Analyzing the code below for what it does actually
```java 
public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

```

## What is a Activity
The Activity class is a crucial component of an Android app, and the way activities are launched and put together is a fundamental part of the platform's application model. Unlike programming paradigms in which apps are launched with a ```main()``` method, the Android system initiates code in an Activity instance by invoking specific callback methods that correspond to specific stages of its lifecycle.

To declare your activity, open your manifest file and add an
```<activity>``` element as a child of the ```<application>``` element.

For example:
```xml
<manifest>
...
  <application>
      <activity android:name=".ExampleActivity">
      ...
      </activity>
    ...
  </application>
...
</manifest>
```


## OnCreate Method
Over the course of its lifetime, an activity goes through a number of states. You use a series of callbacks to handle transitions between states.

onCreate()
You must implement this callback, which fires when the system creates your activity. Your implementation should initialize the essential components of your activity: 

For example, your app should create views and bind data to lists here. Most importantly, this is where you must call ```setContentView()``` to define the layout for the activity's user interface.

```java
@Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
    }
```

## ```setContentView()```
when the activity is starting. This is where most initialization should go: calling ```setContentView(int)``` to inflate the activity's UI, using ```findViewById(int)``` to programmatically interact with widgets (Buttons, EditText,etc..) in the UI
```java
@Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
```

## ```findViewById()```

Finds a view that was identified by the android:id XML attribute
and retrieve the widgets in that UI that you need to interact with programmatically.

findViewById connects your backend code with the User Interface elements, layouts, buttons, etc. Every component in the user interface has an ID associated with it, which allows you to control its actions from backend. Just pass the Id in the findViewById function and store what it returns in another variable in your code. And you can now control it accordingly.

for Example
```java
@Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        EditText editText = (EditText) findView ById(R.id.idFromXML);

    }
```

