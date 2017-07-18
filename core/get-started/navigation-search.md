---
title: Recherche de navigation
description: "Cette rubrique explique comment utiliser la fonctionnalité de recherche pour accéder aux pages dans Microsoft Dynamics 365 for Finance and Operations."
author: aneesmsft
manager: AnnBe
ms.date: 04/27/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 25991
ms.assetid: eef0676f-c4b1-490e-a032-e9c8580f3fea
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 431165d541c9a3b63100a93108ee770df8e88aa8
ms.contentlocale: fr-fr
ms.lasthandoff: 06/13/2017

---

# <a name="navigation-search"></a>Recherche de navigation

[!include[banner](../includes/banner.md)]


Cette rubrique explique comment utiliser la fonctionnalité de recherche pour accéder aux pages dans Microsoft Dynamics 365 for Finance and Operations.

Finance and Operations propose une fonctionnalité pour un large éventail de secteurs et de marchés verticaux. L'application comprend un certain nombre de zones et de pages pour effectuer diverses tâches. Pour rechercher rapidement les pages qu'il vous faut pour effectuer vos tâches, utilisez la fonctionnalité de recherche de navigation. 

Pour utiliser cette fonction, cliquez sur l'icône **Rechercher** pour afficher la zone **Rechercher**. Vous pouvez ensuite entrer un ou plusieurs mots dans la zone. Le système recherche immédiatement les pages pertinentes dans l'application qui correspondent aux mots que vous avez entrés. Par exemple, vous pouvez taper « facture fournisseur » comme entrée, puis le système affiche les résultats correspondant à cette entrée. 

**Remarque :** la zone **Rechercher** vous aide rechercher et accéder aux pages. Elle ne vous aidera pas à rechercher des données spécifiques ou des actions. 

[![search-box](media/navigation-search.png "Zone de recherche") 

## <a name="quickly-navigate-to-a-particular-page"></a>Accéder rapidement à une page spécifique
La fonctionnalité de recherche de navigation est également très utile pour accéder rapidement à une page particulière. Par exemple, si vous êtes un employé des Achats qui utilise souvent la page **Journal des paiements**, vous pouvez entrer « journal des paiements » dans la zone **Rechercher**. Étant donné que l'entrée est une correspondance exacte du titre de la page, celle-ci est répertoriée en haut des résultats de la recherche, et vous pouvez rapidement y accéder. 

Les résultats de la recherche affichent le titre de la page et son chemin de navigation. Indique l'emplacement de la page dans l'application. Cela vous aide également à différencier deux ou plusieurs pages similaires dans les résultats. 

Lorsque vous recherchez une page, votre entrée est mise en correspondance avec le titre de la page, ainsi qu'avec son chemin de navigation. Par exemple, si vous entrez « ventes » dans la zone **Recherche**, vous verrez les résultats des pages disponibles dans la section Comptabilité client - même si les titres de la page ne comprennent pas le mot « ventes. » 

## <a name="quickly-navigate-to-a-page-based-on-the-technical-form-name"></a>Accéder rapidement à une page en fonction de son nom technique
La fonctionnalité de recherche de navigation inclut également une fonctionnalité très demandée par les utilisateurs avec pouvoirs : la possibilité d'accéder rapidement à une page en fonction de son nom technique. De nombreux utilisateurs sont si familiarisé avec le système qu'ils connaissent les noms exacts des écrans qu'ils utilisent. Si vous êtes l'un de ces utilisateurs, vous pouvez entrer **écran :** suivi du nom de l'écran que vous recherchez. Par exemple, si vous entrez **écran : vendinvoice**, les résultats de la recherche affichent toutes les pages où le nom d'écran commence par **vendinvoice**. 

## <a name="administration-and-security"></a>Administration et sécurité
D'un point de vue d'administration et de sécurité, la fonctionnalité de recherche de navigation ne fait apparaître que deux types de résultats :

-   les pages activées dans la configuration actuelle (par clés de configuration) ;
-   les pages auxquelles l'utilisateur a accès en fonction de son rôle d'utilisateur.

La liste des résultats de la recherche est limitée à 10 articles. Si vous ne trouvez pas ce que vous recherchez dans les résultats, vous devez essayer de raffiner ou actualiser l'entrée. 

## <a name="development"></a>Développement 
D'un point de vue du développement, la fonctionnalité de recherche de navigation est très accessible car il n'existe pratiquement aucun délai entre le déploiement des options de menu et leur capacité à s'afficher dans les résultats de la recherche. Tant que les options de menu sont liées au volet de navigation ou au tableau de bord, elles peuvent automatiquement faire l'objet d'une recherche. 

