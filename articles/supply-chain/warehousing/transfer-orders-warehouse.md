---
title: Paramétrage des entrepôts pour les ordres de transfert
description: Cet article décrit la procédure de paramétrage des entrepôts pour les ordres de transfert.
author: Mirzaab
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation,CustVendTransportPoint2Point
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 984f90343805d35833b7ddd1a175af5833c23dd5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905513"
---
# <a name="set-up-warehouses-for-transfer-orders"></a>Paramétrage des entrepôts pour les ordres de transfert 

[!include [banner](../includes/banner.md)]

Les niveaux d’entrepôt permettent de créer une hiérarchie prenant en charge les ordres de transfert entre entrepôts. À partir de ce paramétrage, le calcul PDP/MRP calcule les demandes d’articles au niveau d’entrepôt individuel et génère des ordres de transfert prévisionnels à partir d’un entrepôt source affecté pour les exécuter.

1.  Cliquez sur **Gestion des stocks > Paramétrage > Décomposition du stock > Entrepôts**.

2.  Sélectionnez l’entrepôt à recharger.

3.  Dans l’organisateur **Planification**, activez la case à cocher **Rechargement**.

4.  Dans le champ **Entrepôt principal**, sélectionnez l’entrepôt à désigner comme entrepôt source du rechargement. Le PDP/MRP calcule une demande de transfert pour l’entrepôt sélectionné et génère un ordre de transfert prévisionnel à partir de l’**Entrepôt principal** assigné.
   
    > [!NOTE]
    > <P>Si vous ne cochez pas la case <STRONG>Rechargement</STRONG>, l’entrepôt sélectionné se voit attribuer un niveau d’entrepôt lié à <STRONG>Entrepôt principal</STRONG>, mais <STRONG>Entrepôt principal</STRONG> n’est pas paramétré comme entrepôt de rechargement.</P>

5.  Fermez la page pour appliquer le nouveau paramétrage.


> [!TIP]
> <P>Si vous souhaitez désigner un entrepôt pour le rechargement, vous devez commencer par définir l’entrepôt comme une dimension de stock sur la page <STRONG>Groupes de dimension de stockage</STRONG>. Sur cette page, sélectionnez le champ <STRONG>Actif</STRONG> et le champ <STRONG>Plan de couverture par dimension</STRONG> pour l’entrepôt.</P>

## <a name="set-up-transport-lead-time"></a>Paramétrer le délai de transport

Vous devez également paramétrer le délai de transport entre les entrepôts sur la page **Jours de transport**. 
1. Accédez à **Gestion des stocks > Paramétrage > Distribution > Jours de transport**.
2. Dans le champ **Point de réception**, sélectionnez **Entrepôt**.
3. Sélectionnez **Entrepôt d’expédition**, **Entrepôt de réception** et **Jours de transport**. 
4. (En option) Vous pouvez également définir la durée de transport, en fonction du mode de livraison, sous l’onglet **Jours de transport par mode de livraison**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]