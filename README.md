# claude-session

One static page, served by GitHub Pages, that turns an https link into a
Claude desktop app deep link. GitHub strips `claude://` link targets from PR
descriptions, so PRs link here instead:

```
https://carbonara-app.github.io/claude-session/#local_<session id>
```

The page checks that the part after `#` is a Claude Code session id
(`local_…`) and forwards to `claude://claude.ai/epitaxy/<session id>`. Anything
else shows an error and goes nowhere. Once the Claude app takes focus, the
page goes back in history to the PR (or closes itself when it is the only page
in a new tab), so the redirect page never stays open. The id stays in the URL fragment, so it
never reaches a server.

The session opens only on the Mac that ran it, in the Claude desktop app.

Used by `.agents/skills/pull-requests/SKILL.md` in
`Carbonara-App/carbonara-restaurant`.
