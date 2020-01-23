# Jekyll Mentions

@mentionable support for your Jekyll site

[![Gem Version](https://badge.fury.io/rb/jekyll-mentions.svg)](http://badge.fury.io/rb/jekyll-mentions)
[![Build Status](https://travis-ci.org/jekyll/jekyll-mentions.svg?branch=master)](https://travis-ci.org/jekyll/jekyll-mentions)

## Usage

Add the following to your site's `Gemfile`

```
gem 'jekyll-mentions'
```

And add the following to your site's `_config.yml`

```yml
plugins:
  - jekyll-mentions
```

Note: if `jekyll --version` is less than `3.5` use:

```yml
gems:
  - jekyll-mentions
```

In any page or post, use @mentions as you would normally, e.g.

```markdown
Hey @benbalter, what do you think of this?
```

**Note**: Jekyll Mentions simply turns the @mentions into links, it does not notify the mentioned user.

## Configuration

Have your own social network? No problem. We allow you to configure the base URL of all the mentions.

To change it, add the following to your Jekyll configuration:

```yaml
jekyll-mentions:
  base_url: https://twitter.com
```

If you're lazy like me, you can use this shorthand:

```yaml
jekyll-mentions: https://twitter.com
```

An example of Twitter mentions using jekyll-mentions: 

```yaml
plugins:
  - jekyll-mentions

jekyll-mentions:
  base_url: https://twitter.com
```  

Et voilà! Your mentions will now use that base URL instead of the default of `https://github.com`.

## Advanced

_This is the documention for a new feature, [support per-@ overrides](https://github.com/bmann/jekyll-mentions/issues/1). This repo and its issues is where this will be worked on, and then a PR will be made to upstream_

You can configure per-@ overrides and extended information in your `_data` folder.

1. Create a `mentions.json` file in your data folder
2. Make entries!

eg:

```
{
  "@boris": { "network": "https://linkedin.com" },
  "@bmann": { "network": "https://twitter.com"},
  "@borismann": {
    "name": "Boris Mann",
    "url": "https://blog.bmannconsulting.com",
    "photo": "https://blog.bmannconsulting.com/images/bmann_hair_orange_256x256.png"
  }
}
```

Any @-names that are defined in this file will be linked to their custom networks -- or even just linked to an arbitrary URL. This can also be used to create little mini profiles.

Consider using the [h-card property names](https://indieweb.org/h-card) or [person tags](https://indieweb.org/person-tag).



