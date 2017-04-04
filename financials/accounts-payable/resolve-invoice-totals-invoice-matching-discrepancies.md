---
title: "Résolution des écarts lors du rapprochement des totaux de factures"
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 1fd606817b06a05b9abaaedf20ea9872bd7edd5d
ms.openlocfilehash: a54b05bba2549a42f24b8425c9ee418c576d056a
ms.lasthandoff: 03/31/2017


---

# <a name="resolve-discrepancies-during-invoice-totals-matching"></a>Résolution des écarts lors du rapprochement des totaux de factures



Un type de validation du rapprochement de factures est le rapprochement des totaux de facture. Pour spécifier que le système doit effectuer le rapprochement des totaux de facture, sur la page **Paramètres de la comptabilité fournisseur**, sous l'onglet **Contrôle de la facture**, définissez l'option **Mettre en correspondance les totaux de la facture** à **Oui**. 

Vous pouvez utiliser le rapprochement des totaux de facture pour vous assurer que l'écart entre les montants totaux de la facture et les montants attendus n'est pas supérieur à l'écart acceptable. Six totaux sont comparés sur la page **Détails de rapprochement de factures totales**. Si l'un de ces totaux dévie du total correspondant prévu de la commande fournisseur, un écart de rapprochement est signalé. 

Pour réviser la facture qui comporte les écarts de rapprochement des totaux, dans l'espace de travail **Saisie de facture fournisseur**, cliquez sur la vignette **Factures en attente**. Ensuite, dans le volet Actions, sous l'onglet **Revoir**, cliquez sur **Mise en correspondance des détails**.. Si des écarts de rapprochement ont été détectés, des icônes d'avertissement s'affichent en regard du montant de la facture. Vous pouvez afficher plus de détails sur les totaux en affichant les détails de rapprochement des totaux de facture. 

Après avoir identifié un écart, vous devrez peut-être prendre contact avec votre fournisseur si vous pensez que les informations de la facture sont erronées. Selon l'accord trouvé avec votre fournisseur, vous pouvez alors effectuer l'une des opérations suivantes :

-   Accepter la différence de prix et valider la facture avec les écarts de rapprochement. Votre système peut être paramétré pour exiger l'approbation avant d'être en mesure de valider s'il existe des écarts de rapprochement. Dans ce cas, vous devez approuver l'écart de rapprochement et vous pouvez également saisir un commentaire d'approbation. Vous pouvez alors décider de valider la facture.
-   Corriger le montant de la facture et valider cette dernière.
-   Demander au fournisseur un crédit total et une nouvelle facture corrigée.



