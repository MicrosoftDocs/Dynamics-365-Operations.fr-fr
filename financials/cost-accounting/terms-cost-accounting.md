---
title: "Terminologie de contrôle de gestion"
description: "Cette rubrique définit les termes clés utilisées dans le contrôle de gestion."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CAMCostControlWorkspace, CAMCostControlWorkspaceConfiguration
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 223114
ms.assetid: 1c798592-77d0-4a8f-beaa-9159c75957da
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 87c13e268ab8825e06095d24e03694cf0f271a63
ms.openlocfilehash: 1ae6b43bdc1812ca822a1abe2a0e823cb797a511
ms.lasthandoff: 03/31/2017


---

# <a name="cost-accounting-terminology"></a>Terminologie de contrôle de gestion

Cette rubrique définit les termes clés utilisées dans le contrôle de gestion.

**Cost accounting**

Le contrôle de gestion vous permet de collecter des données de différentes sources, telles que la comptabilité, les comptabilités auxiliaires, les budgets, et les informations statistiques. Vous pouvez ensuite analyser, résumer, et évaluer les données de coût, de sorte que la gestion puisse prendre les meilleures décisions possibles concernant les mises à jour de prix, les budgets, le contrôle des coûts, et ainsi de suite. Les données sources utilisées pour l'analyse des coûts sont traitées indépendamment dans le contrôle de gestion. Par conséquent, les mises à jour dans le contrôle de gestion n'affectent pas les données sources. Toutefois, lorsque vous regroupez des données de coût de différentes sources et, en particulier lorsque vous importez les comptes principaux de la comptabilité dans Microsoft Dynamics 365 for Operations en tant qu'éléments de coûts, il existe une redondance des données, car les mêmes données existent dans la comptabilité et le contrôle de gestion. Cette redondance est nécessaire, car vous utilisez la gestion financière pour la génération d'états externes et le contrôle des coûts pour la génération d'états internes.

**Cost accounting ledger**

La comptabilité de contrôle de gestion est une structure spécialisée qui détermine la manière dont les processus, les valeurs, et les quantités sont entrés et présentés pour une section spécifique du contrôle de gestion. La comptabilité de contrôle de gestion définit les processus et les règles permettant de mesurer des coûts sur les objets de coût. Elle gère les transactions de coût, et gère les documents qui enregistrent les modifications apportées aux valeurs et aux quantités que les transactions de coût produisent.

**Cost entry**

Les entrées de coût sont le résultat d'un transfert via des connecteurs de données provenant des écritures comptables, des répartitions de coûts, et des entrées de coût validées dans les journaux de coût.

**Cost object**

Les objets de coût correspondent à tous les types d'objets auquel les coûts sont alloués. Voici quelques objets de coût habituels :

-   Produits
-   Projets
-   Ressources
-   Départements
-   Centres de coût
-   Zones géographiques

La gestion utilise les objets de coût pour mesurer les coûts, mais aussi pour réaliser l'analyse de rentabilité.

**Cost element**

Les éléments de coût sont utilisés comme une fonction permettant de suivre et de catégoriser la destination des coûts. Il existe deux types d'éléments de coût : les coûts principaux et les coûts secondaires. ** Coûts principaux ** les éléments de principal coûts représentent le flux des coûts de la Comptabilité financière au contrôle de gestion. La structure d'élément de coût correspond à la structure de compte de résultat dans la comptabilité, dans laquelle un élément de coût peut correspondre à un compte principal. Tous les comptes principaux ne doivent pas être représentés en tant qu'éléments de coûts, en fonction des besoins de l'entreprise. Voici quelques exemples d'éléments de coût principaux :

-   Coûts des marchandises vendues
-   Coûts indirects liés aux matières
-   Coûts de personnel
-   Coûts énergétiques

**Secondary cost element** 

Les éléments des coûts secondaires représentent le flux interne des coûts, car ces coûts sont créés et utilisées uniquement dans le contrôle de gestion. Les éléments de coûts secondaires permettent de garantir que la source de coûts puisse être suivie. Ces éléments de coût sont utilisés dans les répartitions de coûts et les calculs des frais généraux. Voici quelques exemples d'éléments de coût secondaires :

-   Coûts de production
-   Production, matières, et frais généraux de marketing

**Cost control unit**

Une unité de contrôle des coûts représente la structure de coûts. Elle doit être associée à des dimensions d'objets de coût dans la comptabilité de contrôle de gestion.

**Version**

Les versions sont utilisées pour simuler, afficher, puis comparer différents résultats. Par défaut, tous les coûts réels sont affichés dans une version de base *réelle*. Pour les budgets et les calculs, vous pouvez utiliser autant de versions que vous le souhaitez. Par exemple, vous pouvez importer les données du budget dans une version d'origine puis modifier le budget d'une version modifiée. Pour les calculs, vous pouvez créer plusieurs versions. Dans ces différentes versions, vous pouvez créer des calculs à l'aide de différentes règles de calcul qui s'appliqueront pour la répartition des coûts.

**Statement**

Les relevés sont des vues pour les responsables chargés de contrôler les coûts. Les relevés sont définis par un contrôleur de coût, et ils fournissent une vue d'ensemble rapide des coûts réels et budgétés, et même des écarts et des versions de calcul. Pour assurer que les responsables affichent uniquement les données dont ils sont responsables, les données figurant dans les relevés sont soumises à des règles d'accès.

** Connecteur de données **

Les données peuvent être importées dans le contrôle de gestion depuis des systèmes externes via des connecteurs de données. Par exemple, vous pouvez importer des structures de compte, des dimensions, des écritures comptables, et des écritures budgétaires. Vous pouvez utiliser des connecteurs de données préconfigurés ou des connecteurs personnalisés pour importer les données et de créer des connexions de données.

**Cost classification**

La classification des coûts regroupe les coûts en fonction de leurs caractéristiques communes. Par exemple, les coûts peuvent être regroupés par éléments, traçabilité, et comportement.

-   **Par éléments** : Matières, main d'œuvre, et dépenses.
-   **Par traçabilité** : Coûts directs et coûts indirects. Les coûts directs sont affectés directement aux objets de coût. Les coûts indirects ne sont pas directement traçables jusqu'au objets de coût. Les coûts indirects sont affectés aux objets de coût.
-   **Par comportement** : Fixes, variables, et semi-variables.

**Cost behavior**

Le comportement de coût classifie les coûts en fonction de leur comportement en relation aux modifications des activités professionnelles clées. Pour contrôler les coûts efficacement, la gestion doit comprendre le comportement de coût. Il existe trois types de modèles de comportement de coût : fixes, variables, et semi-variables.

- ** Le coût fixe ** - un coût fixe est un coût qui ne varie pas à court terme, indépendamment des modifications de niveau d'activité. Par exemple, un coût fixe peut être une dépense d'exploitation de base d'une entreprise, comme le loyer, qui n'est pas affecté si le niveau d'activité augmente ou diminue.

- ** Le coût variable ** - Un coût variable change en fonction de les modifications de niveau d'activité. Par exemple, un coût de matières direct spécifique est associé à chaque produit qui est vendu. Plus les produits sont vendus, plus il y a de coûts de matières directs.

- ** le coût Semi- variable ** - Les coûts Semi- variables sont en partie résolus et en partie des coûts variables. Par exemple, les frais d'accès à Internet incluent des frais mensuels d'accès standard et des frais d'utilisation de la bande passante. Les frais mensuels d'accès standard sont un coût fixe, alors que les frais d'utilisation de la bande passante sont un coût variable.

**Overhead cost**

Les frais généraux font référence aux dépenses constantes liées à l'exploitation d'une entreprise. Il s'agit des coûts qui ne peuvent pas être liés directement à des activités d'entreprise spécifiques. Voici quelques exemples de frais généraux :

-   Frais comptables
-   Amortissements
-   Assurance
-   Intérêts
-   Frais juridiques
-   Taxes
-   Coûts des services publics

**Cost allocation**

La répartition des coûts est le processus permettant d'affecter et de répartir les coûts, en fonction des causes principales des coûts courants. Vous pouvez affecter les coûts et les quantités d'un objet de coût à un ou plusieurs autres objets de coûts. Par exemple, tous les coûts de services d'établissement sont affectés aux différents services qui utilisent le bâtiment de bureau commun.

**Cost allocation policy**

La stratégie de répartition des coûts définit les montants et les quantités qui doivent être répartis. Les règles de répartition incluent les règles de source de répartition, qui déterminent les coûts qui sont répartis, et les règles de cibles de répartition, qui déterminent où les coûts sont répartis. Par exemple, tous les coûts des services d'établissement sont une source de répartition qui peut être répartie sur plusieurs services d'une organisation (c'est-à-dire, les cibles de répartition).

**Allocation base**

La base de répartition est la base pouvant être utilisée pour mesurer et quantifier les activités, telles que les heures-machine utilisées, les kilowatt-heures consommés, les heures de main d'œuvre directes consacrées, ou la surface qui est occupée. Elle est utilisée pour répartir les coûts vers un ou plusieurs objets de coût.

**Allocation principle**

L'un des principes de répartition consiste à affecter le coût par taux de coût. Vous pouvez choisir d'affecter des coûts à l'aide du taux de période réel ou d'un taux historique. La répartition qui utilise la méthode réciproque permet de garantir que la base de répartition est déterminée par une série d'équations simultanées avant que la répartition ne soit effectuée à l'aide du taux de période réel.

**Cost roll-up**

L'objectif du repositionnement des coûts est d'inclure tous les coûts pour un objet de coût donné. Le niveau d'agrégation est défini par l'utilisateur. Grâce au repositionnement des coûts, vous pouvez regrouper des éléments de coûts qui doivent être répartis d'un coût l'objet à un autre. Lorsque le repositionnement des coûts n'est pas utilisé, chaque élément des coûts est réparti d'un objet de coût à un autre.

** Stratégie de taux de coût **

Le taux de coût est utilisé pour calculer le prix par objet de coût. Pour comprendre les éléments du prix, vous définissez des stratégies de taux de coût. Il existe deux types de taux de coût : le taux de coût historique et le taux de coût planifié. Un taux de coût historique est un taux calculé qui est utilisé comme multiplicateur pour la base de répartition d'un objet de coût. Le taux est calculé selon les répartitions des coûts de la période précédente. Un taux planifié est un taux défini par l'utilisateur.

** Hiérarchie de dimension **

Les hiérarchies de dimensions sont utilisées comme structures de génération d'états lorsque vous définissez des règles de répartition, de taux de coût, et de repositionnement des coûts, que vous affichez des relevés ou des données dans Microsoft Excel, puis que vous définissez l'accès aux données agrégées. Il existe deux hiérarchies de dimensions : la hiérarchie de catégorisation et la hiérarchie de classification. Une hiérarchie de catégorisation est définie en fonction des éléments de coûts, alors qu'une hiérarchie de classification est définie en fonction des objets de coût.

**Statistical dimension**

Une dimension statistique est l'expression d'un nombre ou d'une somme d'un objet pouvant être utilisée comme base pour les répartitions ou calculs de taux de coût. Elle est créée manuellement ou importée des systèmes sources. Les exemples de dimensions statistiques comptent le nombre d'employés, le nombre de logiciels sous licence sur chaque périphérique, la consommation d'électricité de chaque ordinateur, ou les mètres carrés d'un centre de coût.

**Statistical entry**

Les entrées statistiques conservent la valeur de la somme ou du nombre enregistré pour une dimension statistique donnée. La valeur de la somme ou du nombre enregistré est également appelée l'ampleur.


