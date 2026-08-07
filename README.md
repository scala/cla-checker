# LEGACY

This action is no longer in use.

To migrate to the new Scala CLA checker

1. [github.com/apps/scala-cla-bot](https://github.com/apps/scala-cla-bot) "Configure". Under "Repository access", add the repo.
1. Sign in to [cla.scala-lang.org](https://cla.scala-lang.org), "Configure CLA"
1. Selct the added repo, "Paste a URL from a Gist", `https://gist.github.com/scala-cla/a35963c850090b3f7efec825959693d5`
1. Enable "Share the Gist"
1. Click "Link" and confirm
1. Create a PR to remove the legacy checker. Example: [scala/scala#11266](https://github.com/scala/scala/pull/11266)


# cla-checker

Checks if the author has signed the Scala CLA

Usage
-----

Here's an example that checks if author of Pull Requests had signed Scala CLA.

```yaml
name: "Check Scala CLA"
on:
  pull_request:
jobs:
  cla-check:
    runs-on: ubuntu-latest
    steps:
      - name: Verify CLA
        uses: scala/cla-checker@v1
        with:
          author: ${{ github.event.pull_request.user.login }}
```
