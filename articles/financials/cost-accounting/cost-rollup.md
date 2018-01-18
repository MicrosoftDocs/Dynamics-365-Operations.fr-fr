---
title: "Stratégie de repositionnement des coûts et calcul des frais généraux"
description: "Cette rubrique fournit des informations sur la façon de déterminer le niveau correct d'éléments de coût secondaires et de créer des règles de repositionnement des coûts qui correspondent à la hiérarchie de l'organisation et à la traçabilité des coûts."
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostRollupRule, CAMDimensionHierarchy
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 088883f35fe73c933c1d8558297bee0e3ccc3cb2
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="cost-rollup-policy-and-overhead-calculation"></a>Stratégie de repositionnement des coûts et calcul des frais généraux 

[!include[banner](../includes/banner.md)]

Le contrôle de gestion vous permet de mieux comprendre comment le flux des coûts se rapporte aux produits et services fournis dans une organisation. Pour voir la transparence des coûts, il est primordial d'effectuer la répartition des coûts entre les objets de coût en fonction d'une base de répartition appropriée. Par défaut, la répartition des coûts est effectuée pour l'élément de coût principal, qui est désiré dans certains cas, mais elle comporte certaines implications qui doivent être prises en compte.

-   Les objets de coût auxiliaires se termineront par un solde nul pour l'élément de coût principal après le calcul des frais généraux.

-   Le volume des écritures de coût généré par le calcul des frais généraux peut être très élevé.

-   Il est impossible de suivre le flux des coûts entre les objets de coût.

Pour éviter ces implications, le contrôle de gestion vous permet de configurer la répartition des coûts pour obtenir une adéquation dans les exigences hiérarchiques de votre organisation. Cette rubrique montre comment déterminer le niveau correct d'éléments de coût secondaires et comment créer des règles de repositionnement des coûts qui correspondent à la hiérarchie de l'organisation et à la traçabilité des coûts.

> [!NOTE]
> Vous pouvez modifier les configurations en fonction de l'évolution des exigences hiérarchiques.

## <a name="example-of-cost-rollup-policy-setup"></a>Exemple de paramétrage de la stratégie de repositionnement des coûts

Imaginez qu'une organisation a la structure suivante avec 4 centres de coût.

![Exemple d'une structure d'organisation](./media/dimension-hierarchy-org.png)

**Dimension d'objet de coût**

| Centres de coût | Description          |
|--------------|-----------|
| CC001        | RH        |
| CC002        | Finances   |
| CC003        | Assemblage  |
| CC004        | Emballage |

**Dimension d'élément de coût**

| Éléments de coût | Description | Type    |
|---------------|-------------|---------|
| 1 001          | Électricité | Principale |
| 1 002          | Salaires    | Principale |
| 1003          | Publicité | Principale |

Une hiérarchie de dimensions qui répond aux conditions de génération d'états d'organisation peut être paramétrée comme suit.

**Détails sur la hiérarchie des dimensions**

| Nom de la hiérarchie des dimensions | Dimension    | Nom du type de hiérarchie des dimensions      | Hiérarchie de la liste d'accès |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organisation             | Centres de coût | Hiérarchie de classification de dimension | N°                    |

**Hiérarchie des dimensions**

|              | Plages de membres de la dimension |                     |
|--------------|-------------------------|---------------------|
| **Nœuds**        | **Membre de la dimension de départ**   | **Membre de la dimension de fin** |
| Organisation |                         |                     |
| &nbsp;&nbsp;Admin             |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Finances              | CC001                   | CC001               |
| &nbsp;&nbsp;&nbsp;&nbsp;RH               | CC002                   | CC002               |
| &nbsp;&nbsp;Production               |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Emballage              | CC003                   | CC003               |
| &nbsp;&nbsp;&nbsp;&nbsp;Assemblage             | CC004                   | CC004               |

Une hiérarchie de dimensions qui répond aux exigences de stratégie peut être paramétrée comme suit.

**Détails sur la hiérarchie des dimensions**

| Nom de la hiérarchie des dimensions | Dimension     | Nom du type de hiérarchie des dimensions      |
|--------------------------|---------------|------------------------------------|
| Relevé de compte de résultat  | Éléments de coût | Hiérarchie de classification de dimension |

**Hiérarchie des dimensions**

|                         | Plages de membres de la dimension |                     |
|-------------------------|-------------------------|---------------------|
| Noeuds                   | Membre de la dimension de départ   | Membre de la dimension de fin |
| Relevé de compte de résultat |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Coût principal                    | 10001                   | 10003               |

Une fois que les écritures de comptabilité sont traitées, le solde d'écriture de coût par objet de coût ressemble à ce qui suit.

|                      | **Objet de coût** |           |           |           | **Total**     |
|----------------------|-----------------|-----------|-----------|-----------|---------------|
| **Élément de coût**     | **CC001**       | **CC002** | **CC003** | **CC004** |               |
| **1001 Électricité** | 100,00          | 200 00    | 6.000,00  | 2.000,00  | **8.300,00**  |
| **1002 Salaires**    | 10.000,00       | 10.000,00 | 8.000,00  | 6.500,00  | **34.500,00** |
| **1003 Publicité** | 0 00            | 4.000,00  | 0 00      | 0 00      | **4.000,00**  |
|                      | 10.100,00       | 14.200,00 | 14.000,00 | 8.500,00  | **46.800,00** |

**Dimension statistique**

| Éléments statistiques |    Description   |
|----------------------|------------------|
| SE-1                 | Services HR      |
| SE-2                 | Services Finance |

L'objet de coût CC001 HR contribue aux services des RH pour plusieurs objets de coûts.

Les services RH sont consommés par la répartition suivante de l'ampleur.

| Objet de coût | Description |   Services HR |
|-------------|-------------|----|
| CC002       | Finances     | 35 |
| CC003       | Assemblage    | 55 |
| CC004       | Emballage   | 10 |

L'objet de coût CC002 Finance contribue à plusieurs objets de coûts.

Les services financiers sont consommés par la répartition suivante de l'ampleur.

| Objet de coût |   Description    |  Services Finance   |
|-------------|------------------|----|
| CC003       | Assemblage         | 65 |
| CC004       | Emballage        | 35 |

Les stratégies de répartition des coûts peuvent être paramétrées comme suit.

| Nom de la stratégie | Description     | Hiérarchie des dimensions d'objet de coût | Dimension statistique | Dimension d'élément de coût |
|-------------|-----------------|---------------------------------|-----------------------|------------------------|
| 2017        | Affectation des coûts | Organisation                    | Éléments statistiques  | Éléments de coût          |

Les règles de répartition des coûts peuvent être paramétrées comme suit.

| Nœud de hiérarchie des dimensions d'objet de coût | Comportement de coûts | Base de répartition        |
|--------------------------------------|---------------|------------------------|
| CC001                                | Total         | **Services RH**        |
| CC002                                | Total         | **Services financiers** |

<a name="brhow-cost-flows-between-cost-centers"></a><br>Flux des coûts entre les centres de coût 
---------------------------------------------------

Si vous souhaitez savoir comment le coût s'écoule entre les centres de coût dans l'organisation, vous pouvez créer des éléments de coût du type **Secondaire** pour chaque centre de coût. Ces éléments de coût seront alors utilisés pour transférer les soldes entre les centres de coût lors du calcul des frais généraux.

Les membres de la dimension d'élément de coût peuvent être paramétrés comme suit.

| Éléments de coût | Type          |               |
|---------------|---------------|---------------|
| 1 001          | Électricité   | Principale       |
| 1 002          | Salaires      | Principale       |
| 1003          | Publicité   | Principale       |
| **SC-CC001**  | **RH**        | **Secondaire** |
| **SC-CC002**  | **Finances**   | **Secondaire** |
| **SC-CC003**  | **Assemblage**  | **Secondaire** |
| **SC-CC004**  | **Emballage** | **Secondaire** |

La hiérarchie de dimension **Relevé de compte de résultat** doit être mise à jour avec les nouveaux membres de la dimension afin que la hiérarchie des dimensions contienne les données correctes qui peuvent être utilisées pour définir la génération des états et les stratégies.

**Détails sur la hiérarchie des dimensions**

| Nom de la hiérarchie des dimensions | Dimension     | Nom du type de hiérarchie des dimensions      |
|--------------------------|---------------|------------------------------------|
| Relevé de compte de résultat  | Éléments de coût | Hiérarchie de classification de dimension |

**Hiérarchie des dimensions**

|                         | Plages de membres de la dimension |                     |
|-------------------------|-------------------------|---------------------|
| Noeuds                   | Membre de la dimension de départ   | Membre de la dimension de fin |
| Relevé de compte de résultat |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Coût principal                        | 10001                   | 10003               |
| &nbsp;&nbsp;&nbsp;&nbsp;Coût secondaire                         | **SC-CC001**            | **SC-CC004**        |

Créez une **stratégie de repositionnement des coûts** où chaque centre de coût est mappé à un élément coût correspondant du type **Secondaire**.

**Stratégie de repositionnement des coûts**

| Nom de la stratégie | Description | Hiérarchie des dimensions d'objet de coût | Hiérarchie des dimensions d'élément de coût |
|-------------|-------------|---------------------------------|----------------------------------|
| 2017        | Flux de coût   | Organisation                    | Relevé de compte de résultat          |

**Règles de repositionnement des coûts**

| Nœud de hiérarchie des dimensions d'objet de coût | Nœud de hiérarchie des dimensions d'élément de coût | Élément de coût secondaire |
|--------------------------------------|---------------------------------------|------------------------|
| CC001                                | Relevé de compte de résultat               | **SC-CC001**           |
| CC002                                | Relevé de compte de résultat               | **SC-CC002**           |
| CC003                                | Relevé de compte de résultat               | **SC-CC003**           |
| CC004                                | Relevé de compte de résultat               | **SC-CC004**           |

## <a name="perform-overhead-calculation"></a>Exécuter le calcul des frais généraux

**Journal**

| Journal de saisie | Type de journal            | Période de calendrier fiscal | Année | Période | Version       |
|---------|-------------------------|------------------------|------|--------|---------------|
| 00002   | Journal de répartition des coûts | Exercice                 | 2017    | Période 1 | Calcul des frais généraux / 01-02-2017 11:51:00 PM / Comptabilité /2017 / Période 1 |

Le système applique désormais la **stratégie de repositionnement des coûts** lorsqu'il crée les **entrées du journal pour le solde d'objet de coût**.

**Entrées du journal pour le solde d'objet de coût**

| Date comptable | Objet de coût | Description  | Élément de coût | Description |  Montant |
|-----------------|-------------|--------------|----------|-----------|-----------|
| 31-01-2017      | CC001       | RH           | SC-CC001 | RH        | 10.100,00 |
| 31-01-2017      | CC002       | Finances      | SC-CC002 | Finances   | 17.735,00 |
| 31-01-2017      | CC003       | Assemblage     | SC-CC003 | Assemblage  | 31.082,75 |
| 31-01-2017      | CC004       | Emballage    | SC-CC004 | Emballage | 15.717,25 |

> [!NOTE]
> Les entrées de journal sont créées en fonction des règles dans la **Stratégie de repositionnement des coûts** si une stratégie existe. Le solde affiché est le solde du calcul des frais généraux.

La page **Détails de l'entrée de journal pour le solde d'objet de coût** qui est accessible à partir des entrées de journal affiche la manière dont le solde est obtenu.

**Exemple : Écriture de journal pour l'objet de coût CC002 Finance**

**Détails de l'entrée de journal pour le solde d'objet de coût**

| Membre de la dimension d'élément de coût | Description |  Montant   |
|-------------------------------|-------------|-----------|
| 1 001                          | Électricité | 200 00    |
| 1 002                          | Salaires    | 10.000,00 |
| 1003                          | Publicité | 4.000,00  |
| SC-CC001                      | RH          | 3.535,00  |

**Écritures de coût générées par le calcul des frais généraux**

| Objet de coût | Description  | Élément de coût   | Description  |        Montant     |       Date comptable     |
|-------------|--------------|----------|-----------------|-------------|------------|
| CC001       | RH           | SC-CC001 | RH              | 10.100,00 \- | 31-01-2017 |
| CC002       | Finances      | SC-CC001 | RH              | 3.535,00    | 31-01-2017 |
| CC003       | Assemblage     | SC-CC001 | RH              | 5.555,00    | 31-01-2017 |
| CC004       | Emballage    | SC-CC001 | RH              | 1.010,00    | 31-01-2017 |
| CC002       | Finances      | SC-CC002 | Finances         | 17.735,00 \- | 31-01-2017 |
| CC003       | Assemblage     | SC-CC002 | Finances         | 11.527,75   | 31-01-2017 |
| CC004       | Emballage    | SC-CC002 | Finances         | 6.207,25    | 31-01-2017 |

Après exécution du **calcul des frais généraux**, vous pouvez déclarer les résultats à l'aide des outils tels que Microsoft SharePoint Workspace, Excel ou Power BI.

## <a name="view-reporting-in-excel"></a>Afficher les états générés dans Excel 

Les hiérarchies de dimensions vous permettent d'afficher des données à différents niveaux d'agrégation.

Voici un exemple d'une génération d'états PowerPivot dans Excel.

| **Relevé de compte de résultat** | **Objet de coût** |                |               |               |  **Total**    |
|-----------------------------|-----------------|----------------|---------------|---------------|---------------|
|                             | **CC001**       | **CC002**      | **CC003**     | **CC004**     |               |
| **Coût principal**            | **10.100,00**   | **14.200,00**  | **14.000,00** | **8.500,00**  | **46.800,00** |
| 1001 &nbsp;&nbsp;&nbsp;&nbsp;                            | 100,00          | 200 00         | 6.000,00      | 2.000,00      | **8.300,00**  |
| 1002 &nbsp;&nbsp;&nbsp;&nbsp;                            | 10.000,00       | 10.000,00      | 8.000,00      | 6.500,00      | **34.500,00** |
|1003 &nbsp;&nbsp;&nbsp;&nbsp;                             | 0 00            | 4.000,00       | 0 00          | 0 00          | **4.000,00**  |
|**Coût secondaire**                            | **-10.100,00**  | **-14.200,00** | **17.082.75** | **7.217,25**  | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC001                            | 10.100,00 \-     | 3.535,00       | 5.555,00      | 1.010,00      | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC002                             | 0 00            | 17.735,00 \-    | 11.527,75     | 6.207,25      | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC003                            | 0 00            | 0 00           | 0 00          | 0 00          | 0 00          |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC004                             | 0 00            | 0 00           | 0 00          | 0 00          | 0 00          |
| **Total**                   | **0,00**        | **0,00**       | **31.082,75** | **15.717,25** | **46.800,00** |

Utiliser la **Stratégie de repositionnement des coûts** et les **Éléments de coût du type secondaire** vous permet de conserver le coût principal par objet de coût pour les états internes comme le coût principal qui reste après le **calcul des frais généraux**.

Si le même exemple a été exécuté sans créer la **Stratégie de repositionnement des coûts,** le résultat de génération d'états est comme suit. Le coût est transmis correctement mais la traçabilité et l'analyse de la manière dont les flux de coût entre les centres de coût sont perdus.

| **Relevé de compte de résultat** | **Objet de coût** |           |               |               |          **Total**  |
|-----------------------------|-----------------|-----------|---------------|---------------|---------------|
|                             | **CC001**       | **CC002** | **CC003**     | **CC004**     |               |
| **Coût principal**            | **0,00**        | **0,00**  | **31.082,75** | **15.717,25** | **46.800,00** |
|1001 &nbsp;&nbsp;&nbsp;&nbsp;                              | 0 00            | 0 00      | 6.207,75      | 2.092,25      | **8.300,00**  |
| 1002 &nbsp;&nbsp;&nbsp;&nbsp;                             | 0 00            | 0 00      | 22.275,00     | 12.225,00     | **34.500,00** |
|1003 &nbsp;&nbsp;&nbsp;&nbsp;                              | 0 00            | 0 00      | 2600,00       | 1.400,00      | **4.000,00**  |
|**Coût secondaire**                            | **0,00**        | **0,00**  | **0,00**      | **0,00**      | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC001                             | 0 00            | 0 00      | 0 00          | 0 00          | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC002                             | 0 00            | 0 00      | 0 00          | 0 00          | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC003                             | 0 00            | 0 00      | 0 00          | 0 00          | 0 00          |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC004                             | 0 00            | 0 00      | 0 00          | 0 00          | 0 00          |
| **Total**                   | **0,00**        | **0,00**  | **31.082,75** | **15.717,25** | **46.800,00** |

Selon les exigences de génération d'états et de traçabilité de votre organisation, cette rubrique montre comment déterminer le niveau correct d'éléments de coût secondaires et comment créer des règles de repositionnement des coûts qui correspondent à vos besoins.

Cette séparation précise entre **Affectation des coûts** et **Stratégies de repositionnement des coûts** fournit une souplesse pour effectuer des mises à jour continues sans perturbation.



## <a name="see-also"></a>Voir également :
-  [Dimensions d'objets de coût](cost-objects.md)
-  [Dimensions d'éléments de coût](cost-elements.md)
-  [Hiérarchies des dimensions](dimension-hierarchy.md)
-  [Calcul des frais généraux](overhead-calculation.md)

