---
title: Impossible de configurer un groupe de sécurité pour le générateur de site Commerce lors du déploiement initial
description: Cet article fournit des conseils de résolution des problèmes qui peuvent aider lorsque le groupe de sécurité Microsoft Azure Active Directory (Azure AD) pour le générateur de site Commerce n’apparaît pas comme option lorsque vous créez des composants e-commerce dans Microsoft Dynamics Lifecycle Services (LCS) lors du déploiement initial d’un nouveau locataire e-commerce.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 7098c853c262fd7e0d48231634b232eef71c2b8d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291998"
---
# <a name="cant-configure-a-security-group-for-commerce-site-builder-during-initial-deployment"></a>Impossible de configurer un groupe de sécurité pour le générateur de site Commerce lors du déploiement initial

[!include [banner](../../includes/banner.md)]

Cet article fournit des conseils de résolution des problèmes qui peuvent aider lorsque le groupe de sécurité Microsoft Azure Active Directory (Azure AD) pour le générateur de site Commerce n’apparaît pas comme option lorsque vous créez des composants e-commerce dans Microsoft Dynamics Lifecycle Services (LCS) lors du déploiement initial d’un nouveau locataire e-commerce.

## <a name="description"></a>Description

Lorsque vous créez les composants e-commerce dans le cadre du processus de déploiement d’un nouveau locataire e-commerce qui inclut le composant de générateur de site Commerce, le groupe de sécurité Azure AD n’apparaît pas comme option dans la boîte de dialogue.

## <a name="resolution"></a>Résolution

### <a name="provision-the-e-commerce-site-with-a-user-in-the-correct-tenant"></a>Fournir un client dans le locataire approprié pour le site d’e-commerce

1. Accédez au [Portail Azure](https://portal.azure.com/).
1. Sous le locataire pour lequel le projet LCS pour votre site d’e-commerce a été provisionné, suivez les instructions de [Créer un groupe de base et ajouter des membres à l’aide d’Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).
1. Accédez à [LCS](https://lcs.dynamics.com/) et connectez-vous à l’aide d’un compte qui partage le même locataire que le groupe de sécurité Azure AD que vous venez de créer. Le compte doit avoir accès pour afficher le groupe de sécurité Azure AD.
1. Suivez les étapes de configuration pour configurer le site d’e-commerce. Lorsque vous provisionnez les composants e-commerce, le groupe de sécurité doit maintenant apparaître comme option dans la boîte de dialogue.

> [!NOTE]
> Pour vous assurer que le champ de la boîte de dialogue contient la liste des groupes de sécurité, vous devez sélectionner **Entrer** après avoir entré le nom du groupe de sécurité Azure AD que vous avez créé. Les résultats de la recherche listeront tous les groupes de sécurité Azure AD commençant par le texte de recherche et auxquels l’utilisateur a accès. Vous pouvez utiliser un terme de recherche plus court pour obtenir des résultats de recherche plus larges.

## <a name="additional-resources"></a>Ressources supplémentaires

[Créer un groupe de base et ajouter des membres à l’aide d’Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

[Déployer un nouveau client e-commerce](../deploy-ecommerce-site.md)
