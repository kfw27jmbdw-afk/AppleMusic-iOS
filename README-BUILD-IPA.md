# Apple Music web project — iOS IPA build

This package wraps the existing HTML/CSS/JavaScript project in a Capacitor iOS app. The included GitHub Actions workflow builds an **unsigned** iPhone IPA on a macOS runner.

## Generate the IPA

1. Upload the contents of this folder to a GitHub repository (the workflow file must be at `.github/workflows/build-unsigned-ipa.yml`).
2. Open the repository's **Actions** tab.
3. Select **Build unsigned iOS IPA** and choose **Run workflow**. A push to `main` or `master` also triggers a build.
4. When the run completes, open it and download the `AppleMusic-unsigned-IPA` artifact. Extract the downloaded artifact ZIP to get `AppleMusic-unsigned.ipa`.
5. Use your own sideloading/signing method if it requires a signed IPA.

## Important limitations

- This workflow deliberately does not sign the app; signing requires a valid signing method/certificate or a sideloading tool that can sign it.
- This is a WebView wrapper for the supplied web project, not a native Apple Music app and not affiliated with Apple.
- Google OAuth sign-in can be restricted inside embedded WebViews. If that feature fails in the wrapped app, the OAuth flow may need to be moved to the system browser.
- The project includes the repository's local music and image assets, so the source package is large.
