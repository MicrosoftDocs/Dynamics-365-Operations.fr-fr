---
title: Synchroniser les informations clients intersociétés
description: Cet article explique la synchronisation des informations client pour les commandes intersociétés
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
ms.openlocfilehash: a3a67c9bcf93f88375d2d4d78d87175200626d50
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897514"
---
# <a name="synchronize-intercompany-customer-information"></a>Synchroniser les informations clients intersociétés

[!include [banner](../../includes/banner.md)]

Les informations client sont synchronisées si le champ **Informations client** est activé lors de la création de la commande client ou de la modification du client, de la référence fournisseur ou du numéro de bon de commande client.

Vous pouvez modifier la valeur de ces champs de synchronisation à tout moment. Toutefois, vous pouvez uniquement déterminer si cette valeur est copiée dans les autres commandes intersociétés via la sélection de ce paramètre. Si vous avez activé le champ **Informations client** sur la commande client intersociétés, une modification de la commande client intersociétés est synchronisée avec la commande fournisseur intersociétés. Si vous avez également activé le champ **Informations client** sur la commande fournisseur intersociétés, la synchronisation est également effectuée sur la commande client originale.

> [!NOTE]
> Si vous avez activé le champ **Informations client** sur la commande fournisseur intersociétés et sur la commande client intersociétés, les mises à jour effectuées par un employé d'une société sont remplacées par celles effectuées par un autre employé d'une autre société sur la même commande.

Il est recommandé d'activer le champ **Informations client** dans la commande fournisseur intersociétés. Cela permet de synchroniser la commande client originale avec la commande fournisseur intersociétés ainsi que la commande fournisseur intersociétés avec la commande client intersociétés.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
