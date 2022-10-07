# vue-csv-sample

## What is this
You can find the tutorial [here](www.learningsomethingnew.com/vue-js-vue-cli-3-vuetify-cordova-nano-sql-building-a-cross-platform-app-with-a-local-sql-database-that-can-load-data-from-a-static-csv-file)

## Project setup
```
yarn install
```

### Running in web
```
yarn serve
```

### src-cordova 디렉토리에서 www 디렉토리를 생성한다.
mkdir www
(참조 : https://stackoverflow.com/questions/21276294/cordova-current-working-directory-is-not-a-cordova-based-project)

### src-cordova 디렉토리에서 아래의 명령을 실행한다.
cordova platform add android

### 상기 명령 실행시 아래의 오류에 대해서 하기와 같이 조치한다.

에러 메시지 : Failed to install 'cordova-sqlite-storage': CordovaError: Using "requireCordovaModule" to load non-cordova module "q" is not supported

파일 위치 : ./plugins/cordova-sqlite-storage/scripts/beforePluginInstall.js 

주석 처리 : var Q = context.requireCordovaModule('q')

주석 처리 대신 한 줄 추가 : add var Q = require('q') 

(참조 : https://github.com/storesafe/cordova-sqlite-storage/issues/856)

### Running on Android (프로젝트 루트 디렉토리에서 실행)
```
npm run cordova-serve-android
```

### Running on IOS (ios 실행할 경우)
```
npm run cordova-serve-ios
```

안드로이드 오류 대처
[Android Studio] Could not initialize class com.android.sdklib.repository.AndroidSdkHandler

: https://fall-in-it.tistory.com/m/37

: https://g-father.tistory.com/31
