---
title: "Hiérarchie des dimensions"
description: "Cette rubrique fournit des informations sur les hiérarchies de dimensions. Vous utilisez une hiérarchie de dimensions pour définir la structure d'entreprise, les stratégies de coût et le paramétrage de la sécurité dans le contrôle de gestion."
author: YuyuScheller
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimensionHierarchy,
audience: Application User
ms.reviewer: yuyus
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: YuyuScheller
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: dcbab70d2057a2eb252538a51343fa8bae16873d
ms.contentlocale: fr-fr
ms.lasthandoff: 06/20/2017

---

# <a name="dimension-hierarchy"></a>Hiérarchie des dimensions

[!include[banner](../includes/banner.md)]

Cette rubrique fournit des informations sur les hiérarchies de dimensions. Vous utilisez une hiérarchie de dimensions pour définir la structure d'entreprise, les stratégies de coût et le paramétrage de la sécurité dans le contrôle de gestion.  

## <a name="overview"></a>Vue d'ensemble

Les hiérarchies de dimensions sont utilisées dans divers endroits dans le contrôle de gestion. Une hiérarchie de dimensions vous permet de définir les informations suivantes :

-  La structure hiérarchique qui est intégrée au exigences de l'organisation
-  Stratégies de coût
-  Paramétrage de la sécurité

Voici un exemple d'une hiérarchie de dimensions.

![Exemple d'une hiérarchie de dimensions](./media/dimension-hierarchy.png)

Une hiérarchie de dimensions peut être créée pour les types de dimensions suivants :

-  Dimensions d'éléments de coût
-  Dimensions d'objets de coût
-  Dimensions statistiques

> [!NOTE]
> - Vous pouvez créer plusieurs hiérarchies de dimensions pour la même dimension si différentes perspectives sont nécessaires.
> - Une hiérarchie de dimensions ne peut être associée qu'à une seule dimension.
> - Une hiérarchie de dimensions peut avoir des niveaux illimités dans sa structure. Tous les niveaux sont disponibles dans l'espace de travail **Contrôle des coûts**. Lorsque vous utilisez Microsoft Excel ou Microsoft Power BI pour les déclarations, seuls les 15 premiers niveaux de la hiérarchie de dimensions sont exportés. Cette limitation existe car Excel et Power BI nécessitent un schéma fixe.
> - Une hiérarchie de dimensions n'a pas de date d'effet. Par conséquent, toute modification apportée à une hiérarchie de dimensions est immédiatement stockée dans l'enregistrement, et vous ne pouvez pas comparer la date antérieure et la date postérieure.

## <a name="dimension-hierarchy-type"></a>Type de hiérarchie de dimension

Lorsque vous créez une nouvelle hiérarchie de dimensions, vous devez sélectionner un type de hiérarchie. Accédez à **Contrôle de gestion** > **Dimensions** > **Hiérarchies des dimensions**. Cliquez sur **Nouveau**, puis sélectionnez un type de hiérarchie de dimensions. Vous pouvez sélectionner **Hiérarchie de catégorisation de dimension** ou **Hiérarchie de classification de dimension**.

### <a name="dimension-categorization-hierarchy"></a>Hiérarchie de catégorisation de dimension

Le type **Hiérarchie de catégorisation de dimension** est utilisé pour les déclarations. Il ne prend en charge que les dimensions d'élément de coût. Si vous sélectionnez ce type, les règles suivantes s'appliquent :

-  Un membre de la dimension peut être associé à plusieurs reprises dans la structure de la hiérarchie.
-  Vous pouvez placer un membre de dimension d'élément de coût dans divers nœuds en affectant un comportement de coût au nœud terminal.

### <a name="dimension-classification-hierarchy"></a>Hiérarchie de classification de dimension

Le type **Hiérarchie de classification de dimension** est utilisé pour définir les règles et les déclarations. Il prend en charge toutes les dimensions, comme les objets de coût, les éléments de coût et les dimensions statistiques. Lorsque vous sélectionnez ce type, un membre de la dimension peut être associé une seule fois dans la structure de la hiérarchie.

## <a name="create-and-maintain-a-dimension-hierarchy"></a>Créer et tenir à jour une hiérarchie de dimensions

Une hiérarchie de dimensions est créée comme structure arborescente qui inclut des relations de nœuds et des nœuds terminaux.

-  Un nœud peut comporter 1 : sous-nœuds de _n_.
-  Un nœud ne peut pas avoir des sous-nœuds et des nœuds terminaux qui lui sont affectés à la fois.
-  Un nœud terminal ne peut être affecté qu'au plus bas dans la hiérarchie.

### <a name="example"></a>Exemple

Une petite société a la structure d'organisation suivante, où les services Finances et Ressources humaines sont des départements dépendants de l'administrateur, et les services Assemblage et Emballage sont des départements relevant de la production.

![Exemple d'une structure d'organisation](./media/dimension-hierarchy-org.png)

Une dimension d'objet de coût représente tous les centres de coût dans l'organisation.

- Dimension d'objet de coût
    - Centres de coût

La dimension d'objet de coût qui représente tous les centres de coût peut être paramétrée comme indiqué ici.

| Centres de coût | Description |
|--------------|-------------|
| CC001        | RH          |
| CC002        | Finances     |
| CC003        | Taxes         |
| CC007        | Achats/Ventes       |
| CC005        | Assemblage    |
| CC006        | Emballage   |

Une dimension d'élément de coût représente tous les éléments de coût dans l'organisation.

- Dimension d'élément de coût
    - Éléments de coût

La dimension d'élément de coût qui représente tous les éléments de coût peut être paramétrée comme indiqué ici.

| Éléments de coût | Description |
|---------------|-------------|
| 10001         | Électricité |
| 10010         | Nettoyage    |
| 10011         | Chauffage     |
| 40001         | Coût des marchandises vendues        |

Une hiérarchie de dimensions qui répond aux conditions de génération d'états d'organisation peut être paramétrée comme indiqué ici.

**Détails sur la hiérarchie des dimensions**

| Nom de la hiérarchie des dimensions | Dimension    | Nom du type de hiérarchie des dimensions      | Hiérarchie de la liste d'accès |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organisation             | Centres de coût | Hiérarchie de classification de dimension | N°                    |

La hiérarchie de dimensions pour générer un état peut être paramétrée comme indiqué ici.

|                   | Plages de membres de la dimension   |                         |
|-------------------|---------------------------|-------------------------|
| **Nœuds**         | **Membre de la dimension de départ** | **Membre de la dimension de fin** |
| Organisation      |                           |                         |
| &nbsp;&nbsp;Admin         |                           |                         |
|&nbsp;&nbsp;&nbsp;&nbsp;Finances   | CC002                     | CC003                   |
|                   | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;RH        | CC001                     | CC001                   |
| &nbsp;&nbsp;Production    |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Emballage | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Assemblage  | CC006                     | CC006                   |

Une hiérarchie de dimensions qui répond aux exigences de stratégie peut être paramétrée comme indiqué ici.

**Détails sur la hiérarchie des dimensions**

| Nom de la hiérarchie des dimensions | Dimension     | Nom du type de hiérarchie des dimensions      |
|--------------------------|---------------|------------------------------------|
| Comportement de coûts            | Éléments de coût | Hiérarchie de classification de dimension |

La hiérarchie de dimensions pour générer la stratégie peut être paramétrée comme indiqué ici.

|                   | Plages de membres de la dimension   |                         |
|-------------------|---------------------------|-------------------------|
| **Nœuds**         | **Membre de la dimension de départ** | **Membre de la dimension de fin** |
| Comportement de coûts     |                           |                         |
| &nbsp;&nbsp;Coût fixe    | 10001                     | 10011                   |
|&nbsp;&nbsp;Coût variable | 40001                     | 40010                   |

> [!NOTE]
> Sous **Plages de membres de la dimension**, un nœud peut contenir des plages membres de dimension de 1:_n_. Vous pouvez insérer des ID membre de dimension qui n'existent pas encore comme membres de la dimension. Cette approche rend la hiérarchie résiliente pour l'avenir.  

### <a name="copy-a-hierarchy"></a>Copier une hiérarchie

Vous pouvez copier une hiérarchie de dimension actuelle comme point de départ pour une nouvelle hiérarchie de dimension. Cette approche peut être utile si vous souhaitez comparer la hiérarchie de dimension précédente avec la nouvelle hiérarchie de dimension.

### <a name="rearrange-nodes-in-a-hierarchy"></a>Réorganisation des nœuds dans une hiérarchie

Vous pouvez déplacer le niveau d'un nœud vers le haut ou vers le bas au sein de la structure. De cette manière, vous pouvez réorganiser l'ordre des nœuds pour générer un rapport dans l'espace de travail **Contrôle des coûts**.

Vous déplacez un nœud vers un nouvel emplacement dans la hiérarchie en sélectionnant le nœud cible. Vous pouvez déplacer un nœud de deux manières :

- **Déplacer dessous** – Déplacement du nœud sélectionné de sa position actuelle dans la hiérarchie pour l'insérer **sous** le nœud cible sélectionné.
- **Déplacer après** – Déplacement du nœud sélectionné de sa position actuelle dans la hiérarchie pour l'insérer **après** le nœud cible sélectionné à son niveau dans la hiérarchie.

> [!NOTE] 
> L'ordre des nœuds n'est pas mis à jour lorsque vous exportez des données dans Excel ou Power BI, car ces outils utilisent un ordre de tri alphanumérique par défaut. Vous devez réorganiser l'ordre manuellement.

## <a name="define-dimension-hierarchies-for-reporting"></a>Définir les hiérarchies de dimensions pour la génération d'états

Les hiérarchies de dimensions sont importantes pour la génération d'états. Elles permettent de définir la structure spécifique qui est intégrée à l'organisation individuelle. Les agrégations effectuées au niveau du nœud de la hiérarchie de dimensions permettent aux actionnaires à n'importe quel niveau de l'organisation de voir les données à tous les niveaux.

Les hiérarchies de dimensions sont disponibles dans les outils de génération d'états suivants. Cette approche garantit la cohérence dans la structure hiérarchique.

- Espace de travail **Contrôle des coûts** (Client) :

    - Contrôlé par la configuration

- Espace de travail **Contrôle des coûts** (Application mobile) :

    - Contrôlé par la configuration

- Excel

    - Fournit la possibilité de sélectionner les hiérarchies de dimensions spécifiques par définition d'exportation :

        - Une hiérarchie de dimensions d'élément de coût (obligatoire)
        - Une hiérarchie de dimensions d'objet de coût par défaut (facultatif)
        - Une hiérarchie de dimensions statistiques (facultatif)

- Power BI :

    - Toutes les hiérarchies de dimensions sont disponibles.
    
Si vous créez des états à l'aide d'Excel ou de Power BI, seuls les 15 premiers niveaux de hiérarchies de dimensions sont exportés. Cette limitation existe car un schéma fixe est requis dans Excel et Power BI. Si une hiérarchie a plus de 15 niveaux, aucun niveau supplémentaire ne sera exporté. La table normalisée contient un enregistrement pour chaque membre de dimension dans la hiérarchie. Par conséquent, l'agrégation automatisée se produit. Ce comportement permet de garantir que les soldes à l'un des 15 niveaux disponibles dans la hiérarchie sont toujours corrects.

L'exemple suivant montre la structure d'une hiérarchie de dimensions dans la structure hiérarchique.

| Hiérarchie de dimensions d'objet de coût - Niveau 1 | Hiérarchie de dimensions d'objet de coût - Niveau 2 | Hiérarchie de dimensions d'objet de coût - Niveau 3 | Hiérarchie de dimensions d'objet de coût - Niveau 4 | Hiérarchie de dimensions d'objet de coût - Niveau 15 |
|-------------------------------------------|-------------------------------------------|-------------------------------------------|-------------------------------------------|--------------------------------------------|
| Organisation                              | Admin                                     | Finances                                   | CC002                                     |                                            |
| Organisation                              | Admin                                     | Finances                                   | CC003                                     |                                            |
| Organisation                              | Admin                                     | Finances                                   | CC007                                     |                                            |
| Organisation                              | Admin                                     | RH                                        | CC001                                     |                                            |
| Organisation                              | Production                                | Emballage                                 | CC005                                     |                                            |
| Organisation                              | Production                                | Assemblage                                  | CC006                                     |                                            |

### <a name="update-the-dimension-hierarchies-that-are-used-for-reporting"></a>Mettre à jour des hiérarchies de dimensions utilisées pour la génération d'états 

Au fil du temps, les hiérarchies de dimensions utilisées dans les outils de génération d'état précités doivent être mises à jour. Vous pouvez mettre à jour les hiérarchies de dimensions en actualisant le client.

- Espace de travail **Contrôle des coûts** (Client)
- Espace de travail **Contrôle des coûts** (Application mobile)

Les mises à jour des hiérarchies de dimensions sont remontées toutes les 24 heures par une tâche de mise en cache. Une fois que les données exportées sont mises à jour, les hiérarchies de dimensions mises à jour sont disponibles dans les outils suivants :

- Excel
- Power BI

> [!NOTE] 
> Pour déclencher manuellement une mise à jour du cache de la hiérarchie de dimensions, vous pouvez créer une exportation vers Excel pour la hiérarchie de dimensions ou les hiérarchies qui doivent être mises à jour.

## <a name="define-dimension-hierarchies-for-cost-policies"></a>Définir les hiérarchies de dimensions pour les stratégies de coût

Le contrôle de gestion comprend plusieurs stratégies où des règles détaillées sont définies. Vous devez définir une ou plusieurs hiérarchies de dimensions pour les stratégies suivantes :

- Comportement de coûts
- Distribution des coûts
- Affectation des coûts
- Repositionnement des coûts

Les hiérarchies de dimensions simplifient la création des règles. Pour éviter de devoir créer des règles pour chaque membre de dimension, vous pouvez tirer parti des agrégations des membres de dimension fournis par des niveaux de la hiérarchie des dimensions. Si des règles se chevauchent, vous devez définir des règles spécifiques que le système utilise lorsqu'il effectue un calcul des frais généraux.

### <a name="example-define-a-cost-behavior-policy"></a>Exemple : Définir une stratégie de comportement de coût

Une nouvelle stratégie de comportement de coût est créée, et des hiérarchies de dimensions appropriées sont affectées à la stratégie, comme affiché ici.

**Stratégie de comportement de coûts**

| Nom de la stratégie   | Hiérarchie des dimensions d'élément de coût | Hiérarchie des dimensions d'objet de coût | Devise comptable |
|---------------|----------------------------------|---------------------------------|---------------------|
| Comportement de coûts | Comportement de coûts                    | Organisation                    | USD                 |

**Règles**

| Nœud de hiérarchie des dimensions d'élément de coût | Nœud de hiérarchie des dimensions d'objet de coût | Pourcentage fixe | Montant fixe | Début de validité | Fin de validité |
|---------------------------------------|--------------------------------------|------------------|--------------|------------|----------|
| Coût fixe                            | Organisation                         | 100,00           | 0,00         | 1/1/2017   | Jamais    |
| 10001                                 | Organisation                         | 0,00             | 150,00       | 1/1/2017   | Jamais    |
| 10001 (\*)                             | Finances                              |                  | 50,00        | 1/1/2017   | Jamais    |
| Comportement ou coût variable de coût (\*\*)   | Organisation                         | 0,00             | 0,00         | 1/1/2017   | Jamais    |

\* Le nœud de coût variable n'est pas nécessaire. Si un coût n'est pas classé comme coût fixe, il doit être un coût variable.

\*\* Une règle détaillée est créée pour la combinaison du membre d'élément de coût 10001 et de tous les membres d'objet de coût qui sont regroupés sous le niveau de hiérarchie Finances (CC002, CC003, CC007).

Les règles précédentes montrent la flexibilité que fournissent les hiérarchies des dimensions. En définissant des règles de haut niveau, vous pouvez réduire la maintenance. Vous pouvez alors définir des règles détaillées à insérer dans les objectifs commerciaux spécifiques.

Si les hiérarchies de dimensions utilisées dans les règles sont mises à jour, le système met automatiquement les mises à jour en avant.

Si un niveau de granularité dans les règles n'est plus nécessaire, la règle peut expirer.

Par exemple, une règle de comportement de coût spécifique pour le nœud de hiérarchie de dimensions d'objet de coût Finances n'est plus nécessaire. Dans ce cas, cliquez sur **Règle d'expiration** pour appliquer une expiration à la règle.

| Nœud de hiérarchie des dimensions d'élément de coût | Nœud de hiérarchie des dimensions d'objet de coût | Pourcentage fixe | Montant fixe | Début de validité | Fin de validité  |
|---------------------------------------|--------------------------------------|------------------|--------------|------------|-----------|
| Coût fixe                            | Organisation                         | 100,00           | 0 00         | 1/1/2017   | Jamais     |
| 10001                                 | Organisation                         | 0 00             | 150,00       | 1/1/2017   | Jamais     |
| 10001                                 | Finances                              |                  | 50,00        | 1/1/2017   | 20/1/2017 |
| Comportement ou coût variable de coût        | Organisation                         | 0 00             | 0 00         | 1/1/2017   | Jamais     |

Le calcul des frais généraux qui est effectué après le 20 janvier 2017, ne considère plus cette règle.

> [!NOTE] 
> Les champs **Début de validité** et **Fin de validité** sont des dates effectives et présentent un gain de temps. Vous pouvez faire expirer la règle et exécuter un nouveau calcul des frais généraux le même jour.

## <a name="define-dimension-hierarchies-for-security-setup"></a>Définir les hiérarchies de dimensions pour le paramétrage de la sécurité

Les données de contrôle de gestion doivent être disponibles à tous les gestionnaires qui sont responsables d'une unité organisationnelle. Dans la terminologie du contrôle de gestion, une unité organisationnelle est représentée comme un objet de coût ou un ensemble d'objets de coût.

Potentiellement, tous les responsables pourront accéder aux données commerciales très sensibles, telles que les revenus et les marges. Par conséquent, il est important de paramétrer la sécurité, de sorte que les responsables ne voient que les données qui leur sont appropriées. Pour contrôler la sécurité des données, définissez des hiérarchies de dimensions.

- L'utilisation de hiérarchies de dimensions s'applique uniquement lorsque la valeur de dimension sélectionnée dans la référence de hiérarchie de dimension est une dimension d'objet de coût.
- Une seule hiérarchie de dimension peut être activée par dimension d'objet de coût dans la hiérarchie de la liste d'accès.

**Détails sur la hiérarchie des dimensions**

| Nom de la hiérarchie des dimensions | Dimension    | Nom du type de hiérarchie des dimensions      | Hiérarchie de la liste d'accès |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organisation             | Centres de coût | Hiérarchie de classification de dimension | **Oui**               |

Un nouvel organisateur **Utilisateurs** est disponible dans le concepteur de hiérarchies. Ici, vous pouvez ajouter un ou plusieurs ID utilisateur à chaque nœud dans la hiérarchie.

|                 | Utilisateurs            | Plages de membres de la dimension   |                         |
|-----------------|------------------|---------------------------|-------------------------|
| **Nœuds**       | **ID utilisateur**      | **Membre de la dimension de départ** | **Membre de la dimension de fin** |
| Organisation    | Benjamin, Claire |                           |                         |
| &nbsp;&nbsp;Admin         | Avril            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Finances   | Alicia           | CC002                     | CC003                   |
|                 |                  | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;RH        | Arnie            | CC001                     | CC001                   |
| &nbsp;&nbsp;Production    | David            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Emballage | Ellen            | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Assemblage  | Chris            | CC006                     | CC006                   |

> [!NOTE] 
> Les comptables doivent être affectés au niveau supérieur de la hiérarchie, de sorte qu'ils puissent visualiser toutes les écritures du contrôle de gestion.

Pour activer la hiérarchie de la liste d'accès et ses paramètres de sécurité, accédez à **Contrôle de gestion** > **Paramétrage** > **Paramètres** > **Général**. Sélectionnez le paramètre **Activer l'affichage pour les membres de dimension d'objet de coût**.

Les paramètres de la hiérarchie de la liste d'accès sont utilisés pour contrôler les données affichées dans les sections suivantes :

- Espace de travail **Contrôle des coûts** (Client) :

    - Données des écrans utilisés dans les scénarios d'extraction

- Espace de travail **Contrôle des coûts** (Application mobile) :

    - Soldes dans les cartes

- Power BI :

    - Données qui sont affichées dans une visualisation Power BI
    - Les visualisations des données Power BI sont intégrées dans Microsoft Dynamics 365 for Finance and Operations, Enterprise edition client

> [!NOTE] 
> - Avant que la hiérarchie de la liste d'accès puisse affecter des données Power BI, la hiérarchie de la liste d'accès et la sécurité au niveau de la ligne dans Power BI doivent être jumelées. Pour plus d'informations, voir [Paramétrer la sécurité pour le pack de contenu de gestion des coûts](/dynamics365/unified-operations/dev-itpro/analytics/setup-security-cost-accounting-content-pack).
> - La hiérarchie de la liste d'accès ne permet pas de sécuriser l'exportation des données dans Excel. Par conséquent, cet outil de génération d'états doit uniquement être utilisé par les comptables et les responsables de coût qui doivent avoir un accès complet pour afficher les données.

