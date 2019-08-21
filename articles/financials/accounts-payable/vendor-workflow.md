---
title: Workflow de fournisseur
description: Modifiez les informations du fournisseur et utilisez un workflow pour les approuver.
author: mikefalkner
manager: annbe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Vendor
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 112f9d6adeee583a63da8ab700d7adc179de2c1d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835308"
---
# <a name="vendor-workflow"></a><span data-ttu-id="80bd5-103">Workflow de fournisseur</span><span class="sxs-lookup"><span data-stu-id="80bd5-103">Vendor workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="80bd5-104">Lorsque le workflow de fournisseur est utilisé, les modifications apportées à des champs spécifiques sont envoyées au workflow pour approbation avant d'être ajoutées au fournisseur.</span><span class="sxs-lookup"><span data-stu-id="80bd5-104">When the vendor workflow is used, changes that are made to specific fields are sent to the workflow for approval before they are added to the vendor.</span></span>

## <a name="set-up-the-vendor-workflow"></a><span data-ttu-id="80bd5-105">Paramétrer le workflow de fournisseur</span><span class="sxs-lookup"><span data-stu-id="80bd5-105">Set up the vendor workflow</span></span>

<span data-ttu-id="80bd5-106">Avant de pouvoir utiliser la fonctionnalité de workflow, vous devez l'activer.</span><span class="sxs-lookup"><span data-stu-id="80bd5-106">Before you can use the workflow feature, you must enable it.</span></span>

1. <span data-ttu-id="80bd5-107">Allez dans **Comptabilité fournisseur \> Paramètres \> Paramètres de la comptabilité fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="80bd5-107">Go to **Accounts payable \> Setup \> Accounts payable parameters**.</span></span>
2. <span data-ttu-id="80bd5-108">Sous l'onglet **Général**, dans l'organisateur **Approbation du fournisseur**, définissez l'option **Activer les approbations de fournisseur** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="80bd5-108">On the **General** tab, on the **Vendor approval** FastTab, set the **Enable vendor approvals** option to **Yes**.</span></span>
3. <span data-ttu-id="80bd5-109">Dans le champ **Comportement de l'entité de données**, sélectionnez le comportement à adopter lorsque les données sont importées :</span><span class="sxs-lookup"><span data-stu-id="80bd5-109">In the **Data entity behavior** field, select the behavior that should be used when data is imported:</span></span>

    - <span data-ttu-id="80bd5-110">**Autoriser les modifications sans approbation** – L'entité de données peut mettre à jour l'enregistrement fournisseur sans le traiter via le workflow.</span><span class="sxs-lookup"><span data-stu-id="80bd5-110">**Allow changes without approval** – The data entity can update the vendor record without processing it through the workflow.</span></span>
    - <span data-ttu-id="80bd5-111">**Rejeter les modifications** – Il est impossible d'apporter des modifications à cet enregistrement fournisseur.</span><span class="sxs-lookup"><span data-stu-id="80bd5-111">**Reject changes** – Changes can't be made to the vendor record.</span></span> <span data-ttu-id="80bd5-112">L'importation échouera pour les champs activés pour le workflow.</span><span class="sxs-lookup"><span data-stu-id="80bd5-112">The import will fail for the fields that are enabled for the workflow.</span></span>
    - <span data-ttu-id="80bd5-113">**Créer des propositions de modification** – Tous les champs seront modifiés à l'exception des champs activés pour le workflow.</span><span class="sxs-lookup"><span data-stu-id="80bd5-113">**Create change proposals** – All fields will be changed except the fields that are enabled for the workflow.</span></span> <span data-ttu-id="80bd5-114">Les nouvelles valeurs de ces champs seront proposées au fournisseur en tant que modifications, et le workflow sera lancé automatiquement.</span><span class="sxs-lookup"><span data-stu-id="80bd5-114">The new values for those fields will be added to the vendor as proposed changes, and the workflow will be started automatically.</span></span>

4. <span data-ttu-id="80bd5-115">Dans la liste des champs du fournisseur, activez la case à cocher **Activer** pour chaque champ qui doit être approuvé avant que les modifications soient appliquées.</span><span class="sxs-lookup"><span data-stu-id="80bd5-115">In the list of vendor fields, select the **Enable** check box for every field that must be approved before the changes can be made.</span></span>
5. <span data-ttu-id="80bd5-116">Allez dans **Comptabilité fournisseur \> Paramétrage \> Workflows de la comptabilité fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="80bd5-116">Go to **Accounts payable \> Setup \> Accounts payable workflows**.</span></span>
6. <span data-ttu-id="80bd5-117">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="80bd5-117">Select **New**.</span></span>
7. <span data-ttu-id="80bd5-118">Sélectionnez **Workflow des modifications proposées du fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="80bd5-118">Select **Proposed vendor changes workflow**.</span></span> 
8. <span data-ttu-id="80bd5-119">Paramétrez le workflow afin qu'il corresponde à votre processus d'approbation.</span><span class="sxs-lookup"><span data-stu-id="80bd5-119">Set up the workflow so that it matches your approval process.</span></span> <span data-ttu-id="80bd5-120">L'élément d'approbation de workflow **Approbation de workflow pour la modification proposée du fournisseur** appliquera les modifications au fournisseur.</span><span class="sxs-lookup"><span data-stu-id="80bd5-120">The **Workflow approval for proposed vendor change** workflow approval element will apply the changes to the vendor.</span></span>

## <a name="change-vendor-information-and-submit-the-changes-to-the-workflow"></a><span data-ttu-id="80bd5-121">Modifier les informations du fournisseur et soumettre les modifications au workflow</span><span class="sxs-lookup"><span data-stu-id="80bd5-121">Change vendor information and submit the changes to the workflow</span></span>

<span data-ttu-id="80bd5-122">Lorsque vous modifiez un champ qui est activé pour le workflow, la page **Modifications proposées** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="80bd5-122">When you change a field that is enabled for the workflow, the **Proposed changes** page appears.</span></span> <span data-ttu-id="80bd5-123">Cette page affiche la valeur initiale du champ et la nouvelle valeur entrée.</span><span class="sxs-lookup"><span data-stu-id="80bd5-123">This page shows the original value of the field and the new value that you entered.</span></span> <span data-ttu-id="80bd5-124">Le champ que vous avez modifié est rétabli sur sa valeur d'origine.</span><span class="sxs-lookup"><span data-stu-id="80bd5-124">The field that you changed is reverted to its original value.</span></span> <span data-ttu-id="80bd5-125">Un message de statut vous indique également que vos modifications n'ont pas été soumises.</span><span class="sxs-lookup"><span data-stu-id="80bd5-125">A status message also informs you that your changes haven't been submitted.</span></span> 

<span data-ttu-id="80bd5-126">Chaque fois que vous modifiez un champ qui est activé pour le workflow, il est ajouté à la liste dans la page **Modifications proposées**.</span><span class="sxs-lookup"><span data-stu-id="80bd5-126">Every time that you change a field that is enabled for the workflow, that field is added to the list on the **Proposed changes** page.</span></span> <span data-ttu-id="80bd5-127">Pour ignorer la valeur proposée pour un champ, utilisez le bouton **Ignorer** en regard du champ dans la liste.</span><span class="sxs-lookup"><span data-stu-id="80bd5-127">To discard the proposed value for a field, use the **Discard** button next to the field in the list.</span></span> <span data-ttu-id="80bd5-128">Pour ignorer toutes les modifications, utilisez le bouton **Ignorer toutes les modifications** en bas de la page.</span><span class="sxs-lookup"><span data-stu-id="80bd5-128">To discard all changes, use the **Discard all changes** button at the bottom of the page.</span></span> <span data-ttu-id="80bd5-129">Sélectionnez **OK** pour fermer la page.</span><span class="sxs-lookup"><span data-stu-id="80bd5-129">Select **OK** to close the page.</span></span>

<span data-ttu-id="80bd5-130">Une fois que vous avez au moins une modification proposée, deux onglets supplémentaires apparaissent dans le volet Actions : **Modifications proposées** et **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="80bd5-130">After you have at least one proposed change, two additional tabs appear on the action pane: **Proposed changes** and **Workflow**.</span></span>

1. <span data-ttu-id="80bd5-131">Sélectionnez **Modifications proposées** pour ouvrir la page **Modifications proposées** et consulter vos modifications.</span><span class="sxs-lookup"><span data-stu-id="80bd5-131">Select **Proposed changes** to open the **Proposed changes** page and review your changes.</span></span>
2. <span data-ttu-id="80bd5-132">Sélectionnez **Workflow \> Soumettre pour envoyer les modifications au workflow**.</span><span class="sxs-lookup"><span data-stu-id="80bd5-132">Select **Workflow \> Submit to submit the changes to workflow**.</span></span>

    <span data-ttu-id="80bd5-133">Le statut dans la page est remplacé par **Modifications en attente d'approbation**.</span><span class="sxs-lookup"><span data-stu-id="80bd5-133">The status on the page is changed to **Changes pending approval**.</span></span>

<span data-ttu-id="80bd5-134">Le workflow suit le processus de workflow standard dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="80bd5-134">The workflow follows the standard workflow process in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="80bd5-135">L'approbateur est dirigé vers la page **Fournisseur**, où il peut revoir les modifications sur la page **Modifications proposées**, puis sélectionner **Workflow \> Approuver** pour approuver le workflow.</span><span class="sxs-lookup"><span data-stu-id="80bd5-135">The approver is directed to the **Vendor** page, where he or she can review the changes on the **Proposed changes** page and then select **Workflow \> Approve** to approve the workflow.</span></span> <span data-ttu-id="80bd5-136">Une fois toutes les approbations effectuées, les champs sont mis à jour avec les valeurs que vous avez proposées.</span><span class="sxs-lookup"><span data-stu-id="80bd5-136">After all approvals are completed, the fields are updated with the values that you proposed.</span></span>
