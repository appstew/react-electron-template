# react-electron-template

## features

- you can use this as a basic template to make an [desktop app](./README.md) or [SPA](./README.md).
- codes are based on typescript, react, electron

## start/test

- linux/mac
  1. yarn react-start
  2. yarn electron-start

- windows
  1. yarn react-start-win
  2. yarn electron-start-win

## build at build/

  - yarn build

## packaging at dist/

## other notes
- packaged executables save and use config files at the following dir. this happens even when running windows portable, linux appimage. this is electron's natural behavior.
  - (windows) C:\Users\$USER\AppData\Roaming\$APP_NAME
  - (linux) ~/.config/$APP_NAME

## 

## how I created this template
- cmd/bash

```
yarn create react-app --template typescript $DIRNAME
yarn add -D electron electron-builder
yarn add @material-ui/core @material-ui/icons history @types/history react-router-dom react-router @types/react-router
```
- add/edit package.json
```
  "main": "public/electron.js",
  "homepage": "./"

  "scripts": {
    "react-start": "BROWSER=none yarn start",
    "electron-start": "ELECTRON_START_URL=http://localhost:3000 electron .",
    "react-start-win": "set BROWSER=none && yarn start",
    "electron-start-win": "set ELECTRON_START_URL=http://localhost:3000  && electron .",
    "electron-pack": "yarn electron-builder build",
    "electron-pack-win-portable": "yarn electron-builder -w portable",
    "electron-pack-linux-appimage": "yarn electron-builder -l AppImage",
    "electron-pack-mac": "yarn electron-builder -m"
  }
```

- add/edit follwing files:
  - public/electron.js
  - src/service/history.tsx
  - src/index.tsx
  - tsconfig.json
  - src/App.tsx
  - src/index.tsx
  - src/route/index.tsx
  - src/component/sidebar/Sidebar.tsx
  - src/pages/IndexPage.tsx  
  - src/pages/MessagePage.tsx
  - src/pages/ChannelPage.tsx
  - src/pages/index.tsx
