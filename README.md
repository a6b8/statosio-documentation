<img src="./assets/images/statosio.png" height="60px">

<br>

**Statosio** is a library to generate simple charts, in a fast and reliable way.


## Available Languages:
- **Javascript:** [Github](https://github.com/a6b8/statosio-for-javascript) / [cdnjs](https://cdnjs.com/libraries/statosio)
- **Ruby:** [Github](https://github.com/a6b8/statosio-for-ruby) / [RubyGems](https://rubygems.org/gems/statosio)


## Video Introduction

<iframe width="560" height="315" src="https://www.youtube.com/embed/i6od9O8jz1E?autoplay=1" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


## Source Code

**Javascript**
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/statosio/0.9/statosio.js"></script>
```

**Ruby**
```ruby
require 'statosio'
require 'prawn'
require 'prawn-svg'


file = File.read( 'data.json' )
dataset = JSON.parse( file )

statosio = Statosio::Generate.new
chart = statosio.svg(
    dataset: dataset,
    x: 'name',
    y: 'mobile',
    options: {}
)

Prawn::Document.generate( "statosio.pdf" ) do | pdf |
  pdf.svg( chart, width: 500, )
end
```