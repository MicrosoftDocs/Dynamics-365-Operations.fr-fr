---
title: Création de nouveaux utilisateurs
description: Les utilisateurs sont des employés internes de votre organisation, ou des clients et fournisseurs externes, qui doivent avoir accès au système pour effectuer leurs tâches.
author: maertenm
manager: AnnBe
ms.date: 08/30/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a5635f96132b2e52227b569e7e480fa55e82d61
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180942"
---
# <a name="create-new-users"></a><span data-ttu-id="86df0-103">Création de nouveaux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="86df0-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]
[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="86df0-104">Les utilisateurs sont des employés internes de votre organisation, ou des clients et fournisseurs externes, qui doivent avoir accès au système pour effectuer leurs tâches.</span><span class="sxs-lookup"><span data-stu-id="86df0-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to do their jobs.</span></span>

## <a name="associate-a-user-with-a-license-new-license-types-only"></a><span data-ttu-id="86df0-105">Associer un utilisateur avec une licence (nouveaux types de licence uniquement)</span><span class="sxs-lookup"><span data-stu-id="86df0-105">Associate a user with a license (new license types only)</span></span>
<span data-ttu-id="86df0-106">Pour les clients qui se trouvent sur un des nouveaux types de licence qui ont été ajoutés en octobre 2019, les utilisateurs doivent être associés avec une licence.</span><span class="sxs-lookup"><span data-stu-id="86df0-106">For customers who are on one of the new license types that were added in October 2019, users must be associated with a license.</span></span> <span data-ttu-id="86df0-107">Les utilisateurs associés à une licence sont automatiquement ajoutés comme utilisateurs système sans rôle lors de leur première connexion.</span><span class="sxs-lookup"><span data-stu-id="86df0-107">Users who are associated with a license are automatically added as system users who have no roles the first time that they sign in.</span></span> <span data-ttu-id="86df0-108">Les utilisateurs qui ne sont pas associés à une licence reçoivent un message d'avertissement.</span><span class="sxs-lookup"><span data-stu-id="86df0-108">Users who aren't associated with a licence receive a warning message.</span></span>

<span data-ttu-id="86df0-109">Les administrateurs système peuvent [attribuer des licences aux utilisateurs](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) dans le [Centre d'administration Microsoft 365](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="86df0-109">System admins can [assign licenses to users](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) in the [Microsoft 365 admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="86df0-110">Ajout d'un nouvel utilisateur</span><span class="sxs-lookup"><span data-stu-id="86df0-110">Add a new user</span></span>
1. <span data-ttu-id="86df0-111">Accédez à **Administration système \> Utilisateurs \> Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="86df0-111">Go to **System administration \> Users \> Users**.</span></span>
2. <span data-ttu-id="86df0-112">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="86df0-112">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="86df0-113">Dans le champ **ID d'utilisateur**, entrez un identificateur unique pour l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="86df0-113">In the **User ID** field, enter a unique identifier for the user.</span></span> <span data-ttu-id="86df0-114">Un ID utilisateur est requis.</span><span class="sxs-lookup"><span data-stu-id="86df0-114">A user ID is required.</span></span>  
4. <span data-ttu-id="86df0-115">Dans le champ **Nom d'utilisateur**, saisissez le nom de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="86df0-115">In the **User name** field, enter the user's name.</span></span>  
5. <span data-ttu-id="86df0-116">Dans le champ **Domaine**, entrez le domaine AD DS de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="86df0-116">In the **Domain** field, enter the user's domain.</span></span>  
6. <span data-ttu-id="86df0-117">Dans le champ **Alias**, entrez l'alias utilisateur.</span><span class="sxs-lookup"><span data-stu-id="86df0-117">In the **Alias** field, enter the user's alias.</span></span>  
7. <span data-ttu-id="86df0-118">Sélectionnez la société souhaitée dans le champ **Société**.</span><span class="sxs-lookup"><span data-stu-id="86df0-118">In the **Company** field, select the desired company.</span></span> 
8. <span data-ttu-id="86df0-119">Dans l'organisateur **Rôles de l'utilisateur**, sélectionnez **Affecter des rôles** sur [affecter des rôles de sécurité aux utilisateurs](assign-users-security-roles.md)</span><span class="sxs-lookup"><span data-stu-id="86df0-119">On the **User's roles** FastTab, select **Assign roles** to [assign users to security roles](assign-users-security-roles.md)</span></span>
9. <span data-ttu-id="86df0-120">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="86df0-120">Select **OK**.</span></span>
10. <span data-ttu-id="86df0-121">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="86df0-121">Select **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="86df0-122">Importer des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="86df0-122">Import users</span></span>
1. <span data-ttu-id="86df0-123">Dans la volet Actions, sélectionnez **Importer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="86df0-123">On the Action Pane, select **Import users**.</span></span>
2. <span data-ttu-id="86df0-124">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="86df0-124">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="86df0-125">Sélectionnez **Importer les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="86df0-125">Select **Import users**.</span></span>
4. <span data-ttu-id="86df0-126">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="86df0-126">Select **Close**.</span></span>

