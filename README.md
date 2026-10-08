# Configurateur MURAO Multi-splits

Page autonome (HTML, CSS et JavaScript sans dépendance). Elle n'a besoin d'aucune compilation.

## Contenu

- `index.html` : le configurateur et le récapitulatif.
- `img/` : les 7 photos (groupe blanc et noir, Premium blanc et noir, Smart, Access, cassette DOJO).

## Ajouter au hub

**Site statique (HTML simple)**
Copiez le dossier à la racine du dépôt, par exemple `murao/`. La page s'ouvre sur `/murao/`.

**Next.js**
Copiez le dossier dans `public/murao/`. La page s'ouvre sur `/murao/index.html`. Pour une adresse `/murao`, ajoutez dans `next.config.js` :

```js
async rewrites() {
  return [{ source: '/murao', destination: '/murao/index.html' }];
}
```

**Autre outil (Vite, Astro…)**
Même principe : placez le dossier dans le dossier des fichiers publics (`public/`).

Ne changez pas les noms de fichiers du dossier `img/`, la page les appelle par leur chemin relatif.

## Données

- Tarif catalogue Atlantic, pages 557 à 559, prix en € HT.
- Les prix du cuivre et des câbles se saisissent dans la page. Ils sont gardés dans le navigateur (localStorage).
- Pour mettre à jour les prix du catalogue, modifiez les tableaux `GROUPS` et `RANGES` au début du script de `index.html`.
