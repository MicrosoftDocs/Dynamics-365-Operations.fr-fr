---
title: Création de commandes fournisseur et client intersociétés dans plusieurs sociétés
description: Cet article explique comment créer des commandes fournisseur intersociétés ou des commandes client dans plusieurs sociétés
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 6dce419126d60199bc11d4bd3209185ad779e979
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873548"
---
# <a name="creating-intercompany-purchase-and-sales-orders-in-several-companies"></a>Création de commandes fournisseur et client intersociétés dans plusieurs sociétés

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management ne se limite pas uniquement à la gestion d'une société de production et de plusieurs sociétés de vente. Toutes les sociétés paramétrées pour le commerce intersociétés peuvent être des sociétés de commerce ou des sociétés de production.

Si plusieurs sociétés peuvent fournir le même article, vous pouvez librement choisir la société à laquelle acheter cet article et les mises à jour sont effectuées même si une commande client unique devient plusieurs commandes fournisseur.

De la même manière que vous créez automatiquement une commande fournisseur intersociétés, vous pouvez créer une commande client originale dans votre société puis avoir plusieurs sociétés fournisseur intersociétés qui honorent la commande en créant plus d'une commande fournisseur intersociétés. Microsoft Dynamics 365 Supply Chain Management crée automatiquement des commandes client intersociétés dans les sociétés fournisseur.

Pour ce faire, toutes les sociétés doivent être paramétrées en tant que relations commerciales. Les sociétés fournisseur doivent être paramétrées dans Microsoft Dynamics 365 Supply Chain Management en tant que fournisseurs intersociétés et être le principal fournisseur de l'article en question. Sur le bon de commande, dans **Vue d'en-tête**, vous devez sélectionner le champ **Créer automatiquement des commandes intersociétés** et le champ **Livraison directe** sur le raccourci **Paramètres intersociétés**. Il s'agit du paramétrage par défaut.

Vous créez les lignes de vente de la manière habituelle. Lorsque vous quittez l'enregistrement, un message s'affiche, vous informant que les commandes fournisseur intersociétés et les commandes client intersociétés ont été créées. Ce message contient des liens vers les nouvelles commandes. Pour afficher les commandes client intersociétés créées dans vos sociétés fournisseur, ouvrez la commande client, dans l'onglet **Général**, dans le groupe **Informations associées**, sélectionnez **Références**.

Si vous ouvrez les commandes client intersociétés pour les fournisseurs, vous constatez que Microsoft Dynamics 365 Supply Chain Management renseigne automatiquement le numéro de commande client originale et le numéro de commande client intersociétés pour chaque fournisseur.

De même, si vous ouvrez les commandes fournisseur intersociétés pour les fournisseurs, vous constatez que Microsoft Dynamics 365 Supply Chain Management renseigne automatiquement le numéro de commande client originale et le numéro de commande fournisseur intersociétés pour chaque fournisseur.

> [!NOTE]
> Si les articles commandés existent dans l'une de vos sociétés fournisseur intersociétés mais pas dans l'autre, Microsoft Dynamics 365 Supply Chain Management crée les commandes intersociétés pour la société fournisseur disposant des articles mais arrête la création de la commande pour l'autre société. Un message de notification s'affiche si cela arrive.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
