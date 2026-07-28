# Google indexing fix for arammarquez.com

These changes are for the `Aram-Marquez/website` repository.

## 1. Upload two files

Upload these files to the repository root, beside `index.html` and `CNAME`:

- `robots.txt`
- `sitemap.xml`

Do not put them inside `assets`, `forms`, or `test`.

## 2. Edit `index.html`

Near the top of the file, find:

```html
<title>Aram Marquez</title>
<meta content="" name="description">
<meta content="" name="keywords">
```

Replace those three lines with:

```html
<title>Aram Márquez | Creative Director &amp; Technical 3D Artist</title>
<meta name="description" content="Portfolio of Aram Márquez, a Creative Director and Technical 3D Artist creating games, animation, AR/VR experiences, and playful digital worlds.">
<meta name="robots" content="index, follow, max-image-preview:large">
<link rel="canonical" href="https://arammarquez.com/">
```

Also change the Open Graph URL:

```html
<meta property="og:url" content="https://arammarquez.com">
```

to:

```html
<meta property="og:url" content="https://arammarquez.com/">
```

Finally, replace every backslash in a local asset path with a forward slash.
For example:

```html
assets\img\portfolio\TiS.jpg
```

becomes:

```html
assets/img/portfolio/TiS.jpg
```

Commit the changes to `main`. GitHub Pages should deploy them automatically.

## 3. Verify the deployment

Open these URLs in a private browser window:

- https://arammarquez.com/
- https://arammarquez.com/robots.txt
- https://arammarquez.com/sitemap.xml

The last two should display the contents from the supplied files, not a 404 page.

## 4. Update Google Search Console

1. Open **Sitemaps** and submit `https://arammarquez.com/sitemap.xml`.
2. Open **URL inspection** and inspect `https://arammarquez.com/`.
3. Run **Test live URL**, then choose **Request indexing** if the test succeeds.
4. In the Page indexing report, open the 404 and robots.txt issue groups and
   inspect their example URLs before choosing **Validate fix**.

The four “Page with redirect” URLs generally do not need fixing if they lead to
`https://arammarquez.com/`. The two “Crawled – currently not indexed” URLs may
be experimental pages under `/test/`; do not add them to the sitemap unless
you intentionally want those pages to appear in search results.
