# HOW-TO: Connect your account on the DIWA Virtual Research Environment (VRE) to GitHub

Goals:

  * Create a GitHub account with two-factor authentication
  * Learn how to authenticate to GitHub on the command line using GitHub CLI
  * Set up your account so that you can pull and push changes from GitHub to the VRE

---

## Create your GitHub account

Start out at https://github.com/signup:

![Complete the form. You will be asked to verify your email address -- Go check your email for the verification link.](img/01-gh-signup-filled.png)

![When you have created your account, you should see this success alert.](img/02-gh-signup-success.png)
	
## Fill out your GitHub profile (optional, but recommended)

1. ![Next, head to your settings page on Github](img/11-gh-settings.png)

2. ![Fill out your profile.](img/12-gh-profile-a.png)

3. ![Make sure to save your profile when you are finished.](img/13-gh-profile-b.png)

---

## Set up a two-factor authentication

This will be required to use the VRE in the future. The easiest way to add two-factor authentication is with a passkey on the computer you use to access the VRE.

1. ![Next, go to the password and authentication section of your settings.](img/21-gh-passkey.png)

2. ![Click on Add a passkey.](img/22-gh-add-passkey.png)

3. ![Your computer will ask you to save your passkey.](img/23-ms-save-passkey.png)

4. ![Next, confirm that your passkey was created.](img/24-ms-ok-passkey.png)

5. ![Give the passkey a nickname on GitHub so that you can identify it in the future.](img/25-gh-passkey-nickname.png)

---

## Sign up for the DigitalWaters-fi GitHub organization

Only organization members have access to the VRE. You can request access using the [DigitalWaters-fi organization registration form](https://forms.cloud.microsoft/pages/responsepage.aspx?id=muScnwFRo0qMdQ1ZNa1lJWEtMFscU0JOr8HqIPYV7uJUN0xYMlpTMVBKOTI2MUVJOFpNMkZaNUdOSi4u&route=shorturl)]

1. ![Fill out the form and submit. If you are not doing this as part of an event, please also send a message to the administrators of the organization on GitHub.](img/31-org-signup-form.png)

2. ![Next, on GitHub, go to your organizations page.](img/32-gh-organizations.png)

3. ![You should see and invitation to the organization once your form has been processed.](img/33-gh-accept-org.png)

4. ![Confirm that you want to join the organization.](img/34-gh-join-org.png)

5. ![You should now see a confirmation message.](img/35-gh-org-confirm.png)

---

## Launch a notebook on the VRE

Next, go to the [DigitalWaters-fi homepage](https://github.com/DigitalWaters-fi)

1. ![Navigate to the `Getting Started` section and click the link to the `Virtual Research Lab`.](img/41-open-vre.png)

2. ![Click `Sign in with GitHub`](img/42-vre-sign-in.png)

3. ![Confirm that you want to authorize the Virtual Research Lab application.](img/43-vre-authorize.png)

4. ![Search for Water, and then select the WaterDigitalization.v1 notebook. ***It is important to select the version ending with v1*** or you will not be able to follow subsequent instructions.](img/44-vre-select-notebook.png)

5. ![Click `Launch`](img/45-vre-launch.png)

6. ![You will now see the notebook starting up.](img/46-vre-starting.png)

---

## Log into GitHub from the VRE to authorize your account

### Generate an SSH key on the VRE

This key will be stored in your home folder, which will be available from any notebook on the VRE.

1. ![Launch a `Terminal` window](img/51-jl-launcher.png)

2. ![Type the command `gh auth login` and press enter.](img/52-jl-cli-gh-login.png)

3. ![Select GitHub.com and press enter.](img/53-jl-cli-gh-github.png)

4. ![Select SSH and press enter.](img/54-jl-cli-gh-protocol.png)

5. ![Press enter to confirm you want to generate a new SSH key.](img/55-jl-cli-gh-gen.png)

6. ![Enter your passphrase. If your code is not extremely sensitive, you can skip this step and press enter to save extra steps later on. Your work will still be quite secure without a passphrase.](img/56-jl-cli-gh-pass.png)

7. ![Enter a title for your SSH key so that you can remember which one it is in the event that you need to remove authorization.](img/57-jl-cli-gh-title.png)

8. ![Select that your want to log in in a web browser.](img/58-jl-cli-gh-browser.png)

9. ![Copy your code and click the link to open GitHub.](img/59-jl-cli-gh-open.png)

10. Finally, paste your code into the GitHub window that opens.

### Authorize your account on GitHub

1. ![Confirm that you want to activate your SSH key.](img/60-gh-activation.png)

2. ![Confirm that you want to authorize your SSH key.](img/61-gh-authorize.png)

3. ![Confirm that you want to sign in with your passkey.](img/62-gh-passkey.png)

4. ![You should now see a confirmation message.](img/63-gh-connected.png)

### Check that your authorization was successful

1. ![In your terminal on the VRE, type the command `gh auth status`. You should see a green checkmark if you were successful.](img/71-jl-cli-gh-status.png)

2. ![On the GitHub side, go to your settings page.](img/72-gh-settings.png)

3. ![Select `SSH and GPG keys`. You should now see your new SSH here on GitHub as well.](img/73-gh-ssh-confirm.png)

## Configure `git`

Finally, head back to the terminal on the VRE, and enter the following commands, making sure to replace `Your Name` with your *actual* name a and `your.email@email.com` with your *actual* email. The name and email is required by `git`. They do not have to match your GitHub account; they are used by your collaborators to see what changes you have made.:

```
git config --global user.name "Your Name Here"
```

```
git config --global user.email "your.email@email.com"
```

Next, configure your text editor if you wish. The default text editor, `vi` can be a bit confusing if you are not use to it (but of course you are welcome to use it if you like it!):

```
git config --global core.editor nano
```

Finally, set your merge strategy. For scientific programming the merge strategy doesn't usually matter, but having a default selected will make your life easier when you try to pull in changes your collaborators have made. This code sets the strategy to merge rather than rebase or fast-forward, meaning that if there are multiple users making changes at the same time git will attempt to create its own composite change rather than implement the changes sequentially.

```
git config --global pull.rebase false
```
