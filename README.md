# BundleBus
Simply, it's like Microsoft's' Code-Push but a few significant differences.

# Description
BundleBus(by ZENOME) provides an easy and convenient update and maintenance mechanism once an react-native app is deployed to app store or production.
React-Native developers can simply release and deploy their apps using BundleBus-cli command. The backend server automatically downloads the source code from the developer's github repository and build and release it. If the released react-native app is ready to deploy, it's simply deployed again via cli command. Our backend server will push down the whole bundle and images to the client or only the differences(i.e. updated images).

# What 'Problem' are we trying to solve?
## Problem
- Some clients want to upload their output(i.e, bundle in react-native) on their server.
- When releasing the output, developers typically have to do the same tasks(described below) over and over.
  - Download source files from repository
  - Build to create a new bundle
  - Upload it to the customer server(We call it `release`).
  - Validation team downloads and validates the release.
  - If everything looks good, then that bundle is relocated to a specified location for the end-user to download.(We call it `deploy`).
- When deploying the output, developers have to connect to the server and change the location.

## Solution
- We provide a backend server solution which provides the control of bundle version, build, release and deployment.
- We provide a commandline interface which provides a way to simply do a `release` and `deploy`. So developers just have to enter cli command to release/deploy their product.
- We provide a iOS/Android client library for effective download/merge of a newer bundle version.

# Components
BundleBus has 3 key components consist of backend, client library and cli.
- [Backend](https://github.com/zenome/BundleBus_backend)
- [Client library](https://github.com/zenome/BundleBus_client)
- [Command Line Interface](https://github.com/zenome/BundleBus-cli)

# How to taste it
- Download Backend and run it on your system. See the instruction in the [Backend github](https://github.com/zenome/BundleBus_backend) page.
- Install 'BundleBus-cli' via below command
~~~~
sudo npm install bundlebus-cli -g
~~~~
- Clone our example apps from https://github.com/zenome/BundleBus_example
- Open a terminal window and move to the BundleBus-example folder.
- Register your github token by below command
~~~~
bundlebus register
~~~~
  - `Repository clone url` should be `https://github.com/zenome/BundleBus_example.git`.
  - Enter `Repository - github token`. You can refer [this link.](https://help.github.com/articles/creating-an-access-token-for-command-line-use/)
- Update the source code and commit to the git repository. Make sure that the version field in `package.json` is updated(very important).
- Enter the following command in the terminal window. This may take some time.
~~~~
bundlebus release <ios | android>
~~~~
- Enter command in a terminal.
~~~~
bundlebus deploy <ios | android>
~~~~
- Run your app and check the updated version and overall layouts. The sample app should show the update result. Now, it's time to use BundleBus in your own app.
