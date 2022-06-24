---
title: Créer des demandes d’articles pour des commandes de service
description: Cet article explique comment créer des exigences d'article pour les commandes de service.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5c2c90ff76121b436d0fec532268cd3383de0eab
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888410"
---
# <a name="create-item-requirements-for-service-orders"></a>Créer des demandes d’articles pour des commandes de service

[!include [banner](../includes/banner.md)]

Vous pouvez créer une commande de service pour suivre et gérer les services que vous fournissez à vos clients. Si vous devez réserver des articles spécifiques pour une commande de service, vous pouvez créer des demandes d’article en stock pour celle-ci. Une demande d’article peut être immédiatement consommée du stock, ou elle peut lancer une commande fournisseur pour l’article.

En utilisant une demande d’article au lieu d’une transaction d’article, vous pouvez prévoir la livraison juste avant que l’article soit utilisé, créer une commande fournisseur, inclure l’article dans le cadre d’un accord commercial et inclure la demande d’article dans la planification de la production.

Les demandes d’articles pour les commandes de service sont traitées au travers d’un projet. Pour créer une demande d’articles sur une commande de service, cette dernière doit être associée à un projet. Après avoir créé une demande d’articles pour une commande de service, vous pouvez afficher la demande d’articles dans l’écran **Projets** du projet sélectionné.

## <a name="create-an-item-requirement-for-a-service-order"></a>Création d’une demande d’articles pour une commande de service

1. Accédez à **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.
1. Sélectionnez la commande de service que vous souhaitez créer pour la demande d’articles.
1. Dans le volet **Actions**, sous l’onglet **Répartir**, sélectionnez **Demande d’articles**.
1. Dans l’écran **Demande d’articles**, entrez les informations pour l’article requis. Pour plus d’informations sur les champs spécifiques, voir [Demande d’articles (écran)](https://technet.microsoft.com/library/aa552021\(v=ax.60\)).

## <a name="create-an-item-requirement-for-a-service-agreement"></a>Création d’une demande d’articles pour un accord de service

1. Accédez à **Gestion des services** \> **Commun** \> **Accords de service** \> **Accords de service**.
1. Ouvrez l’accord de service pour lequel vous souhaitez créer une demande d’articles.
1. Dans l’organisateur **Lignes**, sélectionnez **Ajouter** pour créer une ligne.
1. Dans le champ **Type de transaction**, sélectionnez **Article**.
1. Dans le champ **Paramétrage de l’article**, sélectionnez **Demande d’articles**.
1. Dans le champ **Numéro d’article**, sélectionnez l’article requis pour l’accord de service.
1. Dans l’organisateur **Détails de ligne**, sous l’onglet **Dimensions de produit**, dans le champ **Site**, sélectionnez le site de stock pour l’article.
1. Pour créer une commande de service à partir de la ligne d’accord, dans l’organisateur **Lignes**, sélectionnez **Créer des commandes de service**, puis entrez les informations appropriées dans l’écran **Créer des commandes de service**.

## <a name="see-also"></a>Voir également :

[Création de commandes de service automatiquement](create-service-orders-automatically.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
