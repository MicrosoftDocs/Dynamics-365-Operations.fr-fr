---
title: Écritures comptables avancées dans le secteur public
description: Cet article explique comment les organisations du secteur public peuvent utiliser les écritures comptables avancées pour créer, ajuster et contrepasser des écritures comptables.
author: v-kiarnd
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AdvancedLedgerEntry, BudgetControlConfiguration, LedgerParameters
audience: Application User
ms.reviewer: twheeloc
ms.custom: 19511
ms.assetid: 3db0233e-d767-4dc0-b008-733098b6ca70
ms.search.region: Global
ms.search.industry: Public sector
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8b88efca3f29c22b86d925fb76cd869ed7d75c61
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871034"
---
# <a name="advanced-ledger-entries-in-the-public-sector"></a>Écritures comptables avancées dans le secteur public

[!include [banner](../includes/banner.md)]

Cet article explique comment les organisations du secteur public peuvent utiliser les écritures comptables avancées pour créer, ajuster et contrepasser des écritures comptables. Par exemple, vous pouvez utiliser des écritures comptables avancées pour reclassifier des dépenses si des factures sont validées par erreur dans un compte ou projet inapproprié.

## <a name="how-do-i-set-up-advanced-ledger-entries"></a>Comment paramétrer des écritures comptables avancées ?

Vérifiez que la clé **Écriture comptable avancée** **Configuration des licences** est sélectionnée sur la page **Configuration des licences**. Les écritures comptables avancées exigent des définitions de validation de comptabilité. Ces définitions de validation peuvent être paramétrées pour générer plusieurs écritures comptables équilibrées basées sur le compte général spécifié sur la page **Écritures comptables avancées**. Pour plus d’informations sur les définitions de validation pour les écritures comptables avancées, voir [Définitions de validation dans le secteur public](posting-definitions-public-sector.md).

## <a name="can-i-use-budget-control-with-advanced-ledger-entries"></a>Puis-je utiliser le contrôle budgétaire avec les écritures comptables avancées ?
Oui. Si votre organisation utilise le contrôle budgétaire, vous pouvez l’activer pour les écritures comptables avancées sur la page **Configuration du contrôle budgétaire**.

## <a name="can-i-use-advanced-ledger-entries-with-projects"></a>Puis-je utiliser les écritures comptables avancées avec des projets ?
Oui. Si vous souhaitez que les utilisateurs soient en mesure de modifier les dimensions financières pour un projet sur la ligne d’écriture comptable avancée, vous devez sélectionner l’option **Autoriser la modification des dimensions financières dans l’écran d’écriture comptable avancée** sur la page **Paramètres de comptabilité**. Si vous ne sélectionnez pas cette option, les utilisateurs peuvent modifier les dimensions financières dans le champ **Compte général** uniquement si les dimensions financières ne correspondent pas aux dimensions financières par défaut d’un projet.

## <a name="how-do-i-use-advanced-ledger-entries-to-record-year-end-accrual-entries"></a>Comment utiliser les écritures comptables avancées pour enregistrer les entrées de régularisation de fin d’exercice ?
Créez une écriture comptable avancée, sélectionnez l’option **Entrée de contrepassation**, puis entrez une date de contrepassation. L’écriture comptable avancée de contrepassation est créée lors de la validation de l’écriture comptable avancée. L’écriture comptable avancée de contrepassation aura un nouveau numéro de transaction et le statut de brouillon. La date de contrepassation sera utilisée comme date comptable et le montant débiteur ou créditeur de chaque ligne de l’écriture originale sera contrepassé. La même définition de validation sera utilisée. Le libellé de transaction de l’en-tête et des lignes contiendra les mots « Entrée de contrepassation de », le numéro de transaction de l’écriture comptable avancée originale, ainsi que son libellé de transaction.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
