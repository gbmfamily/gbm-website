# Grace Bible Mission Website

A Jekyll-powered website for Grace Bible Mission National — hosted on GitHub Pages at [gbmfamily.org](https://gbmfamily.org).

> **Motto:** Preach · Teach · Disciple

---

## Table of Contents

1. [How the site works](#how-the-site-works)
2. [How to deploy to GitHub Pages](#how-to-deploy-to-github-pages)
3. [Running locally on your computer](#running-locally-on-your-computer)
4. [How to add a new Assembly](#how-to-add-a-new-assembly)
5. [How to add a new Fellowship](#how-to-add-a-new-fellowship)
6. [How to add a Special Programme or Event](#how-to-add-a-special-programme-or-event)
7. [How to update the Weekly Schedule](#how-to-update-the-weekly-schedule)
8. [How to update National Leadership](#how-to-update-national-leadership)
9. [How to add or update Social Media links](#how-to-add-or-update-social-media-links)
10. [How to add images](#how-to-add-images)
11. [How to get a Google Maps embed](#how-to-get-a-google-maps-embed)
12. [How to update site-wide settings](#how-to-update-site-wide-settings)
13. [Site structure](#site-structure)
14. [Field reference — all available fields](#field-reference)

---

## How the site works

This site is built with **Jekyll** — a tool that converts simple text files into a full website. You do NOT need to know HTML or CSS. Everything you'll ever need to edit is a simple text file.

**The golden rule:** every piece of content lives in its own file. To add a new assembly, create one file. To add a programme, create one file. The website reads those files and builds itself automatically.

Every time you push (save) a change to GitHub, the site rebuilds and goes live within a few minutes. No server to manage, no FTP, no hosting dashboard.

---

## How to deploy to GitHub Pages

This site deploys via the standard **GitHub Pages branch method**.

**One-time setup:**
1. Push this repository to GitHub
2. Go to your repo → **Settings → Pages → Source**
3. Set source to **"Deploy from a branch"**
4. Set branch to **`main`** (or whichever branch you use), folder **`/ (root)`**
5. Click Save

GitHub Pages will build and deploy the site automatically every time you push to that branch. The site will be live at `gbmfamily.org` once DNS is pointing to GitHub Pages.

---

## Running locally on your computer

To preview the site before pushing to GitHub:

> **Requirement:** Ruby 3.3.x (NOT 4.0 — the `jekyll-sitemap` gem is not yet compatible with Ruby 4.0 on Windows). Download from [rubyinstaller.org](https://rubyinstaller.org/downloads/) — choose **Ruby+Devkit 3.3.x (x64)**.

1. Open a terminal in the site folder
2. Run `bundle install` (first time only)
3. Run `bundle exec jekyll serve`
4. Open your browser at `http://localhost:4000`

The site will auto-reload when you save changes.

---

## How to add a new Assembly

1. Go to the `_assemblies/` folder
2. Copy `ayekale.md` and rename it — use lowercase letters and hyphens only (e.g. `oke-baale.md`)
3. Edit the fields inside the file
4. Save and push — the assembly appears automatically on the Assemblies page and the homepage preview

### Full example assembly file

```yaml
---
name: GBM Oke Baale Assembly
address: 5, Oke Baale Road, Osogbo, Osun State

service_times:
  - "Sunday School — 9:00 AM"
  - "Sunday Service — 10:00 AM"

pastor:
  name: Pastor John Oladele
  photo: /assets/img/pastors/pastor-oladele.jpg   # leave blank if no photo
  phone: "08012345678"

supporting_leaders:
  - name: Dcn. Amos Fadeyi
    role: Deacon
    photo:

# Banner image at the top of the assembly page (optional)
# Upload to assets/img/assemblies/ — recommended size: 1400 × 500px
# banner: /assets/img/assemblies/oke-baale.jpg

# Social media for this assembly (optional — remove lines that don't apply)
# social:
#   facebook: "https://facebook.com/GBMOkeBaale"
#   instagram: ""
#   whatsapp: ""
#   youtube: ""

# Google Maps embed (see section below for how to get this)
# map_embed: '<iframe src="..." ...></iframe>'

# Assembly-specific upcoming events (optional)
# events:
#   - name: Special Revival
#     date: Sept 14, 2026
#     time: 5:00 PM
#     description: A night of prayer and the Word.
---

A short description of this assembly — who they serve and the community they are in.
```

### Assembly fields at a glance

| Field | Required? | Notes |
|---|---|---|
| `name` | YES | Full name shown as the page heading |
| `address` | YES | Full physical address |
| `service_times` | YES | List — add as many lines as needed |
| `pastor.name` | No | If blank or "To Be Updated", the Leadership section is hidden |
| `pastor.photo` | No | Path to photo in `assets/img/`. Leave blank for initial letter placeholder |
| `pastor.phone` | No | Wrap in quotes: `"08012345678"` |
| `supporting_leaders` | No | Remove the whole block if there are none |
| `banner` | No | Hero image at top of page. Without it, the default dark blue header shows |
| `social` | No | Per-assembly social links (see Social Media section) |
| `map_embed` | No | Google Maps iframe — the map section only appears when this is filled |
| `events` | No | Assembly-specific events list |
| `headquarters: true` | Special | Only for GBM Oke-Oniti — adds the Headquarters badge |

---

## How to add a new Fellowship

1. Go to the `_fellowships/` folder
2. Copy `star.md` and rename it
3. Edit the fields
4. Save and push — it appears automatically on the Fellowships page

### Example fellowship file

```yaml
---
name: Youth Fellowship
tagline: Young people growing in Christ together.
schedule: Every 2nd and 4th Sunday of the month
time: "3:30 PM"
note: Confirm dates via weekly announcements.

# Banner image for this fellowship (optional)
# banner: /assets/img/fellowships/youth.jpg

# Social media (optional)
# social:
#   facebook: ""
#   instagram: ""
#   whatsapp: ""

leadership:
  - name: Bro. Samuel Ojo
    role: Coordinator
    phone: "07012345678"
    photo:
---

A description of what this fellowship is about and who it is for.
```

### Fellowship fields at a glance

| Field | Required? | Notes |
|---|---|---|
| `name` | YES | Full name of the fellowship |
| `tagline` | No | One-line summary shown on the listing card |
| `schedule` | No | When they meet e.g. "Every 4th Sunday" |
| `time` | No | Meeting time |
| `note` | No | A small note shown in the info bar (e.g. "confirm via announcements") |
| `banner` | No | Image shown in the hero and on the listing card |
| `social` | No | Per-fellowship social links |
| `leadership` | No | Remove the whole block if details are unavailable |

---

## How to add a Special Programme or Event

1. Go to the `_programmes/` folder
2. Create a new file — name it clearly (e.g. `revival-2027.md`)
3. Fill in the fields
4. Add `featured: true` to show it on the homepage
5. Save and push — it appears on the Programmes page immediately

### Full example programme file

```yaml
---
title: Revival Night 2027
dates: "Friday, March 5 — Sunday, March 7, 2027"
time: "Starts 5:00 PM daily"
venue: GBM Headquarters
venue_address: No. 1, Grace Bible Mission Street, Oke-Oniti, Osogbo

# Banner image (shown as the hero background on the programme page)
banner: /assets/img/revival-2027.jpeg

featured: true   # set to false (or remove) once the programme is past

audience: "All members and invited guests"
dress_code: "Smart casual — white on Sunday"

register_link: https://forms.gle/your-form-link

contact:
  name: Pastor John Doe
  role: Programme Coordinator
  phone: "08012345678"
  email: "revival@gbmfamily.org"
  whatsapp: "+2348012345678"

# Social media for this programme (optional)
# social:
#   facebook: "https://facebook.com/events/..."
#   instagram: ""
#   whatsapp: ""

# Google Maps embed for the venue (optional)
# map_embed: '<iframe src="..." ...></iframe>'
---

Write a description of the programme here. What to expect, who should come, the theme.
```

### Programme fields at a glance

| Field | Required? | Notes |
|---|---|---|
| `title` | YES | Programme name |
| `dates` | No | Date range as plain text |
| `time` | No | Time info |
| `venue` | No | Venue name |
| `venue_address` | No | Full address — shown below venue name |
| `banner` | No | Hero background image |
| `featured` | No | `true` = shown on homepage. Remove or set `false` when past |
| `audience` | No | Who the programme is for |
| `dress_code` | No | Dress code if any |
| `register_link` | No | URL to registration form — renders a Register button |
| `contact` | No | Contact person block (name, role, phone, email, whatsapp) |
| `social` | No | Programme-specific social links |
| `map_embed` | No | Google Maps embed for the venue |

**To remove a programme from the homepage once it's past:**
- Change `featured: true` to `featured: false`, or delete the file entirely

---

## How to update the Weekly Schedule

Open `_data/weekly_schedule.yml` and edit or add items:

```yaml
- day: Sunday
  programmes:
    - name: Sunday School
      time: 9:00 AM
    - name: Sunday Service
      time: 10:00 AM

- day: Wednesday
  programmes:
    - name: Prayer Meeting
      time: 5:00 PM
```

The schedule appears on both the Homepage and the About page automatically.

---

## How to update National Leadership

Open `_data/leadership.yml`.

- The **first entry** is the General Overseer — displayed as a large featured card
- All other entries appear in the grid below
- The `bio` field only shows on the General Overseer's featured card

```yaml
- name: Pastor Kayode Ajayi
  title: General Overseer
  photo: /assets/img/general-overseer.jpg
  bio: >
    A short bio paragraph for the General Overseer.

- name: Pastor Kayode Olarinre
  title: Deputy General Overseer
  photo: /assets/img/dgo.jpg
```

**To add a photo for a leader:**
1. Upload the photo to `assets/img/` (recommended: 400×400px square, named clearly e.g. `pastor-olarinre.jpg`)
2. Fill in the `photo:` field with the path: `/assets/img/pastor-olarinre.jpg`

---

## How to add or update Social Media links

Social links work at **three levels**:

### 1. Site-wide (footer — appears on every page)
Edit `_config.yml` under the `social:` section:

```yaml
social:
  facebook: "https://facebook.com/GBMFamily"
  instagram: "https://instagram.com/gbmfamily"
  youtube: "https://youtube.com/@GBMMedia"
  twitter: ""       # leave blank to hide
  tiktok: ""
  whatsapp: ""
```

### 2. Per-assembly
Add to the assembly's `.md` file:

```yaml
social:
  facebook: "https://facebook.com/GBMAyekale"
  instagram: ""
  whatsapp: "https://wa.me/grouplink"
```

### 3. Per-fellowship or per-programme
Same format — add a `social:` block to the fellowship or programme file.

**Rules:**
- Leave a platform blank (`""`) or remove its line to hide it
- All platforms supported: `facebook`, `instagram`, `youtube`, `twitter`, `tiktok`, `whatsapp`

---

## How to add images

1. Upload your image to the appropriate subfolder of `assets/img/`:
   - General/church photos → `assets/img/`
   - Assembly hero banners → `assets/img/assemblies/` *(create this folder)*
   - Fellowship banners → `assets/img/fellowships/` *(create this folder)*
   - Pastor/leader photos → `assets/img/pastors/` *(create this folder)*
   - Programme banners → `assets/img/` (root is fine for these)

2. Reference the image in the file like: `/assets/img/your-image.jpg`

**Image naming rules:**
- Lowercase letters only
- Use hyphens instead of spaces
- Keep names short and meaningful: `pastor-olarinre.jpg` not `IMG_20261204_153022.jpg`

**Recommended sizes:**
| Use | Size |
|---|---|
| Assembly / fellowship / programme hero banner | 1400 × 500px |
| Homepage hero | 1600 × 900px |
| Pastor / leader portrait | 400 × 400px (square) |
| Programme banner card | 1200 × 600px |

---

## How to get a Google Maps embed

1. Go to [maps.google.com](https://maps.google.com) and search for the location (or drop a pin on the exact spot)
2. Click the **Share** button
3. Click the **Embed a map** tab
4. Copy the full `<iframe>` code
5. Paste it into the assembly or programme file as the `map_embed` value — the entire iframe must be on **one line**, wrapped in **single quotes**:

```yaml
map_embed: '<iframe src="https://www.google.com/maps/embed?pb=..." width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="strict-origin-when-cross-origin"></iframe>'
```

The map section only appears on the page when `map_embed` is filled in.

---

## How to update site-wide settings

Open `_config.yml` to change:

| Setting | What it controls |
|---|---|
| `title` | Site name shown in browser tab and navbar |
| `tagline` | Subtitle (currently "Preach, Teach, Disciple") |
| `description` | Meta description for search engines |
| `url` | The site's domain (`https://gbmfamily.org`) |
| `church.email` | Email shown in footer |
| `church.youtube` | YouTube channel link |
| `church.address` | HQ address shown in footer |
| `church.founded` | Year founded (shown in footer) |
| `social.*` | Site-wide social media links |

After editing `_config.yml`, push to GitHub and the whole site updates.

---

## Site structure

```
gbm-website/
│
├── _assemblies/            ← One .md file per assembly
│   ├── oke-oniti.md        ← HQ (headquarters: true)
│   ├── ayekale.md
│   ├── agunbelewo.md
│   └── ...                 ← Add new assemblies here
│
├── _fellowships/           ← One .md file per fellowship
│   ├── teenagers.md
│   ├── students.md
│   └── ...                 ← Add new fellowships here
│
├── _programmes/            ← One .md file per special programme
│   ├── liberty-2026.md
│   ├── masterlife-2026.md
│   └── ...                 ← Add new programmes here
│
├── _posts/                 ← Announcements (date-named, e.g. 2026-09-01-title.md)
│
├── _data/
│   ├── leadership.yml      ← National leadership team
│   └── weekly_schedule.yml ← Regular weekly programme schedule
│
├── _layouts/               ← Page templates — DO NOT EDIT
│   ├── default.html        ← Master shell (navbar, footer)
│   ├── home.html           ← Homepage
│   ├── page.html           ← Generic page (About etc.)
│   ├── assembly.html       ← Individual assembly page
│   ├── fellowship.html     ← Individual fellowship page
│   └── programme.html      ← Individual programme page
│
├── _includes/              ← Reusable HTML snippets — DO NOT EDIT
│   ├── navbar.html
│   ├── footer.html
│   └── social-links.html   ← Social media pills (used everywhere)
│
├── assets/
│   ├── css/main.css        ← All styles — DO NOT EDIT
│   ├── js/main.js          ← Mobile nav and animations — DO NOT EDIT
│   └── img/                ← All images go here
│       ├── logo.jpeg
│       ├── general-overseer.jpg
│       ├── dgo.jpg
│       ├── assemblies/     ← Assembly banner images (create as needed)
│       ├── fellowships/    ← Fellowship banner images (create as needed)
│       └── pastors/        ← Pastor portrait photos (create as needed)
│
├── pages/
│   ├── about.md            ← About page content (vision, mission, history)
│   ├── assemblies.md       ← Assemblies listing (auto-populated)
│   ├── fellowships.md      ← Fellowships listing (auto-populated)
│   └── programmes.md       ← Programmes listing (auto-populated)
│
├── index.md                ← Homepage content
├── _config.yml             ← Site-wide settings — safe to edit
├── Gemfile                 ← Ruby gem dependencies — DO NOT EDIT
└── README.md               ← This file
```

---

## Current assemblies

| File | Assembly | Map? |
|---|---|---|
| `oke-oniti.md` | GBM Oke-Oniti (HQ) | ✅ |
| `ayekale.md` | GBM Ayekale | ✅ |
| `agunbelewo.md` | GBM Agunbelewo | ✅ |
| `ogo-oluwa.md` | GBM Ogo Oluwa | ✅ |
| `oke-ila.md` | GBM Oke Ila | ✅ |
| `iludun.md` | GBM Iludun | ✅ |
| `olude.md` | GBM Olude | ✅ |
| `ilesa.md` | GBM Ilesa | ✅ |
| `owode-ede.md` | GBM Owode Ede | ✅ |
| `ibadan.md` | GBM Ibadan | ❌ Pending |
| `oba.md` | GBM Oba | ❌ Pending |
| `ilupeju.md` | GBM Ilupeju | ❌ Pending |
| `solution.md` | GBM Solution | ❌ Pending |
| `bethel.md` | GBM Bethel | ❌ Pending |

---

## Current fellowships

| File | Fellowship | Banner? |
|---|---|---|
| `teenagers.md` | Teenagers Fellowship | ✅ |
| `students.md` | Students Fellowship | ✅ |
| `men-of-vision.md` | Men of Vision | ✅ |
| `star.md` | STAR Fellowship | ✅ |
| `house-fellowship.md` | House Fellowship | ✅ |
| `women-of-grace.md` | Women of Grace | ❌ Pending photo |
| `aquila-priscilla.md` | Aquila & Priscilla | ❌ Pending photo |
| `bride-of-the-lord.md` | Bride of the Lord | ❌ Pending photo |

---

## Things still to complete

- [ ] Add photos for Deputy GO and all AGOs (`_data/leadership.yml`)
- [ ] Add Google Maps embeds for: Ibadan, Oba, Ilupeju, Solution, Bethel assemblies
- [ ] Add banner images for: Women of Grace, Aquila & Priscilla, Bride of the Lord fellowships
- [ ] Fill in pastor names for all assemblies that say "To Be Updated"
- [ ] Add assembly-level social media links where available
- [ ] Upload banner photos for each assembly page
- [ ] Set up site-wide social media (Facebook, Instagram) in `_config.yml`

---

## Questions or issues?

Raise a GitHub Issue in this repository, or contact the site administrator.

> **Grace Bible Mission National** · Preach · Teach · Disciple · gbmfamily.org
