
# ringcentral-engage-demo-email-auto-reply-bot

Demo bot that will auto reply every email with simple message for [RingCentral Engage(Dimelo)](https://www.dimelo.com/en/dimelo-digital).

## Prerequisites

- Nodejs 8.10+/npm, recommend using [nvm](https://github.com/creationix/nvm) to install nodejs/npm
- Yarn (`npm i -g yarn`)
- RingCentral Engage(Dimelo) accout, [request a demo](http://site.dimelo.com/en/demo#schedule-demo)

## Development & Quick start

```bash
# install dependencies
yarn

# run ngrok proxy
# since RingCentral Engage webhook need https endpoint,
# so we need a https proxy for RingCentral Engage webhook to visit our local server
yarn proxy
# will show:
# Forwarding https://xxxxx.ngrok.io -> localhost:3000

# create env file
cp .sample.env .env
# then edit .env, set proper setting,

# run local dev server
yarn start

# and goto your RingCentral Engage digital -> admin -> webhook setting page,
# set URL to https://xxxxx.ngrok.io/dimelo-demo-endpoint
# then set the webhook to be active and not staging

```

## Test bot

- Send a email to your predefined email source address, then bot will auto reply.
- Edit `src/handler.js`'s `reply(event)` function to set your own reply logic.

## License

MIT
  