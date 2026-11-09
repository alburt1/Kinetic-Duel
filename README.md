# Kinetic Duel

Siebe vs Alburt. Post what you did, get scored, and see who wins the week every Sunday at 20:00.

## Setup

**1. Create the Firebase project**
1. Go to https://console.firebase.google.com and click **Create a project**. The free plan is enough.
2. Open **Build > Authentication > Get started**, choose **Email/Password** and enable it.
3. Open **Build > Firestore Database > Create database**. Pick an EU location and start in production mode.
4. In Firestore, open the **Rules** tab, replace everything with the contents of `firestore.rules`, and click **Publish**.

**2. Add your config**
1. In Firebase, open **Project settings** (gear icon) > **Your apps** and click the **web icon** (`</>`). Register an app with any name.
2. Copy the values into `firebase-config.js`.

**3. Publish on GitHub**
1. Upload `index.html`, `firebase-config.js`, `firestore.rules` and this README to a repo.
2. In the repo, open **Settings > Pages**. Under Source choose **Deploy from a branch**, then `main` and `/ (root)`, and save.
3. Your site appears at `https://YOUR-NAME.github.io/REPO-NAME/` after a minute or two.

**4. Allow your site to log in**
In Firebase, open **Authentication > Settings > Authorized domains** and add `YOUR-NAME.github.io`.

**5. Claim your accounts right away**
Alburt and Siebe each open the site, pick their name and click **Create account**. Do this straight after publishing, because until an account is claimed anyone with the link could claim it.

## Forgot a password
There are no real email addresses, so reset emails can't work. Delete the user under **Firebase > Authentication > Users** and create the account again. Your posts are kept.

## How to write posts
Works in English and Dutch. Put separate things between commas.

    bench 4x8 70kg all out, ran 5km, 150g protein, slept 8 hours
    squats 8 reps 100kg
    45 min voetbal, 8u geslapen

## AI reader
Posts are read by Gemini through `netlify/functions/read-workout.mjs`. Add a free key from https://aistudio.google.com/apikey to Netlify as the environment variable `GEMINI_API_KEY`, then redeploy. Without it, the site uses the simple built-in reader.
