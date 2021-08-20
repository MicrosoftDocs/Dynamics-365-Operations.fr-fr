---
title: Conventions
description: Cette rubrique décrit comment configurer des conventions pour établir la manière dont les coûts doivent être comptabilisés dans la comptabilité globale des stocks.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2d629b082b423edf417714b8362be3364bc861e78f62d430a4d7083b8c49611a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773415"
---
# <a name="conventions"></a>Conventions

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Une convention est un conteneur dédié à un ensemble de stratégies qui affectent le comportement du système. En fonction des besoins de votre entreprise, vous devez définir des conventions en combinant les différentes stratégies qui établissent la manière dont les coûts doivent être comptabilisés dans la comptabilité globale des stocks. Vous pouvez associer chaque convention à un ou plusieurs registres pour assurer la cohérence des stratégies comptables appliquées entre les registres.

Pour configurer vos conventions, accédez à **Comptabilité globale des stocks \> Configuration \> Conventions**. Pour chaque convention, définissez les champs suivants :

- **Nom** : saisissez le nom de la convention.
- **Description** : entrez une description de la convention.
- **Politique d’objet de coût** : sélectionnez une politique d’objet de coût. Ces politiques déterminent le niveau de granularité que le système applique pour calculer et maintenir la valeur du stock. Les options prédéfinies suivantes sont disponibles :

    - Produit
    - Produit – Site
    - Produit – Site – Entrepôt

    Par exemple, si vous sélectionnez *Produit – Site*, pour chaque mouvement de stock (entrée ou sortie), le système calcule et maintient le coût de stock de chaque produit au niveau du site. Par conséquent, les mouvements de stock à des niveaux inférieurs, tels que le niveau de l’entrepôt, n’affectent pas la valeur du stock. (Un exemple de transfert au niveau de l’entrepôt est un transfert d’article entre deux entrepôts sur un même site.) De même, vous ne pouvez pas afficher le coût du stock à un niveau inférieur, tel que le niveau de l’entrepôt.

- **Politique de base de la mesure en entrée** : sélectionnez une politique de base de la mesure en entrée. Ces politiques déterminent les coûts qui doivent entrer dans la comptabilité du stock et les coûts qui doivent être facturés. Les options suivantes sont pertinentes pour les sociétés commerciales :

    - **Historique normal** : tous les éléments de coût sont intégrés dans la comptabilité de stock.
    - **Standard** : le coût standard est intégré dans la comptabilité de stock et la différence entre le coût appliqué et les coûts réels est imputée aux comptes d’écart. Si vous souhaitez créer une politique de base de la mesure en entrée *Standard*, vous devez d’abord créer une liste de prix où la politique peut rechercher le coût standard de chaque article.
    - **Listes de prix** : la comptabilité globale des stocks prend en charge la récupération du prix des articles auprès de plusieurs entités juridiques. Vous pouvez définir une liste de prix qu’utilisera la politique de base de la mesure en entrée. De cette façon, le système saura où rechercher le prix des articles. Procédez comme suit pour configurer des listes de prix :

        1. Dans le champ **Nom**, entrez un nom.
        1. Entrez une description dans le champ **Description**.
        1. Dans le champ **Type de coût**, sélectionnez un type de coût (*Coût standard* ou *Coût planifié*).
        1. Dans le champ **Type de prix**, sélectionnez un type de prix (*Coût*, *Achat* ou *Prix de vente*).
        1. Ajoutez une version d’évaluation des coûts.
        1. Dans le volet Actions, sélectionnez **Prix** pour valider le prix des articles sur la liste de prix.

- **Politique d’hypothèse de flux de coûts** : sélectionnez une politique d’hypothèse de flux de coûts. Ces politiques déterminent comment les coûts sont retirés du stock et sont déclarés comme coût des marchandises vendues. Les options prédéfinies suivantes sont disponibles :

    - Moyenne
    - Spécifique – Lot

    > [!NOTE]
    > Comptabilité globale des stockes est un système d’inventaire permanent. Par conséquent, le système suit la valeur du stock transaction par transaction.

- **Politique d’élément de coût** : vous pouvez définir des politiques d’élément de coût et les lier à ce champ. Un *élément de coût* est le coût d’une ressource qui est consommée par un événement. Vous pouvez utiliser des éléments de coût pour suivre et catégoriser les coûts. Pour créer des politiques d’élément de coût, saisissez les informations aux endroits suivants :

    - Champ **Nom**
    - Champ **Description**
    - Liste **Élément de coût**
    - Grille **Règles**

    Si vous ne souhaitez pas décomposer davantage la valeur du stock, vous devez tout de même créer une liste d’éléments de coût comportant un seul élément de coût. Vous devez ensuite créer une politique d’élément de coût pour mapper tous les types de mesure pertinents (éléments de coût) sur cet élément de coût.
