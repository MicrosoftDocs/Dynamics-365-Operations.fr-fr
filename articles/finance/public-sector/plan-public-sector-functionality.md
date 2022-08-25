---
title: Planifier pour la fonctionnalité Secteur public
description: Cet article suggère les premières étapes pour paramétrer la fonctionnalité Secteur public.
author: v-kiarnd
ms.date: 02/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: v-kiarnd
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 19851
ms.assetid: 877eabf3-19c7-4897-b33e-c5a8a319cb35
ms.search.industry: Public sector
ms.search.form: SysConfiguration
ms.openlocfilehash: 4e04af4a92854bddeb265a8a42336aeeab1c15c4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292163"
---
# <a name="plan-for-public-sector-functionality"></a>Planifier la fonctionnalité Secteur public

[!include [banner](../includes/banner.md)]

Cet article suggère les premières étapes pour paramétrer la fonctionnalité Secteur public.

## <a name="what-should-i-do-first"></a>Que dois-je faire en premier lieu ?

Avant de configurer le secteur public et de commencer à ajouter vos données, réfléchissez à la manière dont vous allez utiliser cette fonctionnalité. Votre considération doit identifier les modules qui doivent être configurés pour utiliser les fonctionnalités du secteur public. Le secteur public s’intègre aux éléments suivants dans Dynamics 365 Finance. 

### <a name="accounts-payable"></a>Module Comptabilité fournisseur

page de garde de l’état de paiement générer Montants des lignes de commande fournisseur

### <a name="accounts-receivable"></a>Module Comptabilité client

- Classifications de facturation
- Champs personnalisés du code facturation
- Codes facturation
- Champs personnalisés de facture financière Lignes d’intérêt
- Codes partenaire commercial

### <a name="budgeting"></a>Budget

- Analyse budgétaire
- Analyse budgétaire pour les budgets révisés
- Analyse budgétaire pour les dépenses réelles
- Analyse budgétaire pour les engagements
- Analyse budgétaire pour les engagements préalables

### <a name="french-regulatory-options"></a>Options de réglementation française

**Remarque** Pour plus d’informations sur les options de réglementation françaises, consultez [Comptabilité du secteur public en France](../localizations/emea-fra-public-sector-accounting.md). Les pages suivantes ne sont disponibles que si les trois conditions suivantes sont remplies :

- La clé de configuration **Secteur public** est sélectionnée.
- La sous-clé de configuration **Réglementation française** est sélectionnée.
- L’option **Utiliser les règles comptables du secteur public français** est sélectionnée sur la page **Paramètres du budget**.
- Synthèse de solde
- Clôture de l’engagement
- Tenir à jour les mandats de paiement
- Tenir à jour les titres de recette
- Accès du département au contrat d’achat
- Arborescence des contrats d’achat Seuils de dépense par catégorie
- Historique des blocages de paiements de factures fournisseur

### <a name="general-ledger"></a>Comptabilité

- Écritures comptables avancées
- Associer des hiérarchies financières dérivées
- Hiérarchies financières dérivées
- Filtrer les résultats Types de fonds
- Fonds
- Aperçu de fin d’exercice Transactions comptables

### <a name="procurement-and-sourcing"></a>Approvisionnements

- Type de certification
- Codes commande fournisseur de confirmation
- Montants des lignes des commandes fournisseur

## <a name="additional-resources"></a>Ressources supplémentaires

[Page d’accueil Secteur public](public-sector-functionality.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
