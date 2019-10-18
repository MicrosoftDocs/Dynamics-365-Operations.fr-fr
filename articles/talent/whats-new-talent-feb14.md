---
title: Nouveautés ou modifications dans Dynamics 365 Talent (14 février 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/14/2019
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
ms.search.validFrom: 2019-02-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 9f3fa269217bc03a15fde6ee0fc9d0c502c17b3e
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009120"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-february-14-2019"></a><span data-ttu-id="c7d44-103">Nouveautés ou modifications dans Dynamics 365 Talent (14 février 2019)</span><span class="sxs-lookup"><span data-stu-id="c7d44-103">What's new or changed in Dynamics 365 Talent (February 14, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c7d44-104">Cette rubrique décrit les fonctionnalités inédites ou ayant fait l'objet de modifications dans Talent.</span><span class="sxs-lookup"><span data-stu-id="c7d44-104">This topic describes features that are either new or changed in Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="c7d44-105">Modifications apportées à Attract</span><span class="sxs-lookup"><span data-stu-id="c7d44-105">Changes in Attract</span></span>
<span data-ttu-id="c7d44-106">Cette version comporte des correctifs de bogues mineurs.</span><span class="sxs-lookup"><span data-stu-id="c7d44-106">There are minor bug fixes included with this release.</span></span>

## <a name="changes-in-onboarding"></a><span data-ttu-id="c7d44-107">Modifications apportées à Onboard</span><span class="sxs-lookup"><span data-stu-id="c7d44-107">Changes in Onboarding</span></span>
<span data-ttu-id="c7d44-108">Cette version comporte des correctifs de bogues mineurs.</span><span class="sxs-lookup"><span data-stu-id="c7d44-108">There are minor bug fixes included with this release.</span></span>
 
## <a name="changes-in-core-hr"></a><span data-ttu-id="c7d44-109">Modifications apportées à Core HR</span><span class="sxs-lookup"><span data-stu-id="c7d44-109">Changes in Core HR</span></span> 
<span data-ttu-id="c7d44-110">**Version 8.1.2146**</span><span class="sxs-lookup"><span data-stu-id="c7d44-110">**Build 8.1.2146**</span></span>

### <a name="employee-fixed-compensation-entity-doesnt-export-all-records"></a><span data-ttu-id="c7d44-111">L'entité de rémunération fixe des employés n'exporte pas tous les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="c7d44-111">Employee fixed compensation entity doesn't export all records</span></span>
<span data-ttu-id="c7d44-112">Avec cette modification, l'entité **Rémunération fixe des employés** exporte désormais tous les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="c7d44-112">With this change, the **Employee fixed compensation** entity will now export all records.</span></span> <span data-ttu-id="c7d44-113">L'entité peut être utilisée pour créer et mettre à jour les enregistrements de rémunération fixe pour les employés.</span><span class="sxs-lookup"><span data-stu-id="c7d44-113">The entity can be used to create and update existing fixed compensation records for employees.</span></span> 

### <a name="employment-end-date-doesnt-honor-employee-preferred-time-zone-settings"></a><span data-ttu-id="c7d44-114">La date de fin de contrat ne respecte pas les paramètres de fuseau horaire préférés de l'employé.</span><span class="sxs-lookup"><span data-stu-id="c7d44-114">Employment end date doesn't honor employee preferred time zone settings</span></span>
<span data-ttu-id="c7d44-115">Les dates de fin de contrat respectent maintenant le fuseau horaire préféré de l'utilisateur au début ou à la fin d'un emploi au sein d'une société.</span><span class="sxs-lookup"><span data-stu-id="c7d44-115">Employment end dates are now honoring the user-preferred time zone when creating or ending employment with a company.</span></span>
 
### <a name="uk-addresses-display-in-analytics-as-eastern-switzerland-addresses"></a><span data-ttu-id="c7d44-116">Les adresses britanniques s'affichent dans les analyses comme des adresses de Suisse orientale.</span><span class="sxs-lookup"><span data-stu-id="c7d44-116">UK addresses display in Analytics as Eastern Switzerland addresses</span></span>
<span data-ttu-id="c7d44-117">Dans cette version, une modification a été apportée pour corriger le défaut d'adéquation des adresses dans l'état « Comptage des effectifs par site » de la **Gestion du personnel**.</span><span class="sxs-lookup"><span data-stu-id="c7d44-117">In this release, a change has been made to correct misalignment in addresses in the **Personnel Management** "Headcount by location" report.</span></span>
 
### <a name="termination-code-is-not-populated-on-the-worker-position-assignment-record-when-ending-the-position"></a><span data-ttu-id="c7d44-118">Le code de fin n'est pas renseigné sur l'enregistrement de l'affectation du poste de l'employé à la fin du contrat.</span><span class="sxs-lookup"><span data-stu-id="c7d44-118">Termination code is not populated on the worker position assignment record when ending the position</span></span>
<span data-ttu-id="c7d44-119">Une modification a été apportée pour définir par défaut le code « Motif de fin de contrat » à la fin de l'affectation du poste des employés.</span><span class="sxs-lookup"><span data-stu-id="c7d44-119">A change has been made to default the "Termination reason" code when ending the employees position assignment.</span></span>

### <a name="new-entity-created-for-job-compensation-levels"></a><span data-ttu-id="c7d44-120">Nouvelle entité créée pour les niveaux de rémunération des postes</span><span class="sxs-lookup"><span data-stu-id="c7d44-120">New entity created for job compensation levels</span></span>
<span data-ttu-id="c7d44-121">Une nouvelle entité de l'infrastructure de gestion des données a été créée.</span><span class="sxs-lookup"><span data-stu-id="c7d44-121">A new data management framework (DMF) entity was created.</span></span> <span data-ttu-id="c7d44-122">L'entité propose la création et les mises à jour des niveaux de rémunération, des valeurs marchandes et des informations d'enquête pour chaque tâche définie dans le système.</span><span class="sxs-lookup"><span data-stu-id="c7d44-122">The entity provides for creation and updates to compensation levels, market values, and survey information for each job defined in the system.</span></span>
