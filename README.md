# BundleBus
Bundlebus is an open source framework project developed and distributed by ZENOME. The latest release version is targeted for react-native application deployment. Bundlebus provides an easy and convenient update and maintenance mechanism once an react-native app is deployed to app store or production.
A react-native developers can release and deploy their apps using BundleBus cli command. Then, the backend server will download the source codes from github sites and build and release it. Based on our development experience, all release didn't deploy to the end-user. So if the released react-native app is enough to deploy, you can deploy it by cli command as well. Our backend server will push down whole bundle and images to the client or will push down only differences and images which should be updated.

# What do we want to solve
## Problem
- Some client wants to upload their output(i.e, bundle in react-native) on their server.
- When releasing the output, a developer do same thing every time.
  - Download source files from a repository
  - Make a output( = bundle)
  - Upload it to the customer server(We call it 'release').
  - Validation team download it and do their job.
  - If everything is ok, then that bundle is relocated to specific place for end-user to download it.(We call it 'deploy').
- When deploying the output, a developer have to connect server and change the location.

## Solve
- We provide a backend which provides to control bundle version, build, release and deploy.
- We provide a Command Line Interface which provides to simply do 'release' and 'deploy'. So what developers have to do is just enter cli command to release/deploy their product.
- We provide a iOS/Android client library for effective download/merge released/deployed bundle version.

# Components
BundleBus has 3 components including backend, client library and cli.
- [Backend](https://github.com/zenome/BundleBus_backend)
- [Client library](https://github.com/zenome/BundleBus_client)
- [Command Line Interface](https://github.com/zenome/BundleBus-cli)

# How to taste it.
- Download Backend and run it on your system. See the instruction in Backend github page.
- Install 'BundleBus-cli' by below command
~~~~
npm install BundleBus-cli -g
~~~~
- Clone our example apps from 'https://github.com/zenome/BundleBus-example'
- Open a terminal in a local machine and move to the BundleBus-example folder.
- Register your github token by below command
~~~~
BundleBus register
~~~~
  - "Repository clone url" should be 'https://github.com/zenome/BundleBus_example.git'
  - Enter "Repository - github token". You can refer  [this link.](https://help.github.com/articles/creating-an-access-token-for-command-line-use/)
- Update the source code and commit to the git. Make sure that a version field in 'package.json' MUST be increased.
- Enter command in a terminal. This may take a time.
~~~~
BundleBus release <ios | android>
~~~~
- Enter command in a terminal.
~~~~
BundleBus deploy <ios | android>
~~~~
- Run your apps. And check the version and whole layout. Example app shows the update result. Let's restart your apps as soon as it shows complete.
