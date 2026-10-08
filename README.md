# Company Logos

Find a company logo in Raycast. Copy the image, then paste it into a document, slide, canvas, or chat.

## Install locally

Requires macOS, Raycast, and Node.js 22 or newer.

```sh
git clone https://github.com/mrzmyr/raycast-company-logos.git
cd raycast-company-logos
npm ci
npm run dev
```

Open **Search Company Logos** in Raycast. After the first successful build, you can stop the dev process; the extension remains installed.

## Use

- Search 64 popular companies by name, domain, or product alias.
- Enter another domain or full website URL to fetch its favicon.
- **Enter:** copy the PNG image.
- **⌘Enter:** paste into the previously active app.
- **⌘⇧C:** copy the image URL.
- **⌘O:** open the company website.

Images come from Google's favicon endpoint: `https://www.google.com/s2/favicons?domain=stripe.com&sz=256`. No API key needed. Requests ask for 256 px, but actual resolution depends on the website. These are website icons, not full wordmarks or vector brand assets. Unknown sites may return a generic icon or an error.

Downloaded images are converted to PNG with macOS `sips`, then cached for seven days. Copy and paste use Raycast's file clipboard API; the target app must accept image/file pastes. Preview and download requests send company domains to Google. URL paths and query strings are discarded.

## Source and images

Source code is available under the [MIT license](LICENSE). **Company logos are fetched at runtime and are not included in this repository or its releases.** The catalog contains company names, domains, and search keywords. The bundled extension icon is original geometric artwork.

Keep downloaded logos, caches, and screenshots containing company logos out of contributions. Image files are ignored by Git except for the extension's own icon.

## Check

```sh
npm test
npm run typecheck
npm run lint
npm run build
```

Requires macOS and Raycast. Built with the [Raycast Grid API](https://developers.raycast.com/api-reference/user-interface/grid) and [Clipboard API](https://developers.raycast.com/api-reference/clipboard).
