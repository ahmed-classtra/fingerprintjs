<p align="center">
  <a href="https://fingerprint.com">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="resources/logo_light.svg" />
      <source media="(prefers-color-scheme: light)" srcset="resources/logo_dark.svg" />
      <img src="resources/logo_dark.svg" alt="FingerprintJS logo" width="312px" />
    </picture>
  </a>
</p>
<p align="center">
  <a href="https://github.com/fingerprintjs/fingerprintjs/actions/workflows/test.yml">
    <img src="https://github.com/fingerprintjs/fingerprintjs/actions/workflows/test.yml/badge.svg?branch=v2" alt="Build status">
  </a>
  <a href="https://www.npmjs.com/package/@fingerprintjs/fingerprintjs">
    <img src="https://img.shields.io/npm/v/@fingerprintjs/fingerprintjs.svg" alt="Current NPM version">
  </a>
  <a href="https://www.npmjs.com/package/@fingerprintjs/fingerprintjs">
    <img src="https://img.shields.io/npm/dm/@fingerprintjs/fingerprintjs.svg" alt="Monthly downloads from NPM">
  </a>
  <a href="https://www.jsdelivr.com/package/npm/@fingerprintjs/fingerprintjs">
    <img src="https://img.shields.io/jsdelivr/npm/hm/@fingerprintjs/fingerprintjs.svg" alt="Monthly downloads from jsDelivr">
  </a>
</p>
<p align="center">
  <a href="https://discord.gg/39EpE2neBg">
    <img src="https://img.shields.io/discord/852099967190433792?style=for-the-badge&label=Discord&logo=Discord&logoColor=white" alt="Discord server">
  </a>
</p>

FingerprintJS is a browser fingerprinting library that queries browser attributes and computes a hashed visitor identifier from them. Unlike cookies and local storage, a fingerprint stays the same in incognito/private mode and even when browser data is purged.

[View Our Demo](https://fingerprintjs.github.io/fingerprintjs/).

## Quick start

```html
<script>
  // Initialize the agent at application startup.
  const fpPromise = import('https://openfpcdn.io/fingerprintjs/v3')
    .then(FingerprintJS => FingerprintJS.load())

  // Get the visitor identifier when you need it.
  fpPromise
    .then(fp => fp.get())
    .then(result => {
      // This is the visitor identifier:
      const visitorId = result.visitorId
      console.log(visitorId)
    })
</script>
```

[Run this code](https://stackblitz.com/edit/fpjs-3-cdn?file=index.html&devtoolsheight=100)

📕 [Full documentation](docs/api.md)

## Use the free Pro version to get 99.5% identification accuracy

[Fingerprint Pro](https://fingerprint.com/github/) is a professional visitor identification service that processes all information server-side and transmits it securely to your servers using server-to-server APIs.
Pro combines browser fingerprinting with vast amounts of auxiliary data (IP addresses, time of visit patterns, URL changes and more) to be able to reliably deduplicate different users that have identical devices, resulting in the 99.5% identification accuracy. Fingerprint Pro is available for Web, Android, iOS and other platforms.

**Pro plans start at $0/month - no credit card required.**

<p align="center">
  <a href="https://fingerprint.com/github/">
    <img src="resources/pro_screenshot.png" alt="Pro screenshot" width="697px" />
  </a>
</p>

Full product comparison:

<table>
  <thead>
    <tr>
      <th></th>
      <th align="center">Open Source</th>
      <th align="center">Pro</th>
    </tr>
  </thead>
  <tbody>
    <tr><td colspan="3"><h4>Core Features</h4></td></tr>
    <tr><td>100% open source</td><td align="center">yes</td><td align="center">no<sup>1</sup></td></tr>
    <tr><td>Accuracy</td><td align="center">up to 60%</td><td align="center"><b>99.5%</b></td></tr>
    <tr><td><b>Mobile Native SDKs</b><br/><i>Android, iOS, Flutter, React Native and more</i></td><td align="center">-</td><td align="center"><b>✓</b></td></tr>
    <tr><td><b>Standard fingerprint signals</b><br/><i>screen, os, device name</i></td><td align="center">✓</td><td align="center">✓</td></tr>
    <tr><td><b>Advanced fingerprint signals</b><br/><i>canvas, audio, fonts</i></td><td align="center">✓</td><td align="center">✓</td></tr>
    <tr><td><b>ID type</b></td><td align="center">fingerprint</td><td align="center">visitorID<sup>2</sup></td></tr>
    <tr><td><b>ID lifetime</b></td><td align="center">several weeks</td><td align="center">months/years</td></tr>
    <tr><td><b>ID origin</b></td><td align="center">client</td><td align="center">server</td></tr>
    <tr><td><b>ID collisions</b></td><td align="center">common</td><td align="center">rare</td></tr>
    <!-- -->
    <tr><td colspan="3"><h4>Additional Features</h4></td></tr>
    <tr><td><b>Incognito mode detection</b><br/><i>works in all modern browsers - see our full list of <a href="https://dev.fingerprint.com/docs/browser-support/" target="_blank">browsers supported</a></i></td><td align="center">–</td><td align="center">✓</td></tr>
    <tr><td><b>Server-side accuracy increase</b><br/><i>based on additional server-side signals, such as TLS crypto support, ipv4/v6 data and others</i></td><td align="center">–</td><td align="center">✓</td></tr>
    <tr><td><b>Query API & realtime Webhooks</b><br/><i>build flexible workflows</i></td><td align="center">–</td><td align="center">✓</td></tr>
    <tr><td><b>Ability to evade ad blockers</b></td><td align="center"><a href="docs/evade_ad_blockers.md" target="_blank">supported (NPM, own hosting)</a></td><td align="center"><a href="https://dev.fingerprint.com/docs/subdomain-integration" target="_blank">supported (NPM + subdomain)</a></td></tr>
    <tr><td><b>Geolocation</b><br/><i>based on IP address</i></td><td align="center">–</td><td align="center">✓</td></tr>
    <!-- -->
    <tr><td colspan="3"><h4>Operations</h4></td></tr>
    <tr><td><b>Data security</b></td><td align="center">Your infrastructure</td><td align="center">Encrypted at rest</td></tr>
    <tr><td><b>Storage</b></td><td align="center">Your infrastructure</td><td align="center">Unlimited up to 1 yr</td></tr>
    <tr><td><b>Regions</b></td><td align="center">Your infrastructure</td><td align="center">Hosting in US, EU and Mumbai</td></tr>
    <tr><td><b>Compliance</b></td><td align="center">Your infrastructure</td><td align="center">GDPR, CCPA compliant<sup>3</sup></td></tr>
    <tr><td><b>SLA</b></td><td align="center">No SLA</td><td align="center">99.9% Uptime</td></tr>
    <tr><td><b>Support</b></td><td align="center">GitHub community</td><td align="center">Support team via email, chat, and call-back within 1 business day</td></tr>
  </tbody>
</table>

<sub>1. Pro uses the open source fingerprinting library as well as proprietary technology for increased accuracy and identifier stability.</sub>

<sub>2. VisitorIDs, in comparison to fingerprints, include server side techniques, are deduplicated and utilize fuzzy matching to result in a more accurate and stable identifier. Fingerprint hashes rely on an exact match across all browser attributes, making them less stable across > 4 week time intervals.</sub>

<sub>3. Fingerprint Pro is GDPR and CCPA compliant as the data processor. You still need to be compliant as the data controller and use the identification for fraud prevention under legitimate interest or ask for user consent.</sub>

Pro result example:

```js
{
  "requestId": "HFMlljrzKEiZmhUNDx7Z",
  "visitorId": "kHqPGWS1Mj18sZFsP8Wl",
  "visitorFound": true,
  "confidence": { "score": 0.995 },
  "incognito": false,
  "browserName": "Chrome",
  "browserVersion": "92.0.4515.107",
  "os": "Mac OS X",
  "osVersion": "10.15.6",
  "device": "Other",
  "ip": "192.65.67.131",
  "ipLocation": {
    "accuracyRadius": 100,
    "latitude": 37.409657,
    "longitude": -121.965467
    // ...
  }
}
```

🍿 [Live demo](https://fingerprint.com/demo)

⏱ [How to upgrade from Open Source to Pro in 30 seconds](https://dev.fingerprint.com/v3/docs/migrating-from-open-source-v3)

📕 [Fingerprint Pro documentation](https://dev.fingerprint.com)

▶️ [Video: use Fingerprint Pro to prevent multiple signups](https://www.youtube.com/watch?v=jWX9P5_jZn8)

## Migrating from v2

- [Migration guide](docs/migrating_v2_v3.md)
- [V2 documentation](https://github.com/fingerprintjs/fingerprintjs/tree/v2)

## Version policy

See the compatibility policy for the API and visitor identifiers in the [version policy guide](docs/version_policy.md).

## Supported browsers

The library supports all popular browsers.
See more details and learn how to run the library in old browsers in the [browser support guide](docs/browser_support.md).

## Where to get support

Thanks to our [series B funding](https://fingerprint.com/blog/series-b/), we are happy to provide technical support for our open-source FingerprintJS library. We recommend using GitHub [Issues](https://github.com/fingerprintjs/fingerprintjs/issues) to submit bugs or [Discussions](https://github.com/fingerprintjs/fingerprintjs/discussions) to ask questions.
Using issues and discussions publicly will help the open-source community and other users with similar issues.
However, if you require private support, please email us at [oss-support@fingerprint.com](mailto:oss-support@fingerprint.com).

## Contributing

See the [contributing guidelines](contributing.md) to learn how to start a playground, test and build.

## Other products by Fingerprint

* [BotD -- Easy to use JavaScript bot detection](https://fingerprint.com/products/bot-detection/)
* [AEV -- Android App Environment Verification API](https://github.com/fingerprintjs/aev)
