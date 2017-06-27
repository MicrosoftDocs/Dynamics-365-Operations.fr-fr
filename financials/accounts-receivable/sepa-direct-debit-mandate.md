---
title: "Paramétrer un mandat de débit direct SEPA"
description: 
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ebf80efa32b21184a8effdde4d46c4d0d2179efd
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-sepa-direct-debit-mandate"></a>Paramétrer un mandat de débit direct SEPA

[!include[banner](../includes/banner.md)]




Un débit direct dans l'Espace unique de paiement en euros (SEPA) permet à un créditeur d'encaisser des fonds à partir du compte bancaire d'un client, à condition que le client ait accordé un mandat signé au créditeur. Le mandat que le client signe autorise le créditeur à encaisser un paiement et demande à la banque du client de payer la créance. Cette rubrique présente le processus de paramétrage des mandats de débit direct SEPA.

## <a name="prerequisites"></a>Conditions préalables
Le tableau suivant indique la configuration requise qui doit être en place avant de commencer.

| Catégorie       | Logiciel requis                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Pays/Région | L'adresse principale de l'entité juridique doit être située dans les pays/régions suivants : l'Autriche, la Belgique, l'Allemagne, l'Espagne, la France, l'Italie, ou les Pays-Bas. |

1. Paramétrez une souche de numéros pour les mandats de débit direct. Chaque mandat de débit direct doit avoir un numéro unique. La page **Souches de numéros** vous permet de créer une souche de numéros pour les mandats de débit direct. Vous utiliserez cet identificateur pour affecter la souche de numéros au système de mandat de débit direct sur la page **Paramètres de la comptabilité client**.

2. Définissez les paramètres de la comptabilité client pour les mandats de débit direct. Utilisez la page **Paramètres de la comptabilité client** pour définir les paramètres des mandats de débit direct. Pour définir les paramètres, sous l'onglet **Débit direct**, modifiez les paramètres par défaut selon vos besoins. Ensuite, sous l'onglet **Souches de numéros**, actualisez le champ **ID mandat de débit direct** avec la souche de numéros définie précédemment.

3. Paramétrez un mode de paiement pour les mandats de débit direct. Vous devez définir un mode de paiement pour les mandats de débit direct. Utilisez ce mode de paiement pour rechercher des factures pour lesquelles générer des paiements de débit direct. La page **Modes de paiement** vous permet de paramétrer le mode de paiement. Pour paramétrer un mode de paiement pour les mandats de débit direct, effectuez les étapes supplémentaires suivantes :

-   Dans le champ **Type de paiement**, sélectionnez **Paiement électronique**.
-   Facultatif : si vous prévoyez que chacun de vos clients aura plusieurs mandats, dans le champ **Période**, sélectionnez **Facture**. Cette opération crée un paiement distinct pour chaque facture, et chaque paiement utilisera le mandat indiqué pour la facture.
-   Sélectionnez l'option **Demander un mandat** pour créer des paiements par l'intermédiaire des mandats de débit direct. L'option **Demander un mandat** est uniquement disponible si vous sélectionnez **Paiement électronique** dans le champ **Type de paiement**.

Voir également [Vue d'ensemble du débit direct](sepa-direct-debit-overview.md) 



