---
title: "Accords fournisseur Payer quand payé"
description: "Cet article décrit les conditions Payer au paiement des accords fournisseur. Les conditions Payer au paiement vous permettent de retenir un paiement partiellement ou complètement pour un fournisseur jusqu&quot;à ce que le client du projet vous paie. Cet article fournit également un exemple concret pour vous montrer comment utiliser les conditions Payer au paiement dans un projet."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ProjProjectsListPage
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23131
ms.assetid: 20bf1d7f-8813-4c69-9cd7-576884a7e169
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: ff4e31434da0fa200cc1c563fb53c8650a643443
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="pay-when-paid-vendor-agreements"></a>Accords fournisseur Payer quand payé

[!include[banner](../includes/banner.md)]


Cet article décrit les conditions Payer au paiement des accords fournisseur. Les conditions Payer au paiement vous permettent de retenir un paiement partiellement ou complètement pour un fournisseur jusqu'à ce que le client du projet vous paie. Cet article fournit également un exemple concret pour vous montrer comment utiliser les conditions Payer au paiement dans un projet.

Lorsque vous approuvez l'utilisation d'un fournisseur comme sous-traitant pour travailler sur un projet, vous pouvez différer le paiement au fournisseur ou sous-traitant jusqu'à ce que vous receviez le paiement de votre client pour le projet en question. Pour différer un paiement à un fournisseur, il convient de définir la clause Payer quand payé lorsque vous paramétrez la commande fournisseur avec le fournisseur. Lorsque vous créez une commande fournisseur pour le fournisseur et que vous affectez un ID projet à la commande fournisseur, les termes de la clause Payer quand payé du projet sont associés à la commande fournisseur et au fournisseur. Sur la page **Factures fournisseur avec payer quand payé**, vous pouvez afficher une liste des factures fournisseur impayées pour la commande fournisseur et les factures client associées. Cet écran permet de déterminer s'il convient de payer un fournisseur, ainsi que le montant à payer. Par exemple, lorsqu'un client paie un montant d'une facture du projet, vous pouvez libérer le paiement d'une partie ou la totalité des factures fournisseur associées. Vous pouvez paramétrer des conditions Payer quand payé pour spécifier qu'un fournisseur est payé après que vous avez reçu un pourcentage spécifique du paiement du client. Lorsque vous recevez un paiement partiel d'un client, vous pouvez déclencher manuellement le paiement de certaines des factures fournisseur associées. L'exemple suivant montre comment utiliser la clause Payer quand payé pour différer le paiement d'un fournisseur ou sous-traitant jusqu'à ce que le client vous paie. Votre organisation conclut un accord avec un client pour la fourniture de 100 ordinateurs sur lesquels vous installez des logiciels demandés par le client. Le prix convenu pour chaque ordinateur est de 150,00 euros pièce. Vous faites appel à un fournisseur tiers pour vous fournir les ordinateurs. Le client souhaite approuver la qualité des ordinateurs avant de payer votre organisation. La stratégie de votre organisation est de retenir le paiement à un fournisseur tiers jusqu'à ce que vous ayez été payé par le client pour un projet. Par conséquent, vous paramétrez le projet avec un pourcentage de Payer quand payé de 100 %, de sorte que vous différez tous les paiements au fournisseur tant que vous n'avez pas reçu le paiement intégral pour la facture client. Le fournisseur facture 100,00 euros pour chaque ordinateur. Lorsque le fournisseur vous envoie les ordinateurs, l'expédition comporte une facture de 10 000 euros pour les 100 ordinateurs. Étant donné que vous avez paramétré la clause Payer quand payé pour le projet, vous ne payez pas le fournisseur immédiatement. Après avoir reçu les ordinateurs du fournisseur, vous installez les logiciels requis. Lorsque vous envoyez les ordinateurs au client, vous lui envoyé une facture de 15 000 euros. Le client inspecte les ordinateurs et approuve la qualité du produit. Le client paie alors à votre organisation le montant complet de la facture du projet. Après avoir reçu le paiement intégral du client, vous payez la somme de 10 000 euros au fournisseur, soit le montant total de la facture fournisseur.




