# jsSocials - Simple Social Sharing

[![Build Status](https://travis-ci.org/tabalinas/js-socials.svg?branch=master)](https://travis-ci.org/tabalinas/js-socials)

Project site [js-socials.com](http://js-socials.com/)

**jsSocials** is a simple social network sharing jQuery plugin. It's flexible and easily extensible. 
Configure visual appearance. Choose one of several themes provided. Add any yet unsupported social network if needed.


## Demos

Find demos on the [project site](http://js-socials.com/demos/).


## Getting Started

1. Download the package
2. Add links to `jssocials.css` and chosen theme, e.g. `jssocials-theme-flat.css`
3. Add link to `font-awesome.css` (used for social network logos by default, since you can replace it with image logo or other font if necessary)
4. Add link to `jquery.js` and plugin script `jssocials.min.js`
5. Apply jsSocials to the element on the page `$("#share").jsSocials({ shares: ["twitter"] })`

```html
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" type="text/css" href="font-awesome.css" />
    <link rel="stylesheet" type="text/css" href="jssocials.css" />
    <link rel="stylesheet" type="text/css" href="jssocials-theme-flat.css" />
</head>
<body>
    <div id="share"></div>

    <script src="jquery.js"></script>
    <script src="jssocials.min.js"></script>
    <script>
        $("#share").jsSocials({
            shares: ["twitter", "facebook", "googleplus", "linkedin", "pinterest"]
        });
    </script>
</body>
</html>
```

## Documentation

* [Configuration](#configuration)
* [Methods](#methods)
* [Themes](#themes)
* [Shares](#shares)
* [Custom Share](#custom-share)
* [Adaptiveness](#adaptiveness)


### Configuration

The config object may contain following options:
 
```javascript
{
    shares: ["twitter", "facebook", "googleplus", "linkedin", "pinterest"],
    url: "http://url.to.share",
    text: "text to share",
    showLabel: true,
    showCount: true
}
```

#### shares :`Array`

An array of shares. 

Each share can be

* string - name of share from registry `jsSocials.shares` (e.g. `"twitter"`)
* config - plain object with `share` as name and custom parameters specific for each share. Read more about share config in [Shares section](#shares).

For instance for twitter the config may look like:

```javascript
{
    share: "twitter",           // name of share
    label: "Tweet",             // share button text (optional)
    via: "artem_tabalin",       // custom twitter sharing param 'via' (optional)
    hashtags: "jquery,plugin"   // custom twitter sharing param 'hashtags' (optional)
}
```

#### url :`String`

A string specifying url to share. **window.location.href** used by default.

#### text :`String`

A string specifying text to share. The content of **&lt;meta name="description"&gt;** or **&lt;title&gt;** used by default.

#### showLabel :`true|false|function(screenWidth)`

A boolean specifying whether to show the text on the share button. 
Also accepts function returning true|false depending on screen width for adaptive rendering. Read more in [Adaptiveness section](#adaptiveness)

#### showCount :`true|false|"inside"|function(screenWidth)`

A boolean or "inside" specifying whether and how to show share count. 
Also accepts function returning true|false|"inside" depending on screen width for adaptive rendering. Read more in [Adaptiveness section](#adaptiveness)


### Methods

#### destroy()

Destroys the shares control and brings the Node to its initial state.

````javascript

$("#share").jsSocials("destroy");

````

### option(key, [value])

Gets or sets the value of an option.
 
**key** is the name of the option.

**value** is the new option value to set. 

If `value` is not specified, then the value of the option `key` will be returned.

````javascript

// turn off share count
$("#share").jsSocials("option", "showCount", false);

// get sharing text
var text = $("#share").jsSocials("option", "text");

````

#### refresh()

Refreshes sharing control. 

```javascript

$("#share").jsSocials("refresh");

```

### Themes

To turn on specific theme just link one of stylesheets

* jssocials-theme-flat.css - flat theme
* jssocials-theme-classic.css - classical theme with raised buttons
* jssocials-theme-minima.css - minimalistic theme with logos instead of buttons
* jssocials-theme-plain.css - monochromatic theme

#### flat

![jsSocials - flat theme](https://adfef9eec19058e166f1cd1202add8ac3d019fdf.googledrive.com/secure/AAyT6L_PXrl-a8O3o08VMzz3iIzHYx3XGgytGkj2i5p5fREVsiqBmh1Kb6M8TXGh5lQcB5zu-_QJJ-__3af0eT6DLXPO9dJGcGIGUV8ULVtkCA-3HiVLgf8GWKs-N_volXQtw0ELOKwYFshHBCyq1iN6mfkEIubWnqxaGnbdZyr4BTTWuVP60GvarFxASpk6yB8IBwQ7FGzGbW3cHBUzmAZLR2Kcp4n2_7OVrke4rlYoxJWc1SaEbGoPSaw8vO8NAb3amauDGIa4O4cJYD2ftYH-iTL_BXyoI7_Y24CUEQ-xPKzxud7zaxM6LCOO_4Nmwn6ks386spKgRXu0eDkORCJtoeJQp1sNJtDpCu3lFxT6EQYUxwK4-E_nvpcZuNaRasXqubW4JhdW_zBriekMafHVBKEz0f5JaThGmWw_SbenCHr5EvA8A1Aj2b95q8pQZ9cE626jzgdQD_AIlGpRQ4ugBvc5hF_duRraOgc71HJP1Ink6rph5xn07JeVriA-Q9BdKor_gx7qxnC_dl0SkVHIVNJjuJ0wse4Z_Bs2T5pu1Eo2L4SjQBCIETQlOa4_DUFzllwMYXXxYTTlm9M88w9fEtbx9paNWQ==/host/0BwcJihi374AsfmY5ck9hQmdfZG9oS3dXQUVKenVvXzFyY3gyaDBVLV95SGstTl9GaFc0TnM/flat.png)


## License

MIT © Artem Tabalin
