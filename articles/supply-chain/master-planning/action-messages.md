---
title: Messages d’action
description: Un message d’action est une suggestion générée par le système visant à modifier un ordre prévisionnel ou confirmé existant.
author: ChristianRytt
ms.date: 10/14/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, MCRSalesOrderMessages, MCRSalesTableDetailedStatus, TAMItemVendRebateGroup, TAMVendRebate, TAMVendRebateAgreementLineInfoPart, TAMVendRebateGroup, TAMVendRebateTable, TAMVendRebateTrans, ReqTransActionListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19411
ms.assetid: 52b46d93-7d02-46b5-aad1-9fd08206bf9d
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ea565a8935151235e4c3b103dd86b7131711a4a2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816578"
---
# <a name="action-messages"></a>Messages d’action

[!include [banner](../includes/banner.md)]

Un message d’action est une suggestion générée par le système visant à modifier un ordre prévisionnel ou confirmé existant.

## <a name="introduction"></a>Introduction

Les messages d’action sont générés par le calcul de planification principal en réponse à la modification des demandes. Il est par exemple possible que la date d’expédition ou la quantité ait été modifié sur une commande client pour laquelle vous avez déjà créé une commande fournisseur pour honorer la demande. Dans ce cas, un ou plusieurs messages d’action sont générés par le calcul de planification principal pour mettre la commande fournisseur à jour. Vous devez décider d’apporter ou non les modifications suggérées.

Vous pouvez configurer le mode de calcul des messages d’action pour un groupe de couverture que vous liez à un article.

## <a name="select-action-messages"></a>Sélection des messages d’action

Sur la page **Groupes de couverture**, vous pouvez sélectionner les messages d’action que vous voulez que le système génère, et les groupes de couverture ou les articles auxquels les messages s’appliquent. Vous pouvez sélectionner les messages d’action suivants.

| Message             | Description                                                                                                                                                                                                                                              |
|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Avance**         | Si vous sélectionnez ce message, le système génèrera des messages d’action, si nécessaire, pour déplacer les commandes à une date plus rapprochée. Dans le champ **Marge d’avance**, vous pouvez également spécifier le nombre maximal de jours entre la réception et la sortie sans avance. |
| **Ajourner**        | Si vous sélectionnez ce message, le système génèrera les messages d’action, si nécessaire, pour déplacer les commandes à une date ultérieure. Dans le champ **Marge d’ajournement**, vous pouvez également spécifier le nombre maximal de jours entre la réception et la sortie sans ajournement.       |
| **Diminution**        | Si vous sélectionnez ce message, des commandes fournisseur et d’autres transactions de réception doivent être diminués afin d’éviter des dépassements de niveaux de stock.                                                                                                   |
| **Augmentation**        | Si vous sélectionnez ce message, des commandes fournisseur et d’autres transactions de réception doivent être augmentés afin d’éviter des ruptures de stock.                                                                                                    |
| **Actions déduites** | Si vous sélectionnez ce message, des messages d’action sont créés pour les besoins déduits, par exemple, les actions pour les commandes de composants accomplissant la production.                                                                                                   |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]