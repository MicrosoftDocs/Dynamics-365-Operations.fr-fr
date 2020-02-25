---
title: Permuter entre les configurations de fournisseur
description: Cette rubrique décrit comment basculer l'intégration des données fournisseur entre les applications Finance and Operations et Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 587a9b98f28b11e303aff4b59e9726f220d956eb
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019773"
---
# <a name="switch-between-vendor-designs"></a>Permuter entre les configurations de fournisseur

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

## <a name="vendor-data-flow"></a>Flux de données fournisseur 

Si vous souhaitez utiliser d'autres applications Dynamics 365 pour la gestion des fournisseurs, et si vous souhaitez isoler les informations fournisseur des informations client, vous pouvez utiliser la conception de fournisseur de base.  

![Flux de fournisseur de base](media/dual-write-vendor-data-flow.png)
 
Si vous souhaitez utiliser d'autres applications Dynamics 365 pour la gestion des fournisseurs, et que vous souhaitez continuer d'utiliser l'entité **Compte** pour stocker les informations fournisseur, vous pouvez utiliser la nouvelle conception de fournisseur étendue. Dans cette conception, les informations fournisseur étendues telles que le statut En attente du fournisseur et le profil du fournisseur sont stockées dans l'entité **fournisseurs** dans Common Data Service. 

![Flux de fournisseur étendu](media/dual-write-vendor-detail.jpg)
 
Procédez comme suit pour utiliser la conception étendue de fournisseur : 
 
1. Le pack de solution **SupplyChainCommon** contient les modèles de processus de workflow comme le montre l'illustration suivante.
    > [!div class="mx-imgBorder"]
    > ![Modèles de processus de workflow](media/dual-write-switch-3.png)
2. Permet de créer de nouveaux processus de workflow à l'aide des modèles de processus de workflow : 
    1. Créez un nouveau processus de workflow pour l'entité **Fournisseur** à l'aide du modèle de processus de workflow **Créer des fournisseurs dans l'entité de compte** et cliquez sur **OK**. Ce workflow traite le scénario de création du fournisseur pour l'entité **Compte**.
        > [!div class="mx-imgBorder"]
        > ![Créer des fournisseurs dans l'entité Compte](media/dual-write-switch-4.png)
    2. Créez un nouveau processus de workflow pour l'entité **Fournisseur** à l'aide du modèle de processus de workflow **Mettre à jour l'entité Comptes** et cliquez sur **OK**. Ce workflow traite le scénario de mise à jour du fournisseur pour l'entité **Compte**. 
        > [!div class="mx-imgBorder"]
        > ![Mettre à jour l'entité Comptes](media/dual-write-switch-5.png)
    3. Créez de nouveaux processus de workflow depuis les modèles créés sur l'entité **Comptes**. 
        > [!div class="mx-imgBorder"]
        > ![Créer des fournisseurs dans l'entité Fournisseurs](media/dual-write-switch-6.png)
        > [!div class="mx-imgBorder"]
        > ![Mettre à jour l'entité Fournisseurs](media/dual-write-switch-7.png)
    4. Vous pouvez configurer les workflows comme workflows en temps réel ou workflows d'arrière plan selon vos besoins. 
        > [!div class="mx-imgBorder"]
        > ![Convertir vers un workflow d'arrière-plan](media/dual-write-switch-8.png)
    5. Activez les workflows que vous avez créés sur les entités **Compte** et **Fournisseur** pour commencer à utiliser l'entité **Compte** pour enregistrer les informations fournisseur. 
 
