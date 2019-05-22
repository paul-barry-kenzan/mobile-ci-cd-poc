# Mobile CI/CD POC

## Overview

This is a simple project used to demonstrate the ability to create, modify, sign and deploy mobile applications.

## Technical Difficulties

- In order to successfully deploy an application to the iOS App Store, the Jenkins server must be running on an Apple/OSX machine and running a version of Xcode which is compatible with the targeted iOS version of the application. For example, in order to release an app targeting `iOS 10.3`, Xcode version `10.1` is required. Without this compatability, the application will not be built, thus failing the deployment script.

- Fastlane is a middle-man communicator between the Jenkins server and App Store Connect. During the development of this POC, the App Store Connect API was updated with breaking changes causing parts of Fastlane to fail. This failure caused deployments to fail until Fastlane was patched to correctly access the App Store Connect API.

## Development

### Creating a new app from scratch

1. Create a new React Native app `react-native init <PROJECT NAME>`
1. Open `.xcodeproj` file within Xcode
    - Update Bundle Identifier
    - Select target device: Product > Destination
1. Run `react-native run-ios`
1. Run `fastlane init` within /ios
1. Select `Automate beta distribution to TestFlight` as Fastlane use
1. Create new app within App Dev Center and App Store Connect
1. Run `fastlane beta`
1. Generate Provisioning Profile for new app
1. Encrypt and push profile to private GitHub repo
1. Update Fastfile and Appfile with signing info
1. Run `fastlane beta` again

### Deployment Server Setup

**Note:** As noted above, in order to deploy to the App Store, Xcode _must be_ available on the server and the version must be compatable with the targetted iOS version.

1. Install Xcode, if necessary
1. Install Xcode add-ons (CLI tools)
1. Install Fastlane ( [Fastlane Setup](https://docs.fastlane.tools/getting-started/ios/setup/) )
1. Enable CLI tools via Xcode Preferences
1. Install appropriate version of Node/npm

### Testing in TestFlight
- Users must be added to App Store Connect to ensure access to the app

## Resources

- [Fastlane Docs](https://docs.fastlane.tools/)
- [Fastlane Jenkins Best Practice](https://docs.fastlane.tools/best-practices/continuous-integration/jenkins/)
- [Tutorial #1](https://medium.com/@cherrmann.com/continuous-integration-and-delivery-for-ios-with-jenkins-and-fastlane-part-1-3b17f1901a73)
- [Tutorial #2](https://medium.com/react-native-training/fastlane-for-react-native-ios-android-app-devops-8ca85bee614e)
