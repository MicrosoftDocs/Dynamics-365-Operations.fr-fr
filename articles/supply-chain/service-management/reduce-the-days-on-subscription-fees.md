---
title: Réduction des jours sur les frais d’abonnement
description: Pour réduire le nombre de jours de frais d’abonnement existants, vous pouvez créer une transaction dans laquelle vous supprimez la période qui ne doit plus faire partie de l’intervalle des frais d’abonnement.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df1a27576b93c4ace4a5f17271595d259e96a51a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573223"
---
# <a name="reduce-the-days-on-subscription-fees"></a>Réduction des jours sur les frais d’abonnement 

[!include [banner](../includes/banner.md)]


Pour réduire le nombre de jours de frais d’abonnement existants, vous pouvez créer une transaction dans laquelle vous supprimez la période qui ne doit plus faire partie de l’intervalle des frais d’abonnement.

## <a name="reduce-the-days-on-a-subscription-fee"></a>Réduction des jours sur les frais d’abonnement

1.  Cliquez sur **Gestion des services** \> **Commun** \> **Services récurrents** \> **Tous les abonnements aux services**. Sélectionnez le service récurrent, puis dans le volet Actions, cliquez sur **Frais d’abonnement**

2.  Dans le champ **Type d’abonnement**, sélectionnez **Jours de réduction**.

3.  Utilisez les champs **Date de début** et **Date de fin** pour définir l’intervalle de dates des frais d’abonnement que vous souhaitez supprimer de la période des frais d’abonnement, puis cliquez sur **OK**.

Pour afficher la transaction qui a été créée, dans l’écran **Abonnement**, cliquez sur **Transactions de frais**.

## <a name="example"></a>Exemple

Si une période de transaction d’abonnement court du 1er au 31 janvier et que vous souhaitez réduire la période de 10 jours, créez une transaction dans laquelle la période de réduction court du 1er au 10 janvier. (La période de réduction peut également courir du 5 au 15 janvier, ou toute autre période de dix jours).

De la même manière, si la **Date de début** de la période de réduction est le 21 janvier (31 moins 10), vous pouvez définir la **Date de fin** sur une date ultérieure au 31 janvier et 10 jours seront tout de même enlevés de la période des frais d’abonnement.

## <a name="see-also"></a>Voir également :

[Exemple de jours de réduction](reduction-days-example.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]