---
title: Comptage des balises de stock
description: Cet article fournit des informations sur l'inventaire de balises, que vous utilisez pour comparer le contenu réel d'un entrepôt au stock disponible.
author: yufeihuang
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.reviewer: kamaybac
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ceccfce98a71f7396358de9369af61c9eb96dce
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856162"
---
# <a name="inventory-tag-counting"></a>Comptage des balises de stock

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur l'inventaire de balises, que vous utilisez pour comparer le contenu réel d'un entrepôt au stock disponible.

En créant des lignes dans la page **Comptage des balises**, vous placez un numéro de balise sur chaque article en stock, comme un numéro de 1 à 500. Pendant le comptage, entrez le numéro d’article et la quantité sur une balise correspondante. Cette balise peut ensuite être utilisée comme base pour l’entrée dans le journal de comptage des balises. Après avoir validé le journal de balises, un nouveau journal d’inventaire est créé dans la page **Comptage**. Ce journal est basé sur les lignes du journal de comptage des balises que vous avez créé. Pour compter les balises des articles en fonction d’une dimension de stock particulière, sélectionnez la dimension dans la page **Affichage des dimensions** qui s’affiche lorsque vous créez le journal de comptage des balises. Par exemple, pour compter les articles dans un entrepôt particulier, activez la case à cocher **Entrepôt**. Si le curseur **Verrouiller les articles lors du comptage** est sélectionné dans la page **Paramètres de gestion des stocks et des entrepôts**, les articles ne peuvent pas être mis à jour physiquement lors du comptage. Toutefois, les articles dans les journaux de comptage des balises ne sont pas verrouillés lors du comptage. Les mouvements de stock ne sont pas créés tant que lorsque les lignes de comptage des balises ne sont pas validées et transférées vers un journal d’inventaire. Si les balises sont introduites dans le désordre et que vous voulez connaître les balises manquantes, cliquez sur l’en-tête de colonne **Balise** pour trier les lignes par balise.

## <a name="additional-resources"></a>Ressources supplémentaires

[Inventaire tournant](../warehousing/cycle-counting.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]