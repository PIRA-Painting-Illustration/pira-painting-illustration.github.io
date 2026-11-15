# PIRA landing page

The repository copy of the site for GitHub Pages: the same files as the publish folder. Edit it here
and copy it there (or the other way round) so the two stay the same.

- `index.html`: the page (logo and letters are embedded).
- `media/pira-ad.mp4`: the 30 s ad, with its original backing track (made for PIRA, no third-party music).
- `media/ad-poster.webp`: the video's still before it plays.
- `media/shots/`: screenshots from the app on a tablet, and `lion-timelapse.mp4`, the owner's lion
  painted in PIRA (from its own timelapse export), which also plays in the ad.
- `wiki/`: the PIRA wiki as pages of the site (GitHub wikis need a public repository on the free
  plan). Built from `docs/wiki/` by `python3 web/landing/build_wiki.py`: edit the Markdown there and
  run it, never the HTML. `media/logo-64.png` is the wiki's logo, copied by the same script.
- `.nojekyll`: serve the files as they are.

To publish: make the public repo `PIRA-Painting-Illustration/pira-painting-illustration.github.io`, push
this folder (without `build_wiki.py`) to its `main` branch, and turn on Pages (Settings > Pages > Deploy
from a branch, `main`, `/`). It is then at https://pira-painting-illustration.github.io/.

Custom domain, **pira-art.com**: add a `CNAME` file containing `pira-art.com` to that repo; at the
registrar, point `pira-art.com` at GitHub with A records 185.199.108.153, 185.199.109.153,
185.199.110.153 and 185.199.111.153, and `www` with a CNAME to `pira-painting-illustration.github.io`;
verify the domain in the organisation's Settings > Pages; then set it under the repo's Pages > Custom
domain and tick Enforce HTTPS once the certificate is issued. The app, the README and the release
notes already link to https://pira-art.com.

A new release: raise `PIRA_VERSION` and run `python3 web/landing/build_wiki.py`, which moves the
download links and version labels here and in the wiki to it.

The match-photo screenshot and the ad show a photo by Filippo Molinari from Unsplash (Unsplash License).
Pose data: mocap.cs.cmu.edu (NSF EIA-0196217).
