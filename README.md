# BundleBus
Bundlebus is an open source framework project developed and distributed by ZENOME. The latest release version is targeted for react-native application deployment. Bundlebus provides an easy and convenient update and maintenance mechanism once an react-native app is deployed to app store or production.
A react-native developers can release and deploy their apps using BundleBus cli command. Then, the backend server will download the source codes from github sites and build and release it. Based on our development experience, all release didn't deploy to the end-user. So if the released react-native app is enough to deploy, you can deploy it by cli command as well. Our backend server will push down whole bundle and images to the client or will push down only differences and images which should be updated.

# Components
BundleBus has 3 components including backend, client library and cli.
- [Backend](https://github.com/zenome/BundleBus_backend)
- [Client library](https://github.com/zenome/BundleBus_client)
- [Command Line Interface](https://github.com/zenome/BundleBus-cli)
