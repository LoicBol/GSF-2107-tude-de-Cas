<div align="center">

# Travail de session

### GSF-2107, automne 2026

Date limite : 4 décembre 2026

</div>

## 1. Mise en contexte

Vous êtes une équipe d’experts en finance venant en appui aux conseillers et planificateurs financiers de votre organisation lorsqu’une demande d’un client requière une analyse quantitative.

En ce premier jour de travail de 2027, votre directrice vous demande d’analyser le dossier de *Marie Tremblay*, une ingénieure de 32 ans, qui hésite à se lancer en affaire en créant son entreprise. Avant de prendre sa décision, Mme Tremblay souhaite une évaluation des impacts probables de cette décision sur sa qualité de vie à la retraite en tenant compte de trois profils d’investissement distincts.

Plus précisément, vous devrez :

1. Modéliser l’évolution des revenus annuels de Marie Tremblay selon qu’elle se lance en affaires et crée son entreprise ou non.
2. Calculer le surplus (nouveaux placements) ou le déficit (nouvelle dette) annuel en soustrayant toutes les dépenses des revenus
3. Modéliser l’évolution de la valeur des placements accumulés selon les trois profils d’investissement
4. Modéliser l’évolution de la valeur marchande de la résidence principale
5. Calculer la valeur nette à la fin de chaque année
6. Estimer la probabilité (pourcentage des scénarios générés) que la valeur nette de Mme Tremblay au moment de prendre sa retraite soit supérieure à la cible fixée
7. Répéter l’analyse selon :
   - A1 – Mme Tremblay demeure salariée toute sa carrière
   - A2 – Mme Tremblay se lance en affaires
   - B1 – Profil d’investissement prudent (faible risque, faible rendement espéré)
   - B2 – Profil d’investissement équilibré (risque modéré, rendement espéré modéré)
   - B3 – Profil d’investissement audacieux (risque élevé, rendement espéré élevé)

   **→ 6 combinaisons** (A1/A2 × B1/B2/B3)

## 2. Informations clés sur votre cliente

- **Date de naissance :** 31 décembre 1995
- **Sources de revenus et dépenses :**

| | Montant 2026 | Hypothèses |
|---|---:|---|
| **Revenus** | | |
| Salaire | 95 000 \$ | Variations futures à modéliser (voir consignes) |
| Dividende d'entreprise | 0 \$ | Variations futures à modéliser (voir consignes) |
| **Dépenses** | | |
| Remboursement emprunt hypothécaire | 38 900 \$ | Montant fixe. Dernier paiement en 2057 |
| Dépenses essentielles (nourriture, vêtement, transport, taxes municipales, etc.) | 38 000 \$ | Croissance annuelle de 3% |
| Dépenses compressibles (restaurant, loisir, voyage, etc.) | 11 400 \$ | 12% des revenus totaux à chaque année |
| Remboursement des autres dettes | 0 \$ | Remboursement de 20% du solde + intérêts selon taux en vigueur |
| **Surplus (placement) ou déficit (autres dettes)** | **6 700 \$** | Montant inclus dans la valeur des placements au 31/12/2026 |

- **Bilan personnel au 31 décembre 2026 :**

| | Au 31 décembre 2026 | Hypothèses |
|---|---:|---|
| **Actifs** | | |
| Placements | 45 000 \$ | Selon profil d’investisseur (voir consignes) |
| Propriété (résidence principale) | 920 000 \$ | Selon résultat modélisation (voir consignes) |
| Entreprise (valeur nette de revente) | 0 \$ | Selon résultat modélisation (voir consignes) |
| **Passifs** | | |
| Emprunt hypothécaire (solde) | 598 000 \$ | Remboursement progressif sur 30 ans (jusqu’en 2057) |
| Autres dettes | 0 \$ | Taux d’intérêt applicable : Taux bons du trésor au 31 décembre de chaque année. 20% du solde est remboursé à chaque année |
| **Valeur nette** | **367 000 \$** | |

- **Objectif de retraite :**

Le planificateur financier associé à ce dossier évalue que Marie devra avoir accumulé 3 500 000 \$ à 65 ans (il s’agit de la cible de valeur nette à la fin de 2060) afin de répondre à ses besoins financiers à la retraite.

## 3. Consignes de modélisation

### 3.1 Variables économiques

**• Taux d’intérêt :** Il s’agit du taux des bons du trésor canadien dont l’évolution trimestrielle devra être modélisée. Le taux d’intérêt au 31 décembre 2026 est de 3,10 %.

La variation trimestrielle du taux d’intérêt doit être modélisée via[^1] :

```math
\Delta r_t = 0{,}1 \times (0{,}03 - r_{t-1}) + 0{,}02 \times \sqrt{r_{t-1}} \times Z_t
```

Où :
- $`\Delta r_t`$ est l’écart entre le taux d’intérêt à la fin du trimestre *t* et celui à la fin du trimestre *t-1*
- $`r_{t-1}`$ est le taux d’intérêt à la fin du trimestre précédent
- $`Z_t`$ est un nombre aléatoire distribué selon une loi normale centrée réduite

**• Salaires hebdomadaires moyens :** Il s’agit de la rémunération hebdomadaire moyenne au Québec à travers tous les secteurs d’activité. Le salaire moyen au 31 décembre 2026 est de 1 275 \$.

Pour les fins de l’exercice de modélisation, vous devrez supposer que la croissance des salaires (en pourcentage) d’un trimestre à l’autre suit la distribution empirique de la variation des salaires. Les données historiques de décembre 2000 à juin 2026 se retrouvent à l’onglet « Salaire » du fichier Excel « Données_A26 ».

**• Population :** Il s’agit de la population totale de la province de Québec. Cette variable sera exprimée sur une base annuelle.

Pour les fins de l’exercice de modélisation, vous devrez utiliser les projections de population de l’Institut de la Statistique du Québec pour les années 2027 à 2060. Assurez-vous de retenir les projections du scénario « référence (A2026) » pour les deux sexes (Sexe = 3).

Les données se retrouvent dans le fichier Excel (Tableaux détaillés) « Population selon l’âge et le sexe, scénarios d’analyse de 2026, Québec, 2021-2071 » disponible au : <https://statistique.quebec.ca/fr/document/projections-de-population-le-quebec>

**• Rendements boursiers du S&P 500 :**

La variation annuelle des rendements boursiers doit être modélisée via :

```math
r_t = \mu + \sigma Z_t
```

Où :
- $`\mu`$ est le rendement annuel moyen de l’indice du S&P/500 de 1925 à 2025
- $`\sigma`$ est l’écart-type des rendements annuels de l’indice du S&P/500 sur la même période

**• Federal Funds Rate (FedFund) :** Le taux des Fed Funds à la fin de chaque année future est assumé égal au taux des bons du trésor canadiens 12 mois (voir Taux d’intérêt ici-haut)

### 3.2 Revenus d’emploi de Mme Tremblay

Lorsque Mme Tremblay est salariée (et non à la direction de son entreprise), l’évolution annuelle de son salaire sera modélisée comme suit :

- 10% de chance de bénéficier d’une augmentation de 5,00%
- 40% de chance de bénéficier d’une augmentation de 2,50%
- 45% de chance de bénéficier d’une augmentation de 1,50%
- 5% de (mal)chance de subir une diminution de salaire de 2,00%

### 3.3 Création d’entreprise et implications

La décision de créer une entreprise doit être prise immédiatement (début 2027) et ne peut être remise à plus tard. Lors de la création de l’entreprise, Mme Tremblay :

- Retire ses placements de 45 000 \$ ;
- Contracte une nouvelle dette de 55 000 \$ ;
- Quitte son emploi et renonce de facto à son salaire annuel

En contrepartie :

- La valeur nette de revente de l’entreprise au début 2027 est fixée à 100 000 \$ au moment de sa création.
- Trois scénarios basés sur la probabilité estimée qu’une année connaisse du « succès » entrepreneurial sont possibles :
  - **I. Probabilité supérieure à 75% : Succès important**
    - La valeur nette de revente de l’entreprise croît de 25%
    - La propriétaire (Mme Tremblay) se verse un salaire net de 150 000 \$
    - La propriétaire (Mme Tremblay) se verse un dividende équivalent à 5% de la valeur nette de revente de l’entreprise, après augmentation
  - **II. Probabilité située entre 25 et 75% : Succès modéré**
    - La valeur nette de revente de l’entreprise croît de 10%
    - La propriétaire (Mme Tremblay) se verse un salaire net de 120 000 \$
    - La propriétaire (Mme Tremblay) se verse un dividende équivalent à 2% de la valeur nette de revente de l’entreprise, après augmentation
  - **III. Probabilité inférieure à 25% : Échec**
    - La valeur nette de revente de l’entreprise diminue de 15%
    - La propriétaire (Mme Tremblay) se verse un salaire net de 90 000 \$
    - La propriétaire (Mme Tremblay) ne se verse aucun dividende
- Deux situations peuvent entraîner la fin de l’entreprise. À ce moment Mme Tremblay vend l’entreprise à sa pleine valeur nette de revente (cette valeur est considérée comme un dividende pour les fins de l’exercice de modélisation). L’année suivante, Mme Tremblay redevient salariée et conservera un salaire annuel constant de 95 000 \$ jusqu’à sa retraite.
  - a. La valeur nette de revente chute en-deçà de 50 000 \$.
  - b. Mme Tremblay découvre qu’elle a une faible aptitude pour l’entrepreneuriat

> **Aptitude pour l’entrepreneuriat.** Une entrepreneure ne sait pas parfaitement dès le départ si elle possède les aptitudes nécessaires au succès. Cette aptitude peut prendre deux états : Aptitude **élevée** ou Aptitude **faible**. Au moment du lancement de son entreprise, Mme Tremblay estime, a priori, avoir 75 % de chance de posséder une aptitude élevée et 25 % de chance de posséder une aptitude faible. À la fin de chaque année, Mme Tremblay observe dans lequel des trois scénarios s’est situé son entreprise et utilise ce signal pour réviser annuellement sa croyance. Mme Tremblay considérera avoir une faible aptitude si sa croyance a posteriori de posséder une aptitude faible surpasse 80%.
>
> - Probabilité d’obtenir un succès important lorsqu’on a une aptitude : **élevée = 60%** | **faible = 10%**
> - Probabilité d’obtenir un succès modéré lorsqu’on a une aptitude : **élevée = 20%** | **faible = 35%**
> - Probabilité d’obtenir un échec lorsqu’on a une aptitude : **élevée = 20%** | **faible = 55%**

- Vous jugez que la probabilité qu'une entreprise connaisse une année de succès dépend de l'environnement économique. Cette probabilité doit être estimée à partir de données historiques plutôt que fixée arbitrairement.

  Les données annuelles couvrant la période 1961 à 2025 sur les variations des taux d'intérêt (Federal Funds Rate) et les rendements de l'indice S&P 500 doivent être utilisées[^2] afin d'établir une relation statistique entre ces variables économiques et la survenance d'une année de succès entrepreneurial. Plus précisément, cette relation statistique devra prendre la forme suivante :

```math
P(\text{Succès}) = \frac{1}{1 + \exp[-(\beta_0 + \beta_1 X_1 + \beta_2 X_2)]}
```

À partir de cette relation estimée, vous devrez être en mesure d'associer à chaque combinaison des variables économiques une probabilité de succès.

### 3.4 Valeur des placements

La croissance annuelle de la valeur des placements accumulés est distribuée selon une loi normale dont les paramètres dépendent du profil d’investissement choisi.

| Profil d’investissement | Espérance | Écart-type |
|:---:|:---:|:---:|
| Prudent | 3% | 10% |
| Équilibré | 6% | 15% |
| Audacieux | 10% | 20% |

### 3.5 Valeur de la propriété (résidence principale)

La variation de la valeur des résidences principales dépend de trois variables économiques, soit la variation des taux d’intérêt, l’évolution des salaires moyens et l’évolution de la population.

Estimez la relation entre ces variables et la variation de l’indice de prix des maisons à partir des données historiques disponibles (utilisez la variation en pourcentage de la dernière données disponibles d’un trimestre à celle de la fin du trimestre précédent pour réaliser cette analyse).

Utilisez les coefficients estimés, conjointement avec la variation annuelle des taux d’intérêt (au 31 décembre de chaque année), la croissance des salaires hebdomadaires (au 31 décembre de chaque année) et la croissance annuelle anticipée de la population pour déterminer la croissance de l’indice de prix des maisons dans le futur. Supposez que la propriété de Mme Tremblay croît au rythme de cet indice de prix des maisons.

## 4. Simulations de Monte Carlo

Puisque l’évolution de la valeur nette de Mme Tremblay est incertaine, vous procéderez par simulations de Monte Carlo pour estimer la probabilité (pourcentage des scénarios générés) que la valeur nette de Mme Tremblay au moment de prendre sa retraite soit supérieure à la cible fixée.

Vous devrez simuler 2 500 scénarios pour chaque combinaison de profil d’investissement et de choix de se lancer ou non en affaires.

## 5. Livrables à remettre

### (A) Code Python (Jupyter Notebook) — 25% de la note

Le code doit être fonctionnel, commenté et reproductible.

- Toutes les manipulations de données doivent être effectuées via Python. Le code doit permettre d’importer les données Excel sans que celles-ci n’aient été modifiées.
- Le code doit être annoté (commentaires avec `#` en début de ligne) afin d’expliquer ce que chaque bloc de code réalise comme étape de calcul.
- **Bien que les IAG peuvent être utilisées pour suggérer ou corriger une ligne de code, les différentes étapes du code doivent avoir été réfléchies par vous.**

### (B) Vidéo de présentation — 30% de la note

Une vidéo d’un maximum de 3 minutes doit être produite pour expliquer à Mme Tremblay les scénarios analysés et interpréter les conclusions obtenues.

- Cette vidéo doit s’adresser à Mme Tremblay (et non à votre professeur)
- Vous devez communiquer clairement la recommandation (quelle décision devrait-elle prendre) en justifiant celle-ci à l’aide des résultats obtenus.
- L’information contenue dans la présentation doit être parfaitement cohérente avec les résultats issus de l’exercice de modélisation. Toute divergence sera fortement pénalisée.

### (C) Rapport technique — 45% de la note

Un rapport pdf d’un maximum de 5 pages doit être produit pour expliquer les étapes de modélisation.

- Le rapport doit présenter les différents modèles utilisés en justifiant leur choix, en faisant un bref rappel des données mobilisées.
- Les résultats clés de chaque modèle doivent être analysés (lorsque approprié : sont-ils fiables? Est-ce que les coefficients estimés sont statistiquement significatifs) ?
- Présentez et justifiez toute hypothèse de calcul qui n’était pas spécifiquement indiquée dans les consignes.

---

[^1]: Cette formulation est inspirée du modèle Cox-Ingersoll Ross utilisé pour modéliser l’évolution des taux d’intérêt court terme. La première partie de l’équation traduit un processus de retour à la moyenne, tandis que la racine carrée dans la deuxième partie empêche les taux de devenir négatif.

[^2]: Considérez que les données historiques américaines reflètent bien le lien entre marché boursier, taux d’intérêt et succès entrepreneurial au Canada.
