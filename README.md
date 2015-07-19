# Heroku Buildpack Django Migrate

**N.B. This buildpack is *not* intended for production use.**

Heroku buildpack to run Django migrations on every deploy. This works well with Heroku's automatic deployments where you can push to your Git `develop` branch, for example, and have the changes automatically deployed to a staging app (w/o having to worry about database migrations).

## Setup

1. Set Heroku's default Python buildpack for your app

  ```bash
  heroku buildpacks:set https://github.com/heroku/heroku-buildpack-python
  ```

1. Add this buildpack

  ```bash
  heroku buildpacks:add https://github.com/andreipetre/heroku-buildpack-django-migrate
  ```

Now whenever you push to your Heroku app, it will run `python manage.py migrate` as part of the build process.
