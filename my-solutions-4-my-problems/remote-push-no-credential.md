THIS GUIDE REFERS TO ONLY LINUX SYSTEMS

This is a shortly guide to avoiding the tedious problem of entering you github credentials (or a token) for each `git push` command launched.


Follow these steps:

0. [Original guide](https://github.com/GitCredentialManager/git-credential-manager)
1. ASSUMING YOU ARE USING AN UBUNTO-BASED DISTRO (otherwise see the 0 point):
  Install the (only one) .deb package [from the latest project release](https://github.com/GitCredentialManager/git-credential-manager/releases).
2. Run:
  
    ```shell
    sudo dpkg -i <path-to-package>
    git config --global credential.credentialStore gpg
    ```

3. Launch the following command to check the situation:
  
    ```
    git-credential-menager-core diagnose
    ```
    If you don't get any error, you are ready to launch `git push` command without further impediments, but if an error appears in the `Credential storage` line, run:

    ```
    git config --global credential.credentialStore cache
    ```
    And if also this way was unsuccessful, it's time to see the [appropriete documentation](https://github.com/GitCredentialManager/git-credential-manager/blob/main/docs/configuration.md#credentialcredentialstore).

Useful tips:
- [Command-line usage](https://github.com/GitCredentialManager/git-credential-manager/blob/main/docs/usage.md)
- Run: `git-credential-menager-core --help`
