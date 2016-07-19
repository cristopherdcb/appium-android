# Appium/Android docker image

Is the docker image containing appium and android to run functional test scenarios on android emulators, specifically android 19 (it also support android 21 and 22 but those have not been tested yet)

### How to execute

| Command                                                    | Description                          |
| ---------------------------------------------------------- | ------------------------------------ |
| `sudo docker build -t appium-android .`| Build a new image |
| `sudo docker run --net host -v path-to-your-apk:/apk -di -P --name android appium-android`| it will launch an android emulator, the -v parameter must point to your apk file|
| `sudo docker exec -i android adb -s emulator-5554 shell getprop sys.boot_completed`| This command can be used in order to know if the emulator boot properly, it will return 1 if booted but take into account that may take a while until returns 1|

### Exposed ports

| Port   | Description |
| ------ | ------------|
| `4723`| Appium      |
| `22`  | SSH         |