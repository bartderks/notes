# Git authentication

When trying to use a github.com account in the ```git``` CLI tooling, I had an issue authenticating to github.com due to credentials for a different git solution (work related) were already cached.

## Credential helper

Git CLI uses a credential helper where cached credentials are stored:

```% git config --get credential.helper```

Result: ```osxkeychain```

When using ```git clone```, with a HTTPS endpoint, the username needs to be provided so the credential.helper knows the git endpoint needs to use a different username. [1]

Tried this without username in the URL results in the following issue.

# Links
[1] https://stackoverflow.com/questions/24275375/how-can-i-store-keychain-credentials-for-multiple-github-accounts 
