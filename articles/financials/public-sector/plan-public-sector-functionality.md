---
title: Planifier pour la fonctionnalité Secteur public
description: Cet article suggère les premières étapes pour paramétrer la fonctionnalité Secteur public dans Microsoft Dynamics 365 for Finance and Operations.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysConfiguration
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 19851
ms.assetid: 877eabf3-19c7-4897-b33e-c5a8a319cb35
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 84b7bdb8a95ec1491824cecf187894d70087c543
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550254"
---
# <a name="plan-for-public-sector-functionality"></a>Planification de la fonctionnalité Secteur public

[!include [banner](../includes/banner.md)]

Cet article suggère les premières étapes pour paramétrer la fonctionnalité Secteur public dans Microsoft Dynamics 365 for Finance and Operations.

<a name="what-should-i-do-first"></a>Que dois-je faire en premier lieu ?
-----------------------

Avant de commencer à ajuster les paramètres et à entrer vos données, vous devez prendre en compte les modules Finance and Operations que vous devez paramétrer pour votre organisation du secteur public. La fonctionnalité Secteur public est intégrée aux modules Finance and Operations et produits Microsoft suivants :

### <a name="accounts-payable"></a>Module Comptabilité fournisseur

page de garde de l'état de paiement générer Montants des lignes de commande fournisseur

### <a name="accounts-receivable"></a>Module Comptabilité client

Classification de facturation Champs personnalisés de code personnalisé de facturation Codes de facturation Champs personnalisés de facture financière Lignes d'intérêt Codes partenaires commerciaux

### <a name="budgeting"></a>Budget

Analyse de budget Analyse de budget pour les budgets révisés Analyse de budget pour les dépenses réelles Analyse de budget pour les engagements Analyse de budget pour les engagements préalables

### <a name="french-regulatory-options"></a>Options de réglementation française

**Remarque** Pour plus d'informations sur les options de réglementation françaises, consultez [Comptabilité du secteur public en France](../localizations/emea-fra-public-sector-accounting.md). Les pages suivantes ne sont disponibles que si les trois conditions suivantes sont remplies :

-   La clé de configuration **Secteur public** est sélectionnée.
-   La sous-clé de configuration **Réglementation française** est sélectionnée.
-   L'option **Utiliser les règles comptables du secteur public français** est sélectionnée sur la page **Paramètres du budget**.

Synthèse de solde Engagement Clôture d'engagement Tenir à jour les mandats de paiement Tenir à jour les titres de recette Accès du département au contrat d'achat Arborescence des contrats d'achat Seuils de dépense par catégorie Historique des blocages de paiements de factures fournisseur

### <a name="general-ledger"></a>Comptabilité

Écritures comptables avancées Associer des hiérarchies financières dérivées Hiérarchies financières Filtrer les résultats Types de fonds Fonds Aperçu des transactions de comptabilité de fin d'exercice

### <a name="procurement-and-sourcing"></a>Approvisionnements

Type de certification Codes commande fournisseur de confirmation Montants des lignes des commandes fournisseur



<a name="additional-resources"></a>Ressources supplémentaires
--------

[Fonctionnalité Secteur public](public-sector-functionality.md)



