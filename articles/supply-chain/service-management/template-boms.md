---
title: "Nomenclatures des modèles"
description: "Une nomenclature des modèles permet d'avoir une liste normalisée des composants d'objets de service traités régulièrement."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 6e3a16b9938f6d4222e0a95078356f457e71a1bb
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="template-boms"></a><span data-ttu-id="1107b-103">Nomenclatures des modèles</span><span class="sxs-lookup"><span data-stu-id="1107b-103">Template BOMs</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="1107b-104">Une nomenclature des modèles permet d'avoir une liste normalisée des composants d'objets de service traités régulièrement.</span><span class="sxs-lookup"><span data-stu-id="1107b-104">A template bill of materials (BOM) provides you with a standardized list of components for service objects that are serviced regularly.</span></span> <span data-ttu-id="1107b-105">Les composants figurant dans la nomenclature des modèles représentent les sous-composants individuels de l'objet de service.</span><span class="sxs-lookup"><span data-stu-id="1107b-105">The components that are listed in the template BOM represent the individual subcomponents of the service object.</span></span> <span data-ttu-id="1107b-106">En appliquant la nomenclature des modèles à un objet de service, vous pouvez conserver un enregistrement des sous-composants remplacés sur l'objet de service.</span><span class="sxs-lookup"><span data-stu-id="1107b-106">By applying a template BOM to a service object, you can keep a record of the subcomponents that have been replaced on the service object.</span></span>

<span data-ttu-id="1107b-107">Pour appliquer une nomenclature des modèles à un accord de service ou une commande de service, vous associez celle-ci à une relation d'objets de service.</span><span class="sxs-lookup"><span data-stu-id="1107b-107">To apply a template BOM to a service agreement or a service order, you attach it to a service object relation.</span></span>


> [!NOTE]
> <P><span data-ttu-id="1107b-108">Vous ne pouvez appliquer qu'une seule nomenclature des modèles à un objet de service.</span><span class="sxs-lookup"><span data-stu-id="1107b-108">You can apply only one template BOM to a service object.</span></span></P>

## <a name="create-a-template-bom"></a><span data-ttu-id="1107b-109">Création d'un modèle de nomenclature</span><span class="sxs-lookup"><span data-stu-id="1107b-109">Create a template BOM</span></span>

<span data-ttu-id="1107b-110">Le tableau suivant contient des informations sur les différentes méthodes qui permettent de créer une nomenclature des modèles.</span><span class="sxs-lookup"><span data-stu-id="1107b-110">The following table contains information about the various methods that you can use to create a template BOM.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1107b-111">Méthode</span><span class="sxs-lookup"><span data-stu-id="1107b-111">Method</span></span></p></th>
<th><p><span data-ttu-id="1107b-112">Description </span><span class="sxs-lookup"><span data-stu-id="1107b-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1107b-113">Production</span><span class="sxs-lookup"><span data-stu-id="1107b-113">Production</span></span></p></td>
<td><p><span data-ttu-id="1107b-114">La nomenclature des modèles est basée sur un ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="1107b-114">The template BOM is based on a production order.</span></span> <span data-ttu-id="1107b-115">Cette option s'applique uniquement si vous opérez dans un environnement de production.</span><span class="sxs-lookup"><span data-stu-id="1107b-115">This option is applicable only if you operate in a production environment.</span></span> <span data-ttu-id="1107b-116">Cette méthode permet d'avoir une liste détaillée et actualisée des composants d'un article.</span><span class="sxs-lookup"><span data-stu-id="1107b-116">The benefit is that you have a current, detailed listing of the components that make up an item.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1107b-117">Article BOM</span><span class="sxs-lookup"><span data-stu-id="1107b-117">Item BOM</span></span></p></td>
<td><p><span data-ttu-id="1107b-118">La nomenclature des modèles est basée sur un article de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="1107b-118">The template BOM is based on an item BOM.</span></span> <span data-ttu-id="1107b-119">La nomenclature des articles, à la différence de la nomenclature de production, est une liste statique des composants qui constituent un article.</span><span class="sxs-lookup"><span data-stu-id="1107b-119">The item BOM, unlike the production BOM, is a static list of the components that make up an item.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1107b-120">Modèle existant</span><span class="sxs-lookup"><span data-stu-id="1107b-120">Existing template</span></span></p></td>
<td><p><span data-ttu-id="1107b-121">Le modèle est basé sur une nomenclature des modèles existante.</span><span class="sxs-lookup"><span data-stu-id="1107b-121">The template is based on an existing template BOM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1107b-122">Manuel</span><span class="sxs-lookup"><span data-stu-id="1107b-122">Manual</span></span></p></td>
<td><p><span data-ttu-id="1107b-123">Si vous connaissez les pièces généralement remplacées dans un objet de service, vous pouvez créer votre nomenclature des modèles manuellement.</span><span class="sxs-lookup"><span data-stu-id="1107b-123">If you know what spare parts are typically replaced on a service object, you can create your template BOM manually.</span></span> <span data-ttu-id="1107b-124">Si vous utilisez cette approche, assurez-vous que les composants inclus dans le modèle reflètent les besoins réels de votre lieu de travail.</span><span class="sxs-lookup"><span data-stu-id="1107b-124">This method helps make sure that the components that are included in the template reflect the actual requirements of your workplace.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="apply-the-template-bom-to-a-service-agreement-or-service-order"></a><span data-ttu-id="1107b-125">Appliquer la nomenclature des modèles à un accord de service ou une commande de service</span><span class="sxs-lookup"><span data-stu-id="1107b-125">Apply the template BOM to a service agreement or service order</span></span>

<span data-ttu-id="1107b-126">Vous pouvez appliquer la nomenclature des modèles à un accord de service et/ou à une commande de service.</span><span class="sxs-lookup"><span data-stu-id="1107b-126">You can apply a template BOM to a service agreement, a service order, or both.</span></span> <span data-ttu-id="1107b-127">L'accord de service couvre généralement une relation de long terme avec un client.</span><span class="sxs-lookup"><span data-stu-id="1107b-127">The service agreement usually covers a long-term relationship with a customer.</span></span> <span data-ttu-id="1107b-128">L'historique des remplacements enregistré dans la nomenclature des services constitue des données utiles pour l'accord de service.</span><span class="sxs-lookup"><span data-stu-id="1107b-128">The history of replacements that is recorded in the service BOM is useful data to have for the service agreement.</span></span>

<span data-ttu-id="1107b-129">Vous pouvez également appliquer une nomenclature des modèles à une commande de service pour enregistrer l'historique du service qui a été réalisé sur un objet de service.</span><span class="sxs-lookup"><span data-stu-id="1107b-129">You can also apply a template BOM to a service order to record the history of the service that has been performed on a service object.</span></span>

## <a name="copy-the-history-of-a-service-bom"></a><span data-ttu-id="1107b-130">Copier l'historique d'une nomenclature des services</span><span class="sxs-lookup"><span data-stu-id="1107b-130">Copy the history of a service BOM</span></span>

<span data-ttu-id="1107b-131">Vous pouvez copier l'historique d'une ligne de nomenclature des services d'un accord de service vers un autre accord de service.</span><span class="sxs-lookup"><span data-stu-id="1107b-131">You can copy the history of a service BOM line from one service agreement to another service agreement.</span></span> <span data-ttu-id="1107b-132">En copiant l'historique des services entre des accords de service, vous pouvez conserver l'enregistrement des remplacements effectués sur un article.</span><span class="sxs-lookup"><span data-stu-id="1107b-132">By copying the service history between service agreements, you can preserve the record of replacements for an item.</span></span>

<span data-ttu-id="1107b-133">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="1107b-133">**Example**</span></span>

<span data-ttu-id="1107b-134">Vous avez défini un accord de service de trois ans pour le véhicule d'un client.</span><span class="sxs-lookup"><span data-stu-id="1107b-134">You have set up a three-year service agreement for a customer's car.</span></span> <span data-ttu-id="1107b-135">Pendant cette période, le client s'habitue à l'excellence du service offert par la société.</span><span class="sxs-lookup"><span data-stu-id="1107b-135">During that period, the customer becomes accustomed to the good service that the company provides.</span></span> <span data-ttu-id="1107b-136">Par conséquent, une fois l'accord expiré, le client souhaite en paramétrer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="1107b-136">Therefore, after the agreement expires, the customer wants to set up a new one.</span></span> <span data-ttu-id="1107b-137">Vous êtes désormais en mesure de négocier un accord plus avantageux pour la société.</span><span class="sxs-lookup"><span data-stu-id="1107b-137">You are now able to negotiate a more favorable agreement for the company.</span></span> <span data-ttu-id="1107b-138">Comme l'enregistrement des composants remplacés peut s'avérer utile à l'avenir, vous copiez l'historique de la nomenclature des services vers le nouvel accord.</span><span class="sxs-lookup"><span data-stu-id="1107b-138">Because the record of replaced components might be useful in the future, you copy the history of the service BOM to the new agreement.</span></span>

## <a name="modify-the-template-bom"></a><span data-ttu-id="1107b-139">Modifier la nomenclature des modèles</span><span class="sxs-lookup"><span data-stu-id="1107b-139">Modify the template BOM</span></span>

<span data-ttu-id="1107b-140">Si une nomenclature des modèles n'a pas été associée à un objet de service, vous pouvez modifier ou supprimer les lignes associées.</span><span class="sxs-lookup"><span data-stu-id="1107b-140">If a template BOM has not been attached to a service object, you can modify or delete lines in it.</span></span> <span data-ttu-id="1107b-141">Une fois la nomenclature des modèles associée à un objet de service, vous pouvez seulement modifier la version locale de la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="1107b-141">After the template BOM is attached to a service object, you can modify only the local version of the BOM.</span></span> <span data-ttu-id="1107b-142">Si vous voulez copier le paramétrage de la version locale d'une nomenclature des modèles, vous pouvez créer une nomenclature des modèles basée sur la version locale.</span><span class="sxs-lookup"><span data-stu-id="1107b-142">If you want to duplicate the setup of a local version of a template BOM, you can create a new template BOM based on the local version.</span></span> <span data-ttu-id="1107b-143">Pour plus d'informations, voir [Modifier une nomenclature des services](modify-service-bom.md).</span><span class="sxs-lookup"><span data-stu-id="1107b-143">For more information, see [Modify a Service BOM](modify-service-bom.md).</span></span>

<span data-ttu-id="1107b-144">Si vous remplacez un article dans la nomenclature, vous pouvez enregistrer le remplacement dans la ligne de nomenclature dans le concepteur de nomenclatures.</span><span class="sxs-lookup"><span data-stu-id="1107b-144">If you replace an item in the BOM, you can register the replacement on the BOM line in the BOM designer.</span></span> <span data-ttu-id="1107b-145">Facultatif : vous pouvez créer une ligne de commande de service pour l'objet de remplacement.</span><span class="sxs-lookup"><span data-stu-id="1107b-145">Optionally, you can create a service order line for the replacement object.</span></span> <span data-ttu-id="1107b-146">Si vous créez une ligne de commande de service, vous pouvez facturer l'article de remplacement.</span><span class="sxs-lookup"><span data-stu-id="1107b-146">If you create a service order line, you can invoice the replacement item.</span></span> <span data-ttu-id="1107b-147">Si vous ne créez pas de ligne de commande de service pour un remplacement, l'enregistrement du remplacement est conservé à des fins de suivi de l'historique de l'objet de service.</span><span class="sxs-lookup"><span data-stu-id="1107b-147">If you do not create a service order line for a replacement, the replacement registration is kept to track the history of the service object.</span></span>

## <a name="change-how-information-on-the-bom-line-is-displayed"></a><span data-ttu-id="1107b-148">Modifier l'affichage des informations de la ligne de nomenclature</span><span class="sxs-lookup"><span data-stu-id="1107b-148">Change how information on the BOM line is displayed</span></span>

<span data-ttu-id="1107b-149">Vous pouvez modifier le mode d'affichage des informations de ligne de nomenclature pour toutes les nomenclatures des modèles et des services.</span><span class="sxs-lookup"><span data-stu-id="1107b-149">You can change the way that information on the BOM line is displayed for all template and service BOMs.</span></span> <span data-ttu-id="1107b-150">Les modifications sont appliquées à l'ensemble des nomenclatures des modèles et des services.</span><span class="sxs-lookup"><span data-stu-id="1107b-150">The changes are applied to all template BOMs and service BOMs.</span></span> <span data-ttu-id="1107b-151">Y compris celles associées aux objets de service.</span><span class="sxs-lookup"><span data-stu-id="1107b-151">This includes those that are attached to service objects.</span></span>

## <a name="set-up-number-sequences-for-template-boms"></a><span data-ttu-id="1107b-152">Paramétrer des souches de numéros pour les nomenclatures des modèles</span><span class="sxs-lookup"><span data-stu-id="1107b-152">Set up number sequences for template BOMs</span></span>

<span data-ttu-id="1107b-153">Pour utiliser les nomenclatures des modèles, vous devez paramétrer deux souches de numéros.</span><span class="sxs-lookup"><span data-stu-id="1107b-153">To use template BOMs, you must set up two number sequences.</span></span> <span data-ttu-id="1107b-154">Paramétrez une souche de numéros pour la nomenclature des modèles et une souche de numéros pour le numéro de ligne d'historique de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="1107b-154">Set up one number sequence for the template BOM and one for the BOM history line number.</span></span>


> [!NOTE]
> <P><span data-ttu-id="1107b-155">Les souches de numéros sont utilisées dans l'ensemble de Microsoft Dynamics AX pour attribuer des identificateurs aux enregistrements qui en ont besoin.</span><span class="sxs-lookup"><span data-stu-id="1107b-155">Number sequences are used throughout Microsoft Dynamics AX to allocate identifiers to records that require them.</span></span> <span data-ttu-id="1107b-156">Avant de pouvoir affecter une souche de numéros à une nomenclature des modèles ou une ligne d'historique de nomenclature, vous devez paramétrer des codes souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="1107b-156">Before you can assign a number sequence to a template BOM or a BOM history line number, you must set up number sequences codes.</span></span></P>


## <a name="set-up-number-sequences"></a><span data-ttu-id="1107b-157">Définir des souches de numéros</span><span class="sxs-lookup"><span data-stu-id="1107b-157">Set up number sequences</span></span>

1.  <span data-ttu-id="1107b-158">Dans la page de liste **Souches de numéros**, créez des souches de numéros pour les nomenclatures des modèles et le numéro de ligne d'historique de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="1107b-158">On the **Number sequences** list page, create number sequences for template BOMs and the BOM history line number.</span></span> 

2.  <span data-ttu-id="1107b-159">Cliquez sur **Gestion des services** \> **Paramétrage** \> **Paramètres de gestion des services**.</span><span class="sxs-lookup"><span data-stu-id="1107b-159">Click **Service management** \> **Setup** \> **Service management parameters**.</span></span>

3.  <span data-ttu-id="1107b-160">Cliquez sur **Souches de numéros**, puis sélectionnez un code souche de numéros pour les références de souches de numéros créées dans l'écran **Souches de numéros**.</span><span class="sxs-lookup"><span data-stu-id="1107b-160">Click **Number sequences**, and then select a number sequence code for the number sequence references that you created in the **Number sequences** form.</span></span>

4.  <span data-ttu-id="1107b-161">Fermez l'écran pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="1107b-161">Close the form to save your changes.</span></span>


> [!NOTE]
> <P><span data-ttu-id="1107b-162">Le numéro de ligne d'historique de nomenclature est utilisé par le système pour associer les transactions dans l'historique de nomenclature avec un accord ou une commande de service.</span><span class="sxs-lookup"><span data-stu-id="1107b-162">The BOM history line number is used by the system to associate the transactions in the BOM history with a service agreement or service order.</span></span> <span data-ttu-id="1107b-163">Le numéro n'est pas affiché dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1107b-163">The number is not displayed in the user interface.</span></span></P>



## <a name="see-also"></a><span data-ttu-id="1107b-164">Voir également :</span><span class="sxs-lookup"><span data-stu-id="1107b-164">See also</span></span>

[<span data-ttu-id="1107b-165">Création d'un modèle de nomenclature</span><span class="sxs-lookup"><span data-stu-id="1107b-165">Create a template BOM</span></span>](create-template-bom.md)

[<span data-ttu-id="1107b-166">Gestion des modèles de nomenclatures sur des relations d'objets</span><span class="sxs-lookup"><span data-stu-id="1107b-166">Manage template BOMs on object relations</span></span>](manage-template-boms-on-object-relations.md)

[<span data-ttu-id="1107b-167">Modifier une nomenclature des services</span><span class="sxs-lookup"><span data-stu-id="1107b-167">Modify a Service BOM</span></span>](modify-service-bom.md)

 



