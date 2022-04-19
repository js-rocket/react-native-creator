# Description

This repository contains a script to help initialize a react native application with the bare minimum required functionality.

Its purpose is to address the deficiencies of the `react-native init` command with the following features

* Allows setting the Application Icon name
* Allows setting the IOS and Android Bundle ID
* Helps set the Application icon and splash screen
* Generates Android signing key


# How to use
- Clone this repository and change into repository root folder 
- Execute `./run init` to download latest version of react native and initialize new project with it
- Execute `./run create folderName "application Name" app.bundle.id` to create your new react native app
  for example:
  ```
  ./run create demoapp "Demo App" com.example.demoapp
  ```

- Move newly created project folder into a new location
s

# To create a signing/upload key for Android
- Make a copy of the environment file `cp env.sample .env` and edit the contents of the .env file
- Edit the file `env.settings` and set the value for `ANDROID_KEY_INFO`
- Edit the file `.env` andset the values for the variables `ANDROID_KEYSTORE_PASSWORD` and `ANDROID_ALIAS_PASSWORD`
- Generate production Android key `./run android-key-create`
- From the generated file `.secrets_android/android_key.jks.env` copy the line with `ANDROID_KEYSTORE_BASE64=...` and replace in the `.env` file


# To add an app icon and splash screen
- To set the application icon and splash screen, put a .png picture of size 512 x 512 into the `./assets` folder named `icon.png` and `splash_screen.png` and run the command from the generated project root folder:

`./run update-app-icon`


# TODO
- Implement adapative icon generator for Android
- implement splash screen generator
- Simplify IOS certificate generation through command line


