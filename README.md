
# ringcentral-engage-demo-email-auto-reply-bot

Demo bot that will auto reply every email with simple message for [RingCentral Engage(Dimelo)](https://www.dimelo.com/en/dimelo-digital).

## Prerequisites

- Nodejs 8.10+/npm, recommend using [nvm](https://github.com/creationix/nvm) to install nodejs/npm.
- RingCentral Engage(Dimelo) accout, [request a demo](http://site.dimelo.com/en/demo#schedule-demo).
- Login to your RingCentral Engage(Dimelo) admin console.
- Create a community in RingCentral Engage Digital -> admin -> community.
- Create email source in RingCentral Engage Digital -> admin -> Source, make sure it enabled and active. You only need input a email address in POSTMARK SETTINGS -> Email Address, leave other default.
- Go to RingCentral Engage Digital -> admin -> Agents, click the key icon, give your self read/reply/initiate discussion permission, but make sure do not check Approval required.
- Create a api token in RingCentral Engage Digital -> admin -> API access tokens, select your self as agent.
- Create webhook in RingCentral Engage Digital -> admin -> Webhooks.

## Development & Quick start

```bash
# get the code
git clone git@github.com:zxdong262/ringcentral-engage-demo-email-auto-reply-bot.git
cd ringcentral-engage-demo-email-auto-reply-bot

# install dependencies
npm i

# run ngrok proxy
# since RingCentral Engage webhook need https endpoint,
# so we need a https proxy for RingCentral Engage webhook to visit our local server
npm run proxy
# will show:
# Forwarding https://xxxxx.ngrok.io -> localhost:3000
# remember the https://xxxxx.ngrok.io for later use

# create env file
cp .sample.env .env
# then edit .env, set proper setting according to the tip in .env

# run local dev server
npm start

# and goto your RingCentral Engage digital -> admin -> webhook setting page,
# set URL to https://xxxxx.ngrok.io/dimelo-demo-endpoint
# then set the webhook to be active, not staging and save

```

## Test bot

- Send a email to your predefined email source address, then bot will auto reply with `This is a auto reply by bot`.
- Edit `src/handler.js`'s `reply(event)` function to set your own reply logic.

## License

MIT
  