---
title: "Planifier pour la fonctionnalité Secteur public"
description: "Cet article suggère les premières étapes pour paramétrer la fonctionnalité Secteur public dans Microsoft Dynamics 365 for Operations."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19851
ms.assetid: 877eabf3-19c7-4897-b33e-c5a8a319cb35
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: bbbc33ceab6a448a0d98c5145e3055d0d830aed6
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="plan-for-public-sector-functionality"></a>Planifier pour la fonctionnalité Secteur public

[!include[banner](../includes/banner.md)]


Cet article suggère les premières étapes pour paramétrer la fonctionnalité Secteur public dans Microsoft Dynamics 365 for Operations.

<a name="what-should-i-do-first"></a>Que dois-je faire en premier lieu ?
-----------------------

Avant de commencer à ajuster les paramètres et à entrer vos données, vous devez prendre en compte les modules Microsoft Dynamics 365 for Operations que vous devez paramétrer pour votre organisation du secteur public. La fonctionnalité Secteur public est intégrée aux modules Microsoft Dynamics 365 for Operations et produits Microsoft suivants :

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

 

<a name="see-also"></a>Voir également :
--------

[Fonctionnalité Secteur public](public-sector-functionality.md)




