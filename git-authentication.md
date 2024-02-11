# Git authentication

To properly authenticate on github.com with the git CLI tool, a 'personal access token' needs to be configured. [1]

## Credential helper

Git CLI uses a credential helper where cached credentials are stored. For MacOS, the 'osxkeychain' can be used to securely store credentials.

```% git config --get credential.helper```

Result: ```osxkeychain```

# Links
[1] https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens
