# Unmapped store

The catalogue behind the Marketplace in [Unmapped](https://github.com/bryanttchernovkov/unmapped).
The game reads [`catalogue.yaml`](catalogue.yaml) and installs a universe by downloading the
latest release zip from that universe's own GitHub repository.

## Adding a universe

1. In the universe's repository, add the release workflow (from the engine's universe-author skill)
   and push a version tag such as `v0.1.0`. The release must carry `<id>-<tag>.zip`.
2. Add a cover to `covers/`: a JPEG of about 1200 px wide and under 400 KB. **Covers must be safe
   for work**, whatever the universe is: the Marketplace shows them before anyone opts in. A
   universe without a safe-for-work cover isn't listed.
3. Add an entry to `catalogue.yaml`:

   ```yaml
   - id: graystone                     # the universe's id
     name: Graystone
     tagline: One line under the name.
     repo: owner/graystone             # GitHub owner/name, not a URL
     cover: covers/graystone.jpg
     maturity: mature                  # everyone (default) or mature
     format: 2                         # the content format of its latest release
   ```

4. Check it with `./umt store validate <path to this repo>` from the engine repository.

## Licence

The catalogue is [MIT](LICENSE). Each cover image belongs to its universe and is under that
universe's own licence.
