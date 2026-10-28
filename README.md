# Wow of the Day

A tiny web app that gives kids a fun fact of the day.

1. It asks for their name.
2. They pick a topic (Space, Animals, Human Body, Oceans, Dinosaurs, Science, Our World, or "Surprise me!").
3. It shows a fact with a link to read more.
4. They tap **"Wow, that's so cool!"** or **"I already knew this one, tell me another :)"**.

It is a single static page: no build step, no framework, no server, no tracking.

## Run it locally

Open `index.html` in any browser. That's it.

## Publish with GitHub Pages

1. Create a new repository on GitHub (for example `wow-of-the-day`).
2. Push these files to the `main` branch:

   ```bash
   cd wow-of-the-day
   git init
   git add .
   git commit -m "Wow of the Day"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/wow-of-the-day.git
   git push -u origin main
   ```

3. On GitHub go to **Settings → Pages**.
4. Under **Build and deployment**, set **Source** to **Deploy from a branch**, pick **main** and **/ (root)**, then **Save**.
5. After a minute or so the site is live at `https://YOUR-USERNAME.github.io/wow-of-the-day/`.

## Add or change facts

All the facts live in one list near the bottom of `index.html`, inside the `CATS` array. Each fact is a pair: the text, then the title of a Wikipedia article to link to.

```js
['An octopus has three hearts and blue blood!', 'Octopus'],
```

The second value is the end of the article's web address, so `Octopus` links to `https://en.wikipedia.org/wiki/Octopus`. Use underscores for spaces (`Mount_Everest`). To add a topic, copy a whole `{ key: ..., name: ..., color: ..., facts: [...] }` block, give it a new `key`, and add a matching icon in the `ICONS` object and a colour in the `:root` styles.

Please check that a fact is true and that its link opens before you add it.

## Notes

- Kids' names and progress are saved only in their own browser (`localStorage`). Nothing is sent anywhere.
- A topic shows the same fact all day and a new one the next day. Facts already marked "wow" or "knew it" are not repeated.
- Fonts (Baloo 2 and Nunito) load from Google Fonts. If they can't load, the page falls back to system fonts.
- The page follows the device's light or dark setting.
