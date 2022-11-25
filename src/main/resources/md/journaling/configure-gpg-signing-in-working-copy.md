# Configure GPG Signing in Working Copy

Assuming you have [Universal Clipboard](https://support.apple.com/en-us/HT209460) configured between your Mac and iPhone **and** you have already created GPG keys on your Mac, the process for adding them to Working Copy is quite painless. Feel free to refer to [Working Copy's official documentation for signed commits](https://workingcopyapp.com/manual/signed-commits); however, the guide below should enumerate the required steps more clearly.

On the Mac:

1. Open *Terminal*
2. List all existing GPG keys and associated email addresses on the system:

    ```shell script
    gpg --list-secret-keys --keyid-format LONG
    ```
   
3. Copy the private GPG key for one of the email addresses (this will likely require you to enter the password of the GPG key):

    ```shell script
    (gpg --armor --export-secret-key $EMAIL_ADDRESS) | pbcopy
    ```

As long as Universal Clipboard is properly configured, the iPhone's clipboard is now loaded with the private GPG key. Assuming you have already set up the identity (with the desired email address) within Working Copy, proceed to configure the identity for GPG signing. 

On the iPhone:

1. Open *Working Copy*
2. Select the *gear icon* in the top-left
3. Select *Identities*
4. Select the identity for the email address tied to the private GPG key copied above
5. Select *Signing*
6. Select *Import from Clipboard*
7. Enter the password of the GPG key

Now, you should be able to sign your commits from Working Copy.
