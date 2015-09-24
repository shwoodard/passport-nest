# Passport Nest Strategy

Strategy to authenticate with Nest via OAuth2 in Passport

Get your API key at the [Nest Developer Portal][portal].

For more details, read the [Nest authorization documentation][auth-docs].

## Install

``` sh
npm install passport-nest
```

## Example

See [`examples/`][examples] for a complete working example.

## Usage

Assuming an [express](http://expressjs.com/) app:

``` js
passport.use(new NestStrategy({
  clientID: NEST_ID,
  clientSecret: NEST_SECRET
}));

app.get('/auth/nest', passport.authenticate('nest'));
app.get('/auth/nest/callback', passport.authenticate('nest', {}),
  function(req, res) {
    // token is in req.user.accessToken
});
```

## Contributing

Contributions are always welcome and highly encouraged.

See [CONTRIBUTING](CONTRIBUTING.md) for more information on how to get started.

## License

Apache 2.0 - See [LICENSE](LICENSE) for more information.

[portal]: https://developer.nest.com/clients
[auth-docs]: https://developer.nest.com/documentation/cloud/authorization-overview
[examples]: https://github.com/nestlabs/passport-nest/tree/master/examples
