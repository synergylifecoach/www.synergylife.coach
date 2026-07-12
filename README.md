# www.synergylife.coach

## initial setup

- create a new public repository named `www.synergylife.coach`
- go to https://github.com/synergylifecoach/www.synergylife.coach/settings and configure the new repo
- `mkdir www.synergylife.coach`
- `chmod 0755 www.synergylife.coach`
- `cd www.synergylife.coach`
- `git init`
- `git config user.name synergylifecoach`
- `git config user.email 'synergylifecoach@users.noreply.github.com'`
- `git config pull.ff only`
- `git add -A`
- `git commit -m 'first commit'`
- `git remote add origin https://github.com/synergylifecoach/www.synergylife.coach.git`
- `git switch --orphan gh-pages`
- `git commit --allow-empty --allow-empty-message`
- `git push -u origin gh-pages`
- `git switch master`
- `git push -u origin master`
- go to https://github.com/synergylifecoach/www.synergylife.coach/settings and ensure master is the default branch

## new user setup

- ssh-keygen -t ed25519-sk -O resident -O verify-required -O application=ssh:synergylifecoach -C 'github_synergylifecoach' -f ~/.ssh/id_ed25519_sk_rk_github_synergylifecoach
- add to `~/.ssh/config`
```
Host synergylifecoach.github.com
  Hostname github.com
  User git
  IdentityFile ~/.ssh/id_ed25519_sk_rk_github_synergylifecoach
```
- `git clone https://github.com/synergylifecoach/www.synergylife.coach.git`
- `git config user.name synergylifecoach`
- `git config user.email 'synergylifecoach@users.noreply.github.com'`
- `git remote set-url --push origin git@synergylifecoach.github.com:synergylifecoach/www.synergylife.coach.git`
- `git fetch --all`
- `git branch --track gh-pages origin/gh-pages`

## dev notes

- `find www/ -type f -exec chmod 0644 {} \;`
- `find www/ -type d -exec chmod 0755 {} \;`

bundle install;

cd www;

JEKYLL_ENV=development bundle exec jekyll serve --host 0.0.0.0;

or

JEKYLL_ENV=production bundle exec jekyll build;

for example:

cd /path-to/www.synergylife.coach/www/ && git pull && bundle install && JEKYLL_ENV=production bundle exec jekyll build
