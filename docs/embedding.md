---
title: Embedding
nav_order: 5
layout: default
---

# Embedding

Some partners may wish to embed our plugin directly into their application for a seamless user experience. This guide outlines the requirements and steps to securely embed the plugin using an iframe.

## Prerequisites

- You must be an approved distributor.
- You must provide a list of allowed domains for both `PRODUCTION` and `SANDBOX` environments.
- Only requests from approved domains will be permitted to embed the plugin.

## Allowed Domains

Distributors are required to provide a list of approved domains for our `PRODUCTION` and `SANDBOX` environments. Requests from non-approved domains will be blocked from embedding content.

To update your allowed domains, contact your integration manager or support.

## Embedding via iframe

The recommended way to embed the plugin is via an HTML `<iframe>`. Example:

```html
<iframe
  src="https://plugin.example.com/?env=PRODUCTION"
  width="100%"
  height="600"
  frameborder="0"
  referrerpolicy="strict-origin-when-cross-origin"
  allowfullscreen
></iframe>
```

### Required iframe attributes

- `referrerpolicy="strict-origin-when-cross-origin"` — Ensures the correct referrer is sent for security.

### Referrer Header

Ensure the host domain is included in the `referrer` header. Some frameworks or agents may require manual configuration to ensure this header is set correctly.

## Embedding in Common Frameworks

Most frameworks support embedding web content, often via an iframe or web view. For detailed instructions, refer to the official documentation for your framework:

- [React: Embedding Content](https://react.dev/reference/react-dom/components/iframe)
- [Angular: Security and iframes](https://angular.io/guide/security#embedding-content)
- [Vue.js: Using iframes](https://vuejs.org/guide/essentials/template-syntax.html#raw-html)
- [Svelte: HTML and iframes](https://svelte.dev/tutorial/html-tags)
- [Android WebView](https://developer.android.com/reference/android/webkit/WebView)
- [iOS WebView](https://developer.apple.com/documentation/webkit/wkwebview)
- [.NET MAUI WebView](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/webview)
- [Flutter WebView](https://docs.flutter.dev/cookbook/plugins/play-video-webview)

For other frameworks or platforms, refer to their official documentation for embedding external web content securely.

## Security Considerations

- Only approved domains can embed the plugin.
- The plugin will reject requests from unapproved origins.
- Always use HTTPS for embedding.

## Troubleshooting

- **Blocked by CORS or domain restrictions:** Ensure your domain is on the approved list.
- **Plugin not loading:** Check the iframe `src` URL and required attributes.
- **Referrer issues:** Verify the `referrerpolicy` attribute and your application's referrer settings.

For further assistance, contact [support](support.md).
