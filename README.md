# Simple FAQ Theme for Hugo

You may use this theme for building very simple FAQs or note lists.

**IMPORTANT!** This theme is just a dummy port of [FAQ Template](http://codyhouse.co/gem/css-faq-template/) by CodyHouse. My only goal was to understand how to build a FAQ page with Hugo. The original template contains no styles for text formatting, so this theme also does. Wanna styles? Just fork the repo and write them! There are original sass and css files in static folder. Use custom styling feature to override original css. Don't forget to [share](//github.com/aerohub/hugo-faq-theme/pulls) your work with the community :smile:

## Screenshot

![Me screenshot](https://raw.githubusercontent.com/aerohub/hugo-faq-theme/master/images/screenshot.png)

## Demo

You can see it in action on [Hugo Themes site](http://themes.gohugo.io/theme/hugo-faq-theme/).

## Contents

- [Installation](#installation)
- [Getting started](#getting-started)
    - [Copying files](#copying-files)
	- [FAQ groups](#faq-groups)
    - [Configuring menu](#configuring-menu)
    - [Custom styling](#custom-styling)
    - [Test your site](#test-your-site)
- [Contributing](#contributing)
- [License](#license)


## Installation

Inside the folder of your new Hugo site run:

    $ mkdir themes
    $ cd themes
    $ git clone https://github.com/aerohub/hugo-faq-theme hugo-faq-theme

For more information read the official [setup guide](//gohugo.io/overview/installing/) of Hugo.


## Getting started

After installing the theme successfully it requires a just a few more steps to get your FAQ running.

### Copying files

Take a look inside the [`exampleSite`](//github.com/aerohub/hugo-faq-theme/tree/master/exampleSite) folder of this theme. You'll find a file called [`config.toml`](//github.com/aerohub/hugo-faq-theme/blob/master/exampleSite/config.toml) and a folder called [`data`](//github.com/aerohub/hugo-faq-theme/blob/master/exampleSite/data). To use them, copy the `config.toml` and `data` folder in the root folder of your Hugo site.

### FAQ groups

Go to `your-root/data/faq/groups/`. You'll see some `.toml` data files. Each of them contains questions/answers that grouped by common topic. Please pay attention on the filenames. Numbers in them are for ordering groups on the FAQ page and they are needed. But words are for your convenience. You may use only numbers, if you can keep all of your FAQ items structure in your head.

Now open any of these files with editor. E.g. `01-basics.toml`. On the top you'll see this:

	id = "basics"
	name = "Basics"

	[[items]]

	question = "How do I change my password?"
	answer = "Lorem ipsum dolor sit amet"

- `id` is the group anchor on the page. Keep it in mind, this is what you need to link with a corresponding menu item
- `name` is the name of your group
- `[[items]]` - pairs of questions and answers in this group

### Configuring menu

In the Menu section of your `config.toml` you will find similar structure. The difference is in ordering items: here they are ordered by weight.

	# Menu
	SectionPagesMenu = "main"

		[[menu.main]]
			name = "Basics"
			weight = 10
			url = "#basics"

- `name` is for naming a menu item
- `weight` is for ordering
- `url` is for linking a group (remember `id` from data file?)

### Custom Styling

To edit the css this theme uses, add your CSS to the assets folder then include it as part one of the `[params]` with the label `custom_css`. More information and an example can be found in the example [`config.toml`](//github.com/aerohub/hugo-faq-theme/blob/master/exampleSite/config.toml) file.

### Test your site

In order to see your site in action, run Hugo's built-in local server. 

    $ hugo server -w

Now enter `localhost:1313` in the address bar of your browser.

## Contributing

Did you found a bug or got an idea? Feel free to use the [issue tracker](//github.com/aerohub/hugo-faq-theme/issues). Or make directly a [pull request](//github.com/aerohub/hugo-faq-theme/pulls).

## License

[MIT](//github.com/aerohub/hugo-faq-theme/blob/master/LICENSE.md). And keep in mind the original [CodyHouse Terms](//codyhouse.co/terms/)