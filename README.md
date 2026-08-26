# Grace Bible Mission Website

A Jekyll-powered website for Grace Bible Mission National, hosted on GitHub Pages.

---

## Table of Contents

1. [How the site works](#how-the-site-works)
2. [How to add a new Assembly](#how-to-add-a-new-assembly)
3. [How to add a new Fellowship](#how-to-add-a-new-fellowship)
4. [How to add a Special Programme or Event](#how-to-add-a-special-programme-or-event)
5. [How to update the Weekly Schedule](#how-to-update-the-weekly-schedule)
6. [How to update Leadership](#how-to-update-leadership)
7. [How to add images](#how-to-add-images)
8. [How to get a Google Maps embed](#how-to-get-a-google-maps-embed)
9. [Site structure](#site-structure)
10. [Running locally (optional)](#running-locally-optional)

---

## How the site works

This site is built with **Jekyll** — a tool that converts simple text files (Markdown) into a full website. You do NOT need to know how to code HTML or CSS. You only need to edit simple text files.

Every time you push (save) changes to GitHub, the site automatically rebuilds and goes live within a few minutes. No server to manage.

---

## How to add a new Assembly

1. Go to the `_assemblies/` folder in this repository.
2. Copy any existing file (e.g. `ayekale.md`) and rename it to your new assembly's name (all lowercase, no spaces — use hyphens).
   - Example: `oke-baale.md`
3. Edit the front matter (the section between the `---` lines at the top) with the correct details.
4. Save (commit) the file. The site will update automatically.

### Example assembly file

```
---
name: GBM Oke Baale Assembly
address: 5, Oke Baale Road, Osogbo, Osun State

service_times:
  - "Sunday School — 9:00 AM"
  - "Sunday Service — 10:00 AM"

pastor:
  name: Pastor John Oladele
  photo: /assets/img/pastors/pastor-oladele.jpg
  phone: "08012345678"

supporting_leaders:
  - name: Dcn. Amos Fadeyi
    role: Deacon
    photo:

map_embed: '<iframe src="https://www.google.com/maps/embed?..." width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy"></iframe>'
---

A short description of this assembly. Who they serve, the community they are in.
```

### Fields explained

| Field | Required? | Notes |
|---|---|---|
| `name` | YES | Full name of the assembly |
| `address` | YES | Full address |
| `service_times` | YES | List each service time on its own line |
| `pastor.name` | YES | Full name of the assembly pastor |
| `pastor.photo` | No | Path to photo in `assets/img/pastors/`. Leave blank if no photo |
| `pastor.phone` | No | Phone number (wrap in quotes) |
| `supporting_leaders` | No | Remove this whole section if there are none |
| `map_embed` | No | Google Maps embed code (see section below) |
| `events` | No | Assembly-specific upcoming events |

---

## How to add a new Fellowship

1. Go to the `_fellowships/` folder.
2. Copy any existing file (e.g. `star.md`) and rename it.
3. Edit the front matter with the correct details.
4. Save. The fellowship listing page updates automatically.

### Example fellowship file

```
---
name: Youth Fellowship
tagline: Young people growing in Christ together.
schedule: Every 2nd and 4th Sunday of the month
time: "3:30 PM"
note: Confirm dates via weekly announcements.
leadership:
  - name: Bro. Samuel Ojo
    role: Coordinator
    phone: "07012345678"
    photo:
---

A description of what this fellowship is about and who it is for.
```

---

## How to add a Special Programme or Event

1. Go to the `_programmes/` folder.
2. Create a new file named after the programme (e.g. `revival-2027.md`).
3. Fill in the front matter.
4. Add `featured: true` to make it appear on the homepage.
5. Save. It appears automatically on the Programmes page and the homepage.

### Example programme file

```
---
title: Revival Night 2027
dates: "Friday, March 5 — Sunday, March 7, 2027"
time: "Starts 5:00 PM"
venue: GBM Headquarters, Osogbo
banner: /assets/img/revival-2027.jpeg
register_link: https://forms.gle/your-form-link
featured: true
---

A short description of the programme. What to expect, who should come.
```

To **remove a programme from the homepage** once it's past, either:
- Delete the file, or
- Change `featured: true` to `featured: false`

---

## How to update the Weekly Schedule

Open `_data/weekly_schedule.yml` and edit the times or add new items.

```yaml
- day: Sunday
  programmes:
    - name: Sunday School
      time: 9:00 AM
    - name: Sunday Service
      time: 10:00 AM
```

---

## How to update Leadership

Open `_data/leadership.yml` and edit the list. Each leader looks like this:

```yaml
- name: Pastor Kayode Ajayi
  title: General Overseer
  photo: /assets/img/general-overseer.jpg
```

If there is no photo, leave `photo:` blank or remove the line.

---

## How to add images

1. Upload the image to `assets/img/` (or a subfolder like `assets/img/pastors/`).
2. Reference it in a file like this: `/assets/img/your-image.jpg`

**Image naming tips:**
- Use lowercase letters only
- Use hyphens instead of spaces
- Keep filenames short and meaningful (e.g. `pastor-oladele.jpg`, not `IMG_20261204_153022.jpg`)

**Recommended image sizes:**
- Programme banners: 1200 × 600px
- Pastor/leader photos: 400 × 400px (square)
- Hero/header images: 1600 × 900px

---

## How to get a Google Maps embed

1. Go to [Google Maps](https://maps.google.com) and search for the assembly's address.
2. Click **Share** (the share icon or link).
3. Click **Embed a map**.
4. Copy the full `<iframe>` code shown.
5. Paste it as the `map_embed` value in the assembly's `.md` file:

```yaml
map_embed: '<iframe src="https://www.google.com/maps/embed?..." width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy"></iframe>'
```

> **Note:** Make sure the entire iframe is on one line and wrapped in single quotes `'...'`.

---

## Site structure

```
gbm-website/
├── _assemblies/        ← One file per assembly (add new assemblies here)
├── _fellowships/       ← One file per fellowship
├── _programmes/        ← One file per special programme/event
├── _posts/             ← Announcements (optional)
├── _data/
│   ├── leadership.yml      ← National leadership team
│   └── weekly_schedule.yml ← Regular weekly programmes
├── _layouts/           ← Page templates (don't edit unless you know Jekyll)
├── _includes/          ← Navbar and footer (don't edit)
├── assets/
│   ├── css/main.css    ← All styles (don't edit)
│   ├── js/main.js      ← All JavaScript (don't edit)
│   └── img/            ← All images go here
├── pages/
│   ├── about.md        ← About page content
│   ├── assemblies.md   ← Assemblies listing page
│   ├── fellowships.md  ← Fellowships listing page
│   └── programmes.md   ← Programmes listing page
├── index.md            ← Homepage
├── _config.yml         ← Site settings (title, email, YouTube link, etc.)
├── Gemfile             ← Ruby dependencies (don't edit)
└── README.md           ← This file
```

---

## Running locally (optional)

If you want to preview the site on your computer before pushing to GitHub:

1. Install [Ruby](https://www.ruby-lang.org/en/downloads/) and [Bundler](https://bundler.io/)
2. In a terminal, navigate to the site folder
3. Run: `bundle install`
4. Run: `bundle exec jekyll serve`
5. Open your browser at `http://localhost:4000`

---

## Questions?

Contact the site administrator or raise a GitHub Issue in this repository.

> **Grace Bible Mission National** · Preach · Teach · Disciple
