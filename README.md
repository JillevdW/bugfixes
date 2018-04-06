# bugfixes
(SO) links for bugs I've had to fix

[Android Studio GPU Driver issue for simulator](https://stackoverflow.com/questions/45121828/android-studio-suddenly-got-gpu-driver-issue-when-running-emulator)
------
[XML PHP Parse error: syntax error, unexpected $variable](https://github.com/jhass/nextcloud-keeweb/issues/6)
------
[FinalizerReference OOM](https://stackoverflow.com/questions/23652549/clueless-about-a-possible-android-memory-leak)
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
