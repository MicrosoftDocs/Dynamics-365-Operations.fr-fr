---
title: Recherche de navigation
description: "Cet article décrit comment utiliser la fonctionnalité de recherche pour accéder aux pages dans Microsoft Dynamics 365 pour les opérations."
author: aneesmsft
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 25991
ms.assetid: eef0676f-c4b1-490e-a032-e9c8580f3fea
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 87fed576f8cf358520d94f5cd5b326ff9801913a
ms.lasthandoff: 03/31/2017


---

# <a name="navigation-search"></a>Recherche de navigation

Cet article décrit comment utiliser la fonctionnalité de recherche pour accéder aux pages dans Microsoft Dynamics 365 pour les opérations.

Dynamics 365 pour les opérations fournit une fonctionnalité pour un tableau large de secteurs et de verticales. L'application inclut un certain nombre de zones et de pages pour vous aider à effectuer de nombreuses tâches. Pour trouver rapidement les pages à accomplir vos tâches, utilisez la fonction de recherche de navigation. Pour utiliser cette fonction, cliquez sur l'icône **Rechercher** pour afficher la zone **Rechercher**. Vous pouvez ensuite entrer un ou plusieurs mots dans la zone. Le système recherche immédiatement les pages pertinentes dans l'application qui correspondent aux mots que vous avez entrés. Par exemple, vous pouvez taper « facture fournisseur » comme entrée, puis le système affiche les résultats correspondant à cette entrée. **Remarque :** la zone **Rechercher** vous aide rechercher et accéder aux pages. Elle ne vous aidera pas à rechercher des données spécifiques ou des actions. 

[fenêtre de recherche de![(]. /media/search-box.png)](. /media/search-box.png) Que la fonction de recherche de navigation sert également de grande manière à vous d'accéder rapidement à une page spécifique. Par exemple, si vous êtes commis aux Achats qui utilise fréquemment ** journal des paiements ** la page, vous pouvez entrer « journal des paiements » dans le champ de recherche. L'entrée est une précise - Rapprochez pour le titre de la page, la page est répertoriée en haut des résultats de la recherche, et vous permettent d'accéder à une tâche. 

[rechercher-pour-paiement-journal d'![] (. /media/searching-for-payment-journal.png)](. /media/searching-for-payment-journal.png) 

La liste des résultats de la recherche affiche le titre de la page ainsi que le chemin de navigation. Cela vous aide à vous familiariser avec l'emplacement de la page dans l'application. Cela vous aide également à différencier deux ou plusieurs pages similaires dans les résultats. Lorsque vous recherchez une page, votre entrée est mise en correspondance avec le titre de la page, ainsi qu'avec son chemin de navigation. Par exemple, si vous entrez « Ventes » dans ** ** recherchez la zone, vous ne pourrez afficher les résultats des pages disponibles pour vous dans le secteur des ventes)même si les titres de la page n'incluent pas le mot « Ventes ». 

[![recherche-pour-le-Word- déductible] (. /media/search-for-the-word-receivable.png)](. /media/search-for-the-word-receivable.png) 

Dans une perspective d'administration et de sécurité, les surfaces de fonctionnalité de recherche de navigation uniquement :

-   les pages activées dans la configuration actuelle (par clés de configuration) ;
-   les pages auxquelles l'utilisateur a accès en fonction de son rôle d'utilisateur.

La liste des résultats de la recherche est limitée à 10 articles. Si vous ne trouvez pas ce que vous recherchez dans les résultats, vous devez essayer de raffiner ou actualiser l'entrée. D'un point de vue du développement, la fonctionnalité de recherche de navigation est très accessible car il n'existe pratiquement aucun délai entre le déploiement des options de menu et leur capacité à s'afficher dans les résultats de la recherche. Tant que les options de menu sont liées au volet de navigation ou au tableau de bord, elles peuvent automatiquement faire l'objet d'une recherche. La fonctionnalité de recherche de navigation inclut également une fonctionnalité très demandée par les utilisateurs avec pouvoirs : la possibilité d'accéder rapidement à une page en fonction de son nom technique. De nombreux utilisateurs sont si familiarisé avec le système qu'ils connaissent les noms exacts des écrans qu'ils utilisent. Si vous êtes l'un de ces utilisateurs, vous pouvez entrer **écran :** suivi du nom de l'écran que vous recherchez. Par exemple, si vous entrez **écran : vendinvoice**, les résultats de la recherche affichent toutes les pages où le nom d'écran commence par **vendinvoice**. 

[recherche-pour- écran -vendinvoice - vendinvoice![] (. /media/search-for-form-vendinvoice.png)](. /media/search-for-form-vendinvoice.png)


