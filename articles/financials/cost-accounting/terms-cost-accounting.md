---
title: "Terminologie du contrôle de gestion"
description: "Cette rubrique définit les termes clés utilisées dans le contrôle de gestion."
author: YuyuScheller
manager: AnnBe
ms.date: 08/31/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostAccountingLedger
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 223114
ms.assetid: 1c798592-77d0-4a8f-beaa-9159c75957da
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ed6dead1f4da7abcf96df2487e90f612b57df198
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="cost-accounting-terminology"></a>Terminologie du contrôle de gestion

[!include[banner](../includes/banner.md)]


Cette rubrique définit les termes clés utilisées dans le contrôle de gestion.

**Base de répartition**

La base de répartition est utilisée pour mesurer et quantifier les activités, telles que les heures-machine utilisées, les kilowatt-heures qui sont consommées, ou la superficie qui est occupée. Elle est utilisée comme base de la répartition des coûts vers un ou plusieurs objets de coût

**Contrôle de gestion**

Le contrôle de gestion vous permet de collecter des données de différentes sources, telles que la comptabilité, les comptabilités auxiliaires, les budgets, et les informations statistiques. Vous pouvez ensuite analyser, résumer, et évaluer les données de coût, de sorte que la gestion puisse prendre les meilleures décisions possibles concernant les mises à jour de prix, les budgets, le contrôle des coûts, et ainsi de suite. Les données sources utilisées pour l'analyse des coûts sont traitées indépendamment dans le contrôle de gestion. Par conséquent, les mises à jour dans le contrôle de gestion n'affectent pas les données sources. Toutefois, lorsque vous regroupez des données de coût de différentes sources et, en particulier lorsque vous importez les comptes principaux de la comptabilité dans Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition en tant qu'éléments de coûts, il existe une redondance des données, car les mêmes données existent dans la comptabilité et le contrôle de gestion. Cette redondance est nécessaire, car vous utilisez la gestion financière pour la génération d'états externes et le contrôle des coûts pour la génération d'états internes.

**Comptabilité de contrôle de gestion**

Définie par le calendrier, la devise et la dimension d'élément de coût, elle contrôle les processus et les stratégies pour mesurer des coûts. 

**Écriture de coût**

Les entrées de coût sont le résultat d'un transfert via des connecteurs de données provenant des écritures comptables, des répartitions de coûts, et des entrées de coût validées dans les journaux de coût.

**Objet de coût**

Tout type d'objet sélectionné pour le contrôle des coûts. Les coûts ou les produits sont directement validés ou affectés aux objets de coûts. Voici quelques objets de coût habituels :

-  Produits
-  Projets
-  Départements
-  Centres de coût

La gestion utilise les objets de coût pour mesurer les coûts, mais aussi pour réaliser l'analyse de rentabilité.

**Élément de coût**

Utilisé comme une fonction pour suivre et classer les coûts. Il existe deux types d'éléments de coût : principaux et secondaires.

Les éléments de coûts principaux représentent le flux des coûts entre la comptabilité financière et le Contrôle de gestion. La structure correspond généralement à la structure de compte de résultat dans la comptabilité, dans laquelle un élément de coût peut correspondre à un compte principal. Tous les comptes principaux ne doivent pas être représentés en tant qu'éléments de coûts, en fonction des besoins de l'entreprise. 

Les éléments des coûts secondaires représentent le flux interne des coûts, car ces coûts sont créés et utilisées uniquement dans le Contrôle de gestion. Ils sont utilisés dans les règles de repositionnement des coûts pour regrouper des coûts dans les plages significatives utilisées par le calcul des frais généraux. 

**Classification des coûts**

La classification des coûts regroupe les coûts en fonction de leurs caractéristiques communes. Par exemple, les coûts peuvent être regroupés par éléments, traçabilité, et comportement.

-   **Par éléments** : Matières, main d'œuvre, et dépenses.
-   **Par traçabilité** : Coûts directs et coûts indirects. Les coûts directs sont affectés directement aux objets de coût. Les coûts indirects ne sont pas directement traçables jusqu'au objets de coût. Les coûts indirects sont affectés aux objets de coût.
-   **Par comportement** : Fixes, variables, et semi-variables.

**Comportement de coûts**

Le comportement de coût classifie les coûts en fonction de leur comportement en relation aux modifications des activités professionnelles clées. Pour contrôler les coûts efficacement, la gestion doit comprendre le comportement de coût. Il existe trois types de modèles de comportement de coût : fixes, variables, et semi-variables.

- **Coût fixe** - Un coût fixe est un coût qui ne varie pas à court terme, indépendamment des modifications au niveau de l'activité. Par exemple, un coût fixe peut être une dépense d'exploitation de base d'une entreprise, comme le loyer, qui n'est pas affecté si le niveau d'activité augmente ou diminue.

- **Coût variable** - Un coût variable change en fonction des modifications de niveau d'activité. Par exemple, un coût de matières direct spécifique est associé à chaque produit qui est vendu. Plus les produits sont vendus, plus il y a de coûts de matières directs.

- **Coût semi-variable** - Les coûts semi-variables sont des coûts en partie fixes et en partie variables. Par exemple, les frais d'accès à Internet incluent des frais mensuels d'accès standard et des frais d'utilisation de la bande passante. Les frais mensuels d'accès standard sont un coût fixe, alors que les frais d'utilisation de la bande passante sont un coût variable.

**Unité de contrôle des coûts**

L'unité de contrôle des coûts représente la structure de coûts. La structure détermine la façon dont les coûts s'écoulent dans un ordre hiérarchique entre les dimensions des objets de coûts et leurs objets de coûts respectifs. 

**Distribution des coûts**

Est utilisée pour distribuer le coût d'un objet de coût vers un ou plusieurs autres objets de coût en appliquant une base de répartition appropriée. La distribution et la répartition des coûts diffèrent car la distribution des coûts a toujours lieu au niveau de l'élément de coût principal du coût d'origine sans traitement réciproque.

**Affectation des coûts**

Est utilisée pour affecter le solde d'un objet de coût à d'autres objets de coût en appliquant une base de répartition. Finance and Operations prend en charge la méthode de répartition réciproque. Dans la méthode de répartition réciproque, les services mutuels que les objets de coût auxiliaires échangent sont totalement identifiés. Le système détermine automatiquement l'ordre correct selon lequel exécuter les répartitions et les itérer. Le solde d'un objet de coût est réparti par une seule base de répartition. Les répartitions entre plusieurs dimensions d'objets de coût et leurs membres respectifs sont prises en charge. L'ordre de répartition est contrôlé par l'unité de contrôle des coûts.

**Stratégie de répartition des coûts**

La stratégie de répartition des coûts définit les montants et les quantités qui doivent être répartis. Les règles de répartition incluent les règles de source de répartition, qui déterminent les coûts qui sont répartis, et les règles de cibles de répartition, qui déterminent où les coûts sont répartis. Par exemple, tous les coûts des services d'établissement sont une source de répartition qui peut être répartie sur plusieurs services d'une organisation (c'est-à-dire, les cibles de répartition).

**Repositionnement des coûts**

L'objectif des règles de repositionnement des coûts est de regrouper des coûts dans les plages significatives. Le niveau d'agrégation est défini par l'utilisateur et requiert l'affectation d'un élément de coût secondaire. Lorsque le repositionnement des coûts n'est pas utilisé, chaque élément des coûts est réparti d'un objet de coût à un autre

**Stratégie de taux de coût**

Le taux de coût est utilisé pour calculer le prix par objet de coût. Pour comprendre les éléments du prix, vous définissez des stratégies de taux de coût. Il existe deux types de taux de coût : le taux de coût historique et le taux de coût planifié. Un taux de coût historique est un taux calculé qui est utilisé comme multiplicateur pour la base de répartition d'un objet de coût. Le taux est calculé selon les répartitions des coûts de la période précédente. Un taux planifié est un taux défini par l'utilisateur.

**Hiérarchie des dimensions**

Il existe deux hiérarchies de dimensions : la hiérarchie de catégorisation et la hiérarchie de classification. Le type Hiérarchie de catégorisation de dimension est utilisé pour les déclarations. Il ne prend en charge que les dimensions d'élément de coût. Le type Hiérarchie de classification de dimension est utilisé pour définir les règles et les déclarations. Il prend en charge toutes les dimensions, comme les objets de coût, les éléments de coût et les dimensions statistiques. 

**Connecteur de données**

Le contrôle de gestion prend en charge l'intégration des données des systèmes sources via un ensemble de connecteurs de données. Les connecteurs de données suivants sont disponibles :

-  Transactions importées (préconfigurées)
-  Dynamics 365 for Finance and Operations, Enterprise edition (préconfiguré)
-  Dynamics AX (configuration obligatoire)

**Remarque :** Les transactions importées du connecteur de données sont basées sur les entités de données.

**Fournisseur de données**

La plupart des systèmes sources peuvent fournir les données qui correspondent à une ou plusieurs sources de données dans le contrôle de gestion. Pour aligner les données des systèmes sources à la source de données dans le contrôle de gestion, un fournisseur de données doit être configuré. Le tableau suivant répertorie la disponibilité des fournisseurs de données par connecteur de données et source de données.

|  **Sources de données** |  **Connecteur de données pour les transactions importées** | **Connecteur de données Microsoft Dynamics 365 for Finance and Operations, Enterprise edition**  | **Connecteur de données Dynamics AX**  |
|---|---|---|---|
| Membres de la dimension d'élément de coût  |  Oui | Oui  | Oui  |
|  Membres de la dimension d'objet de coût |  Oui | Oui  | Oui  |
|  Membres de la dimension statistique | Oui  | N°  | N°  |
|  Comptabilité | Oui  | Oui  | Oui  |
|  Écritures budgétaires  | Oui  | Oui  | Oui  |
|  Mesures statistiques | Oui  | Oui  | Oui  |

**Formule**

Les bases de répartition des formules vous permettent de définir des formules avancées pour accomplir la base de répartition correcte. Vous pouvez créer des bases de répartition de formule manuellement. Vous pouvez utiliser les opérateurs disponibles pour définir votre formule.

|  **Symboles** | **Détails**  |
|---|---|
|  ( ) | Parenthèses  |
|  < |  Inférieur à |
|  > |  Supérieur à |
|  + |  Addition |
|  – |  Soustraction |
| *  | Multiplication  |
    
Les instructions IF traditionnelles ne sont pas prises en charge. Toutefois, vous pouvez créer des instructions et les valider si elles sont vraies.

|  **Validation du relevé** | **Résultat**  |
|---|---|
|  a > b| Vrai  |
|  a > b |  Faux |
    
**Frais généraux**

Les frais généraux font référence aux dépenses constantes liées à l'exploitation d'une entreprise. Il s'agit des coûts qui ne peuvent pas être liés directement à des activités d'entreprise spécifiques. Voici quelques exemples de frais généraux :

-   Frais comptables
-   Amortissements
-   Assurance
-   Intérêts
-   Frais juridiques
-   Taxes
-   Coûts des services publics

**Taux de frais généraux**

Les taux sont définis par objet de coût et élément de coût. Il existe deux types de taux : période fiscale et spécifié par l'utilisateur. Les taux de période fiscale sont définis par le calcul des frais généraux. Un taux utilisateur spécifique est défini par l'utilisateur et peut être utilisé pour affecter les coûts entre les objets de coût à un taux prédéterminé dans le calcul des frais généraux.

**Publié**

Si vous définissez ce champ sur Oui, un utilisateur doté d'un des rôles suivants peut consulter l'état dans l'espace de travail Contrôle des coûts :

-  Gestionnaire de contrôle de gestion
-  Contrôleur de gestion
-  Commis contrôleur de gestion
-  Contrôleur d'objet de coût

Si vous définissez ce champ sur Non, seuls les utilisateurs dotés d'un des rôles suivants peuvent consulter l'état dans l'espace de travail Contrôle des coûts :

-  Gestionnaire de contrôle de gestion
-  Contrôleur de gestion
-  Commis contrôleur de gestion

**Dimension statistique**

Une dimension statistique et ses membres permettent d'enregistrer et de contrôler les entrées non monétaires dans le module Contrôle de gestion. Les membres de la dimension statistique peuvent être utilisés à deux fins :

-  Comme base de répartition dans les stratégies telles que la distribution ou la répartition des coûts.
-  Pour la déclaration de la consommation non monétaire.

Une dimension statistique est l'expression d'un nombre ou d'une somme d'une activité pouvant être utilisée comme base pour les répartitions ou calculs de taux. Elle est créée manuellement ou importée des systèmes sources. Les exemples de dimensions statistiques comptent le nombre d'employés, le nombre de logiciels sous licence sur chaque périphérique, la consommation d'électricité de chaque ordinateur, ou les mètres carrés d'un centre de coût.

**Instruction**

Les relevés sont des vues pour les responsables chargés de contrôler les coûts. Les relevés sont définis par un contrôleur de coût, et ils fournissent une vue d'ensemble rapide des coûts réels et budgétés, et même des écarts. Un responsable peut détailler davantage au besoin. Pour assurer que les responsables affichent uniquement les données dont ils sont responsables, les données figurant dans les relevés sont soumises à des règles d'accès.

**Version**

Les versions sont utilisées pour simuler, afficher, puis comparer différents résultats. Par défaut, tous les coûts réels sont affichés dans une version de base *réelle*. Pour les budgets et les calculs, vous pouvez utiliser autant de versions que vous le souhaitez. Par exemple, vous pouvez importer les données du budget dans une version d'origine puis modifier le budget d'une version modifiée. Pour les calculs, vous pouvez créer plusieurs versions. Dans ces différentes versions, vous pouvez créer des calculs à l'aide de différentes règles de calcul qui s'appliqueront pour la répartition des coûts.



