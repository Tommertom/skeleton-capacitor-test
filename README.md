# Skeleton Capacitor test

Create through:
* running the npm create skeleton-app
* switching to adapter static - as I want a SPA so all assets are shipped in the APK (but SSR is possible too)
* adding Capacitor integration (@capacitor/cli, /core and /android)
* run npm run build
* running npx cap init, and change webdir to build
* npx cap open android - to trust the project - kill studio then
* npx cap run android - to run on emulator


## Known issue
At first run, the styles are not applied - only after a few seconds