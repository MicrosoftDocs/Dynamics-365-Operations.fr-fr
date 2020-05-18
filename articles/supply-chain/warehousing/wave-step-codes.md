---
title: Codes étape de vague
description: Cette rubrique fournit une vue d'ensemble des codes étape de vague et de leur utilisation.
author: josaw1
manager: tfehr
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 251e9982451c888424589e0f0d6fce48aab42df1
ms.sourcegitcommit: 68092ed283bfbb7b6f611cce1b62c791f9b6a208
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2020
ms.locfileid: "3323575"
---
# <a name="wave-step-codes"></a><span data-ttu-id="78f0c-103">Codes étape de vague</span><span class="sxs-lookup"><span data-stu-id="78f0c-103">Wave step codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="78f0c-104">Les codes étape de vague désignent des codes que les utilisateurs peuvent paramétrer et utiliser pour lier des instances spécifiques de méthodes de vague à un modèle correspondant.</span><span class="sxs-lookup"><span data-stu-id="78f0c-104">Wave step codes are codes that users can set up and use to link specific instances of wave methods to a corresponding template.</span></span> <span data-ttu-id="78f0c-105">Parmi les modèles figurent des modèles pour le réapprovisionnement, la mise en conteneur, l'impression d'étiquettes, la création de chargement et le tri.</span><span class="sxs-lookup"><span data-stu-id="78f0c-105">The templates include templates for replenishment, containerization, label printing, load building, and sorting.</span></span>

<span data-ttu-id="78f0c-106">Lorsque les codes étape de vague ne sont pas utilisés, les utilisateurs doivent saisir un texte libre en référence à un modèle spécifique depuis l'instance de la méthode de vague.</span><span class="sxs-lookup"><span data-stu-id="78f0c-106">When wave step codes aren't used, users must enter free text to reference a specific template from the wave method instance.</span></span> <span data-ttu-id="78f0c-107">Le texte libre est enclin aux erreurs, car les utilisateurs doivent veiller à ce que le texte de l'étape de vague qu'ils ajoutent pour une méthode d'étape de vague spécifique dans un modèle de vague corresponde exactement au texte d'étape de vague dans le modèle cible.</span><span class="sxs-lookup"><span data-stu-id="78f0c-107">Free text is prone to errors because users must make sure that the wave step text that they add for a specific wave step method in a wave template exactly matches the wave step text in the target template.</span></span>

<span data-ttu-id="78f0c-108">Les codes étape de vague pour un type d'étape de vague spécifique sont configurés sur une page à part.</span><span class="sxs-lookup"><span data-stu-id="78f0c-108">Wave step codes for a specific wave step type are set up on a separate page.</span></span> <span data-ttu-id="78f0c-109">Pour chaque instance de méthode d'étape de vague dans un modèle de vague qui exige un code étape de vague, il convient de sélectionner ce dernier dans une liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="78f0c-109">For every wave step method instance in a wave template that requires a wave step code, the wave step code must be selected in a drop-down list.</span></span> <span data-ttu-id="78f0c-110">La sélection dans une liste déroulante remplace la saisie de texte libre et permet de réduire le risque et l'impact d'erreurs humaines.</span><span class="sxs-lookup"><span data-stu-id="78f0c-110">Selection in a drop-down list replaces free text entry and helps reduce the risk and impact of human error.</span></span> <span data-ttu-id="78f0c-111">Les codes de configuration sont utilisés pour associer une méthode d'étape de vague dans un modèle de vague à un modèle cible pour la méthode.</span><span class="sxs-lookup"><span data-stu-id="78f0c-111">Setup codes are used to link a wave step method in a wave template to a target template for the method.</span></span>

> [!NOTE]
> <span data-ttu-id="78f0c-112">L'utilisation de la fonction de codes d'étapes de vague est facultative.</span><span class="sxs-lookup"><span data-stu-id="78f0c-112">Use of the wave step codes feature is optional.</span></span> <span data-ttu-id="78f0c-113">Elle est activé à l'échelle de l'organisation pour toutes les entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="78f0c-113">It is enabled organization-wide for all legal entities.</span></span>

## <a name="setup-demo"></a><span data-ttu-id="78f0c-114">Démonstration de paramétrage</span><span class="sxs-lookup"><span data-stu-id="78f0c-114">Setup demo</span></span> 

<span data-ttu-id="78f0c-115">Pour cette démonstration, il convient d'avoir des données de démonstration installées, et vous utiliserez l'entreprise de données de démonstration **USMF**.</span><span class="sxs-lookup"><span data-stu-id="78f0c-115">For this demo, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="enable-wave-step-codes"></a><span data-ttu-id="78f0c-116">Activer les codes étape de vague</span><span class="sxs-lookup"><span data-stu-id="78f0c-116">Enable wave step codes</span></span>

<span data-ttu-id="78f0c-117">Procédez comme suit pour activer la fonctionnalité des codes étape de vague.</span><span class="sxs-lookup"><span data-stu-id="78f0c-117">Follow these steps to turn on the wave step codes feature.</span></span>

1. <span data-ttu-id="78f0c-118">Accédez à **Gestion des fonctions**.</span><span class="sxs-lookup"><span data-stu-id="78f0c-118">Go to **Feature Management**.</span></span>
2. <span data-ttu-id="78f0c-119">Sélectionnez pour activer la fonction appelée **Code d'étape de vague à l'échelle de l'organisation**.</span><span class="sxs-lookup"><span data-stu-id="78f0c-119">Select to enable the feature called **Organization-wide Wave Step Code**.</span></span>

<span data-ttu-id="78f0c-120">Tous les textes libres d'étape de vague existant dans toutes les entités juridiques sont mis à niveau vers la nouvelle structure.</span><span class="sxs-lookup"><span data-stu-id="78f0c-120">All existing wave step free texts in all legal entities are upgraded to the new structure.</span></span> <span data-ttu-id="78f0c-121">Une fois cette mise à niveau terminée pour toutes les entités juridiques, la fonctionnalité est activée.</span><span class="sxs-lookup"><span data-stu-id="78f0c-121">After this upgrade is completed for all legal entities, then the feature is enabled.</span></span> <span data-ttu-id="78f0c-122">Si la fonctionnalité ne peut pas être activée pour une ou plusieurs entités juridiques, alors la fonctionnalité n'est activée pour aucune entité juridique.</span><span class="sxs-lookup"><span data-stu-id="78f0c-122">If the feature cannot be enabled for one or more legal entities, then the feature is not enabled for any legal entities.</span></span>

<span data-ttu-id="78f0c-123">Pendant l'activation, les validations sont effectuées pendant la mise à niveau des données.</span><span class="sxs-lookup"><span data-stu-id="78f0c-123">During the enablement, validations are done during the data upgrade.</span></span> <span data-ttu-id="78f0c-124">Si la mise à niveau échoue, vous recevez un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="78f0c-124">If the upgrade fails, you receive an error message.</span></span> <span data-ttu-id="78f0c-125">Une mise à niveau risque d'échouer en raison des conflits suivants :</span><span class="sxs-lookup"><span data-stu-id="78f0c-125">An upgrade might fail because of the following conflicts:</span></span>

- <span data-ttu-id="78f0c-126">Des doublons de texte libre d'étape de vague existent.</span><span class="sxs-lookup"><span data-stu-id="78f0c-126">Duplicate wave step free texts exist.</span></span>
- <span data-ttu-id="78f0c-127">Des personnalisations existent.</span><span class="sxs-lookup"><span data-stu-id="78f0c-127">Customizations exist.</span></span>
- <span data-ttu-id="78f0c-128">Un texte libre d'étape de vague associé à une instance de méthode d'étape de vague ne correspond pas au type de modèle prévu.</span><span class="sxs-lookup"><span data-stu-id="78f0c-128">A wave step free text that is associated with a wave step method instance doesn't match the expected template type.</span></span>

<span data-ttu-id="78f0c-129">Après avoir corrigé les conflits identifiés au cours des validations, vous pouvez réessayer d'activer la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="78f0c-129">After you've resolved any conflicts that are identified during the validations, you can retry to enable the feature.</span></span>

<span data-ttu-id="78f0c-130">Une fois la fonctionnalité validée, la page **Codes étape de vague** (**Gestion des entrepôts \> Configuration \> Vagues \> Codes étape de vague**) est disponible.</span><span class="sxs-lookup"><span data-stu-id="78f0c-130">When the feature has been enabled, the **Wave step codes** page (**Warehouse management \> Setup \> Waves \> Wave step codes**) becomes available.</span></span> <span data-ttu-id="78f0c-131">Cette page affiche les codes étape de vague mis à niveau lorsque la fonction Codes étape de vague à l'échelle de l'organisation a été activée.</span><span class="sxs-lookup"><span data-stu-id="78f0c-131">This page lists the wave step codes that were upgraded when the Organization-wide Wave Step Code feature was enabled.</span></span>

### <a name="create-new-wave-step-codes"></a><span data-ttu-id="78f0c-132">Créer des codes étape de vague</span><span class="sxs-lookup"><span data-stu-id="78f0c-132">Create new wave step codes</span></span>

<span data-ttu-id="78f0c-133">Vous pouvez utiliser la page **Codes étape de vague** pour créer et supprimer des codes étape de vague.</span><span class="sxs-lookup"><span data-stu-id="78f0c-133">You can use the **Wave step codes** page to create and delete wave step codes.</span></span>

<span data-ttu-id="78f0c-134">Chaque nouveau code étape de vague et son ID associé doivent être uniques dans tous les types d'étape de vague et doivent être définis pour un type d'étape de vague spécifique.</span><span class="sxs-lookup"><span data-stu-id="78f0c-134">Every new wave step code and its associated ID must be unique across all wave step types, and they must be defined for a specific wave step type.</span></span>

### <a name="apply-wave-step-codes"></a><span data-ttu-id="78f0c-135">Appliquer les codes étape de vague</span><span class="sxs-lookup"><span data-stu-id="78f0c-135">Apply wave step codes</span></span>

<span data-ttu-id="78f0c-136">Après avoir défini les codes étape de vague appropriés, ils peuvent être appliqués aux méthodes de processus de vague.</span><span class="sxs-lookup"><span data-stu-id="78f0c-136">After you've defined the appropriate wave step codes, they can be applied to the wave process methods.</span></span>

<span data-ttu-id="78f0c-137">Pour appliquer des codes étape de vague, accédez au modèle cible approprié.</span><span class="sxs-lookup"><span data-stu-id="78f0c-137">To apply wave step codes, go to the appropriate target template.</span></span> <span data-ttu-id="78f0c-138">Voici les modèles cibles sur lesquels les codes étape de vague sont désignés :</span><span class="sxs-lookup"><span data-stu-id="78f0c-138">Here are the target templates that the wave step codes are designated to point to:</span></span>

- <span data-ttu-id="78f0c-139">**Modèles de réapprovisionnement :** Gestion des entrepôts \> Configuration \> Réapprovisionnement \> Modèles de réapprovisionnement</span><span class="sxs-lookup"><span data-stu-id="78f0c-139">**Replenishment templates:** Warehouse management \> Setup \> Replenishment \> Replenishment templates</span></span>
- <span data-ttu-id="78f0c-140">**Modèles de création de chargement :** Gestion des entrepôts \> Configuration \> Chargement \> Modèles de création de chargement</span><span class="sxs-lookup"><span data-stu-id="78f0c-140">**Load build templates:** Warehouse management \> Setup \> Load \> Load build templates</span></span>
- <span data-ttu-id="78f0c-141">**Modèles de tri :** Gestion des entrepôts \> Configuration \> Emballage \> Modèles de tri sortants</span><span class="sxs-lookup"><span data-stu-id="78f0c-141">**Sort templates:** Warehouse management \> Setup \> Packing \> Outbound sorting templates</span></span>
- <span data-ttu-id="78f0c-142">**Modèles de mise en conteneur :** Gestion des entrepôts \> Configuration \> Conteneurs \> Modèles de création de conteneur</span><span class="sxs-lookup"><span data-stu-id="78f0c-142">**Containerization templates:** Warehouse management \> Setup \> Containers \> Container build templates</span></span>
- <span data-ttu-id="78f0c-143">**Modèles d'impression d'étiquette :** Gestion des entrepôts \> Configuration \> Acheminement des documents \> Modèles d'étiquette de vague</span><span class="sxs-lookup"><span data-stu-id="78f0c-143">**Label printing templates:** Warehouse management \> Setup \> Document routing \> Wave label templates</span></span>

<span data-ttu-id="78f0c-144">Les modèles de cette liste sont appliqués lorsqu'ils font référence à une méthode de traitement par vague sélectionnée dans un modèle de vague.</span><span class="sxs-lookup"><span data-stu-id="78f0c-144">The templates in this list are applied when they are referenced from a wave process method that is selected in a wave template.</span></span> <span data-ttu-id="78f0c-145">Lorsque le code étape de vague sur une méthode de traitement par vague dans un modèle de vague correspond au code étape de vague dans un des types de modèle, le modèle est appliqué.</span><span class="sxs-lookup"><span data-stu-id="78f0c-145">When the wave step code on a wave process method in a wave template matches the wave step code in one of the templates types, the template is applied.</span></span>

### <a name="sample-scenario"></a><span data-ttu-id="78f0c-146">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="78f0c-146">Sample scenario</span></span>

<span data-ttu-id="78f0c-147">La procédure suivante permet de garantir que le modèle de réapprovisionnement que vous avez créé sera appliqué au modèle de vague.</span><span class="sxs-lookup"><span data-stu-id="78f0c-147">The following procedure helps guarantee that the replenishment template that you created will be applied for the wave template.</span></span>

1. <span data-ttu-id="78f0c-148">Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Codes étape de vague**, puis créez un code étape de vague de type **Réapprovisionnement**.</span><span class="sxs-lookup"><span data-stu-id="78f0c-148">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**, and create a wave step code for the **Replenishment** type.</span></span>
2. <span data-ttu-id="78f0c-149">Accédez à **Gestion des entrepôts \> Configuration \> Réapprovisionnement \> Modèles de réapprovisionnement**, et créez un modèle de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="78f0c-149">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**, and create a replenishment template.</span></span>
3. <span data-ttu-id="78f0c-150">Dans le modèle de réapprovisionnement, sélectionnez le code étape de vague créé pour le type **Réapprovisionnement**.</span><span class="sxs-lookup"><span data-stu-id="78f0c-150">In the replenishment template, select the wave step code that you created for the **Replenishment** type.</span></span>
4. <span data-ttu-id="78f0c-151">Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**, puis sélectionnez le modèle de vague que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="78f0c-151">Go to **Warehouse management \> Setup \> Waves \> Wave templates**, and select the wave template that you intend to use.</span></span>
5. <span data-ttu-id="78f0c-152">Dans le modèle, sous l'organisateur **Méthodes**, sélectionnez la méthode **Réapprovisionnement**.</span><span class="sxs-lookup"><span data-stu-id="78f0c-152">In the template, on the **Methods** FastTab, select the **Replenishment** method.</span></span>
6. <span data-ttu-id="78f0c-153">Dans le champ **Code étape de vague**, sélectionnez le code étape de vague que vous avez sélectionné dans le modèle de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="78f0c-153">In the **Wave step code** field, select the wave step code that you selected in the replenishment template.</span></span>

<span data-ttu-id="78f0c-154">Vous effectuez ces étapes pour chaque entité juridique.</span><span class="sxs-lookup"><span data-stu-id="78f0c-154">You perform these steps for each legal entity.</span></span>
