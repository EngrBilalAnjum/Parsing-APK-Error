# Parsing-APK-Error
"There is a problem parsing the package"
If you face the above error on Testing APK, below is the solution to that problem.
Go to "Edit" on top left menu
Scroll down and Click on "Project Settings"
Go to "Player" option
Now click on "Publish Settings"
Under the Build Section Check the option name as: 
"Custom Main Manifesr"  & "Custom Base Gradle Template"
Now Go to "Project" Layout
Open "Plugin" Folder then in "Android" folder Double Click on "AndroidManifest" file.
Copy and Paste the below code and Save it.
///////////////////////////////////////////////////////
<?xml version="1.0" encoding="utf-8"?>
<manifest
    xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.unity3d.player"
    xmlns:tools="http://schemas.android.com/tools">
    <application>
        <activity android:name="com.unity3d.player.UnityPlayerActivity"
                  android:theme="@style/UnityThemeSelector"
			      android:exported="true"
				  android:largeHeap="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
            <meta-data android:name="unityplayer.UnityActivity" android:value="true" />
        </activity>
    </application>
</manifest>
///////////////////////////////////////////////////////

Now Come Back into Unity and Make New APK.
"There is a problem parsing the package" issue will be resolved.
