# Kickicons!

This is the [Bower][bower] package for [Kickserv Kickicons][kickicons].

## Add Kickicons to your project

1. Create a new file called *bower.json* (if you don't have one already).

2. Add a new line for the Octicon dependency, pointing to the correct repository:

  ``` json
  {
    "name": "my_great_project",
    "dependencies": {
      "kickicons": "*"
    }
  }
  ```

3. Run `bower install`. The Kickicons styles will be downloaded to *bower_components/kickicons*.

4. Link to the `kickicons.css` stylesheet in the `<head>` of your `<html>` page:

  ``` html
  <link rel="stylesheet" href="bower_components/kickicons/kickicons/kickicons.css">
  ```

4. Simply use an icon in your HTML page:

  ``` html
  <span class="ki-microscope"></span>
  ```

### Rails' asset pipeline

Kickicons includes a stylesheet specifically for [Rails 4/Sprockets][sprockets].

1. Create a new file called *vendor/assets/bower.json* (if you don't have one already).

2. Add a new line for the Octicon dependency, pointing to the correct repository:

  ``` json
  {
    "name": "my_great_project",
    "dependencies": {
      "kickicons": "*"
    }
  }
  ```

3. `cd` into `vendor/assets` and run `bower install`. The Kickicons styles will be downloaded to *vendor/assets/bower_components/kickicons*.

4. Open your config/application.rb, and add this line inside your Application:

  ``` ruby
  config.assets.precompile += %w(*.svg *.eot *.woff *.ttf)
  ```

5. In your application stylesheet, require `sprockets-kickicons`:

  ``` css
  /*
  = require sprockets-kickicons
  */
  ```

6. Simply use an icon in your HTML page:

  ``` html
  <span class="ki-flame"></span>
  ```

7. If you want a view helper, add something like this to *app/helpers/application_helper.rb*:

  ``` ruby
  def octicon(code)
    content_tag :span, '', :class => "ki-#{code.to_s.dasherize}"
  end
  ```

## Best practices

- Kickicons look best in sizes that are multiples of 16px. You can update the size using the `font-size` CSS property. For example:

  ``` css
  .ki {
    font-size: 32px;
  }
  ```

- Kickicons are not monospaced. This lets them work well next to type, but it means they won’t stack nicely by default. If you intend to stack kickicons, such as in navigation, you will want to add some CSS to make them the same width, and centered. For example:

  ``` css
  .navigation .ki {
    width: 16px;
    text-align: center;
  }
  ```

### Resources

- [dojo.kickserv.com](http://dojo.kickserv.com/icons) - the Dojo website, in the Icons section
- Read why [icon fonts are awesome](http://css-tricks.com/examples/IconFont/)
- How to compose your [HTML for icon font usage](http://css-tricks.com/html-for-icon-font-usage/)

## Why can't I see the characters in Font Book??

Give this a try, you should be all set:

![](http://cl.ly/image/2r1B1F2l3Q0D/content#png)

## Versions

Kickicons operates similarly to [Semver](http://semver.org/) with the following version convention:

- Major: Breaking changes — removed icons, markup changes, unicode switches, css renames, icon redesigns
- Minor: Non-breaking changes — new icons, new aliases, minor icon changes
- Patch: Unnoticeable tweaks — slight visual changes, package updates


[kickicons]: http://dojo.kickserv.com/icons
[bower]: http://bower.io/
[sprockets]: http://guides.rubyonrails.org/asset_pipeline.html
