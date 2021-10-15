---
title: Conversions de devise intersociétés
description: Cette rubrique explique les conversions de devises pour les transactions intersociétés
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 540849003d532ef2f0905c18332d9cb82a04cf7c
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548272"
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
