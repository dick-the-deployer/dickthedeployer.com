+++
date = "2015-11-22T20:11:22+01:00"
title = "Generic hook"
+++

To notify Dick the Deployer about the changes in repository you can use generic hook.
To do so please send `POST` request to `api/hooks` endpoint, with `json` body:

```json
{
    host: 'my-gitlab.example.com'
    path: 'open-source/wizzard'
    ref: 'master'
    sha: '44a5d78fd58cb9d5de4'
    lastMessage: 'Wand support implemented'
}
```

You can automate this using post-commit hook feature. Docs are avaliable [here](https://git-scm.com/book/uz/v2/Customizing-Git-Git-Hooks).