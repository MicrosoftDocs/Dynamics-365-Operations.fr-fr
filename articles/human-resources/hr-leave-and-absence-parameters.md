---
title: Configuration des paramètres de congé et d'absence
description: Définissez les paramètres des ressources humaines pour les congés et les absences dans Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2acb8502ebcab122a0a1ff21e9f5e23931026327
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008997"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="fcfe9-103">Configuration des paramètres de congé et d'absence</span><span class="sxs-lookup"><span data-stu-id="fcfe9-103">Configure leave and absence parameters</span></span>

<span data-ttu-id="fcfe9-104">Avant de configurer des plans de congé et d'absence dans Dynamics 365 Human Resources, il est judicieux de vérifier la configuration de tous les paramètres des ressources humaines associés, notamment :</span><span class="sxs-lookup"><span data-stu-id="fcfe9-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="fcfe9-105">Souche de numéros pour les demandes de congé</span><span class="sxs-lookup"><span data-stu-id="fcfe9-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="fcfe9-106">Paramètres relatifs au Family Medical and Leave Act (FMLA)</span><span class="sxs-lookup"><span data-stu-id="fcfe9-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="fcfe9-107">Paramètres en libre-service des employés pour les demandes de congé et d'absence</span><span class="sxs-lookup"><span data-stu-id="fcfe9-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="fcfe9-108">Paramètres de congé et d'absence</span><span class="sxs-lookup"><span data-stu-id="fcfe9-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="fcfe9-109">Afficher et modifier les paramètres des ressources humaines</span><span class="sxs-lookup"><span data-stu-id="fcfe9-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="fcfe9-110">Dans la page **Plans de congé et d'absence**, sélectionnez l'onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="fcfe9-111">Sous **Configuration**, sélectionnez **Paramètres des ressources humaines**.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="fcfe9-112">Sur l'onglet **Souches de numéros**, vérifiez le **Code souche de N°** pour **ID de demande de congé** et changez si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="fcfe9-113">Ce paramètre détermine la souche utilisée pour attribuer automatiquement les ID aux demandes de congé.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="fcfe9-114">Sur l'onglet **FMLA**, vérifiez les paramètres FMLA et modifiez-les si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="fcfe9-115">Sur l'onglet **Libre-service employé**, indiquez si les gestionnaires peuvent saisir des demandes de congé et d'absence au nom de leurs employés.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

6. <span data-ttu-id="fcfe9-116">Sur l'onglet **Types de congé et d'absence**, vérifiez les paramètres FMLA et modifiez-les si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-116">On the **Leave and absence** tab, verify the settings and change as necessary.</span></span>

7. <span data-ttu-id="fcfe9-117">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-117">Select **Save**.</span></span>

## <a name="configure-calendar-parameters"></a><span data-ttu-id="fcfe9-118">Configurer les paramètres de calendrier</span><span class="sxs-lookup"><span data-stu-id="fcfe9-118">Configure calendar parameters</span></span>

<span data-ttu-id="fcfe9-119">Si vous avez activé la fonction d'aperçu du calendrier des congés et des absences, vous devez configurer des paramètres supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-119">If you have enabled the Leave and absence calendar preview feature, you need to configure additional parameters.</span></span> 

[!include [banner](includes/preview-feature-leave-absence.md)]

> [!NOTE]
> <span data-ttu-id="fcfe9-120">Pour la version préliminaire du 3 février 2020, seules les **Demandes de congé en attente** sont activées.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-120">For the preview release on February 3, 2020, only **Pending leave requests** are enabled.</span></span>

1. <span data-ttu-id="fcfe9-121">Dans la page **Plans de congé et d'absence**, sélectionnez l'onglet **Liens**.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-121">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="fcfe9-122">Sous **Configuration**, sélectionnez **Paramètres des ressources humaines**.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-122">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="fcfe9-123">Sur l'onglet **Calendrier**, modifiez les paramètres de calendrier si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-123">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="fcfe9-124">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="fcfe9-124">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="fcfe9-125">Voir également :</span><span class="sxs-lookup"><span data-stu-id="fcfe9-125">See also</span></span>

- [<span data-ttu-id="fcfe9-126">Vue d'ensemble des congés et des absences</span><span class="sxs-lookup"><span data-stu-id="fcfe9-126">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
