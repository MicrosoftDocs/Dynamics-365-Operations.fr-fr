---
title: Codes étape de vague
description: Cette rubrique fournit une vue d'ensemble des codes étape de vague et de leur utilisation.
author: josaw1
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0f89c6098db9e2e3a9aa4ee3666e4b9ae608f054
ms.sourcegitcommit: d8f1135cdbc2deca70bc4b2805a0519253c9a31f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2019
ms.locfileid: "1992355"
---
# <a name="wave-step-codes"></a><span data-ttu-id="acc8f-103">Codes étape de vague</span><span class="sxs-lookup"><span data-stu-id="acc8f-103">Wave step codes</span></span>

[!include [banner](../includes/preview-banner.md)]
[!include [banner](../includes/banner.md)]

## <a name="about-wave-step-codes"></a><span data-ttu-id="acc8f-104">À propos des codes étape de vague</span><span class="sxs-lookup"><span data-stu-id="acc8f-104">About wave step codes</span></span>

<span data-ttu-id="acc8f-105">Les codes étape de vague désignent des codes que les utilisateurs peuvent paramétrer et utiliser pour lier des instances spécifiques de méthodes de vague à un modèle correspondant.</span><span class="sxs-lookup"><span data-stu-id="acc8f-105">Wave step codes are codes that users can set up and use to link specific instances of wave methods to a corresponding template.</span></span> <span data-ttu-id="acc8f-106">Parmi les modèles figurent des modèles pour le réapprovisionnement, la mise en conteneur, l'impression d'étiquettes, la création de chargement et le tri.</span><span class="sxs-lookup"><span data-stu-id="acc8f-106">The templates include templates for replenishment, containerization, label printing, load building, and sorting.</span></span>

<span data-ttu-id="acc8f-107">Lorsque les codes étape de vague ne sont pas utilisés, les utilisateurs doivent saisir un texte libre en référence à un modèle spécifique depuis l'instance de la méthode de vague.</span><span class="sxs-lookup"><span data-stu-id="acc8f-107">When wave step codes aren't used, users must enter free text to reference a specific template from the wave method instance.</span></span> <span data-ttu-id="acc8f-108">Le texte libre est enclin aux erreurs, car les utilisateurs doivent veiller à ce que le texte de l'étape de vague qu'ils ajoutent pour une méthode d'étape de vague spécifique dans un modèle de vague corresponde exactement au texte d'étape de vague dans le modèle cible.</span><span class="sxs-lookup"><span data-stu-id="acc8f-108">Free text is prone to error, because users must make sure that the wave step text that they add for a specific wave step method in a wave template exactly matches the wave step text in the target template.</span></span>

<span data-ttu-id="acc8f-109">Les codes étape de vague pour un type d'étape de vague spécifique sont configurés sur une page à part.</span><span class="sxs-lookup"><span data-stu-id="acc8f-109">Wave step codes for a specific wave step type are set up on a separate page.</span></span> <span data-ttu-id="acc8f-110">Pour chaque instance de méthode d'étape de vague dans un modèle de vague qui exige un code étape de vague, il convient de sélectionner ce dernier dans une liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="acc8f-110">For every wave step method instance in a wave template that requires a wave step code, the wave step code must be selected in a drop-down list.</span></span> <span data-ttu-id="acc8f-111">La sélection dans une liste déroulante remplace la saisie de texte libre et permet de réduire le risque et l'impact d'erreurs humaines.</span><span class="sxs-lookup"><span data-stu-id="acc8f-111">Selection in a drop-down list replaces free text entry and helps reduce the risk and impact of human error.</span></span> <span data-ttu-id="acc8f-112">Les codes de configuration sont utilisés pour associer une méthode d'étape de vague dans un modèle de vague à un modèle cible pour la méthode.</span><span class="sxs-lookup"><span data-stu-id="acc8f-112">Setup codes are used to link a wave step method in a wave template to a target template for the method.</span></span>

> [!NOTE]
> <span data-ttu-id="acc8f-113">L'utilisation de la fonctionnalité de codes étape de vague est facultative, et la prise en charge se fait par entité juridique.</span><span class="sxs-lookup"><span data-stu-id="acc8f-113">Use of the wave step codes feature is optional, and uptake is per legal entity.</span></span> <span data-ttu-id="acc8f-114">Par conséquent, si une entité juridique spécifique utilise la fonctionnalité, tous les codes étape de vague d'une entité juridique sont mis à niveau vers la nouvelle structure.</span><span class="sxs-lookup"><span data-stu-id="acc8f-114">Therefore, if a specific legal entity uses the feature, all existing wave step codes in that legal entity are upgraded to the new structure.</span></span>

## <a name="setup-demo"></a><span data-ttu-id="acc8f-115">Démonstration de paramétrage</span><span class="sxs-lookup"><span data-stu-id="acc8f-115">Setup demo</span></span> 

<span data-ttu-id="acc8f-116">Pour cette démonstration, il convient d'avoir des données de démonstration installées, et vous utiliserez l'entreprise de données de démonstration **USMF**.</span><span class="sxs-lookup"><span data-stu-id="acc8f-116">For this demo, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="enable-wave-step-codes"></a><span data-ttu-id="acc8f-117">Activer les codes étape de vague</span><span class="sxs-lookup"><span data-stu-id="acc8f-117">Enable wave step codes</span></span>

<span data-ttu-id="acc8f-118">Procédez comme suit pour activer la fonctionnalité des codes étape de vague.</span><span class="sxs-lookup"><span data-stu-id="acc8f-118">Follow these steps to turn on the wave step codes feature.</span></span>

1. <span data-ttu-id="acc8f-119">Accédez à **Gestion des entrepôts \> Configuration \> Paramètres de gestion des entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="acc8f-119">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
2. <span data-ttu-id="acc8f-120">Sous l'onglet **Général**, dans l'organisateur **Traitement de vague**, définissez l'option **Activer les codes étape de vague** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="acc8f-120">On the **General** tab, on the **Wave processing** FastTab, set the **Enable wave step codes** option to **Yes**.</span></span>

<span data-ttu-id="acc8f-121">Tous les textes libres d'étape de vague existants sont mis à niveau vers la nouvelle structure.</span><span class="sxs-lookup"><span data-stu-id="acc8f-121">All existing wave step free texts are upgraded to the new structure.</span></span> <span data-ttu-id="acc8f-122">Une fois cette mise à niveau terminée pour une entité juridique, l'option **Activer les codes étape de vague** n'est plus disponible sur la page **Paramètres de gestion des entrepôts**.</span><span class="sxs-lookup"><span data-stu-id="acc8f-122">After this upgrade is completed for a legal entity, the **Enable wave step codes** option is no longer available on the **Warehouse management parameters** page.</span></span>

<span data-ttu-id="acc8f-123">Les validations sont effectuées pendant la mise à niveau, et si la mise à niveau est un échec, vous recevez un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="acc8f-123">Validations are done during the upgrade, and if the upgrade fails, you receive an error message.</span></span> <span data-ttu-id="acc8f-124">Une mise à niveau risque d'échouer en raison des conflits suivants :</span><span class="sxs-lookup"><span data-stu-id="acc8f-124">An upgrade might fail because of the following conflicts:</span></span>

- <span data-ttu-id="acc8f-125">Des doublons de texte libre d'étape de vague existent.</span><span class="sxs-lookup"><span data-stu-id="acc8f-125">Duplicate wave step free texts exist.</span></span>
- <span data-ttu-id="acc8f-126">Des personnalisations existent.</span><span class="sxs-lookup"><span data-stu-id="acc8f-126">Customizations exist.</span></span>
- <span data-ttu-id="acc8f-127">Un texte libre d'étape de vague associé à une instance de méthode d'étape de vague ne correspond pas au type de modèle prévu.</span><span class="sxs-lookup"><span data-stu-id="acc8f-127">A wave step free text that is associated with a wave step method instance doesn't match the expected template type.</span></span>

<span data-ttu-id="acc8f-128">Après avoir corrigé les conflits identifiés au cours des validations, vous pouvez relancer le processus de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="acc8f-128">After you've resolved any conflicts that are identified during the validations, you can rerun the upgrade process.</span></span>

<span data-ttu-id="acc8f-129">Une fois la mise à niveau validée, la page **Codes étape de vague** (**Gestion des entrepôts \> Configuration \> Vagues \> Codes étape de vague**) est disponible.</span><span class="sxs-lookup"><span data-stu-id="acc8f-129">When the upgrade succeeds, the **Wave step codes** page (**Warehouse management \> Setup \> Waves \> Wave step codes**) becomes available.</span></span> <span data-ttu-id="acc8f-130">Cette page affiche les codes étape de vague mis à niveau lorsque la fonction des codes étape de vague a été activée.</span><span class="sxs-lookup"><span data-stu-id="acc8f-130">This page lists the wave step codes that were upgraded when the wave step codes feature was turned on.</span></span>

### <a name="create-new-wave-step-codes"></a><span data-ttu-id="acc8f-131">Créer des codes étape de vague</span><span class="sxs-lookup"><span data-stu-id="acc8f-131">Create new wave step codes</span></span>

<span data-ttu-id="acc8f-132">Vous pouvez utiliser la page **Codes étape de vague** pour créer et supprimer des codes étape de vague.</span><span class="sxs-lookup"><span data-stu-id="acc8f-132">You can use the **Wave step codes** page to create and delete wave step codes.</span></span>

<span data-ttu-id="acc8f-133">Chaque nouveau code étape de vague et son ID associé doivent être uniques dans tous les types d'étape de vague et doivent être définis pour un type d'étape de vague spécifique.</span><span class="sxs-lookup"><span data-stu-id="acc8f-133">Every new wave step code and its associated ID must be unique across all wave step types, and they must be defined for a specific wave step type.</span></span>

### <a name="apply-wave-step-codes"></a><span data-ttu-id="acc8f-134">Appliquer les codes étape de vague</span><span class="sxs-lookup"><span data-stu-id="acc8f-134">Apply wave step codes</span></span>

<span data-ttu-id="acc8f-135">Après avoir défini les codes étape de vague appropriés, ils peuvent être appliqués aux méthodes de processus de vague.</span><span class="sxs-lookup"><span data-stu-id="acc8f-135">After you've defined the appropriate wave step codes, they can be applied to the wave process methods.</span></span>

<span data-ttu-id="acc8f-136">Pour appliquer des codes étape de vague, accédez au modèle cible approprié.</span><span class="sxs-lookup"><span data-stu-id="acc8f-136">To apply wave step codes, go to the appropriate target template.</span></span> <span data-ttu-id="acc8f-137">Voici les modèles cibles sur lesquels les codes étape de vague sont désignés :</span><span class="sxs-lookup"><span data-stu-id="acc8f-137">Here are the target templates that the wave step codes are designated to point to:</span></span>

- <span data-ttu-id="acc8f-138">**Modèles de réapprovisionnement :** Gestion des entrepôts \> Configuration \> Réapprovisionnement \> Modèles de réapprovisionnement</span><span class="sxs-lookup"><span data-stu-id="acc8f-138">**Replenishment templates:** Warehouse management \> Setup \> Replenishment \> Replenishment templates</span></span>
- <span data-ttu-id="acc8f-139">**Modèles de création de chargement :** Gestion des entrepôts \> Configuration \> Chargement \> Modèles de création de chargement</span><span class="sxs-lookup"><span data-stu-id="acc8f-139">**Load build templates:** Warehouse management \> Setup \> Load \> Load build templates</span></span>
- <span data-ttu-id="acc8f-140">**Modèles de tri :** Gestion des entrepôts \> Configuration \> Emballage \> Modèles de tri sortants</span><span class="sxs-lookup"><span data-stu-id="acc8f-140">**Sort templates:** Warehouse management \> Setup \> Packing \> Outbound sorting templates</span></span>
- <span data-ttu-id="acc8f-141">**Modèles de mise en conteneur :** Gestion des entrepôts \> Configuration \> Conteneurs \> Modèles de création de conteneur</span><span class="sxs-lookup"><span data-stu-id="acc8f-141">**Containerization templates:** Warehouse management \> Setup \> Containers \> Container build templates</span></span>
- <span data-ttu-id="acc8f-142">**Modèles d'impression d'étiquette :** Gestion des entrepôts \> Configuration \> Acheminement des documents \> Modèles d'étiquette de vague</span><span class="sxs-lookup"><span data-stu-id="acc8f-142">**Label printing templates:** Warehouse management \> Setup \> Document routing \> Wave label templates</span></span>

<span data-ttu-id="acc8f-143">Les modèles de cette liste sont appliqués lorsqu'ils font référence à une méthode de traitement par vague sélectionnée dans un modèle de vague.</span><span class="sxs-lookup"><span data-stu-id="acc8f-143">The templates in this list are applied when they are referenced from a wave process method that is selected in a wave template.</span></span> <span data-ttu-id="acc8f-144">Lorsque le code étape de vague sur une méthode de traitement par vague dans un modèle de vague correspond au code étape de vague dans un des types de modèle, le modèle est appliqué.</span><span class="sxs-lookup"><span data-stu-id="acc8f-144">When the wave step code on a wave process method in a wave template matches the wave step code in one of the templates types, the template is applied.</span></span>

### <a name="sample-scenario"></a><span data-ttu-id="acc8f-145">Exemple de scénario</span><span class="sxs-lookup"><span data-stu-id="acc8f-145">Sample scenario</span></span>

<span data-ttu-id="acc8f-146">La procédure suivante permet de garantir que le modèle de réapprovisionnement que vous avez créé sera appliqué au modèle de vague.</span><span class="sxs-lookup"><span data-stu-id="acc8f-146">The following procedure helps guarantee that the replenishment template that you created will be applied for the wave template.</span></span>

1. <span data-ttu-id="acc8f-147">Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Codes étape de vague**, puis créez un code étape de vague de type **Réapprovisionnement**.</span><span class="sxs-lookup"><span data-stu-id="acc8f-147">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**, and create a wave step code for the **Replenishment** type.</span></span>
2. <span data-ttu-id="acc8f-148">Accédez à **Gestion des entrepôts \> Configuration \> Réapprovisionnement \> Modèles de réapprovisionnement**, et créez un modèle de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="acc8f-148">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**, and create a replenishment template.</span></span>
3. <span data-ttu-id="acc8f-149">Dans le modèle de réapprovisionnement, sélectionnez le code étape de vague créé pour le type **Réapprovisionnement**.</span><span class="sxs-lookup"><span data-stu-id="acc8f-149">In the replenishment template, select the wave step code that you created for the **Replenishment** type.</span></span>
4. <span data-ttu-id="acc8f-150">Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**, puis sélectionnez le modèle de vague que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="acc8f-150">Go to **Warehouse management \> Setup \> Waves \> Wave templates**, and select the wave template that you intend to use.</span></span>
5. <span data-ttu-id="acc8f-151">Dans le modèle, sous l'organisateur **Méthodes**, sélectionnez la méthode **Réapprovisionnement**.</span><span class="sxs-lookup"><span data-stu-id="acc8f-151">In the template, on the **Methods** FastTab, select the **Replenishment** method.</span></span>
6. <span data-ttu-id="acc8f-152">Dans le champ **Code étape de vague**, sélectionnez le code étape de vague que vous avez sélectionné dans le modèle de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="acc8f-152">In the **Wave step code** field, select the wave step code that you selected in the replenishment template.</span></span>
