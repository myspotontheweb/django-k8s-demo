# Releases

## Changes

Create a changelog entry

```bash
changie new
```

## Create a new release

```bash
changie batch auto
changie merge

git add .
git commit -m $(changie latest)
git push

gh release create $(changie latest) -F .changes/$(changie latest).md
```