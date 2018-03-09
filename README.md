This repo is the Google Maps API for iOS that you can install using Carthage.  Unfortunately, Google does not natively support Carthage, instead requiring CocoaPods or manual integration, and according to this issue https://issuetracker.google.com/issues/35827791, it seems like official support won't be coming soon.

This repo is up to date as of 2.6.0

In the event that a more recent version is available and not integrated, here's how to do it:

1. Fork the repo and clone it.
2. Open the project in Xcode.
3. Download the desired distribution from https://developers.google.com/maps/documentation/ios-sdk/start as listed in the "Install Manually" tab.
4. Open up 2 Finder Windows. One focused on the sources folder of your cloned project, the other at the GoogleMaps distribution you downloaded. Maps 2.6.0 has 4 frameworks that need to be integrated:
    * Base/GoogleMapsBase.framework
    * Maps/GoogleMaps.framework
    * Maps/GoogleMapsCore.framework
    * M4B/GoogleMapsM4B.framework
5. For each Framework, expand the contents and do the following:
    1. Copy files in the  Headers, Modules, and Resources  into the corresponding (sources) folder of the repo.
    1. Make sure that all headers are added to the project. If you have to add new ones, inspect the header section of the framework's target and make sure that they are added as `public`.
    1. Cop the binary and bundle.
5. Update the version number each Target's General settings.
6. You may have to read over the GoogleMaps manual installation instructions as required frameworks may have been added.  Compare the requirements with what is specified in the target's `Build Phases`/`Link Binary with Libraries`
7. (Optional) - Submit a pull request so I can pick up your changes!

This repo was forked from https://github.com/leoneparise/GoogleMaps-Carthage. Unfortunately, it erratically updated and the Places API has not been updated since 2.1.0.


