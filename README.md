# gitlab-backup

Easily backup all projects from one GitLab instance
and then restore them to another one.

Uses GitLab's API, `git clone --mirror` and `git push --mirror`.

## Configuration

Create a file called `.access_tokens.json` next to `gitlab-backup`
containing a map from GitLab hosts to personal access tokens.

Example:

```json
{
  "gitlab.com": "...",
  "gitlab.example.org": "..."
}
```

## Usage

To backup all projects you have access to on `gitlab.com` and push them `gitlab.example.org`:

```sh
./gitlab-backup backup gitlab.com
./gitlab-backup restore gitlab.com gitlab.example.org
```

## TODO

- Don't hardcode my username for detecting own projects when restoring
- Allow a custom naming scheme when restoring
- Better error handling with retries
