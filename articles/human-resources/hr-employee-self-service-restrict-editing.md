---
title: Restreindre la modification des informations personnelles
description: Empêcher les employés de modifier leurs coordonnées dans Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6e43b9127b247fa618558b725837d12bf290662f
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052023"
---
# <a name="restrict-editing-of-personal-information"></a><span data-ttu-id="f9bdb-103">Restreindre la modification des informations personnelles</span><span class="sxs-lookup"><span data-stu-id="f9bdb-103">Restrict editing of personal information</span></span>

[!include [applies to](../includes/applies-to-hr.md)]
[!include [preview feature](./includes/preview-feature.md)]

<span data-ttu-id="f9bdb-104">Cette rubrique décrit comment empêcher les employés de modifier les détails de contact dans Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f9bdb-104">This topic describes how to restrict employees from editing contact details in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="f9bdb-105">Vous souhaiterez peut-être empêcher les employés de modifier certaines informations de contact, telles que leur adresse professionnelle ou leur adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="f9bdb-105">You might want to prevent employees from editing certain contact details, such as their business location or email address.</span></span>

> [!NOTE]
> <span data-ttu-id="f9bdb-106">Pour utiliser cette fonctionnalité, vous devez d’abord activer **(Aperçu) Empêchez les employés d’ajouter ou de modifier des adresses et des informations de contact à des fins spécifiques** dans la gestion des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="f9bdb-106">To use this feature, you must first enable **(Preview) Restrict employees from adding or editing address and contact information for select purposes** in Feature management.</span></span> <span data-ttu-id="f9bdb-107">Pour plus d’informations sur l’activation des fonctionnalités en version préliminaire, consultez [Gérer les fonctionnalités](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="f9bdb-107">For more information about enabling preview features, see [Manage features](hr-admin-manage-features.md).</span></span><br><br><span data-ttu-id="f9bdb-108">![Activer la fonctionnalité d’aperçu](./media/hr-employee-self-service-restrict-enable.png)</span><span class="sxs-lookup"><span data-stu-id="f9bdb-108">![Enable preview feature](./media/hr-employee-self-service-restrict-enable.png)</span></span>

## <a name="choose-the-information-an-employee-can-add-or-edit"></a><span data-ttu-id="f9bdb-109">Choisissez les informations qu’un employé peut ajouter ou modifier</span><span class="sxs-lookup"><span data-stu-id="f9bdb-109">Choose the information an employee can add or edit</span></span>

1. <span data-ttu-id="f9bdb-110">Dans Human Resources, sélectionnez **Gestion du personnel**, sélectionnez **Liens**, puis sélectionnez **Paramètres Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="f9bdb-110">In Human Resources, select **Personnel management**, select **Links**, and then select **Human resources parameters**.</span></span>

   ![Accéder aux paramètres de Human resources](./media/hr-employee-self-service-human-resources-parameters.png)

2. <span data-ttu-id="f9bdb-112">Sur la page **Paramètres des ressources humaines**, sélectionnez l’onglet **Libre-service des employés**.</span><span class="sxs-lookup"><span data-stu-id="f9bdb-112">On the **Human resources parameters** page, select the **Employee self service** tab.</span></span>

   ![Sélectionnez Libre-service employé](./media/hr-employee-self-service-tab.png)

3. <span data-ttu-id="f9bdb-114">Sur l’onglet **Libre-service des employés**, décochez toutes les informations dans la section **Adresse et coordonnées** que vous ne souhaitez pas que les employés ajoutent ou modifient.</span><span class="sxs-lookup"><span data-stu-id="f9bdb-114">On the **Employee self service** tab, uncheck all information in the **Address and contact information** section that you don't want employees to add or edit.</span></span> <span data-ttu-id="f9bdb-115">Dans cet exemple, nous avons décoché les coordonnées **Professionnelles**.</span><span class="sxs-lookup"><span data-stu-id="f9bdb-115">In this example, we've unchecked **Business** contact information.</span></span>

   ![Restreindre la modification des informations de contact professionnel](./media/hr-employee-self-service-restrict-business.png)

4. <span data-ttu-id="f9bdb-117">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f9bdb-117">Select **Save**.</span></span>

   ![Enregistrer les modifications](./media/hr-employee-self-service-restrict-save.png)

## <a name="employee-experience"></a><span data-ttu-id="f9bdb-119">Expérience des employés</span><span class="sxs-lookup"><span data-stu-id="f9bdb-119">Employee experience</span></span>

<span data-ttu-id="f9bdb-120">Une fois que vous avez empêché les employés d’ajouter ou de modifier les coordonnées, ils peuvent voir les informations, mais ne peuvent pas les modifier.</span><span class="sxs-lookup"><span data-stu-id="f9bdb-120">After you've restricted employees from adding or editing contact details, they can see the information, but can't change it.</span></span>

<span data-ttu-id="f9bdb-121">Dans cet exemple, où les employés ne peuvent pas modifier les coordonnées **Professionnelles**, ils peuvent toujours voir les informations dans le libre-service des employés :</span><span class="sxs-lookup"><span data-stu-id="f9bdb-121">In this example, where employees are restricted from editing **Business** contact details, they can still see the information in Employee self service:</span></span>

![Afficher les coordonnées professionnelles](./media/hr-employee-self-service-restrict-view.png)

<span data-ttu-id="f9bdb-123">Cependant, lorsqu’ils sélectionnent les coordonnées professionnelles, le volet **Modifier l’adresse** apparaît en lecture seule et ils ne peuvent modifier aucun des champs.</span><span class="sxs-lookup"><span data-stu-id="f9bdb-123">However, when they select the business contact details, the **Edit address** pane appears as read-only, and they can't change any of the fields.</span></span>

![Les coordonnées professionnelles s’affichent en lecture seule](./media/hr-employee-self-service-restrict-read-only.png)

<span data-ttu-id="f9bdb-125">De plus, s’ils sélectionnent **Ajouter** pour ajouter une nouvelle adresse, ils ne peuvent pas sélectionner **Professionnelle** dans la liste déroulante **But**.</span><span class="sxs-lookup"><span data-stu-id="f9bdb-125">In addition, if they select **Add** to add a new address, they can't select **Business** from the **Purpose** dropdown box.</span></span>

![L’employé ne peut pas ajouter d’adresse professionnelle](./media/hr-employee-self-service-restrict-add.png)

<span data-ttu-id="f9bdb-127">Les employés bénéficient de la même expérience lorsqu’ils sélectionnent **Détails du contact** sur la page **Renseignements personnels** et ajoutent une nouvelle adresse.</span><span class="sxs-lookup"><span data-stu-id="f9bdb-127">Employees get the same experience when they select **Contact details** on the **Personal information** page and add a new address.</span></span> <span data-ttu-id="f9bdb-128">La liste déroulante **But** affiche uniquement les types d’informations qu’ils peuvent ajouter.</span><span class="sxs-lookup"><span data-stu-id="f9bdb-128">The **Purpose** dropdown box only displays the types of information they can add.</span></span> 

![L’employé ne peut pas sélectionner l’entreprise dans la liste déroulante Objectif](./media/hr-employee-self-service-restrict-purpose.png)

<span data-ttu-id="f9bdb-130">**Détails du contact** montre maintenant **But** dans la grille.</span><span class="sxs-lookup"><span data-stu-id="f9bdb-130">**Contact details** now shows **Purpose** in the grid.</span></span>

![Le but s’affiche dans la grille des détails du contact](./media/hr-employee-self-service-restrict-purpose-grid.png)

## <a name="see-also"></a><span data-ttu-id="f9bdb-132">Voir également :</span><span class="sxs-lookup"><span data-stu-id="f9bdb-132">See also</span></span>

[<span data-ttu-id="f9bdb-133">Vue d’ensemble du libre-service pour employés et pour responsables</span><span class="sxs-lookup"><span data-stu-id="f9bdb-133">Employee and Manager self service overview</span></span>](hr-employee-manager-self-service-overview.md)<br>
[<span data-ttu-id="f9bdb-134">Configurer les paramètres de Human Resources</span><span class="sxs-lookup"><span data-stu-id="f9bdb-134">Configure Human resources parameters</span></span>](hr-setup-parameters.md)<br>
[<span data-ttu-id="f9bdb-135">Modifier les informations personnelles</span><span class="sxs-lookup"><span data-stu-id="f9bdb-135">Edit personal information</span></span>](hr-employee-manager-self-service-edit-personal-information.md)