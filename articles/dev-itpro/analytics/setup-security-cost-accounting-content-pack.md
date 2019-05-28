---
title: Paramétrage de la sécurité pour l'analyse de contrôle de gestion - Contenu Power BI
description: Cette rubrique explique comment propager la sécurité au niveau des accès dans le contrôle de gestion à la sécurité au niveau des lignes dans Microsoft Power BI. Cette fonctionnalité permet de garantir que les utilisateurs n'affichent que les données Power BI auxquelles ils sont autorisés à accéder.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 270294
ms.assetid: 3a7ba8b0-ac57-4159-9cd8-4308f6021f36
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d1cd378a58d4a4fe4388238f97e84a8e2b07937b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551458"
---
# <a name="set-up-security-for-the-cost-accounting-analysis-power-bi-content"></a>Paramétrage de la sécurité pour l'analyse de contrôle de gestion - Contenu Power BI

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment propager la sécurité au niveau des accès dans le contrôle de gestion à la sécurité au niveau des lignes dans Microsoft Power BI. Cette fonctionnalité permet de garantir que les utilisateurs n'affichent que les données Power BI auxquelles ils sont autorisés à accéder.

## <a name="overview"></a>Présentation

Le contenu **Analyse du contrôle de gestion** Microsoft Power BI utilise la sécurité au niveau des lignes de Power BI pour restreindre l'accès des utilisateurs. La sécurité est basée sur la hiérarchie organisationnelle au niveau des accès qui est définie dans les paramètres du contrôle de gestion. Pour plus d'informations sur le contenu Power BI **Analyse du contrôle de gestion**, voir [Contenu Power BI d'analyse du contrôle de gestion](cost-accounting-analysis-content-pack.md).

## <a name="setup"></a>Paramétrage
Pour propager la sécurité au niveau des accès à Power BI, le propriétaire du contenu Power BI doit procéder comme suit.

> [!NOTE]
> L'utilisateur qui publie le contenu Power BI **Analyse du contrôle de gestion** en devient automatiquement le propriétaire. Seul un propriétaire peut paramétrer la sécurité dans Power BI. En outre, jusqu'à ce qu'un propriétaire ajoute d'autres utilisateurs sur PowerBI.com, personne sauf le propriétaire ne peut afficher de données dans le contenu Power BI **Analyse du contrôle de gestion**.

1. Publiez le fichier de définition sur Power BI.
2. Connectez-vous à PowerBI.com.
3. Cherchez le jeu de données pour le contenu Power BI **Analyse du contrôle de gestion**.
4. Ouvrez la page de sécurité.

    ![Ouverture de la page de sécurité](./media/CA-picture-1.png)

5. Le rôle **Contrôleur d'objet de coût** est déjà créé. Ajoutez d'autres membres qui appartiennent à la hiérarchie organisationnelle au niveau des accès du contrôle de gestion.

    ![Ajout de membres](./media/CA-picture-2.png)

Les utilisateurs qui sont ajoutés au rôle **Contrôleur d'objet de coût** ne voient que les données auxquelles ils sont autorisés, conformément à la définition donnée dans la hiérarchie organisationnelle au niveau des accès du contrôle de gestion.

> [!NOTE]
> La sécurité au niveau de la ligne s'applique aux vignettes et aux états dans Microsoft Dynamics 365 for Finance and Operations intégrés depuis Power BI.

## <a name="updating-security"></a>Mise à jour de la sécurité
Si la sécurité au niveau des accès dans le contrôle de gestion subit des mises à jour et que vous souhaitez que Power BI en tienne compte, vous devez mettre à jour le magasin d'entités pour le contenu Power BI **Analyse du contrôle de gestion**. Une fois la mise à jour du magasin d'entités effectuée à partir de Finance and Operations, vous devez mettre à jour les artefacts sur PowerBI.com. Pour plus d'informations sur la procédure de mise à jour d'un magasin d'entités, voir [Mettre à jour le magasin d'entités](power-bi-integration-entity-store.md#update-entity-store). Le propriétaire du contenu Power BI **Analyse du contrôle de gestion** doit également effectuer une mise à jour du magasin d'entités si de nouveaux utilisateurs obtiennent l'accès à la hiérarchie organisationnelle. En outre, le propriétaire doit ajouter les nouveaux utilisateurs au rôle **Contrôleur d'objet de coût** sur PowerBI.com, de sorte que la sécurité au niveau des lignes s'applique à eux.

## <a name="disabling-security"></a>Désactivation de la sécurité
Supposons que votre organisation souhaite restreindre l'accès aux données. Si, pour quelque raison, les paramètres de sécurité sont désactivés lorsque vous exécutez le contrôle de gestion, le propriétaire doit ajouter des utilisateurs au rôle **Contrôleur de gestion** dans Power BI. Si vous passez la sécurité de l'état activé à l'état désactivé, il est bon de supprimer des utilisateurs du rôle **Contrôleur d'objet de coût**. Et inversement si vous réactivez la sécurité. Les utilisateurs peuvent appartenir aux deux rôles. L'accès conjoint est la réunion des deux rôles. Dans le cas du contenu Power BI **Analyse du contrôle de gestion**, les utilisateurs qui disposent de l'accès conjoint ont un accès sans restriction aux données. Si votre objectif est de restreindre les accès, les utilisateurs doivent être affectés uniquement au rôle **Contrôleur d'objet de coût**. Ces mises à jour de sécurité au niveau des lignes prennent effet immédiatement. Les utilisateurs affectés doivent actualiser leur navigateur.

## <a name="additional-resources"></a>Ressources supplémentaires
Pour en savoir plus sur la sécurité au niveau des lignes de Power BI, voir [Gérer la sécurité de votre modèle dans Power BI](https://powerbi.microsoft.com/en-us/documentation/powerbi-admin-rls/#manage-security-on-your-model).
