This is a separate RSS feed meant to be used with [better_feediverse](https://github.com/The-Spinoff-Group/better_feediverse), but should also work with other social media publishers.

# Installation

While this project only adds a single XML file to your site it is deployed as a theme. Hugo supports multiple themes at once, which are merged, making handling of this project very easy.

Add the repository to your themes directory, either by `git clone`, `git submodule add` or just extract the zip file into your themes folder.

    # use only one of these, whatever suits your setup
    git clone https://github.com/schneidr/hugo-mastofeed.git themes/mastofeed
    git submodule add https://github.com/schneidr/hugo-mastofeed.git themes/mastofeed

Add to your Hugo `config.toml`:

    # add "mastofeed" as another theme
    theme = [ "my-theme", "mastofeed" ]

    [outputs]
      # just add "Mastofeed", example:
      home = ["HTML", "RSS", "JSON", "Mastofeed"]
    
    [outputFormats]
      [outputFormats.Mastofeed]
        baseName = 'mastofeed'
        isPlainText = true
        mediaType = 'application/rss+xml'

After building the site the feed will be available under `https://example.org/mastofeed.xml`.
