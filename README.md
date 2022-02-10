# wkhtmltopdf Buildpack

This is a [buildpack][0] for bundling a compatible [wkhtmltopdf][1] binary with
your environment.

## Versions

* Buildpack:   `0.2`
* wkhtmltopdf: `0.12.3` by default

## Usage

[Add this buildpack][2] to your Scalingo application to install the `wkhtmltopdf`
and `wkhtmltoimage` binaries, and the corresponding library `libwkhtmltox`.
You need to setup your application to use a multi-buildpack environment.
Then, your application need both the wkhtmltopdf buildpack and the one for
the technology you use in your application. Here is an example using the Ruby buildpack:

```bash
$ scalingo env-set 'BUILDPACK_URL=https://github.com/Scalingo/multi-buildpack.git'
$ echo 'https://github.com/Scalingo/wkhtmltopdf-buildpack' >> .buildpacks
$ echo 'https://github.com/Scalingo/ruby-buildpack' >> .buildpacks
$ git add .buildpacks
$ git commit -m 'Add multi-buildpack'
```

If you want to use a `wkhtmltopdf` version other than 0.12.3, set
`WKHTMLTOPDF_VERSION`:

```bash
scalingo env-set WKHTMLTOPDF_VERSION="0.12.4"
```

## Troubleshooting

If you run into issues when trying to deploy with this buildpack, make sure your
app is running on the stack `scalingo` or `scalingo-18`. You can check this
with:

```bash
$ scalingo apps-info
```

[0]: http://doc.scalingo.com/buildpacks/
[1]: http://wkhtmltopdf.org/
[2]: https://doc.scalingo.com/platform/deployment/buildpacks/multi
