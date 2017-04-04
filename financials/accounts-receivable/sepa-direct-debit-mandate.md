---
title: "Paramétrer un mandat de débit direct SEPA"
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 114dee90b0fe525f0b3efabbf651d2804a22dd7d
ms.openlocfilehash: bb835f8dad16938b56365c7b06d4a0228f9aba66
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-sepa-direct-debit-mandate"></a>Paramétrer un mandat de débit direct SEPA



Un débit direct dans l'Espace unique de paiement en euros (SEPA) permet à un créditeur d'encaisser des fonds à partir du compte bancaire d'un client, à condition que le client ait accordé un mandat signé au créditeur. Le mandat que le client signe autorise le créditeur à encaisser un paiement et demande à la banque du client de payer la créance. Cette rubrique est planifiée pour afficher le processus de paramétrage des mandats de débit direct SEPA.

## <a name="prerequisites"></a>Conditions préalables
Le tableau suivant indique la configuration requise qui doit être en place avant de commencer.

| Catégorie       | Logiciel requis                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Pays/Région | L'adresse principale de l'entité juridique doit être située dans les pays/régions suivants : l'Autriche, la Belgique, l'Allemagne, l'Espagne, la France, l'Italie, ou les Pays-Bas. |

1. Paramétrez une souche de numéros pour les mandats de débit direct que chaque mandat de débit direct doit avoir un numéro unique. La page **Souches de numéros** vous permet de créer une souche de numéros pour les mandats de débit direct. Vous utiliserez cet identificateur pour affecter la souche de numéros au système de mandat de débit direct sur la page **Paramètres de la comptabilité client**.

2. Définition des paramètres des ventes pour les mandats de débit direct utilisent ** des paramètres des ventes ** la page permet de définir les paramètres des mandats de débit direct. Pour paramétrer les paramètres, sous ** débit direct ** l'onglet, modifiez les paramètres par défaut comme vous le souhaitez. Puis, dans ** des souches de numéros ** l'onglet, mettez ** ID de mandat de débit direct ** à jour le champ avec la souche de numéros paramétrée auparavant.

3. Paramétrage d'un mode de paiement pour les mandats de débit direct que vous devez paramétrer un mode de paiement pour les mandats de débit direct. Utilisez ce mode de paiement pour rechercher des factures pour lesquelles générer des paiements de débit direct. La page **Modes de paiement** vous permet de paramétrer le mode de paiement. Pour paramétrer un mode de paiement pour les mandats de débit direct, effectuez les étapes supplémentaires suivantes :

-   Dans le champ **Type de paiement**, sélectionnez **Paiement électronique**.
-   Facultatif : Si vous vous attendez à ce que chacun de vos clients avoir les mandats multiples, dans ** période ** le champ, sélectionnez ** facture **. Un paiement distinct est créé pour chaque facture, et chaque paiement utilise le mandat spécifié pour la facture.
-   Sélectionnez l'option **Demander un mandat** pour créer des paiements par l'intermédiaire des mandats de débit direct. L'option **Demander un mandat** est uniquement disponible si vous sélectionnez **Paiement électronique** dans le champ **Type de paiement**.

Voir également [vue d'ensemble de débit direct] (sepa-direct-debit-overview.md) 

