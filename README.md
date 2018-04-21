# wordup-demo
Demo of roots.io Wordpress  tools

Download it and `$ cd trellis`, then run `$ vagrant up`.

This is the shortcut if something doesn't work please clone trellis, bedrock and then sage inside bedrock by:

`git clone --depth=1 git@github.com:roots/trellis.git && rm -rf trellis/.git`
`git clone --depth=1 git@github.com:roots/bedrock.git site && rm -rf site/.git`

sudo apt install php7.2-mbstring
sudo apt install php7.2-simplexml

inside `site/web/app/themes` (you need to have composer installed):

`composer create-project roots/sage sage-demo`

then inside:

`composer install`

and finally:

`npm install`

polish language in WP Bedrock admin:

modify composer.json in `site/`

add:

```
    {
        "type": "composer",
        "url": "https://wpackagist.org"
    }
```

to `repositories` then:

`"koodimonni-language/pl_pl": "*",`

to `reaquire` and finally:

```
    "dropin-paths": {
        "htdocs/wp-content/languages/": ["vendor:koodimonni-language"],
        "htdocs/wp-content/languages/plugins/": ["vendor:koodimonni-plugin-language"],
        "htdocs/wp-content/languages/themes/": ["vendor:koodimonni-theme-language"],
        "htdocs/wp-content/": ["package:wpackagist-plugin/wp-redis:object-cache.php"]
    },
```
to `extra`