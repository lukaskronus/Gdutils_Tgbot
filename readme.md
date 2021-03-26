**How to Use**

- Step 1: Run `curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -` (change 14.x to 12.x if getting error, see below)
- Step 2: Run `sudo apt install build-essential nodejs -y` to install `build-essential`, `nodejs` and `npm`
- Step 3: Move to `Gdutils_Tgbot` and run `sudo npm install --unsafe-perm=true --allow-root` to install all dependencies in `node_modules`
   ** If error occurred, remove everything in `node_modules`, change nodejs version to 12.x and re-run the command
- Step 4: Run `nano config.js` and edit the config file
```
  client_id: 'your_client_id',
  client_secret: 'your_client_secret',
  refresh_token: 'your_refrest_token',
  expires: 0, // Can be left blank
  access_token: '', // Can be left blank
  tg_token: 'bot_token', // Your telegram bot token，Go here https://core.telegram.org/bots#6-botfather
  tg_whitelist: ['your_tg_username'] // Your tg username(t.me/username)，Bot will accept command from these users, You can add multiple users if you wish to
```
- (Optional) Step 5: Run `./validate-sa.js -h` to validate all service accounts in `sa` folder (Note: you must copy your json files to `sa` folder before run this command)
- Step 6: Run `sudo npm i pm2 -g` to install `pm2`
- Step 7: Run `sudo pm2 start server.js --node-args="--max-old-space-size=1024"` to start bot server
- Step 8: Run `node index.js` to start the bot or run `sudo pm2 start index.js` to make the bot running persistently
