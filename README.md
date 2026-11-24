# Lodestar Teen Trivia

A static site: `index.html` is the whole game, `config.js` holds your Firebase settings.
The host computer and the team computers sync through a Firebase Realtime Database.

## 1. Set up Firebase (about 10 minutes, free plan)

1. Go to https://console.firebase.google.com and create a project (Analytics can stay off).
2. Build > Realtime Database > Create database. Start in locked mode.
3. On the database's Rules tab, paste the contents of `database.rules.json` and publish.
4. Build > Authentication > Get started > Sign-in method > enable Anonymous.
5. Project settings (gear icon) > Your apps > add a Web app. Copy the `firebaseConfig` values
   into `config.js`. Make sure `databaseURL` is there; copy it from the Realtime Database page if not.

## 2. Deploy

Any static host works. With GitHub Pages:

    git init && git add . && git commit -m "Lodestar Teen Trivia"
    git branch -M main
    git remote add origin https://github.com/YOUR_NAME/lodestar-teen-trivia.git
    git push -u origin main

Then in the repo: Settings > Pages > Deploy from a branch > main, root folder.
Your site appears at https://YOUR_NAME.github.io/lodestar-teen-trivia/ after a minute or two.

If you use a custom domain or another host, add that domain under
Authentication > Settings > Authorized domains in Firebase.

## 3. Check it

Open the site on two different computers. Host on one, join as a team on the other.
The pill in the top right should read "Live across devices".

## Notes

- Questions and the game in progress are saved in the host computer's browser. Use
  Edit questions > Save and load to copy your questions to another computer.
- Correct answers stay on the host computer until the reveal.
- The database only holds room state (team names, rosters, guesses, scores).
  Delete the `rooms` node in the Firebase console after the event to clear it.
