---
title: Collaborateurs chargés d'approuver les non-conformités
description: Cette rubrique décrit comment configurer les collaborateurs chargés d'approuver les non-conformités.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5979cb33146a00c3ea49ada9577140b24c07928f
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956657"
---
# <a name="workers-responsible-for-approving-nonconformances"></a><span data-ttu-id="e22dd-103">Collaborateurs chargés d'approuver les non-conformités</span><span class="sxs-lookup"><span data-stu-id="e22dd-103">Workers responsible for approving nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e22dd-104">Cette rubrique décrit comment configurer les collaborateurs chargés d'approuver les non-conformités.</span><span class="sxs-lookup"><span data-stu-id="e22dd-104">This topic describes how to configure workers that are responsible for approving nonconformances.</span></span>

<span data-ttu-id="e22dd-105">Les non-conformités doivent être approuvées avant que les utilisateurs puissent commencer à saisir des détails tels que des corrections ou des opérations.</span><span class="sxs-lookup"><span data-stu-id="e22dd-105">Nonconformances must be approved before users can start to enter details such as corrections or operations.</span></span> <span data-ttu-id="e22dd-106">Avant que les utilisateurs puissent approuver ou rejeter les non-conformités, leur ID utilisateur (enregistrement d'utilisateur) doit être lié à un enregistrement de collaborateur.</span><span class="sxs-lookup"><span data-stu-id="e22dd-106">Before users can approve or reject nonconformances, their user ID (user record) must be linked to a worker record.</span></span> <span data-ttu-id="e22dd-107">Vous pouvez éventuellement configurer des collaborateurs responsables de la qualité, puis autoriser un collaborateur à approuver le travail au nom d'un autre collaborateur.</span><span class="sxs-lookup"><span data-stu-id="e22dd-107">You can optionally configure workers that are responsible for quality and then allow one worker to approve work on behalf of another worker.</span></span>

## <a name="enable-a-user-for-nonconformance-processing"></a><span data-ttu-id="e22dd-108">Activer un utilisateur pour le traitement de non-conformité</span><span class="sxs-lookup"><span data-stu-id="e22dd-108">Enable a user for nonconformance processing</span></span>

<span data-ttu-id="e22dd-109">Avant qu'un utilisateur puisse approuver ou rejeter les non-conformités, vous devez lier son enregistrement utilisateur à un enregistrement de collaborateur.</span><span class="sxs-lookup"><span data-stu-id="e22dd-109">Before a user can approve or reject nonconformances, you must link their user record to a worker record.</span></span> <span data-ttu-id="e22dd-110">Les champs d'approbation peuvent ensuite être définis automatiquement et l'utilisateur actuel peut être automatiquement renseigné pour la feuille de temps.</span><span class="sxs-lookup"><span data-stu-id="e22dd-110">The approval fields can then be automatically set, and the current user can be automatically filled in for the timesheet.</span></span> <span data-ttu-id="e22dd-111">Avant que l'utilisateur puisse utiliser les notes du document, vous devez activer la gestion des documents dans les options d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e22dd-111">Before the user can use the document notes, you must activate document handling in their user options.</span></span>

1. <span data-ttu-id="e22dd-112">Accédez à **Administration système \> Utilisateurs \> Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="e22dd-112">Go to **System administration \> Users \> Users**.</span></span>
1. <span data-ttu-id="e22dd-113">Recherchez et ouvrez l'utilisateur qui devrait être en mesure d'approuver ou de rejeter les non-conformités.</span><span class="sxs-lookup"><span data-stu-id="e22dd-113">Find and open the user who should be able to approve or reject nonconformances.</span></span>
1. <span data-ttu-id="e22dd-114">Définissez le champ **Personne** sur le nom du collaborateur associé à l'enregistrement utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="e22dd-114">Set the **Person** field to the name of the worker that is related to the current user record.</span></span>
1. <span data-ttu-id="e22dd-115">Dans le volet Actions, sélectionnez **Options utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="e22dd-115">On the Action Pane, select **User options**.</span></span>
1. <span data-ttu-id="e22dd-116">Sur la page **Options** de l'enregistrement utilisateur actuel, sur l'onglet **Préférences**, définissez l'option **Activer la gestion des documents** sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="e22dd-116">On the **Options** page for the current user record, on the **Preferences** tab, set the **Enable document handling** option to *Yes*.</span></span>
1. <span data-ttu-id="e22dd-117">Fermez les pages.</span><span class="sxs-lookup"><span data-stu-id="e22dd-117">Close the pages.</span></span>

## <a name="define-workers-that-are-responsible-for-quality"></a><span data-ttu-id="e22dd-118">Définir les collaborateurs responsables de la qualité</span><span class="sxs-lookup"><span data-stu-id="e22dd-118">Define workers that are responsible for quality</span></span>

1. <span data-ttu-id="e22dd-119">Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Collaborateurs responsables de la qualité**.</span><span class="sxs-lookup"><span data-stu-id="e22dd-119">Go to **Inventory management \> Setup \> Quality control \> Workers responsible for quality**.</span></span>
2. <span data-ttu-id="e22dd-120">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e22dd-120">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="e22dd-121">Dans le champ **Collaborateur**, sélectionnez le collaborateur qui entre les données de qualité.</span><span class="sxs-lookup"><span data-stu-id="e22dd-121">In the **Worker** field, select the worker that enters quality data.</span></span>
4. <span data-ttu-id="e22dd-122">Dans le champ **Responsable du collaborateur**, sélectionnez le collaborateur au nom duquel le collaborateur sélectionné effectue le travail.</span><span class="sxs-lookup"><span data-stu-id="e22dd-122">In the **Worker responsible** field, select the worker that the selected worker enters work on behalf of.</span></span> <span data-ttu-id="e22dd-123">Lorsque des non-conformités sont créées et mises à jour, ce collaborateur sera entré par défaut dans les champs **Collaborateurs**.</span><span class="sxs-lookup"><span data-stu-id="e22dd-123">When nonconformances are created and updated, this worker will be entered by default in **Worker** fields.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e22dd-124">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e22dd-124">Additional resources</span></span>

- [<span data-ttu-id="e22dd-125">Vue d’ensemble de la gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="e22dd-125">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="e22dd-126">Activer la gestion de la qualité et de la non-conformité</span><span class="sxs-lookup"><span data-stu-id="e22dd-126">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="e22dd-127">Frais de qualité</span><span class="sxs-lookup"><span data-stu-id="e22dd-127">Quality charges</span></span>](quality-charges.md)
- [<span data-ttu-id="e22dd-128">Zones de contrôle pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="e22dd-128">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="e22dd-129">Types de diagnostic pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="e22dd-129">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="e22dd-130">Frais de qualité pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="e22dd-130">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="e22dd-131">Opérations pour les non-conformités</span><span class="sxs-lookup"><span data-stu-id="e22dd-131">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="e22dd-132">Gestion de la qualité pour les processus d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="e22dd-132">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
