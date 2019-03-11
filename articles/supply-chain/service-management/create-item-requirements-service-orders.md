---
title: Création d'une demande d'articles à partir d'une commande de service
description: Si vous devez réserver des articles spécifiques pour une commande de service, vous pouvez créer des demandes d'article en stock pour celle-ci.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a5a730ae945af15c7bd4020c734bac971d8186e2
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "312207"
---
# <a name="create-item-requirements-for-service-orders"></a>Création d'une demande d'articles à partir d'une commande de service 

[!include [banner](../includes/banner.md)]


Vous pouvez créer une commande de service pour suivre et gérer les services que vous fournissez à vos clients. Si vous devez réserver des articles spécifiques pour une commande de service, vous pouvez créer des demandes d'article en stock pour celle-ci. Une demande d'article peut être immédiatement consommée du stock, ou elle peut lancer une commande fournisseur pour l'article.

En utilisant une demande d'article au lieu d'une transaction d'article, vous pouvez prévoir la livraison juste avant que l'article soit utilisé, créer une commande fournisseur, inclure l'article dans le cadre d'un accord commercial et inclure la demande d'article dans la planification de la production.

Les demandes d'articles pour les commandes de service sont traitées au travers d'un projet. Pour créer une demande d'articles sur une commande de service, cette dernière doit être associée à un projet. Après avoir créé une demande d'articles pour une commande de service, vous pouvez afficher la demande d'articles dans l'écran **Projets** du projet sélectionné.

## <a name="create-an-item-requirement-for-a-service-order"></a>Création d'une demande d'articles pour une commande de service

1.  Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.

2.  Sélectionnez la commande de service que vous souhaitez créer pour la demande d'articles.

3.  Dans le volet **Actions**, sous l'onglet **Dispatch**, cliquez sur **Demande d'articles**.

4.  Dans l'écran **Demande d'articles**, entrez les informations pour l'article requis. Pour plus d'informations sur les champs spécifiques, voir [Demande d'articles (écran)](https://technet.microsoft.com/en-us/library/aa552021\(v=ax.60\)).

## <a name="create-an-item-requirement-for-a-service-agreement"></a>Création d'une demande d'articles pour un accord de service

1.  Cliquez sur **Gestion des services** \> **Commun** \> **Accords de service** \> **Accords de service**.

2.  Ouvrez l'accord de service pour lequel vous souhaitez créer une demande d'articles.

3.  Dans l'organisateur **Lignes**, cliquez sur **Ajouter** pour créer une ligne.

4.  Dans le champ **Type de transaction**, sélectionnez **Article**.

5.  Dans le champ **Paramétrage de l'article**, sélectionnez **Demande d'articles**.

6.  Dans le champ **Numéro d'article**, sélectionnez l'article requis pour l'accord de service.

7.  Dans l'organisateur **Détails de ligne**, sous l'onglet **Dimensions de produit**, dans le champ **Site**, sélectionnez le site de stock pour l'article.

8.  Pour créer une commande de service à partir de la ligne d'accord, dans l'organisateur **Lignes**, cliquez sur **Créer des commandes de service**, puis entrez les informations appropriées dans l'écran **Créer des commandes de service**. 


## <a name="see-also"></a>Voir également :

[Création de commandes de service automatiquement](create-service-orders-automatically.md).

  


