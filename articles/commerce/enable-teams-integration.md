---
title: Activer l’intégration de Dynamics 365 Commerce et Microsoft Teams
description: Cette rubrique décrit comment activer l’intégration de Microsoft Dynamics 365 Commerce et Microsoft Teams.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: eb0b8b419b302fbd0bc107bca22f8b26774ba3c7
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019833"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a><span data-ttu-id="b2659-103">Activer l’intégration de Dynamics 365 Commerce et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b2659-103">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b2659-104">Cette rubrique décrit comment activer l’intégration de Microsoft Dynamics 365 Commerce et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b2659-104">This topic describes how to enable Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

<span data-ttu-id="b2659-105">Pour configurer Teams avec les informations provenant de Dynamics 365 Commerce et synchroniser les fonctionnalités de gestion des tâches entre Teams et l’application de point de vente (PDV), vous devez activer les fonctionnalités d’intégration dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="b2659-105">To provision Teams with information from Dynamics 365 Commerce and synchronize the task management features between Teams and the point of sale (POS) application, you must enable the integration features in Commerce headquarters.</span></span>

> [!NOTE]
> <span data-ttu-id="b2659-106">Lorsque vous activez l’intégration de Teams, vous acceptez de partager vos données avec Teams.</span><span class="sxs-lookup"><span data-stu-id="b2659-106">When you enable Teams integration, you consent to share your data with Teams.</span></span> <span data-ttu-id="b2659-107">Les données partagées avec Teams peuvent résider dans un pays différent de vos données Commerce et être soumises à des normes de conformité différentes.</span><span class="sxs-lookup"><span data-stu-id="b2659-107">Data that is shared with Teams might reside in a different country than your Commerce data, and it might be subject to different compliance standards.</span></span> <span data-ttu-id="b2659-108">Pour plus d’informations, reportez-vous au [Centre de gestion de la confidentialité Microsoft](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="b2659-108">For more information, see the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="b2659-109">Pour plus d’informations sur les politiques de confidentialité de Microsoft, consultez la [Déclaration de confidentialité de Microsoft](https://aka.ms/privacy).</span><span class="sxs-lookup"><span data-stu-id="b2659-109">For information about Microsoft privacy policies, see the [Microsoft Privacy Statement](https://aka.ms/privacy).</span></span>

## <a name="enable-teams-integration"></a><span data-ttu-id="b2659-110">Activer l’intégration de Teams</span><span class="sxs-lookup"><span data-stu-id="b2659-110">Enable Teams integration</span></span>

<span data-ttu-id="b2659-111">Avant de pouvoir activer l’intégration de Microsoft Teams avec Commerce, vous devez inscrire l’application Teams auprès de votre locataire dans le portail Azure.</span><span class="sxs-lookup"><span data-stu-id="b2659-111">Before you can enable Microsoft Teams integration with Commerce, you must register the Teams application with your tenant in the Azure portal.</span></span>

<span data-ttu-id="b2659-112">Pour inscrire l’application Teams auprès de votre locataire dans le portail Azure, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="b2659-112">To register the Teams application with your tenant in the Azure portal, follow these steps.</span></span>

1. <span data-ttu-id="b2659-113">Suivez les étapes de [Démarrage rapide : inscrire une application sur la plateforme d’identité Microsoft](/azure/active-directory/develop/quickstart-register-app) pour inscrire l’application Teams auprès de votre locataire dans le portail Azure.</span><span class="sxs-lookup"><span data-stu-id="b2659-113">Follow the steps in [Quickstart: Register an app in the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app) to register the Teams application with your tenant in the Azure portal.</span></span>
1. <span data-ttu-id="b2659-114">Copiez la valeur de l’**ID d’application (client)** de la page **Présentation** pour l’application inscrite.</span><span class="sxs-lookup"><span data-stu-id="b2659-114">Copy the **Application (client) ID** value from the **Overview** page for the registered app.</span></span> <span data-ttu-id="b2659-115">Vous utiliserez cette valeur pour activer l’intégration de Teams dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="b2659-115">You will use this value to enable Teams integration in Commerce headquarters.</span></span>
1. <span data-ttu-id="b2659-116">Copiez la valeur du certificat qui a été entrée lorsque vous avez [ajouté un certificat](/azure/active-directory/develop/quickstart-register-app#add-a-certificate) à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="b2659-116">Copy the certificate value that was entered when you [added a certificate](/azure/active-directory/develop/quickstart-register-app#add-a-certificate) in step 1.</span></span> <span data-ttu-id="b2659-117">Le certificat est également appelé clé publique ou clé d’application.</span><span class="sxs-lookup"><span data-stu-id="b2659-117">The certificate is also known as the public key or application key.</span></span> <span data-ttu-id="b2659-118">Vous utiliserez cette valeur pour activer l’intégration de Teams dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="b2659-118">You will use this value to enable Teams integration in Commerce headquarters.</span></span>

<span data-ttu-id="b2659-119">Pour activer l’intégration de Teams dans Commerce Headquarters, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="b2659-119">To enable Teams integration in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="b2659-120">Accédez à **Retail et Commerce \> Paramétrage du canal \> Configuration de l’intégration de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="b2659-120">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams integration configuration**.</span></span>
1. <span data-ttu-id="b2659-121">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="b2659-121">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="b2659-122">Définissez l’option **Activer l’intégration de Microsoft Teams** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="b2659-122">Set the **Enable Microsoft Teams integration** option to **Yes**.</span></span>
1. <span data-ttu-id="b2659-123">Dans les champs **ID d’application** et **Clé d’application**, entrez les valeurs que vous avez obtenues lors de l’inscription de l’application Teams dans le portail Azure.</span><span class="sxs-lookup"><span data-stu-id="b2659-123">In the **Application ID** and **Application key** fields, enter the values you obtained when you registered the Teams application in the Azure portal.</span></span>
1. <span data-ttu-id="b2659-124">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b2659-124">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="b2659-125">L’illustration suivante montre un exemple de la configuration de l’intégration Teams dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="b2659-125">The following illustration shows an example of the configuration of Teams integration in Commerce headquarters.</span></span>

![Configuration de l’intégration de Teams dans Commerce Headquarters](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

## <a name="disable-teams-integration"></a><span data-ttu-id="b2659-127">Désactiver l’intégration de Teams</span><span class="sxs-lookup"><span data-stu-id="b2659-127">Disable Teams integration</span></span>

<span data-ttu-id="b2659-128">Pour désactiver l’intégration de Microsoft Teams dans Commerce Headquarters, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="b2659-128">To disable Microsoft Teams integration in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="b2659-129">Accédez à **Retail et Commerce \> Paramétrage du canal \> Configuration de l’intégration de Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="b2659-129">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="b2659-130">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="b2659-130">On the Action Pane, select **Edit**.</span></span>
3. <span data-ttu-id="b2659-131">Définissez l’option **Activer l’intégration de Microsoft Teams** sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="b2659-131">Set the **Enable Microsoft Teams integration** option to **No**.</span></span>
4. <span data-ttu-id="b2659-132">Effacez les valeurs des champs **ID d’application** et **Clé d’application**.</span><span class="sxs-lookup"><span data-stu-id="b2659-132">Clear the values from the **Application ID** and **Application Key** fields.</span></span>
1. <span data-ttu-id="b2659-133">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b2659-133">On the Action Pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="b2659-134">Une fois que vous avez désactivé l’intégration de Teams avec Commerce, les terminaux de point de vente n’afficheront plus les tâches publiées à partir de l’application Teams.</span><span class="sxs-lookup"><span data-stu-id="b2659-134">After you disable Teams integration with Commerce, POS terminals will no longer show tasks that are published from the Teams application.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b2659-135">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b2659-135">Additional resources</span></span>

[<span data-ttu-id="b2659-136">Présentation de l’intégration de Dynamics 365 Commerce et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b2659-136">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="b2659-137">Configuration de Microsoft Teams à partir de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="b2659-137">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="b2659-138">Synchroniser la gestion des tâches entre Microsoft Teams et les PDV Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="b2659-138">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="b2659-139">Gérer les rôles utilisateur dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b2659-139">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="b2659-140">Mapper les magasins et les équipes si votre organisation a des équipes préexistantes dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b2659-140">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="b2659-141">FAQ sur l’intégration de Dynamics 365 Commerce et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b2659-141">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)