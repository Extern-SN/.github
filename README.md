# .github

Modèles d'issue communs aux dépôts de l'organisation Extern-SN.

GitHub les applique à tout dépôt de l'organisation qui n'a pas son propre dossier `.github/ISSUE_TEMPLATE`. Un dépôt qui en crée un remplace l'ensemble de ces modèles, pas seulement l'un d'eux.

| Formulaire | Label | Usage |
|---|---|---|
| Tâche | `feature` | Développement chiffré en taille XS à XXL |
| Bug | `bug` | Comportement incorrect constaté |
| Constat d'audit | `audit` | Écart relevé lors d'un audit |

Chaque formulaire commence par un champ "Référence d'origine" (ticket GLPI, tâche Odoo ou client), facultatif : une demande interne sans référence prend l'issue elle-même comme référence.

Le modèle de PR (`pull_request_template.md`) rappelle les règles vérifiées par `validate-pr` dans les dépôts qui l'appellent : branche `feature/`, `fix/` ou `hotfix/`, et un seul label de version. Comme pour chaque fichier commun, un dépôt qui a le sien le garde.

`CONTRIBUTING.md` et `SECURITY.md` servent de défaut de la même façon.

`.github/workflow-templates/` propose des workflows d'amorce dans l'onglet Actions de chaque dépôt (« New workflow », section de l'organisation). Ils ne font qu'appeler le kit `Extern-SN/github-workflows` au tag `v1` : validation des PR, tag de version, sécurité des workflows, CI PHP, Node ou Python. Un workflow créé ainsi est une copie, il ne suit pas les évolutions de l'amorce.

Un label posé par un formulaire n'est appliqué que s'il existe à la fois dans ce dépôt et dans le dépôt cible. Les issues créées par `gh issue create --body` ne passent pas par ces formulaires.

Ce dépôt est public, condition imposée par GitHub pour que les modèles d'issue s'appliquent à toute l'organisation. N'y mettre aucune information interne.
