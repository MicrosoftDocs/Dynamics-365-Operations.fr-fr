---
title: Créer des entités juridiques
description: Cette rubrique décrit comment créer des entités juridiques dans Microsoft Dynamics 365 Commerce, qui doit être créé et configuré avant de créer des canaux.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 016b67631a53139d12d65dfaf594f49b030326b1
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478210"
---
# <a name="create-legal-entities"></a><span data-ttu-id="38fb4-103">Créer des entités juridiques</span><span class="sxs-lookup"><span data-stu-id="38fb4-103">Create legal entities</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="38fb4-104">Cette rubrique décrit comment créer des entités juridiques dans Microsoft Dynamics 365 Commerce, qui doit être créé et configuré avant de créer des canaux.</span><span class="sxs-lookup"><span data-stu-id="38fb4-104">This topic describes how to create legal entities in Microsoft Dynamics 365 Commerce, which must be created and configured before creating channels.</span></span>

<span data-ttu-id="38fb4-105">Une entité juridique est une organisation qui dispose d’une structure juridique enregistrée ou légalement déclarée.</span><span class="sxs-lookup"><span data-stu-id="38fb4-105">A legal entity is an organization that has a registered or legislated legal structure.</span></span> <span data-ttu-id="38fb4-106">Les entités juridiques peuvent passer des contrats juridiques et sont tenues de préparer des relevés faisant état de leurs performances.</span><span class="sxs-lookup"><span data-stu-id="38fb4-106">Legal entities can enter into legal contracts and are required to prepare statements that report on their performance.</span></span>

<span data-ttu-id="38fb4-107">Une société est un type d’entité juridique.</span><span class="sxs-lookup"><span data-stu-id="38fb4-107">A company is a type of legal entity.</span></span> <span data-ttu-id="38fb4-108">Actuellement, les entreprises sont les seuls types d’entité juridique que vous pouvez créer et chaque entité juridique est associée à un ID société.</span><span class="sxs-lookup"><span data-stu-id="38fb4-108">Currently, companies are the only kind of legal entity that you can create, and every legal entity is associated with a company ID.</span></span> <span data-ttu-id="38fb4-109">Cette association existe car certaines zones fonctionnelles du programme utilisent un ID société, ou *DataAreaId*, dans leurs modèles de données.</span><span class="sxs-lookup"><span data-stu-id="38fb4-109">This association exists because some functional areas in the program use a company ID, or *DataAreaId*, in their data models.</span></span> <span data-ttu-id="38fb4-110">Dans ces zones fonctionnelles, les sociétés sont utilisées en tant que limite pour la sécurité des données.</span><span class="sxs-lookup"><span data-stu-id="38fb4-110">In these functional areas, companies are used as a boundary for data security.</span></span> <span data-ttu-id="38fb4-111">Les utilisateurs peuvent accéder aux données uniquement pour la société à laquelle ils sont actuellement connectés.</span><span class="sxs-lookup"><span data-stu-id="38fb4-111">Users can access data only for the company that they are currently logged on to.</span></span> 

<span data-ttu-id="38fb4-112">Lors de la création d'un canal, vous devez spécifier à quelle entité juridique appartient ce canal.</span><span class="sxs-lookup"><span data-stu-id="38fb4-112">When creating a channel, you must specify which legal entity that channel belongs to.</span></span>

## <a name="create-a-new-legal-entity"></a><span data-ttu-id="38fb4-113">Créer une entité juridique</span><span class="sxs-lookup"><span data-stu-id="38fb4-113">Create a new legal entity</span></span>

<span data-ttu-id="38fb4-114">Pour créer une entité juridique dans Dynamics 365 Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="38fb4-114">To create a new legal entity in Dynamics 365 Commerce, follow these steps.</span></span>

1. <span data-ttu-id="38fb4-115">Dans le volet de navigation, accédez à **Modules \> Configuration du siège \> Entités juridiques**.</span><span class="sxs-lookup"><span data-stu-id="38fb4-115">In the navigation pane, go to  **Modules \> Headquarters setup \> Legal entities**.</span></span>
1. <span data-ttu-id="38fb4-116">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="38fb4-116">On the action pane, select **New**.</span></span> <span data-ttu-id="38fb4-117">Le volet **Nouvelle entité juridique** s'affiche à droite.</span><span class="sxs-lookup"><span data-stu-id="38fb4-117">The **New legal entity** pane appears on the right.</span></span>
1. <span data-ttu-id="38fb4-118">Dans le champ **Nom**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="38fb4-118">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="38fb4-119">Dans le champ **Société**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="38fb4-119">In the **Company** field, enter a value.</span></span>
1. <span data-ttu-id="38fb4-120">Dans le champ **Pays/Région**, sélectionnez ou entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="38fb4-120">In the **Country/region** field, enter or select a value.</span></span>
1. <span data-ttu-id="38fb4-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="38fb4-121">Select **OK**.</span></span> 

   ![Création d'entité juridique](media/legal-entities.png)

1. <span data-ttu-id="38fb4-123">Dans la section **Général**, indiquez les informations générales suivantes concernant l'entité juridique :</span><span class="sxs-lookup"><span data-stu-id="38fb4-123">In the **General** section, provide the following general information about the legal entity:</span></span> 
   1. <span data-ttu-id="38fb4-124">Entrez un nom de recherche si celui-ci est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="38fb4-124">Enter a search name, if a search name is required.</span></span> <span data-ttu-id="38fb4-125">Il s’agit d’un nom alternatif pouvant être utilisé pour rechercher cette entité juridique.</span><span class="sxs-lookup"><span data-stu-id="38fb4-125">A search name is an alternate name that can be used to search for this legal entity.</span></span> 
   1. <span data-ttu-id="38fb4-126">Choisissez si cette entité juridique est utilisée en tant que société de consolidation.</span><span class="sxs-lookup"><span data-stu-id="38fb4-126">Select whether this legal entity is being used as a consolidation company.</span></span>
   1. <span data-ttu-id="38fb4-127">Choisissez si cette entité juridique est utilisée en tant que société d'élimination.</span><span class="sxs-lookup"><span data-stu-id="38fb4-127">Select whether this legal entity is being used as an elimination company.</span></span> 
   1. <span data-ttu-id="38fb4-128">Sélectionnez la **langue par défaut** pour l'entité.</span><span class="sxs-lookup"><span data-stu-id="38fb4-128">Select the **default language** for the entity.</span></span> 
   1. <span data-ttu-id="38fb4-129">Sélectionnez le **fuseau horaire** pour l'entité.</span><span class="sxs-lookup"><span data-stu-id="38fb4-129">Select the **time zone** for the entity.</span></span>
1. <span data-ttu-id="38fb4-130">Dans la section **Adresses**, sélectionnez **Modifier** pour saisir les informations d'adresse, telles que la rue, le numéro, le code postal et la ville.</span><span class="sxs-lookup"><span data-stu-id="38fb4-130">In the **Addresses** section, select **Edit** to enter address information, such as the street name and number, postal code, and city.</span></span>
1. <span data-ttu-id="38fb4-131">Dans la section **Informations de contact**, entrez les informations relatives aux modes de communication, notamment les adresses e-mail, les URL et les numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="38fb4-131">In the **Contact information** section, enter information about methods of communication, such as email addresses, URLs, and telephone numbers.</span></span>
1. <span data-ttu-id="38fb4-132">Dans la section **Génération d'état statutaire**, entrez les numéros d'enregistrement utilisés pour la génération d'états statutaires.</span><span class="sxs-lookup"><span data-stu-id="38fb4-132">In the **Statutory reporting** section, enter the registration numbers that are used for statutory reporting.</span></span>
1. <span data-ttu-id="38fb4-133">Dans la section **Numéros d'enregistrement**, entrez toutes les informations requises par l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="38fb4-133">In the **Registration numbers** section, enter any information required by the legal entity.</span></span>
1. <span data-ttu-id="38fb4-134">Dans la section **Informations sur le compte en banque**, entrez les comptes bancaires et les numéros d'acheminement de l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="38fb4-134">In the **Bank account information** section, enter bank accounts and routing numbers for the legal entity.</span></span>
1. <span data-ttu-id="38fb4-135">Dans la section **Commerce extérieur et logistique**, entrez les informations d'expédition pour l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="38fb4-135">In the **Foreign trade and logistics** section, enter shipping information for the legal entity.</span></span>
1. <span data-ttu-id="38fb4-136">Dans la section **Séquences de nombres**, vous pouvez visualiser les souches de numéros associées à l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="38fb4-136">In the **Number sequences** section, you can view the number sequences that are associated with the legal entity.</span></span> <span data-ttu-id="38fb4-137">Ce sera vide pour commencer.</span><span class="sxs-lookup"><span data-stu-id="38fb4-137">This will be empty to start with.</span></span>
1. <span data-ttu-id="38fb4-138">Dans la section **Image de tableau de bord**, affichez ou modifiez les images de logo et de tableau de bord associées à l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="38fb4-138">In the **Dashboard image** section, view or change the logo and dashboard image associated with the legal entity.</span></span>
1. <span data-ttu-id="38fb4-139">Dans la section **Immatriculation fiscale**, entrez les numéros d'enregistrement utilisés pour les déclarations aux administrations fiscales.</span><span class="sxs-lookup"><span data-stu-id="38fb4-139">In the **Tax registration** section, enter the registration numbers that are used to report to tax authorities.</span></span>
1. <span data-ttu-id="38fb4-140">Dans la section **Taxe sur les honoraires**, entrez les informations de déclaration des honoraires associées à l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="38fb4-140">In the **Tax 1099** section, enter 1099 information for the legal entity.</span></span>
1. <span data-ttu-id="38fb4-141">Dans la section **Informations fiscales**, entrez les informations fiscales associées à l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="38fb4-141">In the **Tax invormation** section, enter tax information for the legal entity.</span></span>
1. <span data-ttu-id="38fb4-142">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="38fb4-142">Select **Save**.</span></span>

<span data-ttu-id="38fb4-143">L'image suivante présente les détails d'un exemple d'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="38fb4-143">The following image shows details of an example legal entity.</span></span>

![Section générale de l'entité juridique](media/legal-entities-general.png)
   
## <a name="additional-resources"></a><span data-ttu-id="38fb4-145">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="38fb4-145">Additional resources</span></span>

[<span data-ttu-id="38fb4-146">Vue d'ensemble des organisations et des hiérarchies d'organisation</span><span class="sxs-lookup"><span data-stu-id="38fb4-146">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="38fb4-147">Planifier votre hiérarchie d'organisation</span><span class="sxs-lookup"><span data-stu-id="38fb4-147">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="38fb4-148">Hiérarchies de l'organisation</span><span class="sxs-lookup"><span data-stu-id="38fb4-148">Organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="38fb4-149">Présentation des canaux</span><span class="sxs-lookup"><span data-stu-id="38fb4-149">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="38fb4-150">Conditions préalables au paramétrage du canal</span><span class="sxs-lookup"><span data-stu-id="38fb4-150">Channel setup prerequisites</span></span>](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
