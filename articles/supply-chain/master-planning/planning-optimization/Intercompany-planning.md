---
title: Planification intersociétés
description: Cet article décrit la planification intersociétés et explique comment configurer la planification intersociétés dans Microsoft Dynamics 365 Supply Chain Management.
author: t-benebo
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 3d1c82aa3810b37b06b9d9157e73588fc1727348
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740030"
---
# <a name="intercompany-planning"></a>Planification intersociétés

[!include [banner](../../includes/banner.md)]

Pour certaines organisations, les opérations logistiques dépendent d’autres entités juridiques (entreprises) de l’organisation. Ces opérations sont gérées en utilisant les ventes et les achats intersociétés, car chaque entité juridique dispose d’un plan comptable distinct.

Cet article décrit la planification intersociétés et explique comment configurer la planification intersociétés dans Microsoft Dynamics 365 Supply Chain Management.

Cet article utilise les termes intersociétés importants suivants :

- **En amont** – Une référence relative dans une entreprise ou une chaîne d’approvisionnement. Elle indique un mouvement dans la direction du fournisseur de matière première.
- **En aval** – Une référence relative dans une entreprise ou une chaîne d’approvisionnement. Elle indique un mouvement dans la direction du client.
- **Demande intersociétés planifiée** – Demande planifiée pour un produit dans une entreprise, basée sur la demande planifiée pour le produit d’une entreprise en aval.

Dans la planification, un plan dans une société peut inclure une demande intersociétés planifiée liée à des ordres planifiés d’un plan d’une autre société. Cette fonctionnalité est utile, car elle offre une visibilité complète sur les commandes planifiées dans toutes les entreprises. Elle garantit également que tous les ordres d’approvisionnement planifiés requis sont créés, mais sans exiger que les ordres planifiés soient confirmés pour la demande intersociétés.

Si vous exécutez la planification à partir d’un plan directeur qui inclut la demande planifiée en aval, les commandes fournisseur prévisionnelles des fournisseurs intersociétés associés seront incluses dans le plan en tant que demande.

## <a name="required-setup"></a>Paramétrage requis

Pour utiliser la planification intersociétés, vous devez préparer votre système de la manière suivante :

1. Les produits concernés doivent être commercialisés dans toutes les entreprises concernées. Pour plus d’informations, voir [Configurer et utiliser les transactions intersociétés dans Dynamics 365 Supply Chain Management](/training/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/).
1. La demande en aval doit être couverte par des achats auprès d’un fournisseur qui a une relation intersociétés avec la société en amont et les dimensions de stock par défaut pertinentes (site et entrepôt) sur le client. Pour plus d’informations, voir [Configurer et utiliser les transactions intersociétés dans Dynamics 365 Supply Chain Management](/training/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/).
1. Le plan directeur de l’entreprise en amont doit inclure la demande planifiée en aval, et l’entreprise et le plan directeur pertinents doivent être spécifiés dans les plans en aval.

## <a name="include-planned-downstream-demand"></a>Inclure la demande prévisionnelle intersociétés

Procédez comme suit pour configurer votre plan directeur afin qu’il inclue une prévision de la demande en aval.

1. Accédez à **Planification \> Paramétrage \> Plans \> Plans généraux**.
1. Sélectionnez ou créez un plan général.
1. Dans le raccourci **Planification intersociétés**, définissez les champs suivants :

    - **Inclure la demande en aval planifiée** – Réglez cette option sur *Oui* pour activer la planification intersociétés pour le plan directeur.
    - **Plans en aval** – Si vous définissez l’option **Inclure la demande en aval planifiée** sur *Oui*, utilisez la barre d’outils et la grille pour ajouter les plans directeurs souhaités d’autres entreprises.

## <a name="peg-across-companies-by-using-multilevel-pegging"></a>Choisissez entre les entreprises en utilisant l’origine des besoins à plusieurs niveaux

Dans l’origine des besoins à plusieurs niveaux, vous pouvez afficher l’origine des besoins entre les entreprises pour voir la source initiale de la demande qui est couverte par une approvisionnement.

Pour afficher les informations d’origine des besoins à plusieurs niveaux, procédez comme suit.

1. Accédez à **Planification \> Planification \> Ordres prévisionnels**.
1. Sélectionnez ou ouvrez un ordre prévisionnel.
1. Dans le volet Actions, sous l’onglet **Afficher**, dans le groupe **Besoins**, sélectionnez **Origine des besoins à plusieurs niveaux**.

### <a name="intercompany-example-that-involves-two-companies"></a>Exemple intersociétés impliquant deux entreprises

Pour cet exemple, un ordre de fabrication planifié est créé dans la société USMF pour couvrir une commande client dans la société DEMF. Dans USMF, la demande directe est la demande intersociétés planifiée. Pour faire apparaître cette demande dans USMF, la planification est d’abord exécutée dans DEMF, puis dans USMF.

L’illustration suivante montre comment cet exemple peut apparaître sur la page **Origine des besoins à plusieurs niveaux** pour l’ordre de fabrication planifié.

![Exemple intersociétés impliquant deux entreprises.](media/IntercompanyPlanning1.png)

### <a name="intercompany-example-that-involves-three-companies"></a>Exemple intersociétés impliquant trois entreprises

Pour cet exemple, une commande fournisseur prévisionnelle est créé dans la société USMF pour couvrir une commande client dans la société FRRT. Dans les sociétés DEMF et USMF, la demande directe est la demande intersociétés planifiée. Pour faire apparaître cette demande dans USMF, la planification est d’abord exécutée dans FRRT, puis dans DEMF et enfin dans ESMF.

L’illustration suivante montre comment cet exemple peut apparaître sur la page **Origine des besoins à plusieurs niveaux** pour l’ordre de fabrication planifié.

![Exemple intersociétés impliquant trois entreprises.](media/IntercompanyPlanning2.png)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
