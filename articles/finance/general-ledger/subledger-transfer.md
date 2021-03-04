---
title: Transfert de la sous-comptabilité vers la comptabilité
description: Cette rubrique décrit les fonctionnalités de Microsoft Dynamics 365 Finance en matière de transfert de la sous-comptabilité dans la comptabilité.
author: roschlom
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 7addb1f26a33db84d947e6fede876be648d2c654
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645168"
---
# <a name="subledger-transfer-to-the-general-ledger"></a>Transfert de la sous-comptabilité vers la comptabilité

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les fonctionnalités de Microsoft Dynamics 365 Finance qui sont liées aux règles permettant le transfert par lots des écritures de journal de comptabilité auxiliaire.

Dans la version 8.1, des modifications ont été apportées pour permettre le transfert des règles, ce qui a rendu l’option **Synchrone** obsolète. Pour plus d’informations, voir [Fonctionnalités supprimées ou obsolètes pour Finance and Operations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features?toc=/dynamics365/finance/toc.json#finance-and-operations-81-with-platform-update-20).

Les options suivantes sont disponibles pour le transfert par lots de la comptabilité auxiliaire. 

 - Asynchrone : cette option programme immédiatement le transfert des écritures de la comptabilité auxiliaire vers la comptabilité. Le n° document de comptabilité est enregistré dès que les ressources peuvent traiter cette demande sur le serveur. 

- Lot programmé : cette option ajoute les écritures de la comptabilité auxiliaire transférées vers la file d’attente de traitement dans la comptabilité où les entrées sont traitées dans l’ordre de réception. Le n° document de comptabilité est enregistré au moment programmé si les ressources peuvent réaliser ce traitement par lots sur le serveur. 
 
Dans la version 10.0.8, des améliorations ont été apportées pour améliorer les performances de l’option Asynchrone. Cette fonctionnalité est activée sous le nom **Optimisation des performances du transfert de la comptabilité auxiliaire vers la comptabilité**. 
 
Cette fonctionnalité améliore le transfert de données de la comptabilité auxiliaire vers la comptabilité. Elle rend le processus plus efficace et regroupe des ensembles de transactions plus petites à transférer. Elle offre une utilisation plus efficace du serveur de traitement par lots. Pour que l’option de transfert Asynchrone fonctionne avec cette fonctionnalité, le serveur de traitement par lots doit être configuré, en ligne et fonctionnel. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]