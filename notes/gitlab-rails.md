---
tags: [ruby]
title: gitlab-rails
created: '2019-12-30T13:15:51.142Z'
modified: '2020-09-02T17:48:52.203Z'
---

# gitlab-rails

## usage
```sh
gitlab-rails COMMAND

generate        # Generate new code (short-cut alias: "g")
console         # Start the Rails console (short-cut alias: "c")
server          # Start the Rails server (short-cut alias: "s")
test            # Run tests except system tests (short-cut alias: "t")
test:system     # Run system tests
new             # Create a new Rails application. "rails new my_app" creates a new application called MyApp in "./my_app"

```

### console
```sh
gitlab-rails console

gitlab-rails console -e production
```
```ruby
# Reset root/admin password
# find the user:
# user = User.find_by(email: "admin@example.com")
# user = User.find_by(username: "root")
# user = User.find_by(name: "Administrator")
# user = User.find_by(admin: true)
user = User.find_by(username: "root")
user.password = 'secret_pass'
user.password_confirmation = 'secret_pass'
user.save!

# Re-enable standard login
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
- https://docs.gitlab.com/ee/security/reset_root_password.html
- https://gist.github.com/dnozay/188f256839d4739ca3e4
- https://docs.gitlab.com/12.5/ee/api/settings.html
- https://gitlab.com/gitlab-org/omnibus-gitlab/issues/561
