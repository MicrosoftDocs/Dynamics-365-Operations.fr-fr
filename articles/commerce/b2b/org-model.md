---
title: Créer des hiérarchies de modélisation organisationnelle pour les organisations B2B
description: Cette rubrique décrit comment créer des hiérarchies de modélisation organisationnelle pour les organisations B2B (business-to-business).
author: josaw1
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 487af939f92ece8bc3e543b3beeffa239baa1863
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799827"
---
# <a name="create-org-modeling-hierarchies-for-b2b-organizations"></a><span data-ttu-id="9dde8-103">Créer des hiérarchies de modélisation organisationnelle pour les organisations B2B</span><span class="sxs-lookup"><span data-stu-id="9dde8-103">Create org modeling hierarchies for B2B organizations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9dde8-104">Cette rubrique décrit comment créer des hiérarchies de modélisation organisationnelle pour les organisations B2B (business-to-business) dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9dde8-104">This topic describes how to create organizational modeling hierarchies for business-to-business (B2B) organizations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="9dde8-105">Dans Commerce Headquarters, les organisations partenaires sont représentées par des clients et des entités de hiérarchie cliente.</span><span class="sxs-lookup"><span data-stu-id="9dde8-105">In Commerce headquarters, business partner organizations are represented by customer and customer hierarchy entities.</span></span> <span data-ttu-id="9dde8-106">L’organisation partenaire et ses utilisateurs sont représentés par des clients et les hiérarchies de clients sont utilisées pour associer ces clients les uns aux autres.</span><span class="sxs-lookup"><span data-stu-id="9dde8-106">The business partner organization and its users are represented as customers, and customer hierarchies are used to associate those customers with each other.</span></span>

<span data-ttu-id="9dde8-107">Lorsqu’une demande de partenaire commercial pour rejoindre un site de commerce électronique B2B est approuvée, les actions suivantes sont effectuées :</span><span class="sxs-lookup"><span data-stu-id="9dde8-107">When a business partner request to join a B2B e-commerce site is approved, the following actions are performed:</span></span>

- <span data-ttu-id="9dde8-108">Deux nouveaux enregistrements client sont créés dans le système : un enregistrement client **Type d’organisation** pour l’organisation partenaire et un enregistrement client **Type de personne** pour le demandeur (c’est-à-dire l’utilisateur partenaire qui a soumis la demande).</span><span class="sxs-lookup"><span data-stu-id="9dde8-108">Two new customer records are created in the system: a **Type Organization** customer record for the business partner organization and a **Type Person** customer record for the requestor (that is, the business partner user who submitted the request).</span></span>
- <span data-ttu-id="9dde8-109">Un nouvel enregistrement de hiérarchie client est créé sous **Client \> Hiérarchie des clients**.</span><span class="sxs-lookup"><span data-stu-id="9dde8-109">A new customer hierarchy record is created under **Customer \> Customer hierarchy**.</span></span> <span data-ttu-id="9dde8-110">Cet enregistrement a les propriétés d’en-tête suivantes :</span><span class="sxs-lookup"><span data-stu-id="9dde8-110">This record has the following header properties:</span></span>

    - <span data-ttu-id="9dde8-111">**ID de la hiérarchie client** - Un identifiant unique pour la hiérarchie client.</span><span class="sxs-lookup"><span data-stu-id="9dde8-111">**Customer hierarchy ID** – A unique ID for the customer hierarchy.</span></span> <span data-ttu-id="9dde8-112">Cet ID utilise la souche de numéros définie dans les paramètres partagés de Commerce dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="9dde8-112">This ID uses the number sequence that is defined in Commerce shared parameters in Commerce headquarters.</span></span>
    - <span data-ttu-id="9dde8-113">**Nom** - Le nom de l’organisation du partenaire commercial, tel que spécifié dans la demande d’intégration.</span><span class="sxs-lookup"><span data-stu-id="9dde8-113">**Name** – The organization name of the business partner, as specified in the onboarding request.</span></span>
    - <span data-ttu-id="9dde8-114">**Objectif** - Cette propriété est définie sur la valeur prédéfinie **Organisation B2B**.</span><span class="sxs-lookup"><span data-stu-id="9dde8-114">**Purpose** – This property is set to the predefined value **B2B organization**.</span></span>
    - <span data-ttu-id="9dde8-115">**Organisation** - L’ID client du partenaire commercial.</span><span class="sxs-lookup"><span data-stu-id="9dde8-115">**Organization** – The customer ID of the business partner.</span></span>

<span data-ttu-id="9dde8-116">Voici les détails de l’enregistrement de la hiérarchie client :</span><span class="sxs-lookup"><span data-stu-id="9dde8-116">Here are the details of the customer hierarchy record:</span></span>

- <span data-ttu-id="9dde8-117">L’enregistrement client du demandeur est associé à la hiérarchie client.</span><span class="sxs-lookup"><span data-stu-id="9dde8-117">The customer record of the requestor is associated with the customer hierarchy.</span></span>
- <span data-ttu-id="9dde8-118">Le rôle d’administrateur est associé au demandeur.</span><span class="sxs-lookup"><span data-stu-id="9dde8-118">The administrator role is associated with the requestor.</span></span>

<span data-ttu-id="9dde8-119">Lorsque l’administrateur ajoute plus d’utilisateurs à l’organisation partenaire sur un site B2B, un nouvel enregistrement client pour chaque utilisateur est créé dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="9dde8-119">When the administrator adds more users are to the business partner organization on a B2B site, a new customer record for each user is created in Commerce headquarters.</span></span> <span data-ttu-id="9dde8-120">Cet enregistrement client est également ajouté à l’enregistrement de hiérarchie client correspondant pour le partenaire et a le rôle d’un « utilisateur ».</span><span class="sxs-lookup"><span data-stu-id="9dde8-120">This customer record is also added to the relevant customer hierarchy record for the business partner and has the role of a "user."</span></span>

> [!NOTE]
> <span data-ttu-id="9dde8-121">Dans la plupart des cas, les valeurs de propriété correspondantes de tous les enregistrements client d’une hiérarchie doivent correspondre.</span><span class="sxs-lookup"><span data-stu-id="9dde8-121">In most cases, the corresponding property values of all customer records in a hierarchy should match.</span></span> <span data-ttu-id="9dde8-122">Par exemple, étant donné que tous les utilisateurs partenaires doivent obtenir des prix similaires pour les produits, leur groupe de prix et les configurations associées doivent correspondre.</span><span class="sxs-lookup"><span data-stu-id="9dde8-122">For example, because all business partner users should get similar prices for products, their price group and associated configurations should match.</span></span> <span data-ttu-id="9dde8-123">Cependant, le système n’applique pas cette cohérence.</span><span class="sxs-lookup"><span data-stu-id="9dde8-123">However, the system doesn't enforce this consistency.</span></span> <span data-ttu-id="9dde8-124">Par conséquent, les utilisateurs de Commerce Headquarters concernés sont responsables de s’assurer que les valeurs de propriété et les configurations correspondent pour tous les clients d’une hiérarchie donnée.</span><span class="sxs-lookup"><span data-stu-id="9dde8-124">Therefore, the relevant Commerce headquarters users are responsible for ensuring that the property values and configurations match for all customers in a given hierarchy.</span></span>

<span data-ttu-id="9dde8-125">Les utilisateurs de Commerce Headquarters peuvent consulter les valeurs de propriété de tous les enregistrements client de la hiérarchie dans une vue côte à côte.</span><span class="sxs-lookup"><span data-stu-id="9dde8-125">Commerce headquarters users can look at the property values for all customer records in the hierarchy in a side-by-side view.</span></span> <span data-ttu-id="9dde8-126">Sélectionnez les propriétés d’enregistrement client pertinentes en sélectionnant les noms d’onglet dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="9dde8-126">Select the relevant customer record properties by selecting the tab names on the drop-down menu.</span></span> <span data-ttu-id="9dde8-127">Les utilisateurs peuvent directement afficher et modifier les valeurs de propriété à partir de cette vue.</span><span class="sxs-lookup"><span data-stu-id="9dde8-127">Users can directly view and edit the property values from this view.</span></span> <span data-ttu-id="9dde8-128">Sinon, si vous souhaitez appliquer toutes les valeurs de l’enregistrement client administrateur à tous les enregistrements client utilisateur, sélectionnez **Remplacer** dans les détails de la hiérarchie client.</span><span class="sxs-lookup"><span data-stu-id="9dde8-128">Alternatively, if you want to apply all the values from the administrator customer record to all the user customer records, select **Override** in the customer hierarchy details.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9dde8-129">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="9dde8-129">Additional resources</span></span>

[<span data-ttu-id="9dde8-130">Configurer un site d’e-commerce B2B</span><span class="sxs-lookup"><span data-stu-id="9dde8-130">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="9dde8-131">Gérer les partenaires commerciaux sur les sites de commerce électronique B2B</span><span class="sxs-lookup"><span data-stu-id="9dde8-131">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="9dde8-132">Configurer le mode de paiement du compte client pour les sites de commerce électronique B2B</span><span class="sxs-lookup"><span data-stu-id="9dde8-132">Configure the customer account payment method for B2B e-commerce sites</span></span>](payment-method.md)

[<span data-ttu-id="9dde8-133">Définir des limites de quantité de produits pour les sites de commerce électronique B2B</span><span class="sxs-lookup"><span data-stu-id="9dde8-133">Set product quantity limits for B2B e-commerce sites</span></span>](quantity-limits.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]