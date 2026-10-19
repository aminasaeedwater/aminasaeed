# Researcher & artist site — GitHub Pages template

A free blog and course site that lives at `https://YOUR-USERNAME.github.io`. No domain, no hosting bill, no build tools. You edit text files in your browser on GitHub and the site updates itself.

---

## 1. Put it online (about 10 minutes)

1. **Create a GitHub account** at github.com if you don't have one. Your username becomes your web address, so choose it with that in mind.
2. **Create a new repository** (the green "New" button).
   - Repository name: exactly `YOUR-USERNAME.github.io` (e.g. `jaywater.github.io`)
   - Set it to **Public**
   - Click **Create repository**
3. **Upload the files.** On the new repository page, click **uploading an existing file**. Unzip this template on your computer, open the folder, select *everything inside it* (including the `_posts`, `_layouts`, `_includes`, `_data` and `assets` folders) and drag it into the browser window. Click **Commit changes**.
4. **Turn on Pages.** Go to **Settings → Pages**. Under *Build and deployment*, set Source to **Deploy from a branch**, Branch to **main** and folder to **/ (root)**. Click **Save**.
5. Wait one or two minutes, then visit `https://YOUR-USERNAME.github.io`. Your site is live.

> If you'd rather keep `YOUR-USERNAME.github.io` for something else, you can name the repository anything (e.g. `water`). Your site will then be at `https://YOUR-USERNAME.github.io/water/` — in that case open `_config.yml` and set `baseurl: "/water"`.

---

## 2. Make it yours

Almost everything is edited in two files. Open one on GitHub, click the pencil icon, change the words in quotes, and click **Commit changes**. The site updates in about a minute.

| What you want to change | Where |
|---|---|
| Name in the top bar, contact email, LinkedIn, Instagram | `_config.yml` |
| Hero text, about, stats, research areas, selected work, journey | `_data/profile.yml` |
| Artworks: titles, medium, year, images, artist statement | `_data/profile.yml` → `studio:` |
| Course title, status, sign-up link | `_config.yml` → `course:` |
| Course outline, audience, FAQ | `_data/course.yml` |
| Colours | top of `assets/css/style.css` |

**Your portrait:** upload a photo (portrait orientation) to `assets/images/`, then set `portrait:` under `hero:` in `_data/profile.yml`, e.g. `"/assets/images/portrait.jpg"`. Until then a painting fills the frame.

**Your artwork:** the six paintings in `assets/images/art/` are placeholders. Photograph your work in daylight, crop to the edge of the paper, save as JPG under ~500 KB, upload to `assets/images/art/`, and update each `image:` path and caption under `studio: pieces:`. The first four appear on the home page; all of them appear on the Art page.

**Contact form:** GitHub Pages can't send email, so the form needs a free form service. Create a form at formspree.io, copy its endpoint (looks like `https://formspree.io/f/abcdwxyz`) into `contact: form_action:` in `_config.yml`. Without it, the form opens the visitor's email app if you've set `author: email:`.

To hide the course until you're ready, set `show: false` under `course:` in `_config.yml`.

---

## 3. Write a blog post

1. Open the `_posts` folder on GitHub and click **Add file → Create new file**.
2. Name it `YYYY-MM-DD-short-title.md`, for example `2026-11-02-pfas-explained.md`. The date in the name is the publish date.
3. Paste the contents of `POST-TEMPLATE.md`, write your post, and click **Commit changes**.

The three posts already in `_posts` are samples — edit or delete them.

**Images:** upload them to `assets/images/` and add them to a post with
`![Description](/assets/images/photo.jpg)`. Keep photos under ~500 KB each.

**Topics:** the `tags:` line at the top of each post feeds the Topics page. Reuse the same spellings so posts group together.

**Drafts:** to work on a post without publishing it, put it in a `_drafts` folder instead of `_posts` (create the folder). Move it to `_posts` and add a date to the filename when it's ready.

---

## 4. Connecting your course

GitHub Pages hosts the *marketing* for your course — the outline, the blog posts that build trust, the sign-up button. It must not handle the payments or student logins themselves (GitHub's rules don't allow running a shop on Pages, and it can't do secure checkout).

So the course content and checkout live on a course platform, and this site links to it:

1. Create your course on a platform (see the course setup analysis for which one).
2. Copy the checkout or waitlist link it gives you.
3. Paste it into `_config.yml` → `course:` → `enroll_url:`.

Every "Join the waitlist" / "Enrol" button on the site now points there.

---

## 5. Optional: preview on your own computer

You don't need this — GitHub builds the site for you. If you want to preview changes before publishing, install Ruby, then in this folder run:

```
bundle install
bundle exec jekyll serve
```

and open http://localhost:4000.

---

## What's inside

```
_config.yml        site settings (start here)
_data/profile.yml  home page wording, research, art, journey
_data/course.yml   course page content
_posts/            your blog posts
_layouts/          page templates
_includes/         header, footer, waterline, contact form, artwork frame
assets/css/        the theme
about.md           About page
art.html           Art page (gallery built from profile.yml)
assets/images/art/ placeholder paintings — replace with your own
course.md          Course page intro text
topics.html        Topics page (auto-generated from tags)
blog/index.html    Blog archive (auto-generated)
POST-TEMPLATE.md   copy this to start a new post
```

The site also generates an RSS feed (`/feed.xml`), a sitemap for search engines, and link previews for social media automatically.
