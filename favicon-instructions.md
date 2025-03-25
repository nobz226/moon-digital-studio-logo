# Implementing the Favicon

This document explains how to add the Moon Digital Studio favicon to your GoDaddy website.

## Option 1: Using the SVG Favicon (Modern Browsers)

1. Download the `favicon.svg` file from this repository
2. Upload it to your GoDaddy website's root directory
3. Add the following code to the `<head>` section of your HTML (or in your Next.js layout component):

```html
<link rel="icon" type="image/svg+xml" href="/favicon.svg">
```

## Option 2: Using PNG/ICO Favicons (Maximum Compatibility)

For maximum browser compatibility, you should also include traditional favicon formats:

1. Download the SVG favicon and convert it to:
   - 16x16 favicon.ico
   - 32x32 favicon.ico
   - 180x180 apple-touch-icon.png
   - 192x192 android-chrome-192x192.png
   - 512x512 android-chrome-512x512.png

2. Upload all these files to your GoDaddy website's root directory

3. Add the following code to the `<head>` section of your HTML:

```html
<link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
<link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
<link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png">
<link rel="icon" type="image/x-icon" href="/favicon.ico">
<link rel="manifest" href="/site.webmanifest">
```

4. Create a `site.webmanifest` file with the following content:

```json
{
  "name": "Moon Digital Studio",
  "short_name": "Moon Digital",
  "icons": [
    {
      "src": "/android-chrome-192x192.png",
      "sizes": "192x192",
      "type": "image/png"
    },
    {
      "src": "/android-chrome-512x512.png",
      "sizes": "512x512",
      "type": "image/png"
    }
  ],
  "theme_color": "#9BE8F1",
  "background_color": "#121212",
  "display": "standalone"
}
```

## Adding to Your Next.js Project

Since your website is using Next.js, the simplest method is:

1. Download the favicon.svg (and optionally the other formats)
2. Place the files in your `public` directory in your Next.js project
3. In your `app/layout.tsx` file, add the appropriate link tags mentioned above in the `<head>` section

For example, add this to your layout.tsx file:

```tsx
// In your app/layout.tsx
export default function RootLayout({
  children,
}: {
  children: React.ReactNode
}) {
  return (
    <html lang="en">
      <head>
        <link rel="icon" type="image/svg+xml" href="/favicon.svg" />
        {/* Add other favicon links here if using multiple formats */}
      </head>
      <body>{children}</body>
    </html>
  )
}
```

## Online Favicon Generator

If you want to generate all the different sizes and formats at once, you can use an online tool like:

1. [RealFaviconGenerator](https://realfavicongenerator.net/)
2. [Favicon.io](https://favicon.io/)

Upload the SVG file and download a package with all required sizes and formats.