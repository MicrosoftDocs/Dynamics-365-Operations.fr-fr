---
title: Nouveautés ou modifications dans Dynamics 365 Talent - Core HR (1 octobre 2018)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent - Core HR.
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
ms.openlocfilehash: f872b0907e0f48e0b734c87f0b8fb1a4cfe20cb0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461109"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-core-hr-october-1-2018"></a><span data-ttu-id="a47f7-103">Nouveautés ou modifications dans Dynamics 365 Talent: Core HR (1er octobre 2018)</span><span class="sxs-lookup"><span data-stu-id="a47f7-103">What's new or changed in Dynamics 365 Talent: Core HR (October 1, 2018)</span></span>

<span data-ttu-id="a47f7-104">**Version 8.1.1035.0**</span><span class="sxs-lookup"><span data-stu-id="a47f7-104">**Build 8.1.1035.0**</span></span>

<span data-ttu-id="a47f7-105">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.</span><span class="sxs-lookup"><span data-stu-id="a47f7-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="turn-off-electronic-payment-validation"></a><span data-ttu-id="a47f7-106">Désactiver la validation des paiements électroniques</span><span class="sxs-lookup"><span data-stu-id="a47f7-106">Turn off electronic payment validation</span></span>

<span data-ttu-id="a47f7-107">Les informations de paiement électronique sont validées si vous paramétrez les décaissements pour le dépôt direct via l'espace de travail **Libre-service employé** ou directement dans l'écran Employé.</span><span class="sxs-lookup"><span data-stu-id="a47f7-107">Electronic payment information validation occurs if you set up disbursements for direct deposit either through **Employee self-service** workspace (ESS) or directly on the employee form.</span></span> <span data-ttu-id="a47f7-108">Cette option vous permet de supprimer cette validation si les contrôles de validation ne sont pas nécessaires pour les montants et les valeurs restantes.</span><span class="sxs-lookup"><span data-stu-id="a47f7-108">This option gives you the flexibility to remove that validation if you do not require the validation checks for amounts and remainder values.</span></span> <span data-ttu-id="a47f7-109">Cette fonction est utile si l'intégration s'applique à un système de paie externe qui a des exigences différentes.</span><span class="sxs-lookup"><span data-stu-id="a47f7-109">This feature is helpful if you're integrating with an external payroll system that has different requirements.</span></span>

## <a name="manager-self-service---add-goals-for-team-members-through-the-team-performance-goals-tile"></a><span data-ttu-id="a47f7-110">Responsable en libre-service - Ajoutez des objectifs pour les membres de l'équipe via la vignette Objectifs de performance de l'équipe</span><span class="sxs-lookup"><span data-stu-id="a47f7-110">Manager self-service - Add goals for team members through the Team performance goals tile</span></span>

<span data-ttu-id="a47f7-111">Avant cette version, les responsables peuvent ajouter individuellement des objectifs à leurs employés par le biais des objectifs de performance associés à chaque employé.</span><span class="sxs-lookup"><span data-stu-id="a47f7-111">Prior to this release, managers can add goals to their employees individually through the performance goals associated to each employee.</span></span> <span data-ttu-id="a47f7-112">Avec cette mise à jour, les responsables peuvent accéder à la vignette **Objectifs de performance de l'équipe** et créer de nouveaux objectifs en sélectionnant leurs états directs.</span><span class="sxs-lookup"><span data-stu-id="a47f7-112">With this update, managers can access the **Team performance goals** tile and create new goals by selecting any of their direct reports.</span></span>

## <a name="manager-self-service---add-reviews-for-team-members-through-the-team-performance-reviews-tile"></a><span data-ttu-id="a47f7-113">Responsable en libre-service - Ajoutez des révisions pour les membres de l'équipe via la vignette Révisions des performances de l'équipe</span><span class="sxs-lookup"><span data-stu-id="a47f7-113">Manager self-service - Add reviews for team members through the Team performance reviews tile</span></span>

<span data-ttu-id="a47f7-114">Avant cette version, les responsables peuvent ajouter individuellement des révisions à leurs employés par le biais des révisions associées à chaque employé.</span><span class="sxs-lookup"><span data-stu-id="a47f7-114">Prior to this release, managers can add reviews to their employees individually through the reviews associated to each employee.</span></span> <span data-ttu-id="a47f7-115">Avec cette mise à jour, les responsables peuvent accéder à la vignette **Révisions des performances de l'équipe** et créer de nouvelles révisions en sélectionnant leurs états directs.</span><span class="sxs-lookup"><span data-stu-id="a47f7-115">With this update, managers can access the **Team performance reviews** tile and create new reviews by selecting any of their direct reports.</span></span>

## <a name="configure-proration-options-by-leave-plan"></a><span data-ttu-id="a47f7-116">Configurer les options de calcul au prorata par plan de congé</span><span class="sxs-lookup"><span data-stu-id="a47f7-116">Configure proration options by leave plan</span></span>

<span data-ttu-id="a47f7-117">Les organisations accordent des congés différemment selon la date à laquelle les employés entrent ou quittent la société.</span><span class="sxs-lookup"><span data-stu-id="a47f7-117">Organizations award time off differently based on when employees join and leave the company.</span></span> <span data-ttu-id="a47f7-118">Pour certaines organisations, les employés perçoivent une prime complète à leur date d'entrée tandis que d'autres calculent la prime au prorata.</span><span class="sxs-lookup"><span data-stu-id="a47f7-118">For some organizations, employees are awarded their full allocation on their start date while others prorate the award.</span></span> <span data-ttu-id="a47f7-119">De nouvelles options sont fournies dans cette version pour choisir le mode de calcul au prorata des primes et des régularisations pour les nouveaux employés ou les employés qui quittent une organisation.</span><span class="sxs-lookup"><span data-stu-id="a47f7-119">New options are provided in this release to choose how to prorate the awards and accruals for joiners and leavers in an organization.</span></span> <span data-ttu-id="a47f7-120">Les options sont les suivantes : Au prorata, Régularisation complète et Aucune régularisation.</span><span class="sxs-lookup"><span data-stu-id="a47f7-120">Options include: Prorated, Full accrual, and No accrual.</span></span>

## <a name="other-changes"></a><span data-ttu-id="a47f7-121">Autres modifications</span><span class="sxs-lookup"><span data-stu-id="a47f7-121">Other changes</span></span>

-   <span data-ttu-id="a47f7-122">Entité Employé mise à jour - Le titre **Personnel** peut maintenant être mis à jour à l'aide du complément Excel/de la gestion des données.</span><span class="sxs-lookup"><span data-stu-id="a47f7-122">Employee entity updated - The **Personal** title can now be updated using the Excel add-in/data management.</span></span>

-   <span data-ttu-id="a47f7-123">Modification de la sécurité pour autoriser la suppression des boutons **Supprimer** et **Désactiver** dans le libre-service employé pour les informations de paiement.</span><span class="sxs-lookup"><span data-stu-id="a47f7-123">Security change to allow removal of the **Delete** and **Deactivate** buttons in employee self-service for payment information.</span></span>

## <a name="known-issue"></a><span data-ttu-id="a47f7-124">Problème connu</span><span class="sxs-lookup"><span data-stu-id="a47f7-124">Known issue</span></span>

-   <span data-ttu-id="a47f7-125">**Problème** : lors de l'ajout d'une nouvelle pièce jointe à un collaborateur, les boutons **Nouveau** et **Modifier** sont grisés. **Solution de contournement** : avant d'ouvrir la page de la pièce jointe, vérifiez que les récapitulatifs de la page **Collaborateur** sont fermés.</span><span class="sxs-lookup"><span data-stu-id="a47f7-125">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="a47f7-126">Si les récapitulatifs sont fermés lorsque la page **Collaborateur** est chargée, les boutons **Pièces jointes** sont activés.</span><span class="sxs-lookup"><span data-stu-id="a47f7-126">If the FactBoxes are closed when the **Worker** page is loaded, the **Attachments** buttons will be enabled.</span></span> <span data-ttu-id="a47f7-127">(Ce problème sera résolu dans la prochaine mise à jour de la plateforme.)</span><span class="sxs-lookup"><span data-stu-id="a47f7-127">(This issue will be fixed in the next platform update.)</span></span>
