---
title: Flux de travail de client
description: Cette rubrique fournit des informations sur le flux de travail de client. Vous pouvez modifier des champs spécifiques à un client puis envoyer les modifications pour approbation à l’aide du flux de travail avant de les ajouter au client.
author: mikefalkner
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: c769d225ee0f7b35719c37d9b9bc690a20060911
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817267"
---
# <a name="customer-workflow"></a><span data-ttu-id="cee72-104">Flux de travail de client</span><span class="sxs-lookup"><span data-stu-id="cee72-104">Customer workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cee72-105">Le flux de travail de client a été ajouté à la version 8.0.4.</span><span class="sxs-lookup"><span data-stu-id="cee72-105">The customer workflow has been added to version 8.0.4.</span></span> <span data-ttu-id="cee72-106">Vous pouvez modifier des champs spécifiques à un client puis envoyer les modifications pour approbation à l’aide du flux de travail avant de les ajouter au client.</span><span class="sxs-lookup"><span data-stu-id="cee72-106">You can change specific fields for a customer and then send those changes for approval by using the workflow before they are added to the customer.</span></span>

## <a name="set-up-the-customer-workflow"></a><span data-ttu-id="cee72-107">Paramétrer le flux de travail de client</span><span class="sxs-lookup"><span data-stu-id="cee72-107">Set up the customer workflow</span></span>

<span data-ttu-id="cee72-108">Avant de pouvoir utiliser la fonctionnalité de flux de travail de client, vous devez l’activer.</span><span class="sxs-lookup"><span data-stu-id="cee72-108">Before you can use the customer workflow feature, you must enable it.</span></span>

1. <span data-ttu-id="cee72-109">Accédez à **Comptabilité client \> Configuration \> Paramètres de la comptabilité client**.</span><span class="sxs-lookup"><span data-stu-id="cee72-109">Go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="cee72-110">Dans l’onglet **Général**, sous le raccourci **Approbation du client**, définissez l’option **Activer les approbations de client** sur **Oui** pour activer la fonction.</span><span class="sxs-lookup"><span data-stu-id="cee72-110">On the **General** tab, on the **Customer approval** FastTab, set the **Enable customer approvals** option to **Yes** to enable the feature.</span></span>
3. <span data-ttu-id="cee72-111">Dans le champ **Comportement de l’entité de données**, sélectionnez le comportement que les entités de données doivent adopter lorsque les données sont importées :</span><span class="sxs-lookup"><span data-stu-id="cee72-111">In the **Data entity behavior** field, select the behavior that the data entities should use when data is imported:</span></span>

    - <span data-ttu-id="cee72-112">**Autoriser les modifications sans approbation** : Une entité peut mettre à jour l’enregistrement client sans le traiter via le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="cee72-112">**Allow changes without approval** – An entity can update the customer record without processing it through the workflow.</span></span>
    - <span data-ttu-id="cee72-113">**Rejeter les modifications** : Il est impossible d’apporter des modifications à cet enregistrement client.</span><span class="sxs-lookup"><span data-stu-id="cee72-113">**Reject changes** – Changes can't be made to the customer record.</span></span> <span data-ttu-id="cee72-114">L’importation échouera pour les champs activés pour le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="cee72-114">The import will fail for the fields that are enabled for the workflow.</span></span>
    - <span data-ttu-id="cee72-115">**Créer des propositions de modification** : Tous les champs seront modifiés à l’exception des champs activés pour le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="cee72-115">**Create change proposals** – All fields will be changed except the fields that are enabled for the workflow.</span></span> <span data-ttu-id="cee72-116">Les nouvelles valeurs de ces champs seront proposées au client en tant que modifications et le flux de travail sera lancé automatiquement.</span><span class="sxs-lookup"><span data-stu-id="cee72-116">The new values for those fields will be added to the customer as proposed changes, and the workflow will be started automatically.</span></span>

4. <span data-ttu-id="cee72-117">Dans la liste des champs du client, activez la case à cocher **Activer** pour chaque champ qui doit être approuvé avant que les modifications soient appliquées.</span><span class="sxs-lookup"><span data-stu-id="cee72-117">In the list of customer fields, select then **Enable** check box for every field that must be approved before the changes can be made.</span></span>
5. <span data-ttu-id="cee72-118">Accédez à **Comptabilité client \> Configuration \> Flux de travail de la comptabilité client**.</span><span class="sxs-lookup"><span data-stu-id="cee72-118">Go to **Accounts receivable \> Setup \> Accounts receivable workflows**.</span></span>
6. <span data-ttu-id="cee72-119">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="cee72-119">Select **New**.</span></span>
7. <span data-ttu-id="cee72-120">Sélectionnez **Flux de travail des modifications proposées du client**.</span><span class="sxs-lookup"><span data-stu-id="cee72-120">Select **Proposed customer change workflow**.</span></span> 
8. <span data-ttu-id="cee72-121">Paramétrez le flux de travail afin qu’il corresponde à votre processus d’approbation.</span><span class="sxs-lookup"><span data-stu-id="cee72-121">Set up the workflow so that it matches your approval process.</span></span> <span data-ttu-id="cee72-122">L’élément d’approbation de flux de travail **Approbation de flux de travail pour la modification proposée du client** appliquera les modifications au client.</span><span class="sxs-lookup"><span data-stu-id="cee72-122">The **Workflow approval for proposed customer change** workflow approval element will apply the changes to the customer.</span></span>

## <a name="change-customer-information-and-submit-the-changes-to-the-workflow"></a><span data-ttu-id="cee72-123">Modifier les informations client et envoyer les modifications au flux de travail</span><span class="sxs-lookup"><span data-stu-id="cee72-123">Change customer information and submit the changes to the workflow</span></span>

<span data-ttu-id="cee72-124">Lorsque vous modifiez un champ qui est activé pour le flux de travail, la page **Modifications proposées** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="cee72-124">When you change a field that is enabled for the workflow, the **Proposed changes** page appears.</span></span> <span data-ttu-id="cee72-125">Cette page affiche la valeur initiale du champ et la nouvelle valeur entrée.</span><span class="sxs-lookup"><span data-stu-id="cee72-125">This page shows the original value of the field and the new value that you entered.</span></span> <span data-ttu-id="cee72-126">Le champ que vous avez modifié est rétabli sur sa valeur d’origine.</span><span class="sxs-lookup"><span data-stu-id="cee72-126">The field that you changed is reverted to its original value.</span></span> <span data-ttu-id="cee72-127">Un message de statut dans la page vous informe que vos modifications n’ont pas été soumises.</span><span class="sxs-lookup"><span data-stu-id="cee72-127">A status message on the page informs you that your changes haven't been submitted.</span></span>

<span data-ttu-id="cee72-128">Chaque fois que vous modifiez un champ qui est activé pour le flux de travail, il est ajouté à la liste des modifications proposées.</span><span class="sxs-lookup"><span data-stu-id="cee72-128">Every time that you change a field that is enabled for the workflow, that field is added to the list of proposed changes.</span></span> <span data-ttu-id="cee72-129">Pour ignorer la valeur proposée pour un champ, utilisez le bouton **Ignorer** en regard du champ dans la liste.</span><span class="sxs-lookup"><span data-stu-id="cee72-129">To discard the proposed value for a field, use the **Discard** button next to the field in the list.</span></span> <span data-ttu-id="cee72-130">Pour ignorer toutes les modifications, utilisez le bouton **Ignorer toutes les modifications** en bas de la page.</span><span class="sxs-lookup"><span data-stu-id="cee72-130">To discard all changes, use the **Discard all change** button at the bottom of the page.</span></span> <span data-ttu-id="cee72-131">Cliquez sur **OK** pour fermer la page.</span><span class="sxs-lookup"><span data-stu-id="cee72-131">Select **OK** to close the page.</span></span>

<span data-ttu-id="cee72-132">Une fois que vous avez au moins une modification proposée, deux menus supplémentaires apparaissent dans le volet Actions : **Modifications proposées** et **Flux de travail**.</span><span class="sxs-lookup"><span data-stu-id="cee72-132">After you have at least one proposed change, two additional menus appear on the Action Pane: **Proposed changes** and **Workflow**.</span></span>

1. <span data-ttu-id="cee72-133">Sélectionnez **Modifications proposées** pour ouvrir la page **Modifications proposées** et consulter vos modifications.</span><span class="sxs-lookup"><span data-stu-id="cee72-133">Select **Proposed changes** to open the **Proposed changes** page and review your changes.</span></span>
2. <span data-ttu-id="cee72-134">Sélectionnez **Flux de travail \> Soumettre** pour envoyer les modifications au flux de travail.</span><span class="sxs-lookup"><span data-stu-id="cee72-134">Select **Workflow \> Submit** to submit the changes to the workflow.</span></span>

    <span data-ttu-id="cee72-135">Le statut dans la page est remplacé par **Modifications en attente d’approbation**.</span><span class="sxs-lookup"><span data-stu-id="cee72-135">The status on the page is changed to **Changes pending approval**.</span></span>

<span data-ttu-id="cee72-136">Le flux de travail suit le processus de flux de travail standard dans l’application.</span><span class="sxs-lookup"><span data-stu-id="cee72-136">The workflow follows the standard workflow process in the application.</span></span> <span data-ttu-id="cee72-137">L’approbateur est dirigé vers la page **Client**, où les modifications peuvent être vérifiées sur la page **Modifications proposées**, puis il doit sélectionner **Flux de travail \> Approuver** pour approuver le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="cee72-137">The approver is directed to the **Customer** page where the changes can be reviewed on the **Proposed changes** page and then select **Workflow \> Approve** to approve the workflow.</span></span> <span data-ttu-id="cee72-138">Une fois toutes les approbations effectuées, les champs sont mis à jour avec les valeurs que vous avez proposées.</span><span class="sxs-lookup"><span data-stu-id="cee72-138">After all approvals are completed, the fields are updated with the values that you proposed.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]