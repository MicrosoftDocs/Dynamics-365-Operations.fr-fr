---
title: Tâches d'importation et d'exportation de données
description: L'espace de travail Gestion des données vous permet de créer et de gérer des tâches d'importation et d'exportation de données.
author: Sunil-Garg
manager: AnnBe
ms.date: 03/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application user
ms.reviewer: margoc
ms.search.scope: Operations
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ceb2dfa37b53af83c4faedffa5b312d654c44593
ms.sourcegitcommit: 7b438a94b59ab52518e03b22217cb48e41fbeb71
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2019
ms.locfileid: "834658"
---
# <a name="data-import-and-export-jobs"></a>Tâches d'importation et d'exportation de données

[!include [banner](../includes/banner.md)]

Pour créer et gérer des tâches d'importation et d'exportation de données dans Microsoft Dynamics 365 for Finance and Operations, vous utilisez l'espace de travail **Gestion des données**. Par défaut, le processus d'importation et d'exportation de données crée une table intermédiaire pour chaque entité dans la base de données cible. Les tables intermédiaires permettent de vérifier, nettoyer ou convertir des données avant de les déplacer.

> [!NOTE]
> La présente rubrique suppose que vous êtes familiarisé avec les [entités de données](data-entities.md).

## <a name="data-importexport-process"></a>Processus d'importation et d'exportation de données
Voici les étapes pour importer ou exporter des données.

1. Créez une tâche d'importation ou d'exportation en effectuant les tâches suivantes :

    - Définissez la catégorie de projet.
    - Identifiez les entités à importer ou exporter.
    - Définissez le format de données pour la tâche.
    - Séquencez les entités afin qu'elles soient traitées en groupes logiques et dans un ordre cohérent.
    - Déterminez si vous souhaitez utiliser des tables intermédiaires.

2. Vérifiez que les données sources et cibles sont mises en correspondance correctement.
3. Vérifiez la sécurité de votre tâche d'importation ou d'exportation.
4. Exécutez la tâche d'importation ou d'exportation.
5. Vérifiez que la tâche a été exécutée comme prévu en examinant l'historique des tâches.
6. Nettoyez les tables intermédiaires.

Les autres sections de cette rubrique fournissent plus de détails sur chaque étape du processus.

> [!NOTE]
> Afin d'actualiser l'écran Importation/exportation de données pour afficher la dernière progression, utilisez l'icône d'actualisation d'écran. L'actualisation au niveau du navigateur n'est pas recommandée car elle interrompt les tâches d'importation/d'exportation qui ne sont pas exécutées par lots.

## <a name="create-an-import-or-export-job"></a>Créer une tâche d'importation ou d'exportation
Une tâche d'importation ou d'exportation de données peut être exécutée une ou plusieurs fois.

### <a name="define-the-project-category"></a>Définir la catégorie de projet
Nous vous recommandons de prendre le temps de sélectionner une catégorie de projet appropriée pour votre tâche d'importation ou d'exportation. Les catégories de projet peuvent vous aider à gérer les tâches associées.

### <a name="identify-the-entities-to-import-or-export"></a>Identifier les entités à importer ou exporter
Vous pouvez ajouter des entités spécifiques à une tâche d'importation ou d'exportation ou sélectionner un modèle à appliquer. Les modèles remplissent une tâche avec une liste d'entités. L'option **Appliquer un modèle** n'est disponible qu'après avoir attribué un nom à la tâche et enregistré la tâche.

### <a name="set-the-data-format-for-the-job"></a>Définir le format de données pour la tâche
Lorsque vous sélectionnez une entité, vous devez sélectionner le format des données à exporter ou importer. Définissez des formats à l'aide de la vignette **Paramétrage de sources de données**. Un format de données sources est une combinaison de **Type**, de **Format de fichier**, de **Séparateur de ligne** et de **Séparateur de colonne**. Il existe également d'autres attributs, mais ceux-ci sont les principaux à comprendre. Le tableau suivant répertorie les combinaisons valides.

| Format de fichier            | Séparateur de colonnes/lignes                       | Style XML                 |
|------------------------|--------------------------------------------|---------------------------|
| Excel                  | Excel                                      | \-S/O-                     |
| XML                    | \-S/O-                                      | Élément XML Attribut XML |
| Délimité, largeur fixe | Virgule, point-virgule, onglet, barre verticale, deux points | \-S/O-                     |

### <a name="sequence-the-entities"></a>Séquencer les entités
Les entités peuvent être séquencées dans un modèle de données, ou dans des tâches d'importation et d'exportation. Lorsque vous exécutez une tâche qui contient plusieurs entités de données, vous devez vous assurer que les entités de données sont correctement séquencées. Séquencez principalement les entités afin de pouvoir traiter les dépendances fonctionnelles entre les entités. Si les entités n'ont aucune dépendance fonctionnelle, elles peuvent être planifiées pour l'importation ou l'exportation parallèle.

#### <a name="execution-units-levels-and-sequences"></a>Unités, niveaux et séquences d'exécution
L'unité d'exécution, le niveau dans l'unité d'exécution, et la séquence d'une entité permettent de contrôler l'ordre dans lequel les données sont exportées ou importés.

- Les entités dans différentes unités d'exécution sont traitées en parallèle.
- Dans chaque unité d'exécution, les entités sont traitées en parallèle si elles ont le même niveau.
- À chaque niveau, les entités sont traitées en fonction de leur numéro de séquence à ce niveau-là.
- Une fois qu'un niveau est traité, on passe au niveau suivant.

#### <a name="resequencing"></a>Reséquençage
Vous pouvez reséquencer vos entités dans les cas suivants :

- Si une seule tâche de données est utilisée pour toutes vos modifications, vous pouvez utiliser les options de reséquençage pour optimiser le temps d'exécution de la tâche complète. Dans ces cas, vous pouvez utiliser l'unité d'exécution pour représenter le module, le niveau pour représenter la zone de la fonction dans le module, et la séquence pour représenter l'entité. Grâce à cette approche, vous pouvez travailler dans plusieurs modules en parallèle, mais vous pouvez continuer à travailler dans l'ordre du module. Pour vous assurer que les opérations parallèles sont réussies, vous devez examiner toutes les dépendances.
- Si plusieurs tâches de données sont utilisées (par exemple, une tâche pour chaque module), vous pouvez utiliser le séquençage pour affecter le niveau et la séquence des entités à des fins d'exécution optimale.
- S'il n'existe aucune dépendance du tout, vous pouvez séquencer les entités aux différentes unités d'exécution pour une optimisation maximale.

Le menu **Reséquençage** est disponible si plusieurs entités sont sélectionnées. Vous pouvez effectuer un reséquençage en fonction des options d'unité, de niveau ou de séquence d'exécution. Vous pouvez définir un incrément pour reséquencer les entités sélectionnées. L'unité, le niveau et/ou le numéro de séquence qui est sélectionné pour chaque entité est mis à jour par l'incrément spécifié.

#### <a name="sorting"></a>Tri
Vous pouvez utiliser l'option **Trier par** pour afficher la liste des entités dans l'ordre séquentiel.

### <a name="truncating"></a>Troncation
Pour les projets d'importation, vous pouvez choisir de tronquer des enregistrements dans les entités avant l'importation. Cela est utile si vos enregistrements doivent être importés dans un nouvel ensemble de tables. Ce paramètre est désactivé par défaut.

## <a name="validate-that-the-source-data-and-target-data-are-mapped-correctly"></a>Vérifier que les données sources et cibles sont mises en correspondance correctement
La mise en correspondance est une fonction qui s'applique aux tâches d'importation et d'exportation.

- Dans le contexte d'une tâche d'importation, la mise en correspondance décrit quelles colonnes dans le fichier source deviennent les colonnes dans la table intermédiaire. Par conséquent, le système peut déterminer quelles données de colonne dans le fichier source doivent être copiées dans la colonne de la table intermédiaire.
- Dans le contexte d'une tâche d'exportation, la mise en correspondance décrit quelles colonnes de la table intermédiaire (autrement dit, la table source) deviennent les colonnes dans le fichier cible.

Si les noms de colonne dans la table intermédiaire et le fichier correspondent, le système crée automatiquement la mise en correspondance en fonction des noms. Toutefois, si les noms sont différents, les colonnes ne sont pas mises en correspondance automatiquement. Dans ces cas, vous devez effectuer la mise en correspondance en sélectionnant l'option **Afficher le mappage** sur l'entité dans la tâche de données.

Il existe deux vues de mappage : **Visualisation de la mise en correspondance**, qui est la vue par défaut, et **Détails de la mise en correspondance**. Un astérisque rouge (\*) identifie les champs obligatoires dans l'entité. Ces champs doivent être mis en correspondance avant de pouvoir utiliser l'entité. Si nécessaire, vous pouvez supprimer la mise en correspondance d'autres champs lorsque vous utilisez l'entité. Pour supprimer la mise en correspondance d'un champ, sélectionnez le champ dans la colonne **Entité** ou la colonne **Source**, puis sélectionnez **Supprimer la sélection**. Sélectionnez **Enregistrer** pour enregistrer vos modifications, puis fermez la page pour revenir au projet. Vous pouvez utiliser le même processus pour modifier la mise en correspondance de la table source avec la table intermédiaire après leur importation.

Vous pouvez générer une mise en correspondance sur la page en sélectionnant **Générer la mise en correspondance de la source**. Une mise en correspondance générée se comporte comme une mise en correspondance automatique. Par conséquent, vous devez mettre en correspondance manuellement tous les champs non mis en correspondance.

![Mise en correspondance de données](./media/dixf-map.png)

## <a name="verify-the-security-for-your-import-or-export-job"></a>Vérifier la sécurité de votre tâche d'importation ou d'exportation
L'accès à l'espace de travail **Gestion des données** peut être limité, afin que les utilisateurs non-administrateurs puissent accéder uniquement à des tâches de données spécifiques. L'accès à une tâche de données implique un accès complet à l'historique d'exécution de cette tâche et l'accès aux tables intermédiaires. Par conséquent, vous devez vous assurer que les contrôles d'accès appropriés sont en place lorsque vous créez une tâche de données.

### <a name="secure-a-job-by-roles-and-users"></a>Sécuriser une tâche en fonction des rôles et des utilisateurs
Utilisez le menu **Rôles applicables** pour restreindre la tâche à un ou plusieurs rôles de sécurité. Seuls les utilisateurs disposant de ces rôles ont accès à la tâche.

Vous pouvez également limiter une tâche à des utilisateurs spécifiques. Lorsque vous sécurisez une tâche en fonction des utilisateurs et non des rôles, cela offre plus de contrôle si plusieurs utilisateurs sont affectés à un rôle.

### <a name="secure-a-job-by-legal-entity"></a>Sécuriser une tâche par une entité juridique
Les tâches de données sont globales en nature. Par conséquent, si une tâche de données a été créée et utilisée dans une entité juridique, la tâche est visible dans les autres entités juridiques du système. Ce comportement par défaut peut être préféré dans certains scénarios d'application. Par exemple, une organisation qui permet d'importer des factures à l'aide d'entités de données peut fournir une équipe chargée du traitement centralisé des factures pour la gestion des erreurs de toutes les divisions de l'organisation. Dans ce cas, il est utile que l'équipe de traitement centralisé des factures ait accès aux tâches d'importation de factures de toutes les entités juridiques. Par conséquent, le comportement par défaut correspond aux exigences d'une perspective d'entité juridique.

Cependant, une organisation peut vouloir avoir des équipes de traitement des factures par entité légale. Dans ce cas, une équipe au sein d'une entité juridique doit avoir accès uniquement à la tâche d'importation de facture dans sa propre entité juridique. Pour répondre à cette exigence, vous pouvez configurer le contrôle d'accès basé sur l'entité juridique pour les tâches de données à l'aide du menu **Entités juridiques applicables** dans la tâche de données. Une fois la configuration effectuée, les utilisateurs peuvent afficher uniquement les tâches qui sont disponibles dans l'entité juridique à laquelle ils sont connectés. Pour afficher les tâches d'une autre entité juridique, les utilisateurs doivent afficher cette entité juridique.

Une tâche peut être sécurisée par des rôles, des utilisateurs et une entité juridique en même temps.

## <a name="run-the-import-or-export-job"></a>Exécuter la tâche d'importation ou d'exportation
Vous pouvez exécuter une tâche ponctuelle en sélectionnant le bouton **Importer** ou **Exporter** après avoir défini la tâche. Pour paramétrer une tâche régulière, sélectionnez **Créer une tâche de données répétitive**.

[!NOTE]
Une tâche d'importation ou d'exportation peut être exécutée de façon asynchrone en sélectionnant le bouton **Importer** ou **Exporter**. L'exécution en mode asynchrone utilise la structure asynchrone dans Finance and Operations, ce qui diffère d'une structure par lots. Toutefois, à l'instar de la structure par lots, la structure asynchrone peut également subir un étranglement et par conséquent, la tâche peut ne pas s'exécuter immédiatement. Les tâches peuvent être exécutées également de manière synchrone en sélectionnant **Importer maintenant** ou **Exporter maintenant**. Cela lance la tâche immédiatement et est utile si le mode asynchrone ou par lots ne se lance pas en raison d'un étranglement. Les tâches peuvent également être effectuées dans un lot en sélectionnant l'option **Exécuter en mode de traitement par lots**. Les ressources par lots sont sujettes à l'étranglement, aussi le traitement par lots pourrait ne pas se lancer immédiatement. L'option asynchrone est utile lorsque les utilisateurs interagissent directement avec l'interface utilisateur et ne sont pas des utilisateurs expérimentés en matière de planification par lots. Utiliser un lot reste possible si de grands volumes doivent être exportés ou importés. Les traitements par lots peuvent être prévus pour une exécution sur un groupe de lots spécifique, ce qui permet un plus grand contrôle depuis une perspective d'équilibrage de charge. Si le mode asynchrone et le mode par lots rencontrent tous deux un étranglement en raison de l'utilisation intensive des ressources sur le système, une solution de contournement immédiate consisterait à utiliser la version synchrone de l'importation/exportation. L'option synchrone se lance immédiatement et bloque l'interface utilisateur, qui s'exécute de façon synchrone. La fenêtre du navigateur doit rester ouverte lorsque l'opération synchrone est en cours.

## <a name="validate-that-the-job-ran-as-expected"></a>Vérifier que la tâche a été exécutée comme prévu
L'historique des tâches est disponible pour dépanner et rechercher des tâches d'importation et d'exportation. Les exécutions d'historique des tâches sont planifiées par périodes.

![Plages Historique des tâches](./media/dixf-job-history.md.png)

Chaque exécution de tâche fournit les informations suivantes :

- Détails de l'exécution
- Journal des exécutions

Les détails de l'exécution indiquent l'état de chaque entité de données que la tâche a traitée. Par conséquent, vous pouvez rapidement rechercher les informations suivantes :

- Quelles entités ont été traitées
- Pour une entité, le nombre d'enregistrements ayant été correctement traités et le nombre ayant échoué
- Les enregistrements intermédiaires pour chaque entité

Vous pouvez télécharger les données intermédiaires dans un fichier pour les tâches d'exportation, ou vous pouvez les télécharger sous la forme d'un module pour les tâches d'importation et d'exportation.

Les détails d'exécution vous permettent également d'ouvrir le journal d'exécution.

## <a name="clean-up-the-staging-tables"></a>Nettoyer les tables intermédiaires
Vous pouvez nettoyer les tables intermédiaires à l'aide de la fonction **Nettoyage intermédiaire** dans l'espace de travail **Gestion des données**. Vous pouvez utiliser les options suivantes pour sélectionner les enregistrements à supprimer d'une table intermédiaire :

- **Entité** – Si une seule entité est fournie, tous les enregistrements de la table intermédiaire de cette entité sont supprimés. Permet de supprimer toutes les données de l'entité dans tous les projets de données et toutes les tâches.
- **ID tâche** – Si un seul ID de tâche est fourni, tous les enregistrements de toutes les entités dans la tâche sélectionnée sont supprimés des tables intermédiaires appropriées.
- **Projets de données** – Si un seul projet de données est sélectionné, tous les enregistrements de toutes les entités et de toutes les tâches du projet de données sélectionné sont supprimés.

Vous pouvez également associer les options pour restreindre davantage l'ensemble des enregistrements à supprimer.
