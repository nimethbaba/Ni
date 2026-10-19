# Portfolio Website

A fast, single-page portfolio that shows my C++ programs and lets visitors download the source files. It has four sections: Home, Work, About and Contact.

Built by **Nimeth C.**, a solo developer who writes most of his code by hand and is looking for an internship.

## Features

- Project cards with tags, category filters and a download button for each project's source files
- Dark and light themes, with a layout that works on phones, tablets and desktops
- Keyboard-friendly navigation, visible focus states and reduced-motion support
- A contact form that opens the visitor's email app, so no server or tracking is involved
- No cookies and no data collected

## Projects shown on the site

| Project | Tech | What it does |
|---|---|---|
| Parking Management System | C++, OOP, binary files | 50-slot lot with staff and admin logins, check-in and check-out, hourly billing, history and revenue |
| Bus Ticket System | C++, file storage | Admin menu to add, view and update buses, plus passenger bookings with seat numbers and payment status |
| PDRoute Dispatch (Spiral 1) | C++, input validation | Package registration with priority levels, a 500 kg vehicle limit and an aligned queue table |

## How it's built

- Plain HTML, CSS and JavaScript in one file (`index.html`), with no framework
- Projects are loaded from `works.json`
- Optional Strapi support: set `STRAPI_URL` near the top of the script in `index.html` and the Work page loads from `/api/works` instead. It needs a `works` collection with `title`, `description`, `category`, `tags` (JSON) and `file` (media) fields, public `find` permission and a CORS rule for the site address
- Hosted on GitHub Pages

## Folder structure

```
.
├── index.html
├── works.json
├── README.md
└── files/
    ├── parking-management-system.zip
    ├── bus-ticket-system.zip
    └── pdroute-dispatch.zip
```

## Run it locally

Browsers block `works.json` when a page is opened by double-clicking it, so serve the folder instead:

```bash
python -m http.server 5500
```

Then open `http://localhost:5500`.

## Add a project

1. Put the project's zip file in the `files` folder.
2. Add an entry to `works.json`:

```json
{
  "title": "Project name",
  "category": "Program",
  "tags": ["C++", "Console"],
  "description": "One or two sentences about what it does.",
  "file": "files/project-name.zip"
}
```

3. Commit and push. GitHub Pages updates in a minute or two.

## Edit my details

The name, email, phone, links and skills are in the `PROFILE` block near the top of the script in `index.html`.

## Notes

- The Bus Ticket System uses `conio.h`, so it builds only on Windows.
- Contact: nimesiir@gmail.com
