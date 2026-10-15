Development framework: 
- React Native
- Expo 
- TypeScript
Description:
    We are building SkyCast with React Native and Expo, using TypeScript as our language. React Native lets us build a working Android app with the JavaScript skills we learned in our Web Development courses. Expo makes setup and testing easier, with the Expo Go app, each team member in our group can run the project on their own phone by scanning a QR code, without setting up Android Studio.

    Our group decided to choose TypeScript over plain JavaScript because TypeScript is a superset of JavaScript. All valid JavaScript is also valid TypeScript, so the learning curve is small. TypeScript adds static type checking, which catches mistakes like passing the wrong kind of data to a function while we are writing the code, before the app ever runs, saving our group from spending a lot of time for debugging. When we run the app, Expo's bundler transforms our TypeScript code into JavaScript, which can then be executed by the phone's JavaScript engine. This conversion is necessary because JavaScript engines do not understand TypeScript-specific syntax, such as type annotations and interfaces. By converting TypeScript into JavaScript, the bundler ensures that the code can run properly on the target platform.

    Flutter is also a strong cross-platform framework, but it uses Dart, a language none of us have learned. React Native lets us build on what we are already being taught and strengthen those skills for mobile development, instead of spending our early sprints learning a new language.

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
Description:
    Dependencies are libraries and services we use so our team doesn't have to build every feature from scratch. For navigation, we use Expo Router, which came included with our Expo project setup. Expo Router uses file-based routing, meaning each file inside the "app/" folder becomes a screen in the app. The exceptions are files such as "_layout.tsx", which define shared layouts like our tab bar instead of a screen. Because of this, we keep reusable components in a separate "components/" folder so they don't accidentally become screens.
    
    For weather data, our team chose the Open-Meteo Forecast API because it is free for non-commercial use and don't require an API key. Since Open-Meteo is an external API that we call using "fetch", it doesn't need to be installed as a package. Open-Meteo's license requires credit, so SkyCast will display "Weather data by Open-Meteo.com" wherever weather data is shown.
    
    We use "expo-location" to get the phone's current location through GPS so SkyCast can show the weather where the user is, which requires the user's permission. The Supabase client library then connects the app to our group Supabase project, which provides our PostgreSQL database and user authentication. AsyncStorage saves small, non-sensitive data on the device, such as the user's saved cities and personalized settings.
    
    For styling, we use React Native's built-in "StyleSheet", which is similar to the CSS we already know from our web development courses. 

Target Devices:
- Android phones
- Portrait mode only
- Tested on the Android Studio emulator and on Android phones using Expo Go
Description:
    The course requires the program to run in a Android devices, and we are keeping it as portrait display only.


Navigation strategy: Tabbed and Stacked navigation
- Home: current weather, hourly forecast and 7-day forecast
- Locations: search, save and switch between cities
- Settings: temperature units, account and app info
Description:
    Main screens will be Home (Current weather, hourly forecast, 7 day forecast), Location(Search for other locations, save, and swap between them), and Settings (Celsius vs Fahrenheit, app permissions, account information)

    Navigation isnt fully decided yet but we will use tab navigation for the most part with those 3 main sections. We can include stack navigation for additional pages for account settings or more detailed weather information, this helps the app layout be simple but efficient.


Hardware integrations
- GPS: shows weather for the user's current location
- If location permission is denied, the app shows a saved city or asks the user to search for one
Description:
    We will use the devices location to show the weather information for current location. The app will request for permission to take their location, if granted it will take the area and request the weather data from the API. If the user denies permission, the app will let them manually search.

Database
- Supabase (PostgreSQL) stores saved cities for signed-in users
- Weather data is not stored. It is always loaded fresh from the API
Description: 
    Our team selected Supabase to save cities for users who want to make an account, Supabase has database functionality without needing us to make and keep a separate backend server. an important note is that we wont be keeping weather information directly in the database. we will be retrieving updated weather information from our weather API.

Authentication
- Supabase Auth with email and password
- The app can be used without an account
- Signing in lets users keep their saved cities on any device
- API keys are kept in a .env file that is not uploaded to GitHub
Description:
    We chose to use supabase to allow users to create and sign into their own account with an email and password. This will be an optional feature so users can check the weather without having to make any account. People who do sign in will have access to saved locations of their choice.

    Supabase works well with out planned database and makes authentication easier for us.


AI Features
Description:
    No AI features are planned right now
    
    We dont have anything to implement at the current stage because our main purpose is just the accurate weather information from the external API, Our core features can all be implemented without any AI features. Adding something just for the sake of having an AI feature would complicate the project for no reason. 
    
    If we need to add AI functionality later on in the project we will come together as a group to brainstorm different ways to implement.
