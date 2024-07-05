# Push to Gist

This is a Github Action to push a file to Gist.

## Quick start

```yml
- uses: actions/checkout@v3
- name: Deploy
  uses: stellarhub/push-gist-action@v1
  with:
    token: ${{ secrets.GIST_TOKEN }}
    gist_id: from_gist_url
    file_path: build/book.pdf
    file_type: binary
```

## Setup

### Prep work

1. Create a gist (public or secret) if you don't have one.
1. Generate a new [Personal access token](https://github.com/settings/tokens/). Only the `gist` scope is needed.

### Project setup

1. Go to the repo **Settings > Secrets**. Add the generated token with name `GIST_TOKEN`.
1. Edit workflow file `.github/workflows/deploy.yml` as the example above.

### Options

#### `token`

Personal access token for updating gist.

#### `gist_id`

Id portion from the gist url, e.g. `https://gist.github.com/stellarhub/`**`e885afa349a0e5d1cfb408e46d6a37bc`**.

#### `gist_description` (optional)

Description of the gist.

#### `gist_file_name` (optional)

Name of the file to be added in the gist. If not provided, the original file name from `file_path` will be used.

#### `file_path`

Relative to the current repo's root directory, e.g. `dist/foo.bar`.

#### `file_type` (optional)

Default to `text`. It should be set to `binary` if the file is image, pdf, etc.

## License

[MIT License](https://github.com/stellarhub/actions-deploy-gist/blob/main/LICENSE) © 
