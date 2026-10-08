# Configurateur Multi-splits et Mono-splits (Atlantic, Sinclair, Midea)

Page autonome (HTML, CSS et JavaScript sans dépendance). Elle n'a besoin d'aucune compilation.

## Contenu

- `index.html` : le configurateur et le récapitulatif.
- `img/` : les photos Atlantic (groupe blanc et noir, Premium, Smart, Access, cassette DOJO) Sinclair (groupe, Keyon, Marvin en 4 couleurs) et Midea (groupe, Breezeless E, Solstice blanche et noire).

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

- Atlantic MURAO : tarif catalogue pages 557 à 559, prix en € HT.
- Sinclair : fiches techniques pages 24, 33 et 34, et prix des groupes et unités intérieures du devis Clim Distrib DE/1124 (€ HT). Les options (télécommandes filaires) se saisissent dans la page (tableau « Prix à saisir »).
- Midea : prix du devis E0001091 (€ HT), fiches techniques et brochures Midea (Breezeless E, Solstice, groupes multi). Gamme mono-split Midea incluse. Mono-split Atlantic (Premium, Smart) et Sinclair (Keyon, Marvin) : prix du devis E0001092.
- Liaisons frigorifiques : couronnes doubles 1/4 + 3/8, 1/4 + 1/2, 3/8 + 1/2, 3/8 + 5/8 (prix et longueur saisis dans la page).
- Variantes automatiques entre les 3 marques : Premium = Marvin = Solstice, Access = Keyon = Breezeless E.
- Les prix du cuivre et des câbles se saisissent dans la page. Ils sont gardés dans le navigateur (localStorage).
- Pour mettre à jour les prix du catalogue, modifiez les tableaux `GROUPS_A` et `RANGES_A` (Atlantic) `GROUPS_S` et `RANGES_S` (Sinclair) ou `GROUPS_M` et `RANGES_M` (Midea) au début du script de `index.html`.
- Éco-participation : montants Atlantic repris pour les produits sans valeur (unités intérieures 1,75 €, groupes 2 postes et mono 7,69 €, 3 postes et plus 10,02 €, télécommandes filaires 0,14 €).
- Devis clients : enregistrés dans le navigateur (localStorage, clé murao-devis-v1) avec leurs variantes ; export et import en fichier JSON depuis le récapitulatif.
