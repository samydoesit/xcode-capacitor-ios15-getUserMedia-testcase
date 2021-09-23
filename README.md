# nuxt-capacitor-getusermedia


## navigator.mediaDevices.getUserMedia bug on xcode13
This App displays when build with `xcode12.5.1` a camera stream. There will be two Permission prompts.

If build with `xcode13` a call to `navigator.mediaDevices.getUserMedia()` gets abortet with: `AbortError`, what has changed? No Permission prompt will be displayed.


When build on `xcode12.5.1` since `iOS15` it is also necessary to apply a setTimeout to the video element otherwise it wont get displayed.


Running the App before on `iOS 14.8` was perfectly fine the only issue was that the user had to confirm camera permissions two times on first app run.

## iosBuild test case

```bash 
$ npm install

# genrate static files & open xcode 
npm run build:ios
```


## old
```bash 
# serve with hot reload in browser at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate

```

maybe helpfull links:
https://developer.apple.com/documentation/webkit/wkuidelegate/3763087-webview#discussion

https://nemecek.be/blog/111/wkwebview-improvements-in-ios-15#apis-for-camera-and-microphone