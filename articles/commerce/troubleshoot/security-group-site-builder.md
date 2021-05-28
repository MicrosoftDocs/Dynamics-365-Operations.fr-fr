---
title: Impossible de configurer un groupe de sécurité pour le générateur de site Commerce lors du déploiement initial
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque le groupe de sécurité Microsoft Azure Active Directory (Azure AD) pour le générateur de site Commerce n’apparaît pas comme option lorsque vous créez des composants e-commerce dans Microsoft Dynamics Lifecycle Services (LCS) lors du déploiement initial d’un nouveau locataire e-commerce.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d29e560d0f7b2bbc2415d7a0f6fe18f2ca17dc7c
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020730"
---
# <a name="cant-configure-a-security-group-for-commerce-site-builder-during-initial-deployment"></a><span data-ttu-id="9fc18-103">Impossible de configurer un groupe de sécurité pour le générateur de site Commerce lors du déploiement initial</span><span class="sxs-lookup"><span data-stu-id="9fc18-103">Can't configure a security group for Commerce site builder during initial deployment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9fc18-104">Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsque le groupe de sécurité Microsoft Azure Active Directory (Azure AD) pour le générateur de site Commerce n’apparaît pas comme option lorsque vous créez des composants e-commerce dans Microsoft Dynamics Lifecycle Services (LCS) lors du déploiement initial d’un nouveau locataire e-commerce.</span><span class="sxs-lookup"><span data-stu-id="9fc18-104">This topic provides troubleshooting guidance that can help when the Microsoft Azure Active Directory (Azure AD) security group for Commerce site builder doesn't appear as an option when you create e-commerce components in Microsoft Dynamics Lifecycle Services (LCS) during initial deployment of a new e-commerce tenant.</span></span>

## <a name="description"></a><span data-ttu-id="9fc18-105">Description</span><span class="sxs-lookup"><span data-stu-id="9fc18-105">Description</span></span>

<span data-ttu-id="9fc18-106">Lorsque vous créez les composants e-commerce dans le cadre du processus de déploiement d’un nouveau locataire e-commerce qui inclut le composant de générateur de site Commerce, le groupe de sécurité Azure AD n’apparaît pas comme option dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9fc18-106">When you create the e-commerce components as part of the process of deploying a new e-commerce tenant that includes the Commerce site builder component, the Azure AD security group doesn't appear as an option in the dialog box.</span></span>

## <a name="resolution"></a><span data-ttu-id="9fc18-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="9fc18-107">Resolution</span></span>

### <a name="provision-the-e-commerce-site-with-a-user-in-the-correct-tenant"></a><span data-ttu-id="9fc18-108">Fournir un client dans le locataire approprié pour le site d’e-commerce</span><span class="sxs-lookup"><span data-stu-id="9fc18-108">Provision the e-commerce site with a user in the correct tenant</span></span>

1. <span data-ttu-id="9fc18-109">Accédez au [Portail Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="9fc18-109">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="9fc18-110">Sous le locataire pour lequel le projet LCS pour votre site d’e-commerce a été provisionné, suivez les instructions de [Créer un groupe de base et ajouter des membres à l’aide d’Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="9fc18-110">Under the tenant that the LCS project for your e-commerce site was provisioned for, follow the instructions in [Create a basic group and add members using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span></span>
1. <span data-ttu-id="9fc18-111">Accédez à [LCS](https://lcs.dynamics.com/) et connectez-vous à l’aide d’un compte qui partage le même locataire que le groupe de sécurité Azure AD que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="9fc18-111">Go to [LCS](https://lcs.dynamics.com/), and sign in by using an account that shares the same tenant as the Azure AD security group that you just created.</span></span> <span data-ttu-id="9fc18-112">Le compte doit avoir accès pour afficher le groupe de sécurité Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9fc18-112">The account must have access to view the Azure AD security group.</span></span>
1. <span data-ttu-id="9fc18-113">Suivez les étapes de configuration pour configurer le site d’e-commerce.</span><span class="sxs-lookup"><span data-stu-id="9fc18-113">Complete the setup steps to configure the e-commerce site.</span></span> <span data-ttu-id="9fc18-114">Lorsque vous provisionnez les composants e-commerce, le groupe de sécurité doit maintenant apparaître comme option dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9fc18-114">When you provision the e-commerce components, the security group should now appear as an option in the dialog box.</span></span>

> [!NOTE]
> <span data-ttu-id="9fc18-115">Pour vous assurer que le champ de la boîte de dialogue contient la liste des groupes de sécurité, vous devez sélectionner **Entrer** après avoir entré le nom du groupe de sécurité Azure AD que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="9fc18-115">To ensure that the field in the dialog box is filled with the list of security groups, you must select **Enter** after you enter the name of the Azure AD security group that you created.</span></span> <span data-ttu-id="9fc18-116">Les résultats de la recherche listeront tous les groupes de sécurité Azure AD commençant par le texte de recherche et auxquels l’utilisateur a accès.</span><span class="sxs-lookup"><span data-stu-id="9fc18-116">The search results will list all the Azure AD security groups that start with the search text, and that the user has access to.</span></span> <span data-ttu-id="9fc18-117">Vous pouvez utiliser un terme de recherche plus court pour obtenir des résultats de recherche plus larges.</span><span class="sxs-lookup"><span data-stu-id="9fc18-117">You can use a shorter search term to allow for broader search results.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9fc18-118">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="9fc18-118">Additional resources</span></span>

[<span data-ttu-id="9fc18-119">Créer un groupe de base et ajouter des membres à l’aide d’Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9fc18-119">Create a basic group and add members using Azure Active Directory</span></span>](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

[<span data-ttu-id="9fc18-120">Déployer un nouveau client e-commerce</span><span class="sxs-lookup"><span data-stu-id="9fc18-120">Deploy a new e-commerce tenant</span></span>](../deploy-ecommerce-site.md)