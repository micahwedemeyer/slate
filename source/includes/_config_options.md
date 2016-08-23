# Configuration Options

```ruby
# You can change these settings if necessary, but it's not recommended
use Wrenchmode::Rack,
  jwt: "your-really-long-jwt",
  force_open: false,
  ignore_test_mode: true,
  disable_local_wrench: false,
  check_delay_secs: 5
```

```javascript
// You can change these settings if necessary, but it's not recommended
app.use(wrenchmodeExpress({
  jwt: "your-really-long-jwt",
  forceOpen: false,
  ignoreTestMode: true,
  disableLocalWrench: false,
  checkDelaySecs: 5
}));
```
When instantiating the middleware, you can set the following options:

Option | Usage | Default
---------- | ------- | ------
Force Open | Set to true to force the middlware layer to allow all requests through, regardless of project status on Wrenchmode.com. Effectively disables the middleware. | false
Ignore Test Mode | (Coming soon...) Set to false to if you want the middleware to respond to a project that is in Test mode on Wrenchmode.com This can be useful if you want to test Wrenchmode in a development or staging environment prior to deploying to production. | true
Disable Local Wrench | (Coming soon...) Set to true if you want to disable LocalWrench mode, where the Wrenchmode page is served on your domain. Disabling it will instead force a redirect to the Wrenchmode.com domain. Note: Unless you explicitly want this behavior, it's best to leave this at the default. | false
Check Delay (Seconds) | Change this to modify the rate at which the middleware polls Wrenchmode for updates. Unlikely that this needs anything faster than the default. | 5

