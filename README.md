# Plyr Ads
Preroll plugin for the awesome [Plyr](https://plyr.io) media player.

[Checkout the demo](https://ferdiemmen.github.io/plyr-ads/)

## Installation
    $ npm install plyr-ads --save

## Run demo
    $ gulp demo

## Features
- **Google IMA** - works with the Google IMA SDK
- **Responsive** - works with any screen size
- **SASS** - to include in your build processes

## Features currently being developed
- Youtube video as preroll

## Planned features (in any order)
- VAST support
- Midroll and postroll
- Api
- Events to hook into like: 'started', 'midpoint', 'ended', etc...
...and whatever else has been raised in [issues](https://github.com/ferdiemmen/plyr-ads/issues)

If you have any cool ideas or features, please let me know by [creating an issue](https://github.com/ferdiemmen/plyr-ads/issues/new) or, of course, forking and sending a pull request.

## Initialising

PlyrAds extends on one or many Plyr instance. **Make sure to include the Google IMA SDK and ofcourse Plyr.**

**Html**
```html
<script type="text/javascript" src="https://imasdk.googleapis.com/js/sdkloader/ima3.js"></script>
```

**Javascript**
```javascript
var player = plyr.setup();
plyrAds.setup(player, options);
```

## Options
Options must be passed as an object to the `setup()` method as above or as JSON in `data-plyr` attribute on each of your target elements:

```javascript
var player = plyr.setup();
plyrAds.setup(player, {
  adTagUrl: 'https://pubads.g.doubleclick.net/gampad/ads?sz=640x480&iu=/124319096/external/single_ad_samples&ciu_szs=300x250&impl=s&gdfp_req=1&env=vp&output=vast&unviewed_position_start=1&cust_params=deployment%3Ddevsite%26sample_ct%3Dlinear&correlator='
});
```

<table class="table" width="100%">
  <thead>
    <tr>
      <th width="20%">Option</th>
      <th width="15%">Type</th>
      <th width="15%">Default</th>
      <th width="50%">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>adTagUrl</code></td>
      <td>String</td>
      <td><code>''</code></td>
      <td>**required** A Google IMA compliant ad tag url.</td>
    </tr>
    <tr>
      <td><code>skipButton</code></td>
      <td>Object</td>
      <td><code>{enabled: true, text: 'Skip ad', delay: 10}</code></td>
      <td>To let the visitor skip the ad at a certain point. See <a href="#skipbutton-options">below</a></td>
    </tr>
  </tbody>
</table>  

## Skip button options

<table class="table" width="100%" id="skipbutton-options">
  <thead>
    <tr>
      <th width="20%">Option</th>
      <th width="15%">Type</th>
      <th width="15%">Default</th>
      <th width="50%">Description</th>
    </tr>
  </thead>
    <tbody>
    <tr>
      <td><code>enabled</code></td>
      <td>Boolean</td>
      <td><code>true</code></td>
      <td>Toggles if the skip button should be enabled.</td>
    </tr>
    <tr>
      <td><code>text</code></td>
      <td>String</td>
      <td><code>'Skip ad'</code></td>
      <td>The text shown on the skip button.</td>
    </tr>
    <tr>
      <td><code>delay</code></td>
      <td>Integer (seconds)</td>
      <td><code>10</code></td>
      <td>Countdown timer for when the visitor is able to skip the ad.</td>
    </tr>
  </tbody>
</table>

## Thanks
Thanks to Sam Potts and all his contributors who build the awesome [Plyr](https://plyr.io/) video player.

## Copyright and License
[The MIT license](license.md).
