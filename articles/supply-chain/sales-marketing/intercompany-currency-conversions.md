---
title: Conversions de devise intersociétés
description: Cet article explique les conversions de devises pour les transactions intersociétés
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
ms.openlocfilehash: 41bfafc0dcb3bd356931b67dc63b717c0d098116
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851476"
---
# <a name="intercompany-currency-conversions"></a>Conversions de devise intersociétés

[!include [banner](../../includes/banner.md)]

Lorsque le code devise de la commande client d'origine et de la commande fournisseur intersociétés diffèrent, la devise des champs suivants est convertie si la synchronisation est activée :

- **Prix unitaire**
- **Frais de vente** ou **Frais sur achats**
- **Remise**
- **Remise multiligne**

Ces champs sont ensuite synchronisés avec la ligne de commande client intersociétés d'origine.

Toutefois, comme la devise de la commande fournisseur intersociétés et de la commande client intersociétés est toujours synchronisée, les champs suivants sont synchronisés sans conversion de devise :

- **Prix unitaire**
- **Frais de vente** ou **Frais sur achats**
- **Remise**
- **Pourcentage de remise**
- **Remise multiligne**
- **Pourcentage de remise multiligne**

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
