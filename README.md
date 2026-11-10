# 💍 Luxury Digital Wedding Invitation Suite (Midnight Royal Edition)

A cinematic, mobile-first, high-performance digital wedding invitation experience engineered with pure **vanilla HTML5, modern CSS3, and ECMAScript**. Designed to deliver an unboxing experience inspired by luxury bridal stationery reels, complete with interactive wax seals, video reveals, ambient audio, and guest-tier privacy.

---

## ✨ Key Architectural Features

- **Cinematic Wax Seal & Ring Reveal**: Realistic gold-embossed wax seal with smooth micro-animations transitioning into an unboxing video sequence.
- **Tiered Multi-Event Privacy Engine**: Strict compartmentalization of event tiers. Guests only receive links to the ceremonies they are invited to, preventing unauthorized access to private family venues.
- **Atmospheric Visuals & Ambient Engine**: Animated moonlit hero backdrop, realistic gold sparkle particle canvas, and high-velocity celebratory flower shower animations.
- **Dual Sound Engine**: Crystal metallic ring reveal chime synchronized with romantic acoustic background music, managed via an unobtrusive floating audio controller.
- **1-Tap Interactive WhatsApp RSVP**: Streamlined attendance pills (attendance status and guest count) that generate formatted WhatsApp confirmation messages.
- **Content Protection & Anti-Theft Shield**: Client-side media protection that disables right-click context menus, suppresses drag-and-drop actions, prevents mobile long-press callouts, and disables direct video download controls.
- **Clean URL Routing**: Native Vercel integration delivering clean URL slugs (e.g. `/barat-walima`, `/complete-invitation`) without `.html` extensions.
- **Zero-Dependency Architecture**: 100% standalone — no npm build steps, frameworks, or backend databases required.

---

## 🏛️ Template Suite & Routing

| Template Route | Tier / Description | Included Ceremonies |
| :--- | :--- | :--- |
| **`/`** | **Master Family Portal** | Protected host gateway for generating and copying shareable guest links (PIN-gated). |
| **`/barat-walima`** | **Barat & Walima Tier** | Musical Night, Barat (Sehra Bandi & Departure), and Walima Dinner. |
| **`/mehndi-walima`** | **Musical Night & Walima Tier** | Musical Night and Walima Dinner. |
| **`/walima`** | **Walima Reception Tier** | Exclusive access to Walima Dinner Reception only. |
| **`/complete-invitation`**| **Complete Wedding Celebrations** | Full 4-day wedding itinerary (Mehndi, Musical Night, Barat, and Walima). |

---

## ⚙️ Configuration & Customization

Each invitation template is driven by an intuitive configuration object located at the top of the script block:

```javascript
const C = {
  groom: "Groom Name",
  bride: "Bride Name",
  countdownDate: "2026-12-16T19:00:00+05:00", // ISO 8601 Timestamp
  whatsapp: "923XXXXXXXXX",                  // RSVP Destination Number (Country Code + Number)
  video: "assets/ring.mp4"                   // Reveal Video Path
};
```

---

## 🛡️ Security & Media Protection

The suite implements layered client-side protections to preserve the privacy of invitation media:

1. **Context Menu Guard**: Suppresses the right-click menu across all viewports to prevent casual asset downloads.
2. **Video Element Hardening**: Video tags utilize `controlsList="nodownload nofullscreen noremoteplayback"`, `disablePictureInPicture`, and `pointer-events: none` with transparent protective overlays.
3. **Touch Callout Suppression**: Mobile long-press menus ("Save Image / Video") are disabled via `-webkit-touch-callout: none`.
4. **Keyboard Shortcut Interception**: Blocks browser shortcuts for DevTools and source inspection (`F12`, `Ctrl+Shift+I`, `Ctrl+U`, `Ctrl+S`).
5. **HTTP Security Headers**: `vercel.json` provides strict security headers (`X-Frame-Options`, `X-Content-Type-Options`, `X-XSS-Protection`, `Referrer-Policy`).

---

## 🚀 Deployment & Local Testing

### Local Development
To preview the templates locally:
```bash
# Start local server on port 3000
npx --yes serve . -l 3000
```
Open `http://localhost:3000/` in your browser.

### Vercel Deployment
The repository includes a preconfigured `vercel.json` with `cleanUrls: true`:
```json
{
  "cleanUrls": true,
  "trailingSlash": false,
  "headers": [
    {
      "source": "/(.*)",
      "headers": [
        { "key": "X-Content-Type-Options", "value": "nosniff" },
        { "key": "X-Frame-Options", "value": "SAMEORIGIN" },
        { "key": "X-XSS-Protection", "value": "1; mode=block" },
        { "key": "Referrer-Policy", "value": "strict-origin-when-cross-origin" }
      ]
    }
  ]
}
```
Deploy instantly by pushing to your connected GitHub repository or running:
```bash
vercel --prod
```

---

## 📄 License & Privacy Notice

This repository contains design templates and codebase architecture. All personal identifying information, direct contact numbers, and private venue addresses should be configured locally or via private deployment environment variables.
