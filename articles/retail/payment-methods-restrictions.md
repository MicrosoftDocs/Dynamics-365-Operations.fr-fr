---
title: Restreindre les modes de paiement pour les retours sans reçu
description: Cette rubrique décrit comment la procédure de certains types de paiements peut être limitée en matière de remboursement si les retours sont effectués sans reçu.
author: rapraj
manager: AnnBe
ms.date: 01/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2019-02-01
ms.dyn365.ops.version: AX 10.0.0, Retail Feb 2019 update
ms.openlocfilehash: 1f84a6382453c0ba7540e618ad90ae1d3c684a2b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "315910"
---
# <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Restreindre les modes de paiement pour les retours sans reçu

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Chaque type de paiement accepté par un détaillant doit être configurée lors du paramétrage du système. Cette rubrique décrit comment la procédure de certains types de paiements peut être limitée en matière de remboursement si les retours sont effectués sans reçu.

## <a name="set-up-payment-methods"></a>paramétrer les modes de paiement ;

Pour paramétrer les modes de paiement, vous devez effectuer les tâches suivantes.
1. Créer les modes de paiement acceptés par l'ensemble de l'organisation.
2. Création de types et de numéros de cartes pour l'organisation. Si les cartes de crédit ou de débit sont acceptées, vous devez créer un mode de paiement par carte, puis créer les types et numéros de cartes pour toute l'organisation.
3. Paramétrer les modes de paiement du magasin. Associez les modes de paiement à chaque magasin, puis entrez les paramètres propres au magasin pour chaque mode de paiement de ce dernier.
4. Paramétrer les modes de paiement par carte pour les magasins. Vous devez paramétrer la carte pour tous les modes de paiement par carte acceptés par le magasin.

![Paramétrage du magasin de vente au détail](media/NoReceiptReturns1.png "Paramétrage du magasin de vente au détail") 


## <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Restreindre les modes de paiement pour les retours sans reçu

Pour chaque mode de paiement de magasin, dans la page **Gestion du magasin de vente au détail**, sous **Retours sans reçu**, définissez **Limite pour les remboursements sans reçu** sur **Oui**. 

La valeur par défaut du bouton d'activation/de désactivation est **Non**, ce qui garantit que le mode de paiement est autorisé pour les remboursements. 

Lorsque **Limitation des remboursements sans réception** est défini sur **Activé**, le mode de paiement sélectionné ne sera pas autorisé pour les remboursements. 

![Mode de paiement magasin de vente au détail](media/NoReceiptReturns3.png "Mode de paiement magasin de vente au détail") 

> [!NOTE]
> Quand un agent de caisse sélectionne un mode de paiement limité au remboursement sans reçu, un message s'affiche pour vérifier les modes de paiement acceptables.

![Modes de paiement acceptables](media/NoReceiptReturns4.png "Modes de paiement acceptables") 

Si une transaction a à la fois un retour avec reçu et un retour sans reçu, les conditions de restriction ne seront pas appliquées, car la transaction est un workflow de retour avec reçu. 
