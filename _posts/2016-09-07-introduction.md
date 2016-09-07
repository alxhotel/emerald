---
title: Introduction and Features
---
### Purpose

Since the start of the Internet, people have had a quicker and easier way to communicate over large distances. The quality of the networks have improve so much that we can now stream video and audio nearly without any buffering or dropping packets. This has made possible to be able to live streaming, even in mobile devices.

Now we can take advantage of this situation and create new tools that help people's everyday lifes. We wanted to help get education everywhere, that is why we are building a virtual classroom opensource webapp based on [WebRTC](https://webrtc.org). This application will make easier than every having a live lecture and replay it afterwards.

### Structure

* For the frontend, we are going to use [AngularJS 2](https://angular.io/) with [TypeScript](https://www.typescriptlang.org/) and [ng2-bootstrap](https://github.com/valor-software/ng2-bootstrap).

* For the backend, we are going to use [Java](https://www.java.com/) with the [Spring framework](https://projects.spring.io/spring-framework/). And [MySQL](https://www.mysql.com/) for the database.

* For the integration of [WebRTC](https://webrtc.org/) we are going to use [Kurento](http://www.kurento.org/).

### Features

These last weeks have been assign to decide what are the features of a fully functional virtual classroom for our project. We have came up with these ideas:

- The user can be a student or a teacher.
- The teacher is the "administrator". He is the only one that can create a new room.
- The user must be logged in before entering any room.
- The rooms can be configured to be public (any logged in user can enter) or private (you must know the password to enter).
- The teacher (and students) will share his slides, screen and webcam through the Kurento server (WebRTC).
- Any student can share his screen and webcam, even if he didn't raise his hand.
- Any of the students can raise his hand to ask a question. If the teacher accepts it, the teacher's webcam and screen will be replaced by the student's webcam and screen, until he or the teacher stops it.
- There is a limit of students that can attend a class. This could be a setting for the room, but there should be a max. number for the setting, like 15 people.
- If the teacher needs to sent additional files, he can upload it to his "folder". This folder is unique for every room. All the files in this folder will be available after the lecture.

- Anyone can send a message through the built-in "ephemeral" chat.
  - In this chat, you can send text, image, audio and video. All of them can be viewed in the browser, with an option to download it to their computer. In this part we could use [Webtorrent](https://webtorrent.io) to distribute the ephemeral files.
  - All of the shared files in the chat, will be stored locally and not in the server. (This could be seen as an advantage for live users for been there).
  
- All notifications such as a new message, a raised of a hand will be notify to all browsers as a native notification, if the user accepts to receive them.
- After ending the lecture, the teacher's webcam, slides and files will be stored, so that any user can go back to a previous lecture and replay it ([Youtube](https://youtube.com/) style). It will have a comments section (which is not the same as ephemeral chat). These comments will be saved in the server (only text).

Keep in mind that these features may change in the next couple of weeks.

### Follow the development

You can check out the current version of PeerClass at [this Github repo](https://github.com/alxhotel/peerclass)
