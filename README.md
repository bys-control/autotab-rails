# AutoTab for rails asset pipeline

[![Gem Version](https://badge.fury.io/rb/autotab-rails.svg)](http://badge.fury.io/rb/autotab-rails)
[![Code Climate](https://codeclimate.com/github/sachin87/autotab-rails.png)](https://codeclimate.com/github/sachin87/autotab-rails)
[![License](http://img.shields.io/license/MIT.png?color=green)](http://opensource.org/licenses/MIT)

[Autotab](https://github.com/Mathachew/jquery-autotab) is a jQuery plugin that provides auto tabbing and filtering on text fields in a form. Once the maximum number of characters has been reached within a text field, the focus is automatically set to a defined element. Likewise, clearing out the text field's content by pressing backspace eventually places the focus on a previous element.

The `autotab-rails` gem integrates the `AutoTab` with the Rails asset pipeline.

## Usage

### Install autotab-rails gem

Include `autotab-rails` in Gemefile

    gem 'autotab-rails'

Then run `bundle install`

### Include autotab javascript assets

Add to your `app/assets/javascripts/application.js` if use with jQuery

    //= require autotab-jquery

### Enable autotab javascript by specific css class

Add to one coffee script file, like `custom.js.coffee`

  $(document).ready ->
    $("#first").autotab
      target: "second"
      format: "numeric"

    $("#second").autotab
      target: "third"
      format: "numeric"
      previous: "first"

    $("#third").autotab
      previous: "second"
      format: "numeric"

    return

And this file must be included in `application.js`

    //= require autotab-jquery
    //= require custom

## Limitations

 jquery-autotab does not supports iphone.[READ MORE](https://github.com/Mathachew/jquery-autotab/issues/45)

## Gem maintenance

Maintain `autotab-rails` gem with `Rake` commands.

Update origin autotab source files.

    rake update-autotab

Publish gem.

    rake release

## Contributing to jquery-autotab

    Fork, fix, then send me a pull request.

## License

    MIT license.
