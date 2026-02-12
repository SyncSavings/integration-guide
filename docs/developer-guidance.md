---
title: Developer Guidance
nav_order: 8
layout: default
---

# Developer Guidance: Best Practices & Tips

## Token Generation & Management

- **Use the Token Generation Tool:**
  - Access the [token generation tool](https://token-gen.sandbox.sync-savings.com/) to create and customize JWT payloads for testing and integration.
  - Enter your signing (private) key, adjust the payload as needed, and click **Generate JWT**.

{: .warning}
Your private key is stored only in your browser's Local Storage for convenience.
<br/>
All token generation happens locally—no keys or data are sent to any server.

**Tips:**

- Use test keys for development. Never share or expose production keys in public or shared environments.
- Clear your browser's Local Storage after testing if using a shared device.

## Session Data & Cookie Handling

- **Cookies are used for caching payload and form data between page loads.**
  - This can sometimes cause cross-session data consistency issues.

**Best Practices:**

- Use an anonymous/incognito browser window for each test session to avoid stale data.
- If embedding the app, ensure your host application allows cookies to be set and read as needed.
- Be aware that cookies are partitioned to prevent cross-site tracking and are not accessible by third-party scripts.

**Troubleshooting:**

- If you encounter unexpected data or session issues, try clearing cookies or using a fresh browser session.

## Debugging & Troubleshooting

- **Check Console Logs:** Most integration errors will be logged in the browser console. Review logs for hints on payload issues, token validation, or session problems.
- **Validate JWTs:** Use online tools like [jwt.io](https://jwt.io/) to inspect and debug JWTs if you suspect payload or signature issues.
- **Network Tab:** Use your browser's developer tools to inspect network requests and responses for errors or unexpected data.

For more detailed integration steps, see [Integration Steps](/docs/integration-steps.html).

If you are stuck, refer to the [Support page](/docs/support.html) for help or to raise an issue.
