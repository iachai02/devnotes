# How to start up full stack project

1. Create empty project
2. Create backend and mobile folders
3. `cd backend` and `npm init -y`
   - this will create a package.json file
4. `npm i express` installs web framework
5. `npm i dotenv@16.5.0 cors@2.8.5 @neondatabase/serverless@1.0.0` access environment variables, security standard that controls webpages, Neon's official PostgreSQL driver designed for JavaScript and TypeScript specifically optimized for serverless and edge environments
6. add `type: "module"` to package.json to use imports
7. `npm i -D nodemon` installs a package that updates the server in real time
8. Add a `dev` script with `nodemon server.js` to run the command when using the command `nodemon run dev`

npx expo start --localhost --clear: use to restart client
