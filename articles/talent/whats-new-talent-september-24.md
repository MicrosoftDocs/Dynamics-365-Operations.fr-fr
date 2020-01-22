---
title: Nouveautés ou modifications dans Dynamics 365 Talent - Core HR (24 septembre 2018)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 09/21/2018
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
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e0c1a3bf7613db4887e0943a70ad6262a70997f0
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898964"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-september-24-2018"></a><span data-ttu-id="2575f-103">Nouveautés ou modifications dans Dynamics 365 Talent - Core HR (24 septembre 2018)</span><span class="sxs-lookup"><span data-stu-id="2575f-103">What's new or changed in Dynamics 365 Talent - Core HR (September 24, 2018)</span></span>

<span data-ttu-id="2575f-104">**Version 8.1.1015.0**</span><span class="sxs-lookup"><span data-stu-id="2575f-104">**Build 8.1.1015.0**</span></span>

<span data-ttu-id="2575f-105">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.</span><span class="sxs-lookup"><span data-stu-id="2575f-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="currency-added-to-benefits"></a><span data-ttu-id="2575f-106">Devise ajoutée aux avantages</span><span class="sxs-lookup"><span data-stu-id="2575f-106">Currency added to Benefits</span></span>

<span data-ttu-id="2575f-107">Les plans d'avantages ont été mis à jour pour inclure la devise de l'avantage.</span><span class="sxs-lookup"><span data-stu-id="2575f-107">Benefit plans have been updated to include the currency of the benefit.</span></span> <span data-ttu-id="2575f-108">Ce nouveau champ est également disponible dans la page Avantages inscrits du collaborateur.</span><span class="sxs-lookup"><span data-stu-id="2575f-108">This new field is also available on worker enrolled benefits.</span></span> <span data-ttu-id="2575f-109">Ce nouveau champ fait partie des privilèges de sécurité pour Tenir à jour les avantages et Afficher la liste des avantages.</span><span class="sxs-lookup"><span data-stu-id="2575f-109">This new field is part of the Maintain benefits and View a list of benefits security privilege.</span></span>

## <a name="update-proration-process--leave-and-absence"></a><span data-ttu-id="2575f-110">Mettre à jour le processus de calcul au prorata – Congé et absence</span><span class="sxs-lookup"><span data-stu-id="2575f-110">Update proration process – Leave and Absence</span></span>

<span data-ttu-id="2575f-111">Les organisations accordent des congés différemment selon la date à laquelle les employés entrent ou quittent la société.</span><span class="sxs-lookup"><span data-stu-id="2575f-111">Organizations award time off differently based on when employees join and leave the company.</span></span> <span data-ttu-id="2575f-112">Pour les employés qui quittent l'organisation, certains doivent mettre fin à la prime à la date de résiliation du contrat, tandis que d'autres se basent sur le dernier jour travaillé pour arrêter le processus de régularisation.</span><span class="sxs-lookup"><span data-stu-id="2575f-112">For employees leaving the organization, some may need to end the award on the termination date, while others rely on the last day worked to stop the accrual process.</span></span> <span data-ttu-id="2575f-113">Ces modifications permettent aux organisations de choisir quand mettre fin à l'inscription pendant le processus de résiliation.</span><span class="sxs-lookup"><span data-stu-id="2575f-113">These changes provide organizations the ability to choose when to end enrollment during the termination process.</span></span> <span data-ttu-id="2575f-114">Ces nouvelles options font partie des privilèges pour Mettre fin au contrat d'un collaborateur et Mettre un terme au contrat d'un collaborateur à partir du libre-service des responsables.</span><span class="sxs-lookup"><span data-stu-id="2575f-114">These new options are part of the privileges for Terminate a worker and Terminate a worker from manager self service.</span></span> 

## <a name="other-changes"></a><span data-ttu-id="2575f-115">Autres modifications</span><span class="sxs-lookup"><span data-stu-id="2575f-115">Other changes</span></span>

<span data-ttu-id="2575f-116">Cette version contient plusieurs correctifs de bogue supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="2575f-116">This release includes several additional bug fixes.</span></span>

## <a name="known-issue"></a><span data-ttu-id="2575f-117">Problème connu</span><span class="sxs-lookup"><span data-stu-id="2575f-117">Known Issue</span></span>

-   <span data-ttu-id="2575f-118">**Problème** : lors de l'ajout d'une nouvelle pièce jointe à un collaborateur, les boutons **Nouveau** et **Modifier** sont grisés. **Solution de contournement** : avant d'ouvrir la page de la pièce jointe, vérifiez que les récapitulatifs de la page **Collaborateur** sont fermés.</span><span class="sxs-lookup"><span data-stu-id="2575f-118">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the fact boxes on the **Worker** page are closed.</span></span> <span data-ttu-id="2575f-119">Si les récapitulatifs sont fermés lorsque la page **Collaborateur** est chargée, les boutons des pièces jointes sont activés.</span><span class="sxs-lookup"><span data-stu-id="2575f-119">If the fact boxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="2575f-120">(Ce problème sera résolu dans la prochaine mise à jour de la plateforme.)</span><span class="sxs-lookup"><span data-stu-id="2575f-120">(This issue will be fixed in the next platform update.)</span></span>
