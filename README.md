bestcaptchasolver - Bestcaptchasolver nodeJS client API library
===============================================================

bestcaptchasolver-nodejs is a super easy to use bypass captcha nodeJS API wrapper for bestcaptchasolver.com captcha service

## Installation

    npm install bestcaptchasolver

or

    git clone https://github.com/bestcaptchasolver/bestcaptchasolver-nodejs

## Usage

Set access token, before using the library

``` javascript
var bestcaptchasolver = require('bestcaptchasolver');
bestcaptchasolver.set_access_token('access token from /account');
```


**Get balance**

``` javascript
bestcaptchasolver.account_balance().then(function (balance) {
    console.log('Balance: $', balance);
})
```

**Submit image captcha**

The submission of image captcha is done by sending us the image as a b64 encoded string.
There's the `case_sensitive` parameter as well, which is optional, and by default `false`

``` javascript
bestcaptchasolver.submit_captcha({
    b64image: captcha,
    //case_sensitive: true,                 // optional defaults to false
    //affiliate_id: 'ID of affiliate'       // optional
});
```

**Submit reCAPTCHA**

The `page_url` and `site_key` are the only requirements. There are other optional parameters though.

``` javascript
bestcaptchasolver.submit_recaptcha({
    page_url: 'bestcaptchasolver.com',
    site_key: '6LfGJmcUAAAAALGtIb_FxC0LXm_GwOLyJAfbbUCN',
    //user_agent: 'Your user agent',    // optional
    //proxy: 'abc:def@12.35.56.78:4321 or 12.35.56.78:4321',        // optional
    //type: '1', // 1 - normal, 2 - invisible, 3 - v3, optional and defaults to 1
    //v3_action: '',   // v3 action, optional
    //v3_min_score: '0.3', // if v3, score to target, optional
    //affiliate_id: 'ID of affiliate'       // optional
});
```

Just like the image submission method, this method also returns an ID, which is then used
to get the text or gresponse.

**Retrieve**

Retrieval is done by passing the ID

``` javascript
bestcaptchasolver.retrieve_captcha(id);
```

This method returns an object, with the `text` attribute for image captcha or `gresponse` if submission was done for reCAPTCHA

**If submitted with proxy, get proxy status**

```javascript
log('Recaptcha response: ' + data.gresponse);
log('Proxy status: ' + data.proxy_status);
```
**Set captcha bad**

```javascript
bestcaptchasolver.set_captcha_bad(captcha_id);
```

## Examples
Check the example/example.js

## License
API library is licensed under the MIT License

## More information
More info about the API parameters can be found [here](https://bestcaptchasolver.com/captchabypass-api)


<sup><sub>captcha, bypasscaptcha, decaptcher, decaptcha, 2captcha, deathbycaptcha, anticaptcha, 
bypassrecaptchav2, bypassnocaptcharecaptcha, bypassinvisiblerecaptcha, captchaservicesforrecaptchav2, 
recaptchav2captchasolver, googlerecaptchasolver, recaptchasolverpython, recaptchabypassscript</sup></sub>

