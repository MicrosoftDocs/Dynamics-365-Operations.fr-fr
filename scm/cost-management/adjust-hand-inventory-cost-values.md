---
title: "Ajustement des valeurs de coût du stock disponible"
description: "Utilisez la page Ajustement du stock disponible pour ajuster le coût des quantités de stock disponible une fois qu&quot;un processus de clôture de stock a été exécuté."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventAdjInventOnHand
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 53231
ms.assetid: bc1fde9f-5ad9-4339-8ae8-e2839b792eb2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: a62d8d453be096dda221415437e78c695f3e5cf7
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="adjust-on-hand-inventory-cost-values"></a>Ajustement des valeurs de coût du stock disponible

[!include[banner](../includes/banner.md)]


Utilisez la page Ajustement du stock disponible pour ajuster le coût des quantités de stock disponible une fois qu'un processus de clôture de stock a été exécuté.

Vous pouvez utiliser la page **Ajustement du stock disponible** pour ajuster le coût des quantités de stock disponible une fois qu'un processus de clôture de stock a été exécuté. **Remarque :** pour ouvrir la page **Ajustement du stock disponible**, dans la page **Clôture et ajustement**, sélectionnez l'enregistrement d'un processus de clôture de stock terminé, puis cliquez sur **Ajustement** &gt; **Disponible**. **Exemple :** les transactions suivantes ont lieu en février :

-   1er février : réception financière de stock d'une quantité de 2 au coût de 10,00 EUR ;
-   5 février : réception financière de stock d'une quantité de 1 au coût de 13,00 EUR ;
-   19 février : sortie financière de stock d'une quantité de 1 au coût moyen en cours de 11,00 EUR.

Cet article était paramétré avec le modèle de stock FIFO (premier entré, premier sorti) et la clôture de stock a commencé le 28 février. La transaction de sortie financière de 11,00 EUR sera réglée avec la réception financière datée du 1er février et un ajustement de 1,00 EUR sera effectué. Les réceptions en stock suivantes contiennent les quantités de stock en cours :

-   1 février : quantité de 1 à un coût de 10,00 EUR ;
-   5 février : quantité de 1 à un coût de 13,00 EUR.

Pour définir le coût de ces deux articles sur 15,00 EUR, utilisez l'option d'ajustement disponible et ajustez les quantités disponibles ouvertes à partir de la dernière période de clôture de stock. **Remarque :** la date de validation de la transaction d'ajustement disponible sera la date de la dernière clôture de stock. Cette date ne peut pas être modifiée.




