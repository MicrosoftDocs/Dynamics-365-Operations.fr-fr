---
title: Restreindre les modes de paiement pour les retours sans reçu
description: Cet article décrit comment la procédure de certains types de paiements peut être limitée en matière de remboursement si les retours sont effectués sans reçu.
author: rapraj
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2019-02-01
ms.dyn365.ops.version: AX 10.0.0, Retail Feb 2019 update
ms.openlocfilehash: 091d39ea9fe41d78b7f34f85ecd1894047e022d6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896951"
---
# <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Restreindre les modes de paiement pour les retours sans reçu


[!include [banner](includes/banner.md)]

Chaque type de paiement accepté par un détaillant doit être configurée lors du paramétrage du système. Cet article décrit comment la procédure de certains types de paiements peut être limitée en matière de remboursement si les retours sont effectués sans reçu.

## <a name="set-up-payment-methods"></a>paramétrer les modes de paiement ;

Pour paramétrer les modes de paiement, vous devez effectuer les tâches suivantes.
1. Créer les modes de paiement acceptés par l’ensemble de l’organisation.
2. Création de types et de numéros de cartes pour l’organisation. Si les cartes de crédit ou de débit sont acceptées, vous devez créer un mode de paiement par carte, puis créer les types et numéros de cartes pour toute l’organisation.
3. Paramétrer les modes de paiement du magasin. Associez les modes de paiement à chaque magasin, puis entrez les paramètres propres au magasin pour chaque mode de paiement de ce dernier.
4. Paramétrer les modes de paiement par carte pour les magasins. Vous devez paramétrer la carte pour tous les modes de paiement par carte acceptés par le magasin.

![Paramétrage du magasin.](media/NoReceiptReturns1.png "Paramétrage du magasin de vente au détail") 


## <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Restreindre les modes de paiement pour les retours sans reçu

Pour chaque mode de paiement du magasin, dans la page **Gestion du magasin**, sous **Retours sans reçu**, définissez **Limite pour les remboursements sans reçu** sur **Oui**. 

La valeur par défaut du bouton d’activation/de désactivation est **Non**, ce qui garantit que le mode de paiement est autorisé pour les remboursements. 

Lorsque **Limitation des remboursements sans réception** est défini sur **Activé**, le mode de paiement sélectionné ne sera pas autorisé pour les remboursements. 

![Mode de paiement du magasin.](media/NoReceiptReturns3.png "Mode de paiement du magasin de vente au détail") 

> [!NOTE]
> Quand un agent de caisse sélectionne un mode de paiement limité au remboursement sans reçu, un message s’affiche pour vérifier les modes de paiement acceptables.

![Modes de paiement acceptables.](media/NoReceiptReturns4.png "Modes de paiement acceptables") 

Si une transaction a à la fois un retour avec reçu et un retour sans reçu, les conditions de restriction ne seront pas appliquées, car la transaction est un workflow de retour avec reçu. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]