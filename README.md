# TrapyzLocateSDK

# Instructions #

Download and extract or git clone this repository in the root directory of your project.
### Gradle Configuration###
*Add these dependencies in your App's build.gradle file

```
    compile 'com.android.support:appcompat-v7:26.+'
    compile 'com.google.android.gms:play-services-gcm:11.0.2'
    compile 'com.google.android.gms:play-services-location:11.0.2'
    compile 'com.amitshekhar.android:android-networking:1.0.0'
    compile 'com.github.pwittchen:reactivebeacons:0.5.1'
    compile 'io.reactivex:rxandroid:1.2.1'
```

### Settings.Gradle Configuration###
*Add these dependencies in your App's build.gradle file
```
include ':app', ':trapyzlocate'

```

###Add Service to Manifest ###
* Update your AndroidManifest.xml file by adding the service inside your application block
```
  <service
            android:name= "com.trapyz.trapyzlocatesdk.TrapyzLocationService"
            android:exported="false"
            android:stopWithTask="false"
            android:process=":TrapyzLocationService"/>
            />
```

###Add Permissions to Manifest ###
* Update your AndroidManifest.xml file by adding these permissions
```
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
    <uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
    <uses-permission android:name="android.permission.CHANGE_WIFI_STATE" />
    <uses-permission android:name="android.permission.WAKE_LOCK" />
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
    <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
    <uses-permission android:name="android.permission.READ_PHONE_STATE" />
    <uses-permission android:name="android.Manifest.permission.READ_PHONE_STATE" />
    <uses-permission android:name="android.permission.GET_ACCOUNTS" />
```

###Add ApiKey to Manifest ###
* Add your ApiKey to the manifest file inside your application block
```
        <meta-data android:name="trapyz_sdk_api_key" android:value="YOUR_API_KEY" />

```


###Start/Stop Service###

``` 
            Intent intent = new Intent(Intent.ACTION_SYNC, null, this, com.trapyz.trapyzlocatesdk.TrapyzLocationService.class);
            startService(intent);

```

or


```
        stopService(new Intent(this, com.trapyz.trapyzlocatesdk.TrapyzLocationService.class));
```

*You can implement startService method in the onCreate block of your mainactivity and stopService method in the onStop or onDestroy block of your mainactivity