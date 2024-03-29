[![Maintenance](https://img.shields.io/badge/Maintained%3F-no-red.svg)](https://GitHub.com/betagouv/andi-docker/graphs/commit-activity)
[![Generic badge](https://img.shields.io/badge/ANDi-toujours-green.svg)](https://shields.io/)

<p align="center">
  <a href="https://andi.beta.gouv.fr">
    <img alt="Début description. Marianne. Fin description." src="https://upload.wikimedia.org/wikipedia/fr/3/38/Logo_de_la_R%C3%A9publique_fran%C3%A7aise_%281999%29.svg" width="90" />
  </a>
</p>
<h1 align="center">
  andi.beta.gouv.fr
</h1>

[ANDi](https://andi.beta.gouv.fr) est une service numérique en développement visant à faciliter l'immersion professionnelle des personnes en situation de handicap.

# 🧪 andi-data
Outils, traitements et résultats d'analyses de données d'ANDi, sous forme de notebooks jupyter.

#### Pour lancer l'environnement notebook:

- disposer Python 3.7 dans votre environnement
- disposer de pipenv
- lancer `pipenv install` à la racine du projet
- lancer **jupyter** par la commande `make jupyter`

note: si vous préférez **pip**, un `pip install jupyter` suivi de  `jupyter notebook` suffit également, bien que certains dépendances pourraient manquer (cf `requirements.txt`).

#### Quant au répertoires :

- les différents notebooks se trouvent dans le répertoire **notebooks**
- ressources et référentiels sont dans le répertoire **ressources**
- les listings générés par les notebooks le sont dans le répertoire **outputs**


## Les notebooks :
Les notebooks contiennent leur propre documentation, autant sous forme de commentaires que sous forme de cellules de texte.
Une connaissance de base des outils et concepts en science des données sous Python (numpy, panda, matpotlib) est suggérée pour leur pleine compréhension et utilisation.

### pg_siren_export
Test sur les données de la base de données SIRENE tels que stockées dans la BD PostgreSQL d'ANDi,
première analys sur la taille des secteurs d'activité (par NAF) et le nombre d'établissements.

### analyse_rome_naf_taille
Premières analyses sur les codes ROME et NAF afin de générer un tableau de correspondance.

### correspondance_rome_naf
Notebook qui génère le tableau de correspondance ROME vers NAF à destination du composant matching d'ANDi.

### geogocage_entreprises
Travail de vérification de l'import des entreprises: plotting et heatmap sur la carte du territoire de la France métropolitaine.

### matching_refactor
Vu les besoins croissants de performance de l'algo de matching, un notebook à été organisé pour essayer diverses alternatives. 
La solution finale, impliquant le passage sous PostGIS et la réecriture de l'algorithme, améliore la performance d'un ordre de grandeur,
passant pour la recherche sur Paris de 8s à 800ms. 

### suggestion_rome_ogr
Travail sur la suggestion des ROME à partir d'une saisie texte.
La recherche se fait sur base des labels des codes ROME et OGR, en Python pur.

## Les ressources :
[Le repository de LaBonneBoîte (Pôle Emploi)](https://github.com/StartupsPoleEmploi/labonneboite) contient 
quantité de ressources et analyses très intéressantes qui se sont révélées cruciales au développement du 
service matching d'ANDi. Les notebooks et analyses de ce repository ne sont que la continuation des travaux
entamés par LBB.

## Les résultats :
- andi\_rome2naf\_\[date\].csv : tableau de correspondance pondéré ROME vers NAF
