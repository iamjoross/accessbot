# Installation

## Get code

Clone this repo in your local machine

```bash
git clone https://github.com/foo
```

 Move inside the project folder

```bash
cd foo
```


Confirm you have NodeJs 10.x or higher

```bash
Node-v
```


Enable .env file

```bash
mv .sample.env .env
```

Add App IDs and Secrets to `.env` configuration

_more info at: https://developers.facebook.com/docs/messenger-platform/introduction_

```bash
vim .env
```

Things to update:

```
PAGE_ID=
APP_ID=
PAGE_ACCESS_TOKEN=
APP_SECRET=
VERIFY_TOKEN=<ANY STRING YOU'LL REMEMBER>
```


# Usage

In order to receive messages, we need to be able to get incoming webhooks from Facebook Servers. So we need an external address, a quick way to do this is to use NGROK since it will provide an external https address that will tunnel into your NodeJS running app.

1- Install NGROK in your computer, go to the link and follow the instructions:

https://dashboard.ngrok.com/get-started/setup

2- run in port 80

```bash
./ngrok http 80
```


#### 3. Inside the `.env` config, add the URL provided by NGROK:

```bash
APP_URL=https://<AUTOGENERATED>.ngrok.io
```


#### 4. In the root of the project run app locally:

```bash
node app.js
```
 
 #### 5. Confirm is running by visiting this URL in your browser

`http://localhost:80/`

_You should be able to see a welcome Message._


#### 6. Confirm Token
Pay attention to the Command Line, it will provide you with an URL that you need to visit in order to validate the token.  _it looks similar to this:_

`https://xxxxxxxx.ngrok.io/profile?mode=all&verify_token=xxxxxxx`


#### 7. Test your app 
Go to the link provided by the Terminal, _it looks similar to this:_

`https://m.me/xxxxxx`

#### 6. Test that your app setup is successful

  Send a message to your Page from Facebook or in Messenger, if your webhook receives an event, you have fully set up your app! Voilà!








