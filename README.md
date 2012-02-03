# Imperavi for Rails 3.1+ (still under development)

What is Imperavi? Imperavi is open-source, lightweight and really pretty-looking wysiwyg editor written with JQuery. Look at the demo page: http://imperavi.com/redactor/examples/ (sorry for Russian). Like it?

I created this mountable engine with Imperavi so now you can easily integrate this editor into your app.

## Installation

Put this line into your Gemfile:

```ruby
gem 'imperavi-rails'
```

Then mount the engine in routes.rb:

```ruby
mount ImperaviRails::Engine => "/imperavi"
```

And you're done!

## Usage

Add this helpers into the your view that contains a form:

```ruby
    <%= include_imperavi_stylesheet %>
    <%= include_imperavi_javascript %>
    <%= imperavi :page_article %>
```

In this example `page_article` is an id of textarea field. You can pass additional options to `imperavi` helper as second argument. See the full list of options here: https://github.com/tanraya/imperavi-rails/blob/master/app/helpers/imperavi_rails/imperavi_helper.rb#L35

You may want the text on your page to be styled the same way as it looks in the editor. To do this, add the following styles into your `application.css.scss` (provided that the text on the page is enclosed with `article` tag):

```scss
    @import "imperavi-rails/imperavi/imperavi-base";

    body {
      width: 700px;
      margin: 0 auto;

      article {
        overflow: hidden;
        @include imperavi-base;

        p, div {
          border: 0;
        }

        p {
          padding: 0;
          margin: 0 0 1.5em 0;
        }
      }

      form {
        textarea {
          width: 700px;
          height: 600px;
        }
      }
    }
```

## Deal with images

Uploading images is not part of the imperavi-rails. You have to implement this functionality in your application yourself. It's easy. Read the docs below.

* [How to upload images with imperavi-rails](https://github.com/tanraya/imperavi-rails/wiki/How-to-upload-images-with-imperavi-rails)

Also you can see Dummy app that has working images uploading: https://github.com/tanraya/imperavi-rails/tree/master/spec/dummy

# Contribute

I would appreciate any participation in the project. Any additions, fixes and ideas are welcome!

## How to contribute:

* Fork the project on Github
* Create a topic branch for your changes
* Ensure that the changes in your branch are as atomic as possible
* Create a pull request on Github
