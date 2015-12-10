# CasperJS For PhantomJS 2.0


CasperJS is a navigation scripting & testing utility for [PhantomJS](http://www.phantomjs.org/)
and [SlimerJS](http://slimerjs.org/).

**This project is created to set up casperjs environment with phantomjs 2.0 **
It followed the [Casperjs](https://github.com/n1k0/casperjs) git repository.

## How to install

>  **For windows: **
>- `npm install git://github.com/flyHe/casperjs`
>
>**For mac: **
>
>- `npm install git://github.com/flyHe/casperjs`
>- `cd node_modules/casperjs/phantom/`
>- `chmod +x phantomjs`
>
>**For RHEL 6: **
>- in progress

## Sample test

First install CasperJS

Sample test to see if some dropdown can be opened:

```javascript
casper.test.begin('a twitter bootstrap dropdown can be opened', 2, function(test) {
    casper.start('http://getbootstrap.com/2.3.2/javascript.html#dropdowns', function() {
        test.assertExists('#navbar-example');
        this.click('#dropdowns .nav-pills .dropdown:last-of-type a.dropdown-toggle');
        this.waitUntilVisible('#dropdowns .nav-pills .open', function() {
            test.pass('Dropdown is open');
        });
    }).run(function() {
        test.done();
    });
});
```
Then add test scripts into package.json
```javascript
{
  "name": "twitter-dropdown-test",
  "version": "0.1.0",
  "private": true,
  "scripts": {
    "test": "casperjs test twitter-dropdown-test.js"
  },
  "devDependencies": {
    "casperjs": "git://github.com/flyHe/casperjs"
  }
}
```

Run the script:

> `npm run test`

## Other
- casperjs git:([casperjs](https://github.com/n1k0/casperjs))https://github.com/n1k0/casperjs
- casperjs official website:([casperjs](http://casperjs.org/))http://casperjs.org/
- casperjs API Documentation:([API](http://docs.casperjs.org/en/latest/modules/index.html))http://docs.casperjs.org/en/latest/modules/index.html
