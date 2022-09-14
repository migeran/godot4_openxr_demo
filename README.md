# Godot 4 OpenXR demo project (for Meta Quest 2)

What you are looking at is my absolutely crappy demo project for testing the OpenXR logic we're porting into Godot 4 core. Maybe one day it will evolve into a proper demo project (thats the hope). Contributions super welcome.

Use in combination with https://github.com/godotengine/godot/pull/65798

This version includes an Godot Android plugin that adds the Meta OpenXR Loader to the project. 

## How to build

* Check out the engine source code
* Build the editor for your host, e.g.:
```
scons platform=linuxbsd target=release_debug
```
* Build the Android templates
```
cd $GODOT_FOLDER
scons platform=android target=release
scons platform=android target=release_debug
scons platform=android target=debug
cd platform/android/java
./gradlew generateGodotTemplates
```
* Open the demo project in the editor and install the custom build template we just built.
* Build the MetaOpenXRAndroid plugin which contains the Meta OpenXR Loader:
```
cd $DEMO_FOLDER/android/plugins/MetaOpenXRAndroid
./gradlew assembleDebug
```
* Export and install the project on the device.
  * Make sure that custom build and the MetaOpenXRAndroid plugin are enabled
in the export configuration.

## License

This project is provided under the MIT license

Check license files in the asset and addons folders for 3rd party licenses.
