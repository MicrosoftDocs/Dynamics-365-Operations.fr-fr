---
title: Demandes d'articles dans une commande de service
description: Si vous devez réserver des articles spécifiques pour une commande de service, vous pouvez créer des demandes d'article en stock pour celle-ci.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjSalesItemReq
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3dc7c721af4b25e1586e546392518648110a3fb6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "327502"
---
# <a name="service-order-item-requirements"></a>Demandes d'articles dans une commande de service   

[!include [banner](../includes/banner.md)]


Vous pouvez créer une commande de service pour suivre et gérer les services que vous fournissez à vos clients. Si vous devez réserver des articles spécifiques pour une commande de service, vous pouvez créer des demandes d'article en stock pour celle-ci. Une demande d'article peut être immédiatement consommée du stock, ou elle peut lancer une commande fournisseur pour l'article.

En utilisant une demande d'article au lieu d'une transaction d'article, vous pouvez prévoir la livraison juste avant que l'article soit utilisé, créer une commande fournisseur, inclure l'article dans le cadre d'un accord commercial et inclure la demande d'article dans la planification de la production.

Les demandes d'articles pour les commandes de service sont traitées au travers d'un projet. Pour créer une demande d'article sur une commande de service, cette dernière doit être associée à un projet.

Dès qu'une demande d'article est créée pour une commande de service, elle peut être affichée à partir de **Projet** dans la commande de service individuelle ou via l'écran **Commande client**.

## <a name="view-an-item-requirement-from-a-service-order"></a>Affichage d'une demande d'article à partir d'une commande de service

1.  Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.

2.  Cliquez sur **Répartir**, puis sur **Demande d'articles** pour ouvrir l'écran **Demandes d'articles**.

3.  Cliquez sur l'onglet **Projet**, puis consultez le champ **Commande de service** pour voir les commandes de service pour la demande d'articles.

## <a name="delete-service-orders-with-item-requirements"></a>Suppression des commandes de service avec les demandes d'articles

Si une demande d'articles est créée sur une commande de service, vous ne pouvez pas supprimer la commande de service. Pour pouvoir supprimer la commande de service, vous devez supprimer la demande d'articles.

1.  Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.

2.  Cliquez sur **Répartir**, puis sur **Demande d'articles** pour ouvrir l'écran **Demandes d'articles**. Cet écran affiche la liste des demandes d'articles qui sont créées sur la commande de service.

3.  Sélectionnez la demande d'articles à supprimer, puis cliquez sur **Supprimer**.

- ou -

1.  Cliquez sur **Gestion et comptabilité des projets** \> **Commun** \> **Projets** \> **Tous les projets**.

2.  Ouvrez le projet contenant la commande de service dans laquelle une demande d'articles est créée.

3.  Dans l'écran **Projet**, dans le volet droit, cliquez sur **Demandes d'articles**. L'écran **Demandes d'articles** s'ouvre et affiche la liste des demandes d'article qui sont associées au projet sélectionné.

4.  Sélectionnez la demande d'articles à supprimer, puis cliquez sur **Supprimer**.

## <a name="see-also"></a>Voir également :

[Demandes d'articles (écran)](https://technet.microsoft.com/en-us/library/aa552021\(v=ax.60\))

