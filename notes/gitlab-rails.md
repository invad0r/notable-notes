---
tags: [ruby]
title: gitlab-rails
created: '2019-12-30T13:15:51.142Z'
modified: '2023-03-16T09:11:52.887Z'
---

# gitlab-rails

## usage

```sh
gitlab-rails generate        # alias: "g", generate new code
gitlab-rails console         # alias: "c", start the Rails console
gitlab-rails server          # alias: "s", start the Rails server
gitlab-rails test            # alias: "t", run tests except system tests
gitlab-rails test:system     # run system tests
gitlab-rails new APP_NAME    # create new Rails app
```

## console

```sh
gitlab-rails console

gitlab-rails console -e production
```

```ruby
# Reset root/admin password

# find the user
user = User.find_by(email: "admin@example.com")
user = User.find_by(username: "root")
user = User.find_by(name: "Administrator")
user = User.find_by(admin: true)
user = User.find_by(username: "root")

user.password = 'secret_pass'
user.password_confirmation = 'secret_pass'
user.save!

# re-enable standard login
appsettings = ApplicationSetting.find_by(password_authentication_enabled_for_web: false)  # locate application settings
appsettings.password_authentication_enabled_for_web = true
appsettings.save!

Gitlab::LDAP::Config.providers
```

### dbconsole

> Start a console for the database specified in config/database.yml

```sh
gitlab-rails dbconsole
gitlab-rails db             # short-cut alias
```

```sql
SELECT * FROM pg_stat_ssl;  /* check whether clients are using SSL, you can issue this SQL query */

/* Show all unique JiraService properties */
SELECT DISTINCT properties FROM services WHERE type LIKE '%JiraService%';

/* View the first 5 Lines */
SELECT id,properties FROM services WHERE type LIKE '%JiraService%' LIMIT 5;

/* Replace an old URL */
UPDATE services 
SET properties = replace(properties, 'https://oldproject.atlassian.net', 'https://newproject.atlassian.net') 
WHERE type LIKE '%JiraService%';

/* Replace an old authentication token  */
UPDATE services 
SET properties = replace(properties, 'oldtoken', 'newtoken') 
WHERE type LIKE '%JiraService%';

/* Set the whole config string */
UPDATE services 
SET properties = '{"api_url":"","jira_issue_transition_id":"","password":"newapitoken","url":"https://someproject.atlassian.net","username":"yourusername"}' 
WHERE type LIKE '%JiraService%';
```

## see also

- [[ruby]]
- [[ldapsearch]]
- [docs.gitlab.com/ee/security/reset_root_password](https://docs.gitlab.com/ee/security/reset_root_password.html)
- [gist.github.com/dnozay/188f256839d4739ca3e4](https://gist.github.com/dnozay/188f256839d4739ca3e4)
- [docs.gitlab.com/12.5/ee/api/settings](https://docs.gitlab.com/12.5/ee/api/settings.html)
- [gitlab.com/gitlab-org/omnibus-gitlab/issues/561](https://gitlab.com/gitlab-org/omnibus-gitlab/issues/561)
