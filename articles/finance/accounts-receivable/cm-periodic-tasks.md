---
title: Tâches périodiques de gestion des crédits
description: Cette rubrique décrit les tâches périodiques qui sont une partie nécessaire du processus de gestion des limites de crédit pour les clients.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4ca9bb7f77283ec30d4648d6763f4156494050ac
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124160"
---
# <a name="periodic-credit-management-tasks"></a>Tâches périodiques de gestion du crédit

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les tâches périodiques qui sont une partie nécessaire du processus de gestion des limites de crédit pour les clients.

## <a name="update-risk-scores"></a>Mettre à jour les scores de risque

À mesure que les entreprises évoluent et que les circonstances changent, les risques de crédit pour un client donné peuvent également changer. Pour aider à maintenir des limites de crédit appropriées pour vos clients, vous devez revoir périodiquement les critères de chaque score de risque et mettre à jour les scores de chaque client. Vous pouvez mettre à jour les scores suivants en utilisant la page **Mettre à jour les scores de risque** (**Crédit et relances \> Tâches périodiques \> Gestion de crédit \> Mettre à jour les scores de risque**). Tous les calculs définis par l'utilisateur sont également traités.

- **Jours de paiement moyens** - Ce score est le nombre moyen de jours qu'un client prend pour payer ses factures.
- **Client depuis** - Ce score est le nombre d'années qu'un client a été client de votre organisation.
- **En affaires depuis** - Ce score est le nombre d'années d'activité d'un client. Il utilise la valeur du champ **Début d'activité** sur la page **Clients**.
- **Ventes quotidiennes restantes** - Ce score est basé sur le bilan de la comptabilité client, le chiffre d'affaires et le nombre de jours pour la période précédente de 12 mois.
- **Solde moyen** - Ce score est basé sur le bilan de la comptabilité client pour la période précédente de 12 mois.
- **Groupe de gestion des crédits**, **Statut du compte** et **Pays** - Ces scores utilisent les informations du client.

## <a name="update-customer-balance-statistics"></a>Mettre à jour les statistiques de solde client

Vous pouvez exécuter le processus **Mettre à jour les statistiques de solde client** pour mettre à jour le calcul des statistiques de solde indiquées sur la page **Demande de statistiques de solde**. Ces informations sont utilisées pour calculer les scores de risque et les valeurs qui sont affichées dans les récapitulatifs des statistiques de crédit de la page **Client**.

Lorsque vous exécutez le processus, il met à jour les statistiques de solde client pour un seul client. Pour configurer un traitement par lots pour exécuter le processus pour plusieurs clients, vous pouvez utiliser la page **Calculer les statistiques de solde** (**Gestion de crédit \> Tâches périodiques \> Calculer les statistiques de solde**).
