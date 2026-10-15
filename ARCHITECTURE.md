Development framework: React Native, Ionic, Cordova, Flutter...

Project dependencies: style frameworks, libraries needed for particular features, database tooling, icon libraries -- anything you'll need to set up in relation to react native/other or add to it

Target Devices:
- Android phones
- Portrait mode only
- Tested on the Android Studio emulator and on Android phones using Expo Go

Navigation strategy: Tabbed and Stacked navigation
- Home: current weather, hourly forecast and 7-day forecast
- Locations: search, save and switch between cities
- Settings: temperature units, account and app info

Hardware integrations
- GPS: shows weather for the user's current location

Database
- Weather data is not stored. It is always loaded fresh from the API

Authentication
- Supabase Auth with email and password
- The app can be used without an account
- Signing in lets users keep their saved cities on any device
- API keys are kept in a .env file that is not uploaded to GitHub

AI Features