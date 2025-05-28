# Meetup Arkup juin 2025

### Copyright Bertrand Florat 2025

### Licence
Creative Commons Attribution-ShareAlike 4.0 International License.

## Tips

### Preview

```bash
npx @marp-team/marp-cli@latest slides.md --template bespoke -p -o index.html
```

### Déploiement en HTML + PDF

```bash
export COMMIT_HASH=$(git rev-parse --short HEAD) 
export BUILD_DATE=$(date +%Y-%m-%d)
envsubst < slides.md > slides.generated.md
npx @marp-team/marp-cli slides.generated.md --html --template bespoke --allow-local-files -o index.html
npx @marp-team/marp-cli@latest slides.generated.md --pdf --allow-local-files -o slides-meetup-arkup-2025.pdf
```

