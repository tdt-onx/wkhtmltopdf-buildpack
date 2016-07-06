# wkhtmltopdf Buildpack

This is a [buildpack][0] for bundling a compatible [wkhtmltopdf][1] binary with your environment.

## Versions

* Buildpack:   `0.2`
* wkhtmltopdf: `0.12.2.1`

## Usage

This buildpack only installs wkhtmltopdf, it isn't very useful by itself. You'll probably want to use it as part of a multi-buildpack. Here is an example using the Ruby buildpack.

```bash
$ scalingo env-set 'BUILDPACK_URL=https://github.com/Scalingo/multi-buildpack.git'
$ echo 'https://github.com/Scalingo/wkhtmltopdf-buildpack' >> .buildpacks
$ echo 'https://github.com/Scalingo/ruby-buildpack' >> .buildpacks
$ git add .buildpacks
$ git commit -m 'Add multi-buildpack'
```

[0]: http://doc.scalingo.com/buildpacks/
[1]: http://wkhtmltopdf.org/
