# HOW-TO: Connect your account on the DIWA Virtual Research Environment (VRE) to GitHub

Goals:

  * Create a GitHub account with two-factor authentication
  * Learn how to authenticate to GitHub on the command line using GitHub CLI
  * Set up your account so that you can pull and push changes from GitHub to the VRE

## Create your GitHub accound


1. ![Go to https://github.com/signup and complete the form](img/01-gh-signup-filled.png)
2. You will be asked to verify your email address. Go check your email for the verification link.
3. ![When you have created your account, you should see this success alert.](img/02-gh-signup-success.png)
.keep
	
## Fill out your GitHub profile (optional, but recommended)

1. ![](img/11-gh-settings.png)
2. ![](img/12-gh-profile-a.png)
3. ![](img/13-gh-profile-b.png)

## Set up a two-factor authentication

This will be required to use the VRE in the future.

1. ![](img/21-gh-passkey.png)
2. ![](img/22-gh-add-passkey.png)
3. ![](img/23-ms-save-passkey.png)
4. ![](img/24-ms-ok-passkey.png)
5. ![](img/25-gh-passkey-nickname.png)

## Sign up for the DigitalWaters-fi GitHub organization

Only organization members have access to the VRE.

1. ![](img/31-org-signup-form.png)
2. ![](img/32-gh-organizations.png)
3. ![](img/33-gh-accept-org.png)
4. ![](img/34-gh-join-org.png)
5. ![](img/35-gh-org-confirm.png)

## Launch a notebook on the VRE

1. ![](img/41-open-vre.png)
2. ![](img/42-vre-sign-in.png)
3. ![](img/43-vre-authorize.png)
4. ![](img/44-vre-select-notebook.png)
5. ![](img/45-vre-launch.png)
6. ![](img/46-vre-starting.png)

## Log into GitHub from the VRE to authorize your account

### Generate an SSH key on the VRE

This key will be stored in your home folder, which will be available from any notebook on the VRE.

1. ![](img/51-jl-launcher.png)
2. ![](img/52-jl-cli-gh-login.png)
3. ![](img/53-jl-cli-gh-github.png)
4. ![](img/54-jl-cli-gh-protocol.png)
5. ![](img/55-jl-cli-gh-gen.png)
6. ![](img/56-jl-cli-gh-pass.png)
7. ![](img/57-jl-cli-gh-title.png)
8. ![](img/58-jl-cli-gh-browser.png)
9. ![](img/59-jl-cli-gh-open.png)

### Authorize your account on GitHub

1. ![](img/60-gh-activation.png)
2. ![](img/61-gh-authorize.png)
3. ![](img/62-gh-passkey.png)
4. ![](img/63-gh-connected.png)

### Check that your authorization was successful

1. ![](img/71-jl-cli-gh-status.png)
2. ![](img/72-gh-settings.png)
3. ![](img/73-gh-ssh-confirm.png)
