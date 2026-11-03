# 💍 Royal Digital Wedding Invitation (Light & Dark Editions)

A mobile-first, high-end digital wedding invitation web application featuring interactive unboxing video animations, classical palace archways with heart swans, and complete wedding stationery features.

---

## 🌟 Available Themes & Pages

| Page | Description | Video Default | Hero Visual |
| :--- | :--- | :--- | :--- |
| **[`index.html`](./index.html)** | Master portal allowing guests to pick their preferred experience | – | Dual Experience Selector |
| **[`wedding-invitation-light.html`](./wedding-invitation-light.html)** | **Ivory Daylight Edition:** Warm alabaster, blush garden roses & gold | [`assets/envelope.mp4`](./assets/envelope.mp4) (Silk veil & glowing envelope) | Golden-hour palace arch with daylight swans |
| **[`wedding-invitation-dark.html`](./wedding-invitation-dark.html)** | **Midnight Royal Edition:** Deep velvet obsidian, warm lanterns & royal gold | [`assets/ring.mp4`](./assets/ring.mp4) (Floating golden ring & flare) | Starry twilight arch with lanterns & moonlit swans |

*Note: On both pages, a top navigation bar allows 1-click theme switching as well as toggling between the **Envelope** video and the **Ring** video.*

---

## 🎬 How The Video Animation Reveal Works

1. **Cover State:** When a guest lands on the page, the unboxing video is primed at frame 0 with an interactive glowing wax seal and prompt ("Tap to Open Invitation").
2. **On Click / Tap:** The video plays smoothly with mobile `playsinline` support.
   - **`envelope.mp4`**: A soft silk veil floats away and the envelope flap opens as golden illumination pours out.
   - **`ring.mp4`**: A gold wedding ring lifts out of the envelope, rotates in misty smoke, and bursts into a radiant golden diamond flare.
3. **Seamless Reveal:** Near the end of the video playback, a golden light flash transition triggers, the video overlay dissolves away, and the couple's wedding invitation with drifting petals appears in full glory.
4. **Music Sync:** If background music is configured in `C.audio`, it automatically begins playing on the user's reveal tap.

---

## 🛠️ Configuration & Customization

Open either `wedding-invitation-light.html` or `wedding-invitation-dark.html` and edit the `C` configuration object:

```javascript
const C = {
  groom: "Zohan",
  bride: "Rose",
  date: "2026-09-27T19:00:00+05:00", // ISO date string with timezone
  dateText: "27.09.26",
  venue: "Grand Palace Banquet",
  addr: "Main Boulevard, Islamabad, Pakistan",
  whatsapp: "923001234567", // WhatsApp number for instant RSVPs
  audio: "", // Optional MP3 URL for background romantic music
  video: "assets/envelope.mp4", // Default video ("assets/envelope.mp4" or "assets/ring.mp4")
  events: [
    ["7:00 PM", "Guest Arrival & Welcome Drinks"],
    ["8:00 PM", "Sacred Nikkah Ceremony"],
    ["9:00 PM", "Musical Hour & Photography"],
    ["10:00 PM", "Royal Dinner & Dua"]
  ]
};
```

---

## 📂 Project Assets

```text
├── assets/
│   ├── envelope.mp4             # Silk scarf & unfolding glowing envelope video
│   ├── ring.mp4                 # Floating gold ring & diamond sparkle video
│   ├── hero-arch-swans.jpg      # High-res daylight palace arch & swan lake (Light)
│   ├── hero-arch-swans-dark.jpg # High-res midnight lantern arch & moonlit swans (Dark)
│   └── envelope-embossed.jpg    # Ultra-luxury cotton embossed paper texture
├── index.html                   # Master entry portal with theme choices
├── wedding-invitation-light.html# Ivory & Rose Gold Daylight page
├── wedding-invitation-dark.html # Midnight & Royal Gold page
└── wedding-invitation.html      # Default standalone invitation page
```
