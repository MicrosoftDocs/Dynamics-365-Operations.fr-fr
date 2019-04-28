---
title: Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (15 novembre 2018)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 11/15/2018
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
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b90d4230fe1e666aba4075670f6df206e8df7ce9
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2019
ms.locfileid: "857313"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-november-15-2018"></a><span data-ttu-id="a00d1-103">Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (15 novembre 2018)</span><span class="sxs-lookup"><span data-stu-id="a00d1-103">What's new or changed in Dynamics 365 for Talent Core HR (November 15, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a00d1-104">**Version 8.1.2045**</span><span class="sxs-lookup"><span data-stu-id="a00d1-104">**Build 8.1.2045**</span></span>

<span data-ttu-id="a00d1-105">Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.</span><span class="sxs-lookup"><span data-stu-id="a00d1-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="other-changesfixes"></a><span data-ttu-id="a00d1-106">Autres modifications/corrections</span><span class="sxs-lookup"><span data-stu-id="a00d1-106">Other changes/fixes</span></span>

### <a name="unable-to-change-employees-current-position-to-a-future-open-position"></a><span data-ttu-id="a00d1-107">Impossible de modifier le poste actuel de l'employé avec un futur poste vacant</span><span class="sxs-lookup"><span data-stu-id="a00d1-107">Unable to change employee´s current position to a future open position</span></span>

<span data-ttu-id="a00d1-108">Une modification a été apportée pour activer les transferts de poste lorsque le poste est uniquement disponible dans le futur.</span><span class="sxs-lookup"><span data-stu-id="a00d1-108">A change has been made to enable position transfers when the position is only available in the future.</span></span> 

### <a name="position-does-not-display-when-creating-a-new-employee"></a><span data-ttu-id="a00d1-109">Le poste ne s'affiche pas lors de la création d'un employé</span><span class="sxs-lookup"><span data-stu-id="a00d1-109">Position does not display when creating a new employee</span></span>

<span data-ttu-id="a00d1-110">Une modification a été apportée pour afficher tous les postes à pourvoir disponibles pour une affectation lors de l'embauche de nouveaux employés dans Talent.</span><span class="sxs-lookup"><span data-stu-id="a00d1-110">A change has been made to display all open positions that are available for assignment when hiring new employees in Talent.</span></span> <span data-ttu-id="a00d1-111">Cela inclut les postes historiques ou si les postes ont été datés dans le futur.</span><span class="sxs-lookup"><span data-stu-id="a00d1-111">This includes historical positions or if the postitions have been future dated.</span></span> <span data-ttu-id="a00d1-112">Les postes s'affichent maintenant correctement selon la date de début de l'emploi.</span><span class="sxs-lookup"><span data-stu-id="a00d1-112">Positions will now appear correctly based on the employment start date.</span></span> 

### <a name="termination-date-is-displaying-based-on-user-settings"></a><span data-ttu-id="a00d1-113">La date de fin de contrat s'affiche selon les paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="a00d1-113">Termination date is displaying based on user settings</span></span>

<span data-ttu-id="a00d1-114">Une modification été apportée à la liste des employés passés pour tenir compte des décalages de fuseau horaire pour les fuseaux horaires choisis par les employés lors de l'affichage de la date de fin de contrat.</span><span class="sxs-lookup"><span data-stu-id="a00d1-114">A change has been made to the past employees list to account for any time zone offsets for the employees preferred time zone when viewing the termination date.</span></span>

### <a name="work-items-assigned-to-me-links-not-displaying-the-correct-information"></a><span data-ttu-id="a00d1-115">Les liens des éléments de travail qui me sont affectés n'affichent pas les informations correctes</span><span class="sxs-lookup"><span data-stu-id="a00d1-115">Work items assigned to me links not displaying the correct information</span></span>

<span data-ttu-id="a00d1-116">Avec cette modification, la navigation dans les détails des différents éléments de travail de la liste affichera les informations correcte de l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a00d1-116">With this change, navigation to the details of the individual work items in the list will display the correct information for the item selected.</span></span> <span data-ttu-id="a00d1-117">Ce problème se produisait uniquement avec des options de sécurité avancées.</span><span class="sxs-lookup"><span data-stu-id="a00d1-117">This issue only occurred with advanced security options.</span></span>


## <a name="known-issue"></a><span data-ttu-id="a00d1-118">Problème connu</span><span class="sxs-lookup"><span data-stu-id="a00d1-118">Known issue</span></span>

- <span data-ttu-id="a00d1-119">**Problème** : Lors de l'ajout d'une pièce jointe à un collaborateur, les boutons **Nouveau** et **Modifier** sont grisés.</span><span class="sxs-lookup"><span data-stu-id="a00d1-119">**Issue**: When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out.</span></span> 
- <span data-ttu-id="a00d1-120">**Solution :** Avant d'ouvrir la page de la pièce jointe, assurez-vous que les récapitulatifs sur la page **Collaborateur** sont clôturés.</span><span class="sxs-lookup"><span data-stu-id="a00d1-120">**Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="a00d1-121">Si les récapitulatifs sont fermés lorsque la page **Collaborateur** est chargée, les boutons de pièces jointes sont activés.</span><span class="sxs-lookup"><span data-stu-id="a00d1-121">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="a00d1-122">(Ce problème sera résolu dans la prochaine mise à jour de la plateforme.)</span><span class="sxs-lookup"><span data-stu-id="a00d1-122">(This issue will be fixed in the next platform update.)</span></span>
