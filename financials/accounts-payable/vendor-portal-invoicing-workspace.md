---
title: Espace de travail de facturation de collaboration fournisseur
description: Cette rubrique explique comment afficher des factures fournisseur et envoyer des factures depuis l&quot;espace de travail de facturation de collaboration fournisseur.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 221534
ms.assetid: c4ed62f3-d351-41d7-a2ad-790576cde4ab
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7c8fe2fea08dbad625cd373ca316135ac4e29e13
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="vendor-collaboration-invoicing-workspace"></a>Espace de travail de facturation de collaboration fournisseur

[!include[banner](../includes/banner.md)]


Cette rubrique explique comment afficher des factures fournisseur et envoyer des factures depuis l'espace de travail de facturation de collaboration fournisseur.

L'espace de travail de **facturation de collaboration fournisseur** permet d'afficher les informations de facture fournisseur et d'envoyer des factures à Microsoft Dynamics 365 for Operations à l'aide des fonctionnalités de workflow.
Espace de travail de facturation de collaboration fournisseur
----------------------------------------

### <a name="summary-tiles"></a>Vignettes récapitulatives

Les vignettes **Synthèse** fournissent une vue d'ensemble des factures du fournisseur sélectionné. Vous pouvez afficher les factures selon leur état.
-   Les brouillons de factures n'ont pas été envoyés au workflow.
-   Les factures soumises et non approuvées sont les factures que le fournisseur a envoyé, mais qui n'ont pas été validées dans Dynamics 365 for Operations.
-   Les factures approuvées et non réglées sont celles qui ont été validées dans Dynamics 365 for Operations, mais qui n'ont pas été entièrement réglées.
-   Les factures payées sont celles qui ont été complètement réglées dans Dynamics 365 for Operations.

Cliquez sur une vignette pour ouvrir une vue filtrée de la page **Liste des factures**.
### <a name="tabular-lists"></a>Listes tabulaires

Dans la section **Listes tabulaires**, le statut de la facturation est réparti de manière similaire aux vignettes de synthèse : listes Brouillon et Envoyées, non approuvées. Tandis que dans l'état Brouillon, une facture peut être envoyée au workflow ou être supprimée. La dernière liste tabulaire est un moyen de rechercher des factures. Vous pouvez définir les filtres au fil de la recherche, afin d'accélérer celle-ci.
Page de liste Toutes les factures fournisseur
-----------------------------

Vous pouvez afficher toutes les factures fournisseurs validées ou non validées dans la page de liste **Factures de la collaboration du fournisseur**. Vous pouvez utiliser cette page de liste pour afficher le statut de paiement des factures. Les statuts de règlement incluent Non validée, Impayée, Partiellement payée, et totalement payée.
Création d'une facture à partir d'une commande fournisseur
--------------------------------------------

Vous pouvez créer une nouvelle facture fournisseur en sélectionnant l'action **Nouveau** sous l'espace de travail de **facturation de collaboration fournisseur**. Le numéro de commande fournisseur et le numéro de facture doivent être fournis par le fournisseur. Par défaut, toutes les lignes de la commande du fournisseur s'afficheront sur la nouvelle facture. Les informations sur la quantité et le coût peuvent être modifiées avant d'envoyer la facture fournisseur au workflow. Vous pouvez joindre des fichiers, des notes, des images, et des URL à une facture avant de l'envoyer.



Pour plus d'informations, voir [Collaborer avec des fournisseurs à l'aide du portail Fournisseur](/dynamics365/operations/supply-chain/procurement/collaborate-vendors-vendor-portal)




