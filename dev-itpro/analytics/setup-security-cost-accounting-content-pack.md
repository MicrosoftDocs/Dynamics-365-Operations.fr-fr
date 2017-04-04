---
title: "Sécurité de paramétrage pour le contenu BI de courant d&quot;analyse de contrôle de gestion"
description: "Cette rubrique explique comment propager la sécurité de niveau d&quot;accès dans le contrôle de gestion à la sécurité au niveau de la ligne en BI de courant de Microsoft. Cette fonctionnalité permet de garantir que les utilisateurs peuvent afficher uniquement les données BI de courant qu&quot;ils sont autorisés à accéder à."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 270294
ms.assetid: 3a7ba8b0-ac57-4159-9cd8-4308f6021f36
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 1e42622e7621c645d7eda3299f78c34c7e41a251
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-security-for-the-cost-accounting-analysis-power-bi-content"></a>Sécurité de paramétrage pour le contenu BI de courant d'analyse de contrôle de gestion

Cette rubrique explique comment propager la sécurité de niveau d'accès dans le contrôle de gestion à la sécurité au niveau de la ligne en BI de courant de Microsoft. Cette fonctionnalité permet de garantir que les utilisateurs peuvent afficher uniquement les données BI de courant qu'ils sont autorisés à accéder à.

<a name="overview"></a>Vue d'ensemble
--------

** Analyse de contrôle de gestion ** les utilisations de contenu BI de courant de Microsoft actionnent la sécurité au niveau de la ligne BI pour limiter l'accès d'un utilisateur. La sécurité est basée sur la hiérarchie organisationnelle de niveau d'accès qui est définie dans les paramètres de contrôle de gestion. Pour plus d'informations sur ** analyse de contrôle de gestion ** actionnez le contenu BI, voir [contenu BI de courant d'analyse de contrôle de gestion] (contrôle de gestion - analysis-content-pack.md).

## <a name="setup"></a>Configuration
Pour propager la sécurité de niveau d'accès pour activer le projet BI, le propriétaire du contenu BI de courant doit procéder comme suit. ** Remarque : ** L'utilisateur qui crée ** analyse de contrôle de gestion ** le contenu BI de courant devient automatiquement le propriétaire. Seul un propriétaire peut paramétrer la sécurité en BI de courant. En outre, jusqu'à ce qu'un propriétaire ajoute d'autres utilisateurs dans PowerBI.com, personne à moins que le propriétaire puisse afficher toutes les données dans ** analyse de contrôle de gestion ** actionnez le contenu du projet BI.

1.  Émission du fichier de définition pour activer le projet BI.
2.  Connexion à PowerBI.com.
3.  Rechercher que l'ensemble de données pour ** analyse de contrôle de gestion ** actionnez le contenu du projet BI.
4.  Permet d'ouvrir la page de sécurité. 

    [![ouvrant la page de sécurité] (https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-1.png)] (https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-1.png)

5.  ** Contrôleur d'objet de coût ** le rôle est déjà créé. Ajoutez d'autres membres qui font partie de la hiérarchie d'organisation de niveau d'accès de contrôle de gestion. 

    [![ajoutant membres] (https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-2.png)] (https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-2.png)

Les utilisateurs qui sont ajoutés ** contrôleur d'objet de coût ** au rôle ne voient que les données qu'il leur permettent de consulter, selon la définition dans la hiérarchie organisationnelle de niveau d'accès de contrôle de gestion. ** Remarque : ** la sécurité au niveau de la ligne s'applique aux vignettes et aux états dans Microsoft Dynamics 365 pour les opérations qui sont intégrées du projet BI de courant.

## <a name="updating-security"></a>Mettre la sécurité à jour
Si des mises à jour sont effectuées à la sécurité de niveau d'accès dans le contrôle de gestion, et si vous souhaitez le projet BI de courant pour refléter les mises à jour, vous devez mettre le magasin à jour d'entité pour ** analyse de contrôle de gestion ** actionnez le contenu du projet BI. Lorsque la mise à jour de magasin d'entité de Dynamics 365 pour les opérations, vous devez mettre des artefacts à jour sur PowerBI.com. Pour plus d'informations sur la création d'une mise à jour de magasin d'entité, voir [magasin d'entité de mise à jour power-bi-integration-entity-store.md#update-entity-store] (). Le propriétaire ** analyse de contrôle de gestion ** du contenu BI de courant vous devez également opérer une mise à jour de magasin d'entité si de nouveaux utilisateurs sont autorisés à accéder à la hiérarchie organisationnelle. En outre, le propriétaire doit ajouter les nouveaux utilisateurs ** évaluation des coûts le contrôleur d'objet ** au rôle dans PowerBI.com, de sorte que la sécurité au niveau de la ligne soit appliquée pour eux.

## <a name="disabling-security"></a>Désactiver la sécurité
Nous considérons que votre organisation souhaite restreindre l'accès aux données. Si, pour quelque raison, les paramètres de sécurité sont désactivées lorsque vous exécutez le contrôle de gestion, le propriétaire doit ajouter des utilisateurs ** comptable de coût ** au rôle dans BI de courant à la place. Si vous modifiez la sécurité d'un rapport activé à un état Désactivé, il est utile de supprimer des utilisateurs ** évaluation des coûts le contrôleur d'objet ** du rôle. Et inversement si vous réactivez la sécurité. Les utilisateurs peuvent appartenir à deux rôles. L'accès courant est le syndicat des deux rôles. En cas de ** analyse de contrôle de gestion ** actionnez le contenu BI, les utilisateurs ayant accès commun avoir accès non restriction de données. Si votre objectif est d'appliquer l'accès limité, les utilisateurs doivent être affectés uniquement ** évaluation des coûts le contrôleur d'objet ** au rôle. Ces mises à jour de sécurité au niveau de la ligne entrent immédiatement en vigueur. Les utilisateurs affectés doivent actualiser leur navigateur.

## <a name="additional-resources"></a>Ressources supplémentaires
Pour en savoir plus sur la sécurité au niveau de la ligne BI de courant, voir [gérer la sécurité sur le modèle en BI de courant] (https://powerbi.microsoft.com/en-us/documentation/powerbi-admin-rls/#manage-security-on-your-model).


