

# Commands

Build locally
```
npx quartz build --serve
```


Sync to cloud
```
npx quartz sync
```


- `theme`: configure how the site looks.
    - `cdnCaching`: If `true` (default), use Google CDN to cache the fonts. This will generally will be faster. Disable (`false`) this if you want Quartz to download the fonts to be self-contained.
    - `typography`: what fonts to use. Any font available on [Google Fonts](https://fonts.google.com/) works here.
        - `header`: Font to use for headers
        - `code`: Font for inline and block quotes.
        - `body`: Font for everything
    - `colors`: controls the theming of the site.
        - `light`: page background
        - `lightgray`: borders
        - `gray`: graph links, heavier borders
        - `darkgray`: body text
        - `dark`: header text and icons
        - `secondary`: link colour, current [graph](https://quartz.jzhao.xyz/features/graph-view) node
        - `tertiary`: hover states and visited [graph](https://quartz.jzhao.xyz/features/graph-view) nodes
        - `highlight`: internal link background, highlighted text, [highlighted lines of code](https://quartz.jzhao.xyz/features/syntax-highlighting)
        - `textHighlight`: markdown highlighted text background