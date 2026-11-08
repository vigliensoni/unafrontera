# Una Frontera Líquida

Hugo site (needs Hugo extended ≥ 0.121 for image processing).

    ./serve.sh        # preview at http://localhost:1313
    hugo --gc         # build to public/

## Layout

    hugo.toml                       site config + main navigation
    content/
      _index.md                     home: map, lead text, videos (front matter)
      libretto.md                   plain Markdown page
      bibliography.md               sections + entries in front matter (Markdown
                                    inside each entry), laid out in two columns
      audio/index.md                track list (front matter) + .wav files
      localities/<name>/index.md    one folder per locality: front matter lists
                                    `youtube` and the ordered `photos`; the
                                    photo files sit next to index.md
    layouts/
      _default/baseof.html          page shell (head, header, footer, scripts)
      _default/single.html          generic text page
      index.html                    home
      locality/single.html          video + photo grid
      audio/single.html             audio player list
      partials/                     head, header, nav, titlebar, footer, gallery, youtube
    assets/                         css/js (minified + fingerprinted), home image
    static/                         logo, favicon, Cardo font files

Add a locality: create `content/localities/<name>/index.md` (copy an existing one),
drop the photos in the folder and list them under `photos:`. It appears in the
menu and gets the URL `/<name>/` automatically.
