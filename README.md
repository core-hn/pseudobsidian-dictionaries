# PseudObsidian — Dictionaries

Dépôt de dictionnaires pour le plugin [PseudObsidian-ization](https://github.com/core-hn/pseudobsidian-ization).

Les dictionnaires sont proposés directement dans le wizard du plugin et téléchargés dans le vault de l'utilisateur. Aucune donnée de transcription ne transite par ce dépôt.

## Dictionnaires disponibles

| Fichier | Type | Langue | Rôles | Source |
|---|---|---|---|---|
| `fr-communes.dict.json` | Lieu | FR | Détection + Remplacement + Classes | GeoAPI INSEE |

## Format

Chaque fichier suit le format `DictionaryFile` défini dans [SPECS.md](https://github.com/core-hn/pseudobsidian-ization/blob/main/SPECS.md) du plugin. L'en-tête contient :

- `roles` — `detection`, `replacement`, `classes` (booléens)
- `configSchema` — variables configurables avec valeurs possibles et défauts
- `config` — configuration active (classificationMode, conditions, incrementScope…)
- `author`, `doi`, `license`, `source` — attribution

## Régénérer `fr-communes.dict.json`

```bash
cd ../Pseudobsidianization
node scripts/build-cities.mjs
cp assets/cities.dict.json ../pseudobsidian-dictionaries/fr-communes.dict.json
```

Le script requiert Node ≥ 18 et une connexion internet (appel à `geo.api.gouv.fr`).

## Contribuer un dictionnaire

Ouvrez une issue ou une pull request. Le fichier doit :
- Respecter le schéma `DictionaryFile` (version 1.1)
- Inclure `author`, `license`, `source`
- Ne contenir aucune donnée personnelle

## Licence

Les dictionnaires héritent de la licence de leur source. `fr-communes.dict.json` : Licence Ouverte v2.0 (données INSEE/IGN).
