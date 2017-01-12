# AnalogBridge-Android-Test

This is a demo version for showing AnalogBridge-Android.

AnalogBridge-Android is a library which contains flow for web service in https://analogbridge.io/demo

For use this library

In your build.gradle in your project

```
allprojects {
    repositories {
        jcenter()
        repositories {
            maven {
                url  "http://marcoram.bintray.com/analogbridge"
            }
        }
    }
}
```

Also in your build.gradle in your app module

```
compile 'com.android.support:design:25.0.1'
compile 'com.mikepenz:actionitembadge:3.3.1@aar'
compile 'com.mikepenz:iconics-core:2.8.1@aar'
compile 'com.loopj.android:android-async-http:1.4.9'
compile 'com.stripe:stripe-android:2.0.2'
compile 'com.squareup.picasso:picasso:2.5.2'
compile 'com.marcopok.analogbridge:analogbridgecomponent:0.0.5@aar'
```

In your project, you can use AnalogBridge-Android library

```
Button importButton;
importButton.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View view) {
        //token Request
        getRequest(tokenURL, new RequestParams(), new JsonHttpResponseHandler() {
            @Override
            public void onFailure(int statusCode, Header[] headers, String responseString, Throwable throwable) {
                if (statusCode == 200) {
                    //responseString = token
                    
                    //publicKey and token
                    APIService.sharedService().setAuth(publicKey, responseString, new CompletionHandler() {
                        @Override
                        public void completion(boolean bSuccess, String message) {
                            if (bSuccess == true) {
                                
                            }
                            else {

                            }
                        }
                    });
                }
                else {
                    
                }
            }
        });
    }
});
```
