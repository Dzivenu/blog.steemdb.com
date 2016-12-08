## SteemDB Blog

A basic blog for [steemdb.com](https://steemdb.com) using reprint.


### resources/config/config.yaml
```
# reprint config
reprint:
  # Choose the locale to localize content for
  locale: 'en'

# blog config
blog:
  # Choose a theme by name
  theme: 'steemdb'
  title: 'SteemDB Blog'
  subtitle: ''
  # Filter the content to
  filters:
    # Accounts to load activity of
    accounts:
      'jesta':
        - post
    tags:
      - steemdb

# steemd connection
steem:
  # Steem Node to retreive data
  host: 'http://node.steem.ws'
```

### resources/config/routes.yaml
```
config.routes:
  # Homepage route to handle the options provided in the configuration
  homepage:
    name: 'homepage'
    pattern: /
    method: ['get']
    controller: 'Reprint\Controller\Home::homeAction'

  # View Post
  post_view:
    name: 'post_view'
    pattern: /{category}/@{author}/{permlink}
    method: ['get']
    controller: 'Reprint\Controller\Blog::postAction'
```
