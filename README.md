# Sookie Cookie Consent - GTM Template

Sookie is a lightweight, high-performance Consent Management Platform (CMP) designed to bridge the gap between user privacy and data-driven marketing. This template allows you to easily integrate the Sookie Cookie Banner into your website via Google Tag Manager while maintaining full compliance with **Google Consent Mode v2**.

---

## Features

- **Google Consent Mode v2 Support:** Automatically sets default consent states and updates them based on user interaction.
- **Easy Integration:** Just enter your `Sookie ID` and the template handles the script injection.
- **Auto-Scanning:** Supports real-time cookie scanning and categorization.
- **Lightweight:** Minimal impact on page load speed (LCP).

---

## Installation

1. **Import the Template:**
   - Go to **Templates** in your GTM Container.
   - Click **Search Gallery** and look for "Sookie Cookie Consent" (or import the `template.tpl` file manually).
   - Click **Add to workspace**.

2. **Create the Tag:**
   - Go to **Tags** > **New**.
   - Select **Sookie Cookie Consent** as the Tag Type.
   - Enter your **Sookie ID** (Found in your Sookie Dashboard).

3. **Set the Trigger:**
   - **Crucial:** Use the **"Consent Initialization - All Pages"** trigger. This ensures consent is set before any other tags fire.

---

## Consent Mapping

Sookie categories are mapped to Google Consent Mode as follows:

| Sookie Category | Google Consent Type |
| :--- | :--- |
| **Necessary** | `security_storage`, `functionality_storage` |
| **Preferences** | `personalization_storage` |
| **Statistics** | `analytics_storage` |
| **Marketing** | `ad_storage`, `ad_user_data`, `ad_personalization` |

---

## Advanced Configuration

### Manual Consent Updates
If you are using a custom UI, you can trigger consent updates manually using the following dataLayer push:

```javascript
window.gtag('consent', 'update', {
  'analytics_storage': 'granted',
  'ad_storage': 'granted',
  'ad_user_data': 'granted',
  'ad_personalization': 'granted'
});
