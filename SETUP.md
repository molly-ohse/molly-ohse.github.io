# Getting the website online

## 1. Preview it on your Mac (RStudio)
1. Double-click `mollyohse.github.io.Rproj` to open the project in RStudio.
2. In the R console, run once:
   ```r
   install.packages(c("blogdown", "scholar", "tidyverse", "glue", "httr", "jsonlite"))
   blogdown::install_hugo("0.111.3", extended = TRUE)
   ```
3. Preview: `blogdown::serve_site()` (the site opens in the Viewer; stop with `blogdown::stop_server()`).

## 2. Put it on GitHub
1. On github.com, create a **public** repository named exactly **`<your-github-username>.github.io`**.
2. Upload this whole folder (GitHub Desktop is easiest: File > Add local repository > choose this folder > Publish).
3. On GitHub, go to **Settings > Actions > General > Workflow permissions** and choose **Read and write permissions**.
4. Go to the **Actions** tab and run the **blogdown** workflow once (it builds the site into `docs/`).
5. Go to **Settings > Pages** and set: Source = *Deploy from a branch*, Branch = `main` (or `master`), folder = `/docs`.
6. After a minute the site is live at `https://<your-github-username>.github.io`.

From then on, every time you push a change, GitHub rebuilds the site automatically, and it also refreshes your publication list from ORCID/Google Scholar every Sunday.

## 3. Everyday edits
| To change… | Edit this file |
|---|---|
| Bio, interests, education, profile links | `content/authors/admin/_index.md` |
| Profile photo | replace `content/authors/admin/avatar.png` |
| Banner text | `content/home/hero.md` |
| Research projects | `content/project/<name>/index.md` |
| News post | copy a folder in `content/post/` and edit its `index.md` |
| Papers in revision / in preparation | bottom of `content/publications.Rmarkdown` |
| Supervision | `content/supervision/index.md` |
| CV | replace `static/uploads/cv.pdf` |
| Menu | `config/_default/menus.yaml` |
| Colours | `data/themes/dipper.toml` |

Published papers appear automatically once they are on your ORCID record.
