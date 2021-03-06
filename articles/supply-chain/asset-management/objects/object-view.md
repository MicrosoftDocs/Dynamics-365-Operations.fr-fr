---
title: Vue des actifs
description: Cette rubrique décrit la vue des actifs dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectTree, EntAssetFunctionalLocationTree
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4a7bf1cf07178f570f32e3fa4c4c1e5a2106b10d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837847"
---
# <a name="asset-view"></a>Vue des actifs

[!include [banner](../../includes/banner.md)]

 

Cette rubrique décrit la vue des actifs dans le module Gestion des actifs. La page **Vue des actifs** affiche les actifs actifs et les postes techniques dans une arborescence. Par conséquent, vous pouvez facilement avoir une vue d’ensemble des relations entre les actifs et les postes techniques. En outre, vous pouvez afficher des informations détaillées sur les postes techniques, les actifs et les nomenclatures correspondantes. Vous pouvez également avoir une vue d’ensemble rapide des demandes de maintenance et des ordres de travail actifs qui sont associés à un actif.

1. Sélectionnez **Gestion des actifs** \> **Commun** \> **Actifs** \> **Vue des actifs**.
2. Pour modifier la vue qui s’affiche sur la page, sélectionnez une nouvelle valeur dans le champ **Vue**.

    > [!NOTE]
    > La vue par défaut qui s’affiche lorsque vous ouvrez la page **Vue des actifs** dépend de la valeur sélectionnée dans le champ **Vue** de l’onglet **Actifs** de la page **Paramètres de gestion des actifs** (**Gestion des actifs** \> **Paramétrage** \> **Paramètres de gestion des actifs**).

À droite de la page, les raccourcis affichent les détails de la vue sélectionnée.

La piste de navigation qui apparaît au-dessus de l’arborescence affiche la sélection actuelle dans l’arborescence. Cette piste de navigation utilise le format suivant :

ID poste technique / ID poste technique (s’il existe plusieurs postes techniques) \> ID actif / ID actif(s’il existe plusieurs actifs) - Numéro d’article.

Si vous avez sélectionné un actif dans l’arborescence, vous pouvez sélectionner **Demandes actives** ou **Ordres de travail actifs** pour afficher les demandes de maintenance ou les ordres de travail associés à l’actif. Vous pouvez également sélectionner **Ouvrir** \>, **Poste technique**, **Actif** ou **Nomenclature des actifs** pour ouvrir la vue associée.

L’option **Postes techniques des actifs** que vous pouvez sélectionner dans le champ **Vue** est également disponible dans toute recherche d’actif où vous pouvez sélectionner un actif. L’arborescence s’affiche sous un onglet **Vue des actifs**, par exemple, où vous [créez un actif](../objects/create-an-object.md), créez une demande de maintenance ou créez un ordre de travail.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]