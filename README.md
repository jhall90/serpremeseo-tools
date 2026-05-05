# SERPremeSEO Tools (For Public Distribution)

A growing suite of lightweight, framework-agnostic SEO calculators and ROI tools delivered as Web Components.

This repository contains only the **compiled, production-ready distribution** of each tool for embedding on websites, CMS platforms, and client implementations.

The full source code, build system, and development workflow are maintained in a **separate private repository**.

---

## Live Demos (GitHub Pages)

| Tool | Demo |
| :--- | :--- |
| SEO Opportunity Engine | https://jhall90.github.io/serpremeseo-tools/demo/seo-opportunity-engine.html |

---

## Available Tools

| Tool | Custom Element | Status |
| :--- | :--- | :--- |
| SEO Opportunity Engine | `<seo-opportunity-engine>` | Available |
| Lead Loss Calculator | `<lead-loss-calculator>` | Coming Soon |
| Website Conversion Scorecard | `<conversion-scorecard>` | Coming Soon |
| Legal Case Value Calculator | `<legal-case-value>` | Coming Soon |
| Medical Treatment ROI Calculator | `<medical-treatment-roi>` | Coming Soon |
| Construction Job Value Calculator | `<construction-job-value>` | Coming Soon |

---

## Features

- Drop-in custom elements - one script tag per tool
- Works in WordPress, Webflow, Wix, Squarespace, Shopify, or plain HTML
- No dependencies required
- Loadable via CDN for simple integration
- Shadow DOM isolation for predictable styling
- Supports multiple **branding modes** for agencies, publishers, and embeds
- Emits **custom events** for analytics and conversion tracking

---

## SEO Opportunity Engine

Estimate the traffic, leads, and revenue opportunity from organic search — using your own data.

Inputs: monthly search volume, current rank, target rank, average revenue per client, conversion rate, close rate.
Outputs: Conservative / Likely / Aggressive monthly and annual revenue scenarios with a current baseline comparison.

### CDN Usage (jsDelivr)

```html
<script src="https://cdn.jsdelivr.net/gh/jhall90/serpremeseo-tools@latest/dist/seo-opportunity-engine.min.js"></script>

<seo-opportunity-engine theme="system"></seo-opportunity-engine>
```

Place the script **before** using the `<seo-opportunity-engine>` element.

---

### Basic Usage Example

```html
<script src="https://cdn.jsdelivr.net/gh/jhall90/serpremeseo-tools@latest/dist/seo-opportunity-engine.min.js"></script>

<body>
    <seo-opportunity-engine theme="system"></seo-opportunity-engine>
</body>
```

---

### Branding Modes

| Branding Mode | Intended Use Case                | Behavior                                 |
| :------------ | :------------------------------- | :--------------------------------------- |
| `brand`       | Agency sites / owned properties  | Full branding and visual overrides       |
| `minimal`     | Blogs / educational resources    | Limited branding and neutral visuals     |
| `off`         | Neutral publishers / comparisons | No branding overrides and no attribution |

**Example:**

```html
<seo-opportunity-engine
    branding="minimal"
    theme="system"></seo-opportunity-engine>
```

---

### Advanced Styling (Custom Branding)

The calculator is styled using CSS Variables. Pass your brand colors directly into the `style` attribute.

| Variable                | Description                                          |
| :---------------------- | :--------------------------------------------------- |
| `theme`                 | Use `system` unless forcing `light` or `dark` mode   |
| `--brand-top`           | Gradient start color for the results panel           |
| `--brand-bottom`        | Gradient end color for the results panel             |
| `--chart-conservative`  | Bar color for the Conservative scenario              |
| `--chart-likely`        | Bar color for the Likely scenario                    |
| `--chart-aggressive`    | Bar color for the Aggressive scenario                |
| `--chart-current`       | Bar color for the Current baseline                   |
| `--bg-light`            | Main background color in Light Mode                  |
| `--panel-light`         | Inner card background in Light Mode                  |
| `--text-light`          | Text color in Light Mode                             |
| `--bg-dark`             | Main background color in Dark Mode                   |
| `--panel-dark`          | Inner card background in Dark Mode                   |
| `--text-dark`           | Text color in Dark Mode                              |
| `--font-family`         | Typographic family used across the UI                |
| `--ui-option-font-size` | Font size for dropdowns and inputs                   |

```html
<seo-opportunity-engine
    branding="brand"
    theme="light"
    style="
        --brand-top: #0e2a59;
        --brand-bottom: #0e2a59;
        --chart-conservative: #7dd3fc;
        --chart-likely: #00cc66;
        --chart-aggressive: #ff6a00;
        --chart-current: #64748b;
        --font-family: 'Lato', sans-serif;
    "></seo-opportunity-engine>
```

---

### Elementor (WordPress) Integration because I personally like them. Not Sponsored.

Use this configuration to automatically sync the calculator with your Elementor Site Settings:

```html
<seo-opportunity-engine
    branding="brand"
    theme="system"
    style="
        /* -----------------------------------------------------------
           ELEMENTOR GLOBAL VARIABLE REFERENCE (Site-Wide)
        ----------------------------------------------------------- */

        /* BRAND COLORS */
        --brand-top: var(--e-global-color-primary);
        --brand-bottom: var(--e-global-color-secondary);

        /* CHART COLORS */
        --chart-conservative: #7dd3fc;
        --chart-likely: #00cc66;
        --chart-aggressive: #ff6a00;
        --chart-current: #64748b;

        /* UI - LIGHT THEME */
        --bg-light: #f8fafc;
        --panel-light: #ffffff;
        --text-light: var(--e-global-color-text);

        /* UI - DARK THEME */
        --bg-dark: #0f172a;
        --panel-dark: #1e293b;
        --text-dark: #f8fafc;

        /* FONT & SIZE */
        --font-family: var(--e-global-typography-text-font-family, inherit);
        --ui-option-font-size: 13.3333px;
    "></seo-opportunity-engine>
```

---

### Neutral Publisher Embed (Branding Off)

```html
<seo-opportunity-engine
    branding="off"
    theme="system"></seo-opportunity-engine>
```

---

## Private Source Code

This repository contains **only the distributable build**.
The following items are intentionally excluded:

- Source JavaScript
- SCSS source files
- Development files
- Build pipeline
- Shared formula modules
- Testing utilities

To request access, report issues, or inquire about collaboration, contact the repository owner.

---

## Versioning & CDN Releases

Tag a release:

```sh
git tag v1.0.0
git push origin v1.0.0
```

Load a specific version via CDN:

```
https://cdn.jsdelivr.net/gh/jhall90/serpremeseo-tools@v1.0.0/dist/seo-opportunity-engine.min.js
```

---

## Repository Structure

```
/
├── dist/
│   └── seo-opportunity-engine.min.js
│
├── demo/
│   └── seo-opportunity-engine.html
│
├── index.html
├── LICENSE
└── README.md
```

---

## License

Distributed under the MIT License.  
See the LICENSE file for details.