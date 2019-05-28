---
title: Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (1 octobre 2018)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 15b5fd7095a62aa9b7b79ebfcada667959b756aa
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518020"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-1-2018"></a>Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (1 octobre 2018)

[!include [banner](includes/banner.md)]

**Version 8.1.1035.0**

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.

## <a name="turn-off-electronic-payment-validation"></a>Désactiver la validation des paiements électroniques

Les informations de paiement électronique sont validées si vous paramétrez les décaissements pour le dépôt direct via l'espace de travail **Libre-service employé** ou directement dans l'écran Employé. Cette option vous permet de supprimer cette validation si les contrôles de validation ne sont pas nécessaires pour les montants et les valeurs restantes. Cette fonction est utile si l'intégration s'applique à un système de paie externe qui a des exigences différentes.

## <a name="manager-self-service---add-goals-for-team-members-through-the-team-performance-goals-tile"></a>Responsable en libre-service - Ajoutez des objectifs pour les membres de l'équipe via la vignette Objectifs de performance de l'équipe

Avant cette version, les responsables peuvent ajouter individuellement des objectifs à leurs employés par le biais des objectifs de performance associés à chaque employé. Avec cette mise à jour, les responsables peuvent accéder à la vignette **Objectifs de performance de l'équipe** et créer de nouveaux objectifs en sélectionnant leurs états directs.

## <a name="manager-self-service---add-reviews-for-team-members-through-the-team-performance-reviews-tile"></a>Responsable en libre-service - Ajoutez des révisions pour les membres de l'équipe via la vignette Révisions des performances de l'équipe

Avant cette version, les responsables peuvent ajouter individuellement des révisions à leurs employés par le biais des révisions associées à chaque employé. Avec cette mise à jour, les responsables peuvent accéder à la vignette **Révisions des performances de l'équipe** et créer de nouvelles révisions en sélectionnant leurs états directs.

## <a name="configure-proration-options-by-leave-plan"></a>Configurer les options de calcul au prorata par plan de congé

Les organisations accordent des congés différemment selon la date à laquelle les employés entrent ou quittent la société. Pour certaines organisations, les employés perçoivent une prime complète à leur date d'entrée tandis que d'autres calculent la prime au prorata. De nouvelles options sont fournies dans cette version pour choisir le mode de calcul au prorata des primes et des régularisations pour les nouveaux employés ou les employés qui quittent une organisation. Les options sont les suivantes : Au prorata, Régularisation complète et Aucune régularisation.

## <a name="other-changes"></a>Autres modifications

-   Entité Employé mise à jour - Le titre **Personnel** peut maintenant être mis à jour à l'aide du complément Excel/de la gestion des données.

-   Modification de la sécurité pour autoriser la suppression des boutons **Supprimer** et **Désactiver** dans le libre-service employé pour les informations de paiement.

## <a name="known-issue"></a>Problème connu

-   **Problème** : lors de l'ajout d'une nouvelle pièce jointe à un collaborateur, les boutons **Nouveau** et **Modifier** sont grisés. **Solution de contournement** : avant d'ouvrir la page de la pièce jointe, vérifiez que les récapitulatifs de la page **Collaborateur** sont fermés. Si les récapitulatifs sont fermés lorsque la page **Collaborateur** est chargée, les boutons **Pièces jointes** sont activés. (Ce problème sera résolu dans la prochaine mise à jour de la plateforme.)
