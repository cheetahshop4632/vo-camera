# VO Camera Affiliate — source project + cloud build workflow

Target: Android 8+; intended to test on Redmi Note 12 Pro 5G / HyperOS.

## Important status
This is an **unverified starter project**, not a compiled or tested APK. The GitHub Actions workflow was added so the project can be built in the cloud without a laptop. Build success is not guaranteed until the workflow actually runs.

## What this prototype is intended to do
1. Select a local voice-over file.
2. Start camera recording and play the VO through the phone speaker.
3. Stop the video recording when the audio player reports that playback ended.
4. Save the video in `Movies/VO Camera Affiliate`.

## Important limitation
The prototype records **silent video** and does not record the microphone. The VO is played aloud as a timing/acting guide; add the original VO track to the video during editing if you want the final MP4 to contain that exact clean VO. HyperOS may also interrupt playback or camera operation; test on the actual phone.

## Build APK using only an Android phone (GitHub Actions)
1. Download this ZIP and extract it using a file manager that supports ZIP files.
2. Open https://github.com in Chrome and sign in or create an account.
3. Create a **new repository**. For the easiest setup, choose Public only if you are comfortable with the source being public; otherwise choose Private.
4. Upload the extracted project files and folders to the repository root. Make sure `.github/workflows/build-apk.yml` is included. Some mobile upload interfaces hide dot-folders; if the workflow file is missing, Actions will not show the build workflow.
5. Open the repository's **Actions** tab, choose **Build VO Camera Affiliate APK**, then tap **Run workflow**. If the workflow does not appear, confirm the `.github/workflows/build-apk.yml` file is present on the `main` branch.
6. Wait for the run to finish. A green check means the build job completed; a red cross means it failed and the logs must be checked.
7. On the completed run page, download the artifact named `VO-Camera-Affiliate-debug-apk` (a ZIP), extract it, then install `app-debug.apk` on your phone. Android may ask you to allow installs from that browser/file manager.
8. Test first with a short VO (10–20 seconds). Do not assume it works until tested.

## Security notes
- This workflow builds source code in your repository. Review the source before installing the APK.
- Do not upload passwords, API keys, or signing keystores.
- A debug APK is for testing, not public distribution.
