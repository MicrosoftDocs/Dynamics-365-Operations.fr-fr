---
title: Planifier la fonctionnalité Secteur public
description: Cette rubrique suggère les premières étapes pour paramétrer la fonctionnalité Secteur public.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom: 19851
ms.assetid: 877eabf3-19c7-4897-b33e-c5a8a319cb35
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2ae89d07404c63ebb5d1e82b20c45c7f406a9b9c1bc04b40a7d1d1115a7f2585
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713730"
---
# <a name="plan-for-public-sector-functionality"></a>Planifier la fonctionnalité Secteur public

[!include [banner](../includes/banner.md)]

Cette rubrique suggère les premières étapes pour paramétrer la fonctionnalité Secteur public.

## <a name="what-should-i-do-first"></a>Que dois-je faire en premier lieu ?

Avant de configurer le secteur public et de commencer à ajouter vos données, réfléchissez à la manière dont vous allez utiliser cette fonctionnalité. Votre considération doit identifier les modules qui doivent être configurés pour utiliser les fonctionnalités du secteur public. Le secteur public s’intègre aux éléments suivants : 

### <a name="accounts-payable"></a>Module Comptabilité fournisseur

page de garde de l’état de paiement générer Montants des lignes de commande fournisseur

### <a name="accounts-receivable"></a>Module Comptabilité client

Classification de facturation Champs personnalisés de code personnalisé de facturation Codes de facturation Champs personnalisés de facture financière Lignes d’intérêt Codes partenaires commerciaux

### <a name="budgeting"></a>Budget

Analyse de budget Analyse de budget pour les budgets révisés Analyse de budget pour les dépenses réelles Analyse de budget pour les engagements Analyse de budget pour les engagements préalables

### <a name="french-regulatory-options"></a>Options de réglementation française

**Remarque** Pour plus d’informations sur les options de réglementation françaises, consultez [Comptabilité du secteur public en France](../localizations/emea-fra-public-sector-accounting.md). Les pages suivantes ne sont disponibles que si les trois conditions suivantes sont remplies :

-   La clé de configuration **Secteur public** est sélectionnée.
-   La sous-clé de configuration **Réglementation française** est sélectionnée.
-   L’option **Utiliser les règles comptables du secteur public français** est sélectionnée sur la page **Paramètres du budget**.

Synthèse de solde Clôture d’engagement Tenir à jour les mandats de paiement Tenir à jour les titres de recette Accès du département au contrat d’achat Arborescence des contrats d’achat Seuils de dépense par catégorie Historique des blocages de paiements de factures fournisseur

### <a name="general-ledger"></a>Comptabilité

Écritures comptables avancées Associer des hiérarchies financières dérivées Hiérarchies financières Filtrer les résultats Types de fonds Fonds Aperçu des transactions de comptabilité de fin d’exercice

### <a name="procurement-and-sourcing"></a>Approvisionnements

Type de certification Codes commande fournisseur de confirmation Montants des lignes des commandes fournisseur



## <a name="additional-resources"></a>Ressources supplémentaires

[Page d’accueil Secteur public](public-sector-functionality.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]