## Sublime Text: Markdown

#### Preview markdown
My favorable to work write markdown in Sublime (https://github.com/revolunet/sublimetext-markdown-preview).

##### Issue: github API responded in an unfashion way
Have just got this message *cannot convert markdown* the Sublime kept prompting a dialog *github API responded in an unfashion way :/*. 
I found out I reached a rate limit (for non-authorized accounts). Luckily, we could setup the *Github auth token* for the package in the config:
```
"github_oauth_token": "_TOKEN_GOES_HERE_"
```
Tracking issue: https://github.com/revolunet/sublimetext-markdown-preview/issues/292
