---
title: Folder structure, Frontend & Feature Update
---

### Folder Structure

```
pom.xml
src/
  - main/
    - java/
      - org/
        - urjc/
          - peerclass/
            - PeerClassApp.java <---- main class
            - controllers/
              [Spring Controllers]
            - models/
              [Spring Models]
    - resources/
      - application.properties <---- server config file
      - keystore.jks <---- ssl keys
      - kroom.conf.json <---- kurento room config file
      - log4j.properties <---- log config file
      - static/
        - bower.json <---- for bower components (such as `bootstrap-css-only`)
        - package.json <---- for node modules (such as `angular` modules, `ng2-bootstrap` and `angular material`)
        - tsconfig.json <---- typescript config
        - typings.json
        - gulpfile.js <---- for now, it's being used to compile less files
        - app/
          - main.ts <---- bootstrap angular file
          - app.module.ts <---- main module
          - app.component.ts <---- main component
          - components/
            - [angular 2 components] <---- 2 levels of folder if necessary
        - assets/
          - css
            - [Output of CSS files] <---- compiled with gulpfile.js
            - less
              - [LESS files]
        - typings/
          [Typing files]
  - test
    [Java tests] <---- empty, we will start making tests when we have some logic to test
```

Since we are using [Kurento Room](https://github.com/Kurento/kurento-room), we must override some methods in the main java class (`PeerClassApp.java`) to setup the settings for our project.

### Frontend update

For the design of the app we are going to follow a "dashboard" style. The sidebar will have the current rooms available, the navbar will have links to access the settings, profile and explore/search functions.

The main part of the dashboard will be for the dynamic content (`<router-outlet></router-outlet>`). In there you will be able to watch the live video, chat with your peers and share files, etc.

We are going to use `Angular Material` for the base app, since it has a wider range of components compared to `ng2-bootstrap`. However if there isn't a component in angular material but it's in `ng2-bootstrap`, we will use it for the development process. But since `ng2-bootstrap` doesn't have the same style as `angular material` we will rewrite that component to fit our material design. 

### Feature update

Since, for now, we can't share the screen of the user with the native browser options; we will prompt the user to install a special Chrom/Firefox extension for our site. The development of this extension will be in another repo, [here](https://github.com/alxhotel/peerclass-extension).

Some previous testing of `Webtorrent` has shown a reasonable increase of the CPU usage, this could be a problem when live chatting. We will test this module more when we have, at least, a working chat.

### Follow the development

You can check out the current version of PeerClass at [this Github repo](https://github.com/alxhotel/peerclass)
