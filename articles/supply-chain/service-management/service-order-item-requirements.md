---
title: Demandes d’articles de la commande de service
description: Cet article décrit les exigences relatives aux éléments de commande de service.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjSalesItemReq
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 376cda6bbe1800611e6f24c347b9035469a30a14
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015170"
---
# <a name="service-order-item-requirements"></a>Demandes d’articles de la commande de service

[!include [banner](../includes/banner.md)]

Vous pouvez créer une commande de service pour suivre et gérer les services que vous fournissez à vos clients. Si vous devez réserver des articles spécifiques pour une commande de service, vous pouvez créer des demandes d’article en stock pour celle-ci. Une demande d’article peut être immédiatement consommée du stock, ou elle peut lancer une commande fournisseur pour l’article.

En utilisant une demande d’article au lieu d’une transaction d’article, vous pouvez prévoir la livraison juste avant que l’article soit utilisé, créer une commande fournisseur, inclure l’article dans le cadre d’un accord commercial et inclure la demande d’article dans la planification de la production.

Les demandes d’articles pour les commandes de service sont traitées au travers d’un projet. Pour créer une demande d’article sur une commande de service, cette dernière doit être associée à un projet.

Dès qu’une demande d’article est créée pour une commande de service, elle peut être affichée à partir de **Projet** dans la commande de service individuelle ou via l’écran **Commande client**.

## <a name="view-an-item-requirement-from-a-service-order"></a>Affichage d’une demande d’article à partir d’une commande de service

1. Accédez à **Gestion des services** \> **Commandes de service**\> **Commandes de service**.
1. Sélectionnez **Répartir**, puis sélectionnez **Demande d’articles** pour ouvrir l’écran **Demandes d’articles**.
1. Sélectionnez l’onglet **Projet**, puis consultez le champ **Commande de service** pour voir les commandes de service pour la demande d’articles.

## <a name="delete-service-orders-with-item-requirements"></a>Suppression des commandes de service avec les demandes d’articles

Si une demande d’articles est créée sur une commande de service, vous ne pouvez pas supprimer la commande de service. Pour pouvoir supprimer la commande de service, vous devez supprimer la demande d’articles.

1. Accédez à **Gestion des services** \> **Commandes de service**\> **Commandes de service**.
1. Sélectionnez **Répartir**, puis sélectionnez **Demande d’articles** pour ouvrir l’écran **Demandes d’articles**. Cet écran affiche la liste des demandes d’articles qui sont créées sur la commande de service.
1. Sélectionnez la demande d’articles à supprimer, puis sélectionnez **Supprimer**.

- ou -

1. Accédez à **Gestion et comptabilité des projets** \> **Projets** \> **Tous les projets**.
1. Ouvrez le projet contenant la commande de service dans laquelle une demande d’articles est créée.
1. Dans l’écran **Projet**, dans le volet droit, sélectionnez **Demandes d’articles**. L’écran **Demandes d’articles** s’ouvre et affiche la liste des demandes d’article qui sont associées au projet sélectionné.
1. Sélectionnez la demande d’articles à supprimer, puis sélectionnez **Supprimer**.

## <a name="see-also"></a>Voir également :

[Demandes d’articles (écran)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))



[!INCLUDE[footer-include](../../includes/footer-banner.md)]