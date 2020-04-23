---
title: Sécurité de l'utilisateur du portail fournisseur
description: Cet article détaille la procédure de paramétrage de la sécurité pour les fournisseurs externes qui utilisent le portail Fournisseur. Ces informations ne s'appliquent qu'aux versions de février 2016 &amp; de mai 2016 de Dynamics AX.
author: mkirknel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 30231
ms.assetid: 3574db17-81c7-4c5a-999b-0098aa0b9cda
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 72f353448f3b5d1f816bb240a230e26529c9cec3
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207115"
---
# <a name="vendor-portal-user-security"></a><span data-ttu-id="6b0a7-104">Sécurité utilisateur du portail fournisseur</span><span class="sxs-lookup"><span data-stu-id="6b0a7-104">Vendor portal user security</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6b0a7-105">Cet article détaille la procédure de paramétrage de la sécurité pour les fournisseurs externes qui utilisent le portail Fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-105">This article explains how to set up security for external vendors who use the Vendor portal.</span></span> <span data-ttu-id="6b0a7-106">Ces informations ne s'appliquent qu'aux versions de février 2016 &amp; de mai 2016 de Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-106">This information applies only to the February 2016 &amp; May 2016 versions of Dynamics AX.</span></span>

<span data-ttu-id="6b0a7-107">La fonctionnalité de portail fournisseur a été remplacée par la fonctionnalité étendue de collaboration fournisseur dans la version 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-107">The Vendor portal functionality has been replaced by extended vendor collaboration functionality in Dynamics 365 for Operations version 1611.</span></span> <span data-ttu-id="6b0a7-108">Pour plus d'informations sur le paramétrage de la sécurité pour la collaboration fournisseur, voir [Paramétrer et mettre à jour la collaboration fournisseur](set-up-maintain-vendor-collaboration.md).</span><span class="sxs-lookup"><span data-stu-id="6b0a7-108">For more information about setting up security for vendor collaboration, see [Set up and maintain vendor collaboration](set-up-maintain-vendor-collaboration.md).</span></span> <span data-ttu-id="6b0a7-109">Le portail Fournisseur expose un ensemble limité d'informations sur les commandes fournisseur (CF) aux fournisseurs externes.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-109">The Vendor portal exposes a limited set of information about purchase orders (POs) to external vendors.</span></span> <span data-ttu-id="6b0a7-110">Il est important de paramétrer correctement des autorisations utilisateur pour le portail Fournisseur dans Microsoft Dynamics AX, de sorte que les fournisseurs n'aient pas un accès involontaire aux informations supplémentaires dans votre installation de Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-110">It's important that you correctly set up user permissions for the Vendor portal in Microsoft Dynamics AX, so that vendors don't have unintended access to additional information in your Dynamics AX installation.</span></span> <span data-ttu-id="6b0a7-111">**Important :** à la différence d'autres utilisateurs, les fournisseurs externes ne doivent pas avoir le rôle **SystemUser**.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-111">**Important:** Unlike other users, external vendors should not have the **SystemUser** role.</span></span> <span data-ttu-id="6b0a7-112">Le rôle **SystemUser** octroie l'accès à un ensemble de privilèges qui ne sont pas appropriés aux utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-112">The **SystemUser** role grants access to a set of privileges that aren't suitable for external users.</span></span>

## <a name="setting-up-a-vendor-portal-user"></a><span data-ttu-id="6b0a7-113">Paramétrage d'un utilisateur du portail Fournisseur</span><span class="sxs-lookup"><span data-stu-id="6b0a7-113">Setting up a Vendor portal user</span></span>
<span data-ttu-id="6b0a7-114">Avant de créer un compte utilisateur pour une personne qui utilise le portail Fournisseur, vous devez paramétrer le fournisseur pour autoriser sa collaboration au portail Fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-114">Before you create a user account for someone who will use the Vendor portal, you must set up the vendor to allow for Vendor portal collaboration.</span></span> <span data-ttu-id="6b0a7-115">Utilisez le champ **Collaboration de commande fournisseur** sous l'onglet **Général** dans la page **Fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-115">Use the **Purchase order collaboration** field on the **General** tab on the **Vendors** page.</span></span> <span data-ttu-id="6b0a7-116">Les fournisseurs externes qui utilisent le portail Fournisseur doivent avoir le paramétrage suivant :</span><span class="sxs-lookup"><span data-stu-id="6b0a7-116">External vendors that use the Vendor portal must have the following setup:</span></span>

-   <span data-ttu-id="6b0a7-117">Un compte utilisateur de Microsoft Azure Active Directory (AAD) doit être enregistré pour le fournisseur dans la page **Utilisateurs** dans Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-117">A Microsoft Azure Active Directory (AAD) user account must be registered for the vendor on the **Users** page in Dynamics AX.</span></span>
-   <span data-ttu-id="6b0a7-118">Le fournisseur doit avoir le rôle de sécurité **Fournisseur (externe)**, et non le rôle **SystemUser**.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-118">The vendor must have the **Vendor (external)** security role, not the **SystemUser** role.</span></span> <span data-ttu-id="6b0a7-119">**Remarque :** le rôle **SystemUser** est automatiquement octroyé lorsque vous créez un nouveau compte utilisateur dans Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-119">**Note:** The **SystemUser** role is automatically granted when you create a new user account in Dynamics AX.</span></span> <span data-ttu-id="6b0a7-120">Par conséquent, vous devez supprimer ce rôle et accepter le message d'avertissement reçu.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-120">Therefore, you must remove that role and acknowledge the warning message that you receive.</span></span>
-   <span data-ttu-id="6b0a7-121">L'utilisateur fournisseur ne doit pas avoir l'autorisation d'ajouter des champs supplémentaires à partir des tables de CF sur leur affichage de la CF.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-121">The vendor user should not be granted permission to add additional fields from the PO tables to their view of the PO.</span></span> <span data-ttu-id="6b0a7-122">Sous l'onglet **Personnalisation**, sous l'onglet **Utilisateurs**, réglez l'option **Personnalisation explicite autorisée** pour l'utilisateur sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-122">On the **Personalization** tab, on the **Users** tab, set the **Explicit personalization allowed** option for the user to **No**.</span></span>
-   <span data-ttu-id="6b0a7-123">Le compte utilisateur doit être associé à une personne à contacter enregistrée.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-123">The user account must be associated with a registered contact person.</span></span> <span data-ttu-id="6b0a7-124">Dans la page **Utilisateurs**, sélectionnez une personne à contacter dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-124">On the **Users** page, select a contact person in the **Name** field.</span></span> <span data-ttu-id="6b0a7-125">La personne sélectionnée doit avoir le rôle **Contact** pour le fournisseur approprié.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-125">The person that you select should have the **Contact** role for the relevant vendor.</span></span>

<span data-ttu-id="6b0a7-126">Si la même personne a besoin d'accéder au portail Fournisseur pour plusieurs comptes fournisseur (pour différentes entités juridiques, peut-être), chacun des comptes d'utilisateurs de cette personne doit être associé à la même personne à contacter enregistrée.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-126">If the same person requires access to the Vendor portal for multiple vendor accounts (for different legal entities, perhaps), each of that person's user accounts must be associated with the same registered contact person.</span></span> <span data-ttu-id="6b0a7-127">Le rôle **Fournisseur (externe)** inclut toutes les fonctionnalités de base requises afin d'utiliser la fonctionnalité disponible dans le portail Fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-127">The **Vendor (external)** role includes all the basic capabilities that are required in order to use the functionality that is available in the Vendor portal.</span></span> <span data-ttu-id="6b0a7-128">Ce paramétrage permet de garantir que l'interface utilisateur vue par l'utilisateur externe est concentrée uniquement sur le scénario prévu.</span><span class="sxs-lookup"><span data-stu-id="6b0a7-128">This setup helps guarantee that the user interface that the external user sees is focused on the intended scenario only.</span></span>

<a name="additional-resources"></a><span data-ttu-id="6b0a7-129">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6b0a7-129">Additional resources</span></span>
--------

[<span data-ttu-id="6b0a7-130">Collaborer avec des fournisseurs à l'aide du portail Fournisseur</span><span class="sxs-lookup"><span data-stu-id="6b0a7-130">Collaborate with vendors by using the Vendor portal</span></span>](collaborate-vendors-vendor-portal.md)



