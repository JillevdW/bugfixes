# bugfixes
(SO) links for bugs I've had to fix

[Android Studio GPU Driver issue for simulator](https://stackoverflow.com/questions/45121828/android-studio-suddenly-got-gpu-driver-issue-when-running-emulator)
------
[XML PHP Parse error: syntax error, unexpected $variable](https://github.com/jhass/nextcloud-keeweb/issues/6)
------
[FinalizerReference OOM](https://stackoverflow.com/questions/23652549/clueless-about-a-possible-android-memory-leak)
------
[Missing CFBundleIconName or lots of missing resources with upload to iTunes Connect.](https://stackoverflow.com/questions/46216718/missing-cfbundleiconname-in-xcode9-ios11-app-release)
------
[RecyclerView with EditText views shifting around](https://stackoverflow.com/questions/31844373/saving-edittext-content-in-recyclerview)
------



## Cordova Plugins
I've had a lot of trouble trying to get this setup, so here are some links that could be of use:

[Zip File of a working plugin](https://github.com/cowbell/cordova-plugin-geofence/files/1340828/geofence-plugin.zip)
This is useful to check when some CDV functions are deprecated.

[CDV Objc files](https://github.com/apache/cordova-ios/tree/master/CordovaLib/Classes/Public)
Basically the documentation :)

[Building blocks](https://github.com/ModusCreateOrg/cordova-swift3-plugin-example)
When we need to start all over from scratch.

Workflow for development is like this; create a new plugin, add it to the folder in the cordova project, then add the ios platform to the project. If this succeeds we succeeded in adding the plugin. Now we build the project once, from there we can use Xcode to edit our files. Building still has to be done with ***cordova build ios***. We can then run the app from Xcode to see the logs in there.



## Laravel bugs

[Doctrine issue](https://github.com/doctrine/dbal/issues/2848)
This is important for when the error `SQLSTATE[HY000]: General error: PDO::ATTR_STATEMENT_CLASS requires format array(classname, array(ctor_args)); the classname must be a string specifying an existing class` appears. This error breaks connection with the Database and thus is often observed when trying to login. Solution has to do with either updating PHP-FPM or downgrading the doctrine/dbal dependency. This bug is often caused when using `composer update` instead of composer require/install.



## Nativescript bugs

More javascript related than anything, but Arrays are _reference types_, not _value types_ like in Swift. When mutating an array somewhere (say, with .shift()) you _will_ alter the original.

When encountering this error:
`View not added to this instance. View: CommentNode(377) CurrentParent: undefined ExpectedParent: ScrollView(1066)`
or in general the sentence `View not added to this instance` this can be caused by an empty ng-template being loaded. In one case it happened with this code:

```
<ng-template #loading>
</ng-template>
```
When we add an empty view object between that, so for example `<Label text=""></Label>`, the error is resolved.

## React native bugs

build: react-native run-ios --configuration release

[Xcode 10 libfishhook.a cannot be found](https://github.com/facebook/react-native/issues/19569)

## Swift related error info:

List of NSURLConnection errors.

    NSURLErrorUnknown =             -1,
    NSURLErrorCancelled =           -999,
    NSURLErrorBadURL =              -1000,
    NSURLErrorTimedOut =            -1001,
    NSURLErrorUnsupportedURL =          -1002,
    NSURLErrorCannotFindHost =          -1003,
    NSURLErrorCannotConnectToHost =         -1004,
    NSURLErrorNetworkConnectionLost =       -1005,
    NSURLErrorDNSLookupFailed =         -1006,
    NSURLErrorHTTPTooManyRedirects =        -1007,
    NSURLErrorResourceUnavailable =         -1008,
    NSURLErrorNotConnectedToInternet =      -1009,
    NSURLErrorRedirectToNonExistentLocation =   -1010,
    NSURLErrorBadServerResponse =       -1011,
    NSURLErrorUserCancelledAuthentication =     -1012,
    NSURLErrorUserAuthenticationRequired =  -1013,
    NSURLErrorZeroByteResource =        -1014,
    NSURLErrorCannotDecodeRawData =             -1015,
    NSURLErrorCannotDecodeContentData =         -1016,
    NSURLErrorCannotParseResponse =             -1017,
    NSURLErrorAppTransportSecurityRequiresSecureConnection NS_ENUM_AVAILABLE(10_11, 9_0) = -1022,
    NSURLErrorFileDoesNotExist =        -1100,
    NSURLErrorFileIsDirectory =         -1101,
    NSURLErrorNoPermissionsToReadFile =     -1102,
    NSURLErrorDataLengthExceedsMaximum NS_ENUM_AVAILABLE(10_5, 2_0) =   -1103,

    // SSL errors
    
    NSURLErrorSecureConnectionFailed =      -1200,
    NSURLErrorServerCertificateHasBadDate =     -1201,
    NSURLErrorServerCertificateUntrusted =  -1202,
    NSURLErrorServerCertificateHasUnknownRoot = -1203,
    NSURLErrorServerCertificateNotYetValid =    -1204,
    NSURLErrorClientCertificateRejected =   -1205,
    NSURLErrorClientCertificateRequired =   -1206,
    NSURLErrorCannotLoadFromNetwork =       -2000,

    // Download and file I/O errors
    
    NSURLErrorCannotCreateFile =        -3000,
    NSURLErrorCannotOpenFile =          -3001,
    NSURLErrorCannotCloseFile =         -3002,
    NSURLErrorCannotWriteToFile =       -3003,
    NSURLErrorCannotRemoveFile =        -3004,
    NSURLErrorCannotMoveFile =          -3005,
    NSURLErrorDownloadDecodingFailedMidStream = -3006,
    NSURLErrorDownloadDecodingFailedToComplete =-3007,

    NSURLErrorInternationalRoamingOff NS_ENUM_AVAILABLE(10_7, 3_0) =         -1018,
    NSURLErrorCallIsActive NS_ENUM_AVAILABLE(10_7, 3_0) =                    -1019,
    NSURLErrorDataNotAllowed NS_ENUM_AVAILABLE(10_7, 3_0) =                  -1020,
    NSURLErrorRequestBodyStreamExhausted NS_ENUM_AVAILABLE(10_7, 3_0) =      -1021,

    NSURLErrorBackgroundSessionRequiresSharedContainer NS_ENUM_AVAILABLE(10_10, 8_0) = -995,
    NSURLErrorBackgroundSessionInUseByAnotherProcess NS_ENUM_AVAILABLE(10_10, 8_0) = -996,
    NSURLErrorBackgroundSessionWasDisconnected NS_ENUM_AVAILABLE(10_10, 8_0)= -997,
