# expo-kitten-issue
Issue with Kitten using expo

Reproduce Steps

1. Setup Expo TS project

```
npx create-expo-app -t expo-template-blank-typescript BlankTS
cd BlankTS/
npx expo install react-native-web@~0.18.10 react-dom@18.2.0 @expo/webpack-config@^18.0.1
```

2. Verify working for web
```
npx expo start --web
```

3. Install UI-Kitten Manual Steps\
```
npm i @ui-kitten/components @eva-design/eva
expo install react-native-svg@9.13.6
```

4. Update app.json
If you use Expo for Web, you need to add the following underneath the "web" key in app.json "build": { "babel": { "include": [ "@ui-kitten/components" ] } }

5. Start project and see error
```
npx expo start --web
```

Sample Errors:
```

WARNING in ./node_modules/@eva-design/processor/js/src/service/style/index.js
Module Warning (from ./node_modules/source-map-loader/dist/cjs.js):
Failed to parse source map from '/workspaces/expo-kitten-issue/BlankTS/node_modules/packages/processor/js/src/service/style/index.ts' file: Error: ENOENT: no such file or directory, open '/workspaces/expo-kitten-issue/BlankTS/node_modules/packages/processor/js/src/service/style/index.ts'

WARNING in ./node_modules/@eva-design/processor/js/src/service/style/style.service.js
Module Warning (from ./node_modules/source-map-loader/dist/cjs.js):
Failed to parse source map from '/workspaces/expo-kitten-issue/BlankTS/node_modules/packages/processor/js/src/service/style/style.service.ts' file: Error: ENOENT: no such file or directory, open '/workspaces/expo-kitten-issue/BlankTS/node_modules/packages/processor/js/src/service/style/style.service.ts'
```