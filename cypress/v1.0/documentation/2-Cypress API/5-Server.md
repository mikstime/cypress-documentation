slug: api-server
excerpt: Permanently override default server options

### [Cypress.Server.defaults( *object* )](#usage)

Any configuration you pass to [`cy.server`](http://on.cypress.io/api/server) will only persist until the end of the test. If you find yourself passing the same configuration to each [`cy.server`](http://on.cypress.io/api/server), then you might want to permanently change the default options for all [`cy.server`](http://on.cypress.io/api/server) instances.

[block:callout]
{
  "type": "info",
  "body": "A great place to put this configuration is in your `tests/_support/spec_helper.js` file, since it is loaded before any test files are evaluated."
}
[/block]

```javascript
// pass anything here you'd normally pass
// to cy.server(). These options will be the new defaults.
Cypress.Server.defaults({
  delay: 500,
  force404: false,
  whitelist: function(xhr){
    // handle custom logic for whitelisting
  }
})
```