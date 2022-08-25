---
title: Recherche de navigation
description: Cet article explique comment utiliser la fonctionnalité de recherche pour accéder aux pages.
author: jasongre
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 25991
ms.assetid: eef0676f-c4b1-490e-a032-e9c8580f3fea
ms.openlocfilehash: 4c362e4cd83f926e7e21d775abd24ae6ddfcbbed
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292335"
---
# <a name="navigation-search"></a>Recherche de navigation

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Cet article explique comment utiliser la fonctionnalité de recherche pour accéder aux pages.

L’application comprend un certain nombre de zones et de pages pour vous aider à effectuer diverses tâches. Pour rechercher rapidement les pages qu’il vous faut pour effectuer vos tâches, utilisez la fonctionnalité de recherche de navigation.

Pour utiliser cette fonction, cliquez sur l’icône **Rechercher** pour afficher la zone **Rechercher**. Vous pouvez ensuite entrer un ou plusieurs mots dans la zone. Le système recherche immédiatement les pages pertinentes dans l’application qui correspondent aux mots que vous avez entrés. Par exemple, vous pouvez taper « facture fournisseur » comme entrée, puis le système affiche les résultats correspondant à cette entrée.

> [!NOTE]
> La zone **Rechercher** vous aide rechercher et accéder aux pages. Elle ne vous aidera pas à rechercher des données spécifiques ou des actions.

![search-box.](media/navigation-search.png "zone Recherche")

## <a name="quickly-navigate-to-a-particular-page"></a>Accéder rapidement à une page spécifique

La fonctionnalité de recherche de navigation est également très utile pour accéder rapidement à une page particulière. Par exemple, si vous êtes un employé de comptabilité fournisseur qui utilise souvent la page **Journal des paiements**, vous pouvez entrer « journal des paiements » dans la zone **Rechercher**. Étant donné que l’entrée est une correspondance exacte du titre de la page, la page est répertoriée en haut des résultats de la recherche, et vous pouvez rapidement y accéder.

La liste des résultats de la recherche affiche le titre de la page ainsi que le chemin de navigation. Cela indique l’emplacement de la page dans l’application. Il vous aide également à différencier entre deux ou plusieurs pages similaires dans les résultats.

Lorsque vous recherchez une page, votre entrée est mise en correspondance avec le titre de la page, ainsi qu’avec son chemin de navigation. Par exemple, si vous entrez « client » dans la zone **Recherche**, vous verrez les résultats des pages disponibles dans la section Comptabilité client – même si les titres de la page ne comprennent pas le mot « client ».

## <a name="quickly-navigate-to-a-page-based-on-the-technical-form-name"></a>Accédez rapidement à une page basée sur le nom d'écran

La fonctionnalité de recherche de navigation inclut également une fonctionnalité très demandée par les utilisateurs expérimentés : la possibilité d’accéder rapidement à une page en fonction de son nom d'écran technique. De nombreux utilisateurs sont si familiarisé avec le système qu’ils connaissent les noms exacts des écrans qu’ils utilisent. Si vous êtes l’un de ces utilisateurs, vous pouvez entrer **écran :** suivi du nom de l’écran que vous recherchez. Par exemple, si vous entrez **écran : vendinvoice**, les résultats de la recherche affichent toutes les pages où le nom d’écran commence par **vendinvoice**.

## <a name="administration-and-security"></a>Administration et sécurité

D’un point de vue d’administration et de sécurité, la fonctionnalité de recherche de navigation ne fait apparaître que deux types de résultats :

- Des pages activées dans la configuration actuelle (par clés de configuration) ;
- Des pages auxquelles l’utilisateur a accès en fonction de son rôle d’utilisateur.

La liste des résultats de la recherche est limitée à 10 articles. Si vous ne trouvez pas ce que vous recherchez dans les résultats, vous devez essayer de raffiner ou d'actualiser l’entrée.

## <a name="development"></a>Développement

Du point de vue du développement, la fonctionnalité de recherche de navigation est très facile à exploiter car il n’existe pratiquement aucun retard entre le déploiement des options de menu et leur capacité à s’afficher dans les résultats de la recherche. Tant que les options de menu sont liées au volet de navigation ou au tableau de bord, elles peuvent automatiquement faire l’objet d’une recherche.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
