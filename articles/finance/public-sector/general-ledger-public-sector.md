---
title: Vue d'ensemble du module Comptabilité dans le secteur public
description: Cette rubrique décrit la fonctionnalité Comptabilité disponible pour le secteur public.
author: ShylaThompson
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AdvancedLedgerEntry, JournalizingDefinition, LedgerDerivedFinHierarchies, LedgerFundType, LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 27211
ms.assetid: d737c743-e224-4a30-b4c3-e9568eaddd8c
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 47e79eb12e8f4563595507b0edafba7e056e476c
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770251"
---
# <a name="general-ledger-in-the-public-sector-overview"></a>Vue d'ensemble du module Comptabilité dans le secteur public

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la fonctionnalité Comptabilité disponible pour le secteur public.

<a name="how-do-general-ledger-parameters-need-to-be-set-for-public-sector-organizations"></a>Comment paramètres de comptabilité doivent-ils être définis pour les organisations du secteur public ?
--------------------------------------------------------------------------------

La plupart des paramètres de comptabilité sont définis de la même manière pour les organisations du secteur public et du secteur privé. En outre, il existe des paramètres du secteur public utilisés pour le processus de fin d'exercice pour les fonds. Définissez ces paramètres sur la page **Paramètres de comptabilité**, dans la section **Comptabilité**, dans l'organisateur **Clôture d'exercice**.

-   Sélectionnez **Créer des transactions de clôture lors du transfert** pour générer les entrées de clôture et de solde d'ouverture. Lorsque cette option est sélectionnée, lors des exécutions suivantes de ce processus, le système supprime les transactions des exécutions précédentes et génère de nouvelles entrées de clôture et d'ouverture. Si cette option n'est pas sélectionnée, le système calculera la modification nette et génèrera uniquement cette transaction pour les entrées de clôture et les soldes d'ouverture. **Remarque** : cette option requiert l'utilisation des définitions de validation. Pour plus d'informations, voir [Définitions de validation dans le secteur public](posting-definitions-public-sector.md).
-   Sélectionnez **Utilisez la dimension de fonds pour les transactions de fin d'exercice** afin d'activer la version du secteur public de la page **Transactions d'ouverture**.
-   Sélectionnez **Utilisez la dimension de fonds pour reporter des commandes fournisseur** pour activer la capacité à définir les options de traitement de fin d'exercice pour des fonds spécifiques.

Pour en savoir plus sur le processus de fin d'exercice pour les fonds, voir [Traitement de fin d'exercice dans le secteur public](year-end-processing-public-sector.md).

## <a name="what-fund-classes-and-fund-types-are-available"></a>Les classes et types de fonds sont-ils disponibles ?
Les classes de fonds gouvernementales, propriétaires et fiduciaires sont disponibles pour les organisations du secteur public, ainsi qu'une classe Mémo. Vous créerez les types de fonds dont votre organisation a besoin. Pour plus d'informations, voir [Fonds dans le secteur public](funds-public-sector.md).

## <a name="how-are-financial-dimensions-used-with-funds"></a>Comment les dimensions financières sont-elles utilisées avec les fonds ?
Les numéros de fonds servent de valeurs de dimension dans les numéros de compte financier, dans la mesure où une dimension a été mise en correspondance avec un fonds. Les organisations du secteur public ont généralement besoin des écritures équilibrées pour les dimensions financières associées aux fonds.

## <a name="what-is-the-easiest-way-to-adjust-or-reverse-ledger-entries"></a>Quelle est la manière la plus simple d'ajuster ou de contrepasser des écritures comptables ?
Vous pouvez utiliser les écritures comptables avancées pour créer, ajuster et contrepasser des écritures comptables. Par exemple, vous pouvez utiliser des écritures comptables avancées pour reclassifier des dépenses si des factures sont validées par erreur dans un compte ou projet inapproprié. Pour plus d'informations, voir [Écritures comptables avancées dans le secteur public](advanced-ledger-entries-public-sector.md) et [Définitions de validation dans le secteur public](posting-definitions-public-sector.md).

## <a name="why-should-i-use-posting-definitions"></a>Pourquoi utiliser les définitions de validation ?
Vous pouvez utiliser les définitions de validation pour créer des lignes de journal de comptabilité auxiliaire pour les transactions d'origine qui répondent aux critères sélectionnés, par exemple, pour générer plusieurs écritures comptables équilibrées basées sur des attributs tels que des types de transactions et des comptes. Les définitions de validation permettent un contrôle précis des mises à jour comptables créées par les documents source, contrairement:aux mises à jour largement appliquées des profils de validation. Les définitions de validation de comptabilité sont exigées lorsque vous utilisez des écritures comptables avancées. Les définitions de validation sont utilisées dans le traitement de fin d'exercice des comptes généraux. Vous pouvez utiliser les définitions de validation pour clôturer les comptes pour les soldes de fonds ou les bénéfices non répartis, en fonction de la classe de fonds et du type de clôture de compte. Les définitions de validation sont requises pour clôturer les comptes généraux et transférer les soldes vers la période d'ouverture du nouvel exercice. Pour plus d'informations, voir [Définitions de validation dans le secteur public](posting-definitions-public-sector.md).

## <a name="how-do-i-collect-and-analyze-data-to-meet-the-common-governmentwide-accounting-classification-cgac-requirements"></a>Comment recueillir et analyser des données pour répondre aux exigences des principales classifications comptables applicables au niveau gouvernemental ?
Vous pouvez utiliser des hiérarchies financières dérivées afin de recueillir et d'analyser des données de transaction validées pour des numéros de compte principal, des numéros de compte complet et des valeurs de dimension financière spécifiques. Pour plus d'informations, voir [Hiérarchies financières dérivées dans le secteur public](derived-financial-hierarchies-public-sector.md).

<a name="additional-resources"></a>Ressources supplémentaires
--------

[Vue d'ensemble des modules Comptabilité et États financiers](../general-ledger/general-ledger.md)



