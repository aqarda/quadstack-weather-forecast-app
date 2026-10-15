Development framework: 
- React Native
- Expo 
- TypeScript

Project dependencies:
Navigation | @react-navigation/native
           | @react-navigation/botton-tabs
           | @react-navigation/native-stack
           | @react-native-screens
           | @react-native-safe-area-context
Icons      | @expo/vector-icons
Styling    | React Native 'StyleSheet'
Location   | @expo-location
Backend    | @supabase/supbase-js
Storage    | @react-native-async-storage/async-storage
Weather    | Open-Meteo Forecast API / Geocoding API (called with 'fetch')

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
- If location permission is denied, the app shows a saved city or asks the user to search for one

Database
- Supabase (PostgreSQL) stores saved cities for signed-in users
- Weather data is not stored. It is always loaded fresh from the API

Authentication
- Supabase Auth with email and password
- The app can be used without an account
- Signing in lets users keep their saved cities on any device
- API keys are kept in a .env file that is not uploaded to GitHub

AI Features
- 
- 