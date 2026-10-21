# Shampan Restaurant Attendance

Staff check in and out with a selfie and GPS location. The owner sees daily details, a monthly summary, leave and a salary sheet.

Files
- `index.html` is the whole app (host it on GitHub Pages).
- `firestore.rules` goes into Firebase (Firestore Database > Rules).

This is a separate project from any other attendance app. Create a new Firebase project and a new GitHub repository for it so the data stays apart.

## 1. Firebase

1. console.firebase.google.com > Add project, name it `shampan-attendance`. Analytics off.
2. Build > Authentication > Get started > Sign-in method: enable **Anonymous** and **Email/Password**, Save.
3. Authentication > Users > Add user: your email (lowercase) and a strong password.
4. Build > Firestore Database > Create database. Region asia-south1 (Mumbai) or asia-southeast1 (Singapore), production mode.
5. Firestore > Rules: paste `firestore.rules` (email already set), Publish.
6. Project settings > General > Your apps > web icon `</>` > Register app. Copy the config values.
7. Send the config to Claude, or paste the four values (apiKey, authDomain, projectId, appId) near the top of `index.html`.

## 2. GitHub Pages

1. New public repository, for example `shampan-attendance`.
2. Add file > Upload files: `index.html` and `README.md`. Commit.
3. Settings > Pages > Deploy from a branch > `main` / `(root)` > Save.
4. Link: `https://YOUR-USERNAME.github.io/shampan-attendance/`

## 3. First use

1. Open the link, tap Admin, sign in with the owner email and password.
2. In the restaurant, tap "Use my current location as the restaurant".
3. Add staff with role, salary, optional PIN, weekly off and duty time.
4. Share the link with staff.

Night shifts that pass midnight are supported: a staff member who checked in the evening before can check out after midnight.
