---
title: Vue d'ensemble du workflow de l'abonnement
description: Cette rubrique fournit une vue d'ensemble du workflow de l'abonnement.
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionGroup, SMASubscriptionCreateDialog
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b5cff6910dcb273fc081443546676426387f6625
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566408"
---
# <a name="subscription-workflow-overview"></a>Vue d'ensemble du workflow de l'abonnement 

[!include [banner](../includes/banner.md)]


Vous êtes l'administrateur des abonnements pour une société d'éclairage qui offre des abonnements pour la maintenance de rails de projecteurs. Un client contacte votre société pour acheter un abonnement annuel pour la maintenance de rails de projecteurs.

## <a name="setting-up-subscriptions"></a>Paramétrage des abonnements

Pour paramétrer un abonnement, vous devez tout d'abord créer un groupe d'abonnements pour le nouvel accord de service ou vérifier qu'un groupe d'abonnements existe. Si un groupe d'abonnements existe, vous devez le paramétrer pour envoyer une facture annuelle au client et régulariser le produit des ventes chaque mois de l'année. Pour plus d'informations sur la procédure de paramétrage des abonnements, voir [Paramétrer des groupes d'abonnements](set-up-subscription-groups.md).

Après la création du groupe d'abonnements, vous pouvez créer l'abonnement. Pour plus d'informations sur la création de services récurrents, voir [Création des services récurrents à partir d'un groupe d'abonnements](create-service-subscriptions-from-subscription-group.md).

## <a name="create-and-modify-subscription-transactions"></a>Création et modification de transactions d'abonnement

Après avoir paramétré l'abonnement, vous créez la transaction de frais d'abonnement pour la première période de facturation, à savoir un an. Les transactions sont du type **Normal**. Par conséquent, vous pouvez uniquement créer des transactions d'abonnement dans lesquelles les dates de début et de fin correspondent aux périodes créées précédemment dans l'écran **Types de période**. Pour plus d'informations les transactions de frais, voir [Créer des transactions de redevance](create-subscription-fee-transactions.md).

Après avoir paramétré l'abonnement pour votre client, vous vous rappelez que celui-ci a négocié une remise de 10 % sur tous les prix de la liste des offres de service. Ainsi, vous devez réduire le prix des frais de transaction que vous avez créés.

Plus tard le même jour, votre contact client vous appelle pour dire que, bien que son employeur souhaite toujours l'accord de service pour le rail de projecteurs, il prévoit d'acquérir un nouveau rail de projecteurs au cours de l'année. Il demande donc une maintenance uniquement jusqu'en octobre 2013. Pour réduire le nombre de mois pour l'abonnement souscrit par le client, vous créez une nouvelle transaction de frais d'abonnement de type **Jours de réduction**. Pour plus d'informations sur la réduction des jours, voir [Réduction des jours sur les frais d'abonnement](reduce-the-days-on-subscription-fees.md).

## <a name="invoice-and-accrue-subscription-transactions"></a>Facturation et provisionnement de transactions d'abonnement

Vous avez terminé de paramétrer l'abonnement et vous êtes prêt à envoyer la facture à votre client pour cet abonnement. Pour plus d'informations sur la facturation d'abonnements, voir [Facturation de transactions d'abonnement](invoice-subscription-transactions.md).

Deux jours plus tard, votre client appelle pour dire que l'abonnement doit être facturé en dollars US et non en euros. Vous créez donc un avoir et une transaction d'abonnement libellée dans la devise correcte. Pour plus d'informations sur le crédit des transactions d'abonnements, voir [Crédit de transactions d'abonnement](credit-subscription-transactions.md).

À la fin de chaque mois, vous provisionnez le produit d'un mois de l'abonnement du client sur le compte de résultat et sur les comptes des travaux en cours. Pour plus d'informations sur le produit à recevoir pour les abonnements, voir [Provisionner le produit d'abonnement](accrue-subscription-revenue.md).

  


