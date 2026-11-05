# Mimika Biodiversity Database — starter website

A small static website that reads **only observations from one iNaturalist account** and filters them to a selected iNaturalist place (intended to be Mimika, Papua).

## Included
- `index.html` — website
- `config.js` — account and place configuration

## First preview
1. Extract the ZIP.
2. Open `index.html` in a modern browser while connected to the internet.
3. Expand **Website setup / account settings**.
4. Enter your iNaturalist username (the public username, not your email).
5. Click **Find places**.
6. Select the correct Mimika place. Check its displayed name and boundary carefully.
7. Click **Apply settings**.

The settings entered in the setup panel are saved only in that browser. The website queries iNaturalist's public API; it does not need your password or private login.

## Publish for everyone with GitHub Pages
1. Create a GitHub account if you do not already have one.
2. Create a **public** repository, for example `mimika-biodiversity`.
3. Upload `index.html` and `config.js` to the repository's top level.
4. Edit `config.js`:
   - set `username` to your iNaturalist username
   - set `placeId` to the place ID you selected in the website
   - set `placeName` to the displayed place name
5. In the repository, open **Settings → Pages**.
6. Under Build and deployment, choose **Deploy from a branch**, select `main` and `/ (root)`, then Save.
7. GitHub will provide a public address similar to `https://YOUR-USERNAME.github.io/mimika-biodiversity/`.

GitHub Pages is suitable for this static prototype. A custom domain is optional and can be added later.

## Important data notes
- The species list is generated from iNaturalist's `observations/species_counts` endpoint using `user_login` and `place_id`.
- The recent photo gallery uses the same account and place filters.
- The species count represents taxa found in the account's matching observations; it is not an authoritative checklist of all species in Mimika.
- The site currently shows a limited set of recent observations per species to keep pages responsive.
- Check the iNaturalist place boundary before publishing. A place named “Mimika” may not exactly match the administrative boundary you intend.
- Observations without coordinates or outside the selected place boundary will not be included.
- iNaturalist data can change as identifications and observation details are updated.
- Photos and observation data belong to their respective contributors. The site links back to the original iNaturalist records and retains observer attribution.
- Avoid exposing sensitive species locations. This prototype displays only data returned by iNaturalist; review the visibility settings of sensitive observations before relying on it publicly.

## Current limitations / future improvements
- This is a first prototype, not a complete scientific data repository.
- It does not yet include manually curated fields such as Indonesian/local names, habitat descriptions, conservation status, references, or expert notes.
- It does not have contributor accounts because the intended workflow is that you contribute through your own iNaturalist account.
- It uses the public iNaturalist API and therefore depends on API availability and its usage policies.
