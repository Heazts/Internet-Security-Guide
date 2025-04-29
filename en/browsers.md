# Browsers and Extensions: Browsing with Privacy

The browser is our main gateway to the internet, but it can also be a major source of data collection and tracking. Choosing a privacy-focused browser and configuring it correctly, along with using appropriate extensions, is a fundamental step in protecting your online activity.

## Criteria for Choosing a Secure and Private Browser

When evaluating a browser, consider the following factors:

*   **Open Source:** Open-source browsers allow independent experts to audit the code for vulnerabilities or hidden tracking features. Transparency is crucial.
*   **Frequent Updates:** Online threats evolve rapidly. A secure browser must receive regular updates to fix security flaws and improve protections.
*   **Rendering Engine:** Most browsers use one of a few main engines (Blink/Chromium, Gecko/Firefox, WebKit/Safari). While important, the engine itself doesn't determine privacy; the modifications and settings applied by the browser developer are more relevant.
*   **Business Model:** How does the browser make money? If it's through collecting and selling user data or targeted advertising (like Chrome), there's an inherent conflict of interest with privacy.
*   **Default Privacy Settings:** A good browser should have robust privacy settings enabled by default, without requiring the user to navigate complex menus.
*   **Tracking and Fingerprinting Protection:** Native features to block third-party trackers, tracking cookies, and fingerprinting techniques are essential.

## Analysis of Popular Browsers (Privacy Focus)

No browser is perfect, and the ideal choice may depend on your threat model and preferences. Here is an analysis of popular options, focusing on privacy and security, maintaining neutrality, and based on facts:

*   **Mozilla Firefox**
    *   **Pros:** Open source, developed by a non-profit organization (Mozilla Foundation), highly configurable (`about:config`), strong tracking protection (ETP - Enhanced Tracking Protection), receives frequent updates, large library of extensions.
    *   **Cons:** Telemetry is enabled by default (though it can be disabled), some sponsored features might raise concerns (easily disabled).
    *   **Recommendation:** An excellent overall choice for privacy, especially when configured correctly (disable telemetry, adjust `about:config`).
    *   [![Firefox](https://img.shields.io/badge/Browser-Firefox-FF7139?style=for-the-badge&logo=firefoxbrowser)](https://www.mozilla.org/firefox/)

*   **Brave Browser**
    *   **Pros:** Based on Chromium (good compatibility), aggressively blocks ads and trackers by default (Brave Shields), includes features like native HTTPS Everywhere and fingerprinting randomization, optional cryptocurrency-based business model (BAT) to reward creators (does not collect personal data for this).
    *   **Cons:** Based on Chromium (inherits some Google concerns, although Brave removes much tracking code), history of some controversies (e.g., affiliate link injection, later resolved), crypto features may not appeal to everyone (can be disabled).
    *   **Recommendation:** A solid option with strong default privacy protections, a good alternative for those who prefer the Chromium base.
    *   [![Brave](https://img.shields.io/badge/Browser-Brave-FB542B?style=for-the-badge&logo=brave)](https://brave.com/)

*   **Mullvad Browser**
    *   **Pros:** Developed in collaboration between Mullvad VPN and the Tor Project, focused on minimizing fingerprinting (all users look the same), based on Firefox ESR with Tor Browser privacy settings (without the Tor network by default), does not collect telemetry, open source.
    *   **Cons:** Browsing experience might be slightly affected by strong anti-fingerprinting protections (some sites may break), less customizable than standard Firefox to maintain uniformity.
    *   **Recommendation:** Excellent option for those seeking maximum protection against fingerprinting, ideal in combination with a trusted VPN (like Mullvad).
    *   [![Mullvad Browser](https://img.shields.io/badge/Browser-Mullvad%20Browser-008174?style=for-the-badge&logo=mullvad&logoColor=white)](https://mullvad.net/en/browser)

*   **Librewolf**
    *   **Pros:** A Firefox *fork* focused on privacy and security, removes telemetry, automatic updates, and sponsored features from Firefox, pre-configured with uBlock Origin and enhanced privacy protections.
    *   **Cons:** May require slightly more manual configuration for certain sites due to restrictive settings, update cycle might lag slightly behind the main Firefox release.
    *   **Recommendation:** Great option for users who want a "hardened" Firefox without having to do all the configurations manually.
    *   [![Librewolf](https://img.shields.io/badge/Browser-Librewolf-891AEB?style=for-the-badge&logo=librewolf&logoColor=white)](https://librewolf.net/)

*   **Browsers to Avoid (Privacy Perspective):**
    *   **Google Chrome:** Massive data collection for Google's advertising ecosystem.
    *   **Microsoft Edge:** Also collects a lot of telemetry data and integrates with Microsoft services.
    *   **Opera:** Questionable privacy history, owned by a Chinese consortium.

## Essential Privacy Settings

Regardless of the chosen browser (among the recommended ones), some settings are crucial:

*   **Default Search Engine:** Switch from Google to privacy-focused options like [DuckDuckGo](https://duckduckgo.com/), [Brave Search](https://search.brave.com/), [Startpage](https://www.startpage.com/), or [SearXNG](https://searx.space/) (self-hostable meta-search engine).
*   **Disable Telemetry:** Look in the browser's privacy settings and disable any option that sends usage data, crash reports, or statistics to the developer.
    *   **Firefox:** Go to `Preferences > Privacy & Security > Firefox Data Collection and Use` and uncheck all boxes.
    *   **Brave:** Go to `Settings > Privacy and security` and review data sending options.
*   **Content/Tracking Blocking:** Set tracker blocking to the strictest level possible without breaking the websites you frequently use.
    *   **Firefox:** Under `Privacy & Security`, choose the "Strict" mode for Enhanced Tracking Protection.
    *   **Brave:** Shields are already aggressively configured by default.
*   **Clear Data on Exit:** Configure the browser to automatically clear cookies, history, and other site data upon closing. This helps prevent persistent tracking.
    *   **Firefox:** `Preferences > Privacy & Security > Cookies and Site Data > Delete cookies and site data when Firefox is closed`.
    *   **Brave:** `Settings > Privacy and security > Clear browsing data > On exit`.
*   **HTTPS By Default:** Ensure the browser prioritizes HTTPS (encrypted) connections. Most modern browsers do this by default or have an "HTTPS-Only Mode" option.
*   **Secure DNS (DoH/DoT):** Configure the browser to use a secure and encrypted DNS server, like Quad9 or NextDNS. See more in the [Network Security](network.md) section.

## Recommended Extensions

Extensions can add useful functionality but can also be a security and privacy risk if not chosen carefully. Install only extensions from trusted sources that are strictly necessary.

*   **Content Blocker: uBlock Origin**
    *   **Description:** Essential. Efficiently blocks ads, trackers, malware, and other unwanted content with low resource consumption. It's much more than just an ad blocker.
    *   **Why use it:** Drastically reduces the attack surface, improves page load speed, and prevents tracking by ad networks.
    *   **Availability:** Firefox, Chrome/Brave (and other Chromium-based browsers).
    *   [![uBlock Origin](https://img.shields.io/badge/Extension-uBlock%20Origin-800000?style=for-the-badge&logo=ublockorigin&logoColor=white)](https://ublockorigin.com/)

*   **Password Manager:**
    *   **Description:** Password manager extensions (like [Bitwarden](https://bitwarden.com/) or KeePassXC with integration) make it easy to use strong, unique passwords for each site.
    *   **Why use it:** Essential for the security of your accounts. See more in the [Secure Software](software.md) section.
    *   [![Bitwarden](https://img.shields.io/badge/Extension-Bitwarden-175DDC?style=for-the-badge&logo=bitwarden)](https://bitwarden.com/)

*   **Anti-Fingerprinting (with Caveats):**
    *   **Description:** Some extensions attempt to combat fingerprinting by altering or blocking the information the browser sends to websites. Examples include CanvasBlocker (Firefox).
    *   **Caveats (The Anti-Fingerprinting Paradox):** Trying to block or alter *too much* fingerprinting information can paradoxically make your browser *more* unique and easier to track. Browsers like Brave and Mullvad Browser already incorporate fingerprinting randomization/blocking techniques in a more integrated and balanced way. It's generally better to rely on the browser's native protections (if using Brave or Mullvad) or use uBlock Origin in medium/hard mode, rather than adding many specific anti-fingerprinting extensions, unless you know exactly what you're doing.

## Fingerprinting: What It Is and How to Mitigate?

As mentioned, fingerprinting is the collection of information about your browser and device configuration to create a unique identifier. Sites can analyze:

*   User Agent (browser version and OS)
*   Installed fonts
*   Browser plugins
*   Screen resolution and color depth
*   Time zone
*   Language settings
*   Hardware information (via WebGL, Canvas API, Audio API)
*   And much more...

**Mitigation:**

*   **Use Browsers with Native Protections:** Brave and Mullvad Browser are specifically designed to combat fingerprinting by trying to make all users look as similar as possible.
*   **Firefox (with Configuration):** The "Strict" mode of Enhanced Tracking Protection blocks some known fingerprinting scripts. Additional settings in `about:config` (like `privacy.resistFingerprinting`, which is the basis of Mullvad Browser/Tor Browser) can be used but may break sites.
*   **uBlock Origin:** In medium or hard mode, blocks many third-party scripts that perform fingerprinting.
*   **Minimize Extensions and Fonts:** The fewer non-standard extensions and fonts you have, the less unique your browser will be.
*   **Keep Browser Updated:** New mitigation techniques are implemented over time.

You can test your browser's uniqueness on sites like [Cover Your Tracks (EFF)](https://coveryourtracks.eff.org/) or [AmIUnique](https://amiunique.org/).

## Compartmentalization: Separating Activities

No browser or configuration is 100% foolproof. An effective strategy is **compartmentalization**: using different browsers or browser profiles for different types of activities.

*   **Example:**
    *   **Profile 1 (Personal Firefox/Brave):** For logged-in personal accounts (email, social media, shopping).
    *   **Profile 2 (Mullvad Browser + VPN):** For sensitive research or general browsing without logging in.
    *   **Profile 3 (Work Firefox/Brave):** For work-related accounts and activities.

**How to Implement:**

*   **Browser Profiles:** Most browsers (Firefox, Brave, Chrome) allow creating multiple profiles. Each profile has its own set of cookies, history, extensions, and settings.
*   **Different Browsers:** Using distinct browsers for different purposes is another way to compartmentalize.
*   **Containers (Firefox):** The [Multi-Account Containers](https://addons.mozilla.org/en-US/firefox/addon/multi-account-containers/) extension for Firefox allows isolating sites in tabs with colored "containers," separating cookies and local storage for each context (personal, work, shopping, etc.) within the same browser window.

By carefully choosing and configuring your browser and extensions, and by practicing compartmentalization, you can significantly reduce your exposure to tracking and enhance your online privacy.

