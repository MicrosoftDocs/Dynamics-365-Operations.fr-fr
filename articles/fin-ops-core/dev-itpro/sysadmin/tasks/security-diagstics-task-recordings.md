---
title: Diagnostics de sécurité pour l'enregistrement des tâches
description: Cette rubrique fournit des informations sur la façon d'analyser et de gérer les exigences d'autorisation de sécurité en fonction d'un enregistrement de tâche.
author: Peakerbl
manager: AnnBe
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: ''
ms.dyn365.ops.version: Version 10.0.9
ms.openlocfilehash: 4aecda7e0d604b70dec58a4f5bb2992fe7e0a5e2
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982428"
---
# <a name="security-diagnostics-for-task-recordings"></a><span data-ttu-id="65573-103">Diagnostics de sécurité pour l'enregistrement des tâches</span><span class="sxs-lookup"><span data-stu-id="65573-103">Security diagnostics for task recordings</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="before-you-begin"></a><span data-ttu-id="65573-104">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="65573-104">Before you begin</span></span>

<span data-ttu-id="65573-105">Cette rubrique fournit des informations sur la façon d'analyser et de gérer les exigences d'autorisation de sécurité en fonction d'un enregistrement de tâche.</span><span class="sxs-lookup"><span data-stu-id="65573-105">This topic provides information about how to analyze and manage security permission requirements based on a task recording.</span></span> <span data-ttu-id="65573-106">Avant d'effectuer les étapes de cette rubrique, vous devez disposer d'un enregistrement de tâche du processus technique que vous souhaitez analyser.</span><span class="sxs-lookup"><span data-stu-id="65573-106">Before you complete the steps in this topic, you must have a task recording of the business process that you want to analyze.</span></span> <span data-ttu-id="65573-107">Pour enregistrer un processus métier, voir [Ressources de l'enregistreur de tâches](../../user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="65573-107">To record a business process, see [Task recorder resources](../../user-interface/task-recorder.md).</span></span> 

## <a name="manage-security-for-a-task-recording"></a><span data-ttu-id="65573-108">Gérer la sécurité pour un enregistrement de tâche</span><span class="sxs-lookup"><span data-stu-id="65573-108">Manage security for a task recording</span></span>

1. <span data-ttu-id="65573-109">Accédez à **Administration du système** > **Sécurité** > **Diagnostic de sécurité pour l'enregistrement des tâches**.</span><span class="sxs-lookup"><span data-stu-id="65573-109">Go to **System administration** > **Security** > **Security diagnostic for task recording**.</span></span>
2. <span data-ttu-id="65573-110">Ouvrez l'enregistrement de tâche à partir de son emplacement.</span><span class="sxs-lookup"><span data-stu-id="65573-110">Open the task recording from its location.</span></span> <span data-ttu-id="65573-111">Sélectionnez **Ouvrir depuis ce PC** ou **Ouvert à partir de Lifecycle Services**, puis sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="65573-111">Select **Open from this PC** or **Open from Lifecycle Services**, and then select **Close**.</span></span>
3. <span data-ttu-id="65573-112">Cela ouvrira la page **Détails des éléments du menu Sécurité** qui répertorie les objets de sécurité requis pour le processus.</span><span class="sxs-lookup"><span data-stu-id="65573-112">This will open the **Security menu item details** page that lists the security objects required for the process.</span></span>

 > [!NOTE]
 > <span data-ttu-id="65573-113">Les éléments de menu **Action** et **Production** ne sont pas inclus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="65573-113">The **Action** and **Output** menu items are not included in the list.</span></span>

4. <span data-ttu-id="65573-114">Dans le champ **ID utilisateur**, sélectionnez un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="65573-114">In the **User ID** field, select a user.</span></span> <span data-ttu-id="65573-115">Si l'utilisateur ne dispose pas d'autorisations pour certains éléments de menu, le champ **Autorisations manquantes** sera mis à jour sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="65573-115">If the user does not have permissions for some menu items, the **Missing permissions** field will update to **Yes**.</span></span>
  
  ![Page Détails des éléments du menu Sécurité](../media/Security-Menu-Item-Details.png)

5. <span data-ttu-id="65573-117">Sélectionnez **Ajouter une référence** pour afficher la liste des objets de sécurité, y compris les rôles, les fonctions et les privilèges qui accordent l'autorisation manquante.</span><span class="sxs-lookup"><span data-stu-id="65573-117">Select **Add Reference** to see a list of the security objects, including roles, duties, and privileges that grant the missing permission.</span></span>
6. <span data-ttu-id="65573-118">Sélectionnez un objet de sécurité dans la liste :</span><span class="sxs-lookup"><span data-stu-id="65573-118">Select a security object from the list:</span></span>

    - <span data-ttu-id="65573-119">Si **Rôle** est sélectionné, sélectionnez **Ajouter un rôle à l'utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="65573-119">If **Role** is selected, select **Add role to user**.</span></span> <span data-ttu-id="65573-120">Cela ouvrira la page **Attribuer des utilisateurs aux rôles**.</span><span class="sxs-lookup"><span data-stu-id="65573-120">This will open the **Assign users to roles** page.</span></span> <span data-ttu-id="65573-121">Pour plus d'informations, voir la page [Affecter des utilisateurs à des rôles de sécurité](assign-users-security-roles.md).</span><span class="sxs-lookup"><span data-stu-id="65573-121">For more information, see [Assign users to security roles](assign-users-security-roles.md) page.</span></span>
    - <span data-ttu-id="65573-122">Si **Devoir** est sélectionné, sélectionnez **Ajouter le devoir au rôle**, sélectionnez les rôles auxquels le devoir doit être ajouté, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="65573-122">If **Duty** is selected, select **Add duty to role**, select the roles that the duty should be added to, and then select **OK**.</span></span>
    - <span data-ttu-id="65573-123">Si **Privilège** est sélectionné, sélectionnez **Ajouter le privilège aux devoirs**, sélectionnez les rôles auxquels le devoir doit être ajouté, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="65573-123">If **Privilege** is selected, select **Add privilege to duties**, select the roles that the duty should be added to, and then select **OK**.</span></span>
