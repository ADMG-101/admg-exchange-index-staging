# The ADMG Exchange GitHub App

Exchange reads publisher repositories through its GitHub App, which has **read-only** access to repository contents
and metadata. It cannot push, open pull requests, create releases or change settings, and it never sees repositories
you don't select.

## Install it

1. Open the App's page (**ADMG Exchange Staging** for this staging environment) and choose **Install**, or **Configure**
   if it is already installed on your account.
2. Pick the account or organisation that owns your repository.
3. Choose **Only select repositories** and select the repositories you publish. Installing on a repository needs admin
   rights over it, which is how Exchange knows the repository is yours to publish.
4. Confirm. Exchange picks the repository up on its next discovery run, about every 30 minutes.

**From the ADMG-101 launcher:** go to **Exchange**, then **Creator Hub**, then **Submit Project**, and sign in with
GitHub when asked: the launcher shows a short code to enter at github.com/login/device. Choose your repository, and the
launcher opens the App's installation page with it selected. When you come back, the launcher checks GitHub's records
to confirm the installation; it never installs anything itself.

## Add or remove repositories later

On GitHub, go to your account or organisation's **Settings**, then **Applications**, then **Installed GitHub Apps**,
and choose **Configure** next to the ADMG Exchange App. Removing a repository stops new releases from being discovered.
Releases already approved stay listed unless a moderator decides otherwise.
