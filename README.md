# Heroku Monorepo buildpack that copies an extra directory

Enter this buildpack, which is a copy of [heroku-buildpack-monorepo](https://github.com/lstoll/heroku-buildpack-monorepo) except it also copies another directory.

# Usage

1. Write a bunch of apps and scatter them through out your code base.
2. Realise that a support directory lives outside the target directory.
3. Create a bunch of Heroku apps.
4. For each app, set `APP_BASE=relative/path/to/app/root` and `SUPPORT_DIR=relative/path/to/your/support/dir`, and of course:
   `heroku buildpacks:add -a <app> https://github.com/parndt/heroku-buildpack-monorepo`
5. For each app, `git push git@heroku.com:<app> master`

Note: If you already have other buildpacks defined, you'll need to make sure that the heroku-buildpack-monorepo buildpack is defined first. You can do this by adding `-i 1` to the `heroku buildpacks:add` command.

# Authors

Andrew Gwozdziewycz <apg@heroku.com> and Cyril David <cyx@heroku.com> and now Lincoln Stoll <lstoll@heroku.com>
