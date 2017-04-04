---
title: Espace de travail de facturation de collaboration fournisseur
description: Cette rubrique explique comment afficher des factures fournisseur et envoyer des factures depuis l&quot;espace de travail de facturation de collaboration fournisseur.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 221534
ms.assetid: c4ed62f3-d351-41d7-a2ad-790576cde4ab
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: afa59439e06aad9d669eb352a9837a013f447249
ms.openlocfilehash: 822e621f22f8af63b2a827dcc50a6b0ac68d3e21
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-collaboration-invoicing-workspace"></a>Espace de travail de facturation de collaboration fournisseur

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

Dans la section **Listes tabulaires**, le statut de la facturation est réparti de manière similaire aux vignettes de synthèse : listes Brouillon et Envoyées, non approuvées. Tandis que dans l'état Brouillon, une facture peut être envoyée au workflow ou être supprimée. Dernière liste sous forme de tableau est une option de rechercher des factures. Vous pouvez filtrer comme vous recherche, pour autoriser les recherches plus rapides.
Page de liste Toutes les factures fournisseur
-----------------------------

Vous pouvez afficher toutes les factures fournisseur validées et non validés sur ** des factures de collaboration de fournisseur ** la page de liste. Vous pouvez utiliser cette page de liste pour afficher le statut du paiement des factures. Les statuts de règlement incluent Non validée, Impayée, Partiellement payée, et totalement payée.
Création d'une facture à partir d'une commande fournisseur
--------------------------------------------

Vous pouvez créer une nouvelle facture fournisseur en sélectionnant l'action **Nouveau** sous l'espace de travail de **facturation de collaboration fournisseur**. Le numéro de commande fournisseur et le numéro de facture doivent être fournis par le fournisseur. Par défaut, toutes les lignes de la commande du fournisseur s'afficheront sur la nouvelle facture. Les informations sur la quantité et le coût peuvent être modifiées avant d'envoyer la facture fournisseur au workflow. Vous pouvez joindre des fichiers, des notes, des images, et des URL à une facture avant de l'envoyer.



Pour plus d'informations, voir [collaborant avec des fournisseurs via le portail fournisseur] (/dynamics365/operations/scm/procurement/collaborate-vendors-vendor-portal)


