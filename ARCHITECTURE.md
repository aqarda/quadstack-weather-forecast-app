Development framework: 
- React Native
- Expo 
- TypeScript

Project dependencies:
Navigation | @react-navigation
           | @react-native-screens
           | @react-native-safe-area-context
Icons      | @expo/vector-icons
Location   | @expo-location
Backend    | @supabase/supbase-js
Storage    | @react-native-async-storage/async-storage
Weather    | Open-Meteo Forecast API / Geocoding API

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
- Supabase
- Weather data is not stored. It is always loaded fresh from the API

Authentication
- Supabase Auth with email and password
- The app can be used without an account
- Signing in lets users keep their saved cities on any device
- API keys are kept in a .env file that is not uploaded to GitHub

AI Features
- 
- 