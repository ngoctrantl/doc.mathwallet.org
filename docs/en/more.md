# More Q&A

### Q. How to know whether the address is opened by the dapp browser of Math Wallet ?

If there’s “MdsApp” in useragent, then it is visited by the browser of Math Wallet.

### Q. How to get more current wallet information, such as orientation / language / fullscreen, etc?

We will need math-js-sdk: [https://github.com/mathwallet/math-js-sdk](https://github.com/mathwallet/math-js-sdk)

### Q. How to debug a dApp within Math Wallet?

Please read: [http://blog.mathwallet.org/?p=154](http://blog.mathwallet.org/?p=154)

### Q. Does Math Wallet support testnet chain environment and account?

No, we do not support testnet.

### Q. How to open a dApp in landscape screen orientation?

There are 2 ways:

1 Math Wallet team can help you config your dApp opened in landscape mode by default, you just need to inform us.

2 You can use math-js-sdk: [https://github.com/mathwallet/math-js-sdk](https://github.com/mathwallet/math-js-sdk), issue the orientation() function.

### Q. How to open a dApp in full screen mode?

You can use math-js-sdk: [https://github.com/mathwallet/math-js-sdk](https://github.com/mathwallet/math-js-sdk), issue the fullScreen(1) function.
And we suggest you add a 'Close' button in your dApp, which need to issue fullScreen(0) or close() function.

### Q. How to get DeviceID through Math SDK?

You can use math-js-sdk: [https://github.com/mathwallet/math-js-sdk](https://github.com/mathwallet/math-js-sdk), issue the getAppInfo() function.

### Q. How to get the current language in the dApp?

Sample code below:

```
/**
 * @return {string} country code: cn / ko / en
 */
var getNavLanguage = function(){
  navLanguage = (navigator.language || navigator.browserLanguage ).toLowerCase();
  switch(navLanguage)
  {
  case 'zh-cn' || 'zh-tw' || 'zh-hk':
    navLanguage = 'cn';
    break;
  case 'ko':
    navLanguage = 'ko'
    break;
  default:
    navLanguage = 'en';
  }
  return navLanguage;
}
```

### Q. Does MathWallet support DeepLink?

Yes. Sample URL below, change the dappUrl param as you need:

```
mathwallet://mathwallet.org?param={"action":"openUrl","protocol":"SimpleWallet","dappUrl":"https:\/\/gateway.eosdt.com\/","dappName":"MathWalletSDK-Demos","blockchain":"eosio","version":"1.0","callback":"mathwalletdemos:\/\/mathwalletsdk?action=openUrl","desc":"","dappIcon":""}
```

Currently Deeplink only supports Ethereum, EOS, EOS Force, TRON