<h1 align="center">Whatsapp Push Notify Action 🚀</h1>
<p>
  <img alt="Version" src="https://img.shields.io/badge/version-1.0-blue.svg?cacheSeconds=2592000" />
  <a href="https://github.com/ishween/whatsapp-push-notify-action/blob/master/LICENSE" target="_blank">
    <img alt="License: GNU GPLv3" src="https://img.shields.io/badge/License-GPLv3-blue.svg" />
  </a>
</p>

> A github action which sends a custom Whatsapp message using Twilio bot, forked from https://github.com/ishween/whatsapp-push-notify-action

### Usage
1. Create account in twilio [here](https://www.twilio.com/).  
2. From your twilio dashboard fetch Account Sid and Auth Token.  
3. To encrypt them, create new secrets in your repository named ```account_sid, auth_token, to_whatsapp_no``` and give it's value.  
4. Create a ```.github/workflows/whatsapp-push-notify-action.yml```.  
5. Add the following properties to ```whatsapp-push-notify-action.yml``` file   

```name: When a push occurs in the master branch, a private message is sent on the Whatsapp.
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@master
      - name: whatsapp-notify
        id: whatsapp-notify
        env:
          account_sid: ${{ secrets.account_sid }}
          auth_token: ${{ secrets.auth_token }}
          to_whatsapp_no: ${{ secrets.to_whatsapp_no }}


        uses: khaled-ibtikar/whatsapp-push-notify-action@master
    
```

## 📝 License

Copyright © 2020 [Ishween Kaur](https://github.com/ishween).<br/>
This project is [GNU GPLv3](https://github.com/ishween/whatsapp-push-notify-action/blob/master/LICENSE) licensed.

***


