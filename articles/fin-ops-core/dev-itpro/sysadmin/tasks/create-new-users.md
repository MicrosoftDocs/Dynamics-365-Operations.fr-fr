---
title: Création de nouveaux utilisateurs
description: Les utilisateurs sont des employés internes de votre organisation, ou des clients et fournisseurs externes, qui doivent avoir accès au système pour effectuer leurs tâches.
author: peakerbl
manager: AnnBe
ms.date: 06/08/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6f861b7493d039b332358be7df7d0198cbadcb7a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679838"
---
# <a name="create-new-users"></a><span data-ttu-id="19716-103">Création de nouveaux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="19716-103">Create new users</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="19716-104">Les utilisateurs sont des employés internes de votre organisation, ou des clients et fournisseurs externes, qui doivent avoir accès au système pour effectuer leurs tâches.</span><span class="sxs-lookup"><span data-stu-id="19716-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to do their jobs.</span></span>

## <a name="associate-a-user-with-a-license-new-license-types-only"></a><span data-ttu-id="19716-105">Associer un utilisateur avec une licence (nouveaux types de licence uniquement)</span><span class="sxs-lookup"><span data-stu-id="19716-105">Associate a user with a license (new license types only)</span></span>
<span data-ttu-id="19716-106">Pour les clients qui se trouvent sur un des nouveaux types de licence qui ont été ajoutés en octobre 2019, les utilisateurs doivent être associés avec une licence.</span><span class="sxs-lookup"><span data-stu-id="19716-106">For customers who are on one of the new license types that were added in October 2019, users must be associated with a license.</span></span> <span data-ttu-id="19716-107">Les utilisateurs associés à une licence sont automatiquement ajoutés comme utilisateurs système sans rôle lors de leur première connexion.</span><span class="sxs-lookup"><span data-stu-id="19716-107">Users who are associated with a license are automatically added as system users who have no roles the first time that they sign in.</span></span>

<span data-ttu-id="19716-108">Les administrateurs système peuvent [attribuer des licences aux utilisateurs](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) dans le [Centre d’administration Microsoft 365](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="19716-108">System admins can [assign licenses to users](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) in the [Microsoft 365 admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span></span>

## <a name="associate-an-external-user-with-a-license-new-license-types-only"></a><span data-ttu-id="19716-109">Associer un utilisateur externe avec une licence (nouveaux types de licence uniquement)</span><span class="sxs-lookup"><span data-stu-id="19716-109">Associate an external user with a license (new license types only)</span></span>
<span data-ttu-id="19716-110">Les utilisateurs externes au client dans lequel l’environnement a été déployé doivent être représentés dans le répertoire du client hôte (Azure Active Directory (Azure AD)) afin de leur affecter des licences.</span><span class="sxs-lookup"><span data-stu-id="19716-110">Users external to the tenant that the environment was deployed into need to be represented in the host tenant directory (Azure Active Directory (Azure AD)) so that they can be assigned licenses.</span></span> <span data-ttu-id="19716-111">Ces utilisateurs externes doivent être ajoutés au client dans Azure AD en tant qu’utilisateurs invités, puis se voir attribuer les licences appropriées.</span><span class="sxs-lookup"><span data-stu-id="19716-111">Those external users should be added to the tenant in Azure AD as guest users and then assigned the appropriate licenses.</span></span> <span data-ttu-id="19716-112">Pour plus d’informations, voir [Ajouter utilisateurs de collaboration B2B Azure Active Directory dans le portail Azure](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="19716-112">For more information, see [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="19716-113">Ajout d’un nouvel utilisateur</span><span class="sxs-lookup"><span data-stu-id="19716-113">Add a new user</span></span>
1. <span data-ttu-id="19716-114">Accédez à **Administration système \> Utilisateurs \> Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="19716-114">Go to **System administration \> Users \> Users**.</span></span>
2. <span data-ttu-id="19716-115">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="19716-115">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="19716-116">Dans le champ **ID d’utilisateur**, entrez un identificateur unique pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="19716-116">In the **User ID** field, enter a unique identifier for the user.</span></span> <span data-ttu-id="19716-117">Un ID utilisateur est requis.</span><span class="sxs-lookup"><span data-stu-id="19716-117">A user ID is required.</span></span>  
4. <span data-ttu-id="19716-118">Dans le champ **Nom d’utilisateur**, saisissez le nom de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="19716-118">In the **User name** field, enter the user's name.</span></span>  
5. <span data-ttu-id="19716-119">Dans le champ **Domaine**, entrez le domaine AD DS de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="19716-119">In the **Domain** field, enter the user's domain.</span></span>  
6. <span data-ttu-id="19716-120">Dans le champ **Alias**, entrez l’alias utilisateur.</span><span class="sxs-lookup"><span data-stu-id="19716-120">In the **Alias** field, enter the user's alias.</span></span>  
7. <span data-ttu-id="19716-121">Sélectionnez la société souhaitée dans le champ **Société**.</span><span class="sxs-lookup"><span data-stu-id="19716-121">In the **Company** field, select the desired company.</span></span> 
8. <span data-ttu-id="19716-122">Dans le raccourci **Rôles de l’utilisateur**, sélectionnez **Affecter des rôles** sur affecter des utilisateurs à des rôles de sécurité.</span><span class="sxs-lookup"><span data-stu-id="19716-122">On the **User's roles** FastTab, select **Assign roles** to assign users to security roles.</span></span> <span data-ttu-id="19716-123">Pour plus d’informations, voir [Affecter des utilisateurs à des rôles de sécurité](assign-users-security-roles.md).</span><span class="sxs-lookup"><span data-stu-id="19716-123">For more information, see [Assign users to security roles](assign-users-security-roles.md).</span></span>
9. <span data-ttu-id="19716-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="19716-124">Select **OK**.</span></span>
10. <span data-ttu-id="19716-125">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="19716-125">Select **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="19716-126">Importer des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="19716-126">Import users</span></span>
1. <span data-ttu-id="19716-127">Accédez à **Administration système \> Utilisateurs \> Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="19716-127">Go to **System administration \> Users \> Users**.</span></span>
2. <span data-ttu-id="19716-128">Dans la volet Actions, sélectionnez **Importer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="19716-128">On the Action Pane, select **Import users**.</span></span>
3. <span data-ttu-id="19716-129">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="19716-129">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="19716-130">Sélectionnez **Importer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="19716-130">Select **Import users**.</span></span>
5. <span data-ttu-id="19716-131">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="19716-131">Select **Close**.</span></span>

