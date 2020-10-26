---
title: Configurer des ressources Azure pour l’intelligence IoT
description: Cette rubrique explique comment créer et configurer les ressources Microsoft Azure dont vous avez besoin pour l’intelligence IoT.
author: ''
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bbac1676d28c7285c19ed48f77426a37ce123a29
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982892"
---
# <a name="set-up-azure-resources-for-iot-intelligence"></a>Configurer des ressources Azure pour l’intelligence IoT

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment créer et configurer les ressources Microsoft Azure dont vous avez besoin pour l’intelligence IoT.

## <a name="create-azure-resources"></a>Créer des ressources Azure

Suivez ces étapes pour créer un hub IoT, un cache Redis et un coffre de clés accessibles par Microsoft Dynamics 365 Supply Chain Management.

### <a name="verify-that-the-microsoft-dynamics-erp-microservices-first-party-app-id-is-in-your-tenant"></a>Vérifiez que l’ID d’application pour l’application propriétaire Microservices ERP Microsoft Dynamics est dans votre client

Pour vérifier que l’ID d’application pour l’application propriétaire Microservices ERP Microsoft Dynamics est dans votre client, procédez comme suit.

1. Connectez-vous au portail Azure à l’adresse suivante : <https://portal.azure.com>.
2. Atteindre **Azure Active Directory**.
3. Accédez à **Applications d’entreprise**.
4. Dans le champ **Type d’application**, sélectionnez **Applications Microsoft**.
5. Dans le champ de recherche, entrez **Microservices ERP Microsoft Dynamics**.
6. Vérifiez que **Microservices ERP Microsoft Dynamics** est bien dans la liste. D’autres applications ont des noms similaires. Par conséquent, veillez à disposer de l’application correcte. L’ID de l’application est **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.

    Si l’application ne figure pas dans la liste, vous devez l’ajouter à votre client :

    1. Dans le portail Azure, dans la barre d’outils, sélectionnez le bouton pour ouvrir Azure Cloud Shell.
    2. Exécutez la commande **Module d’installation AzureAD**. Entrer **O** pour installer le module.
    3. Exécutez la commande **Get-InstalledModule -Name "AzureAD"** pour vérifier que le module est installé.
    4. Exécutez la commande **Connect-AzureAD -Confirm** pour exécuter l’authentification.
    5. Exécutez la commande **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.

    Vous pouvez maintenant répéter les étapes 1 à 6 pour vérifier que l’ID d’application se trouve dans votre client.

### <a name="create-a-key-vault-resource"></a>Créer une ressource de coffre de clés

Pour créer une ressource de coffre de clés, procédez comme suit :

1. Dans le portail Azure, créez ou accédez à un groupe de ressources.
2. Sélectionnez **Ajouter**.
3. Sur la page **Nouveau**, entrez **Coffre de clés** dans le champ de recherche. Ensuite, sélectionnez **Créer**.
4. Sur la page **Créer un coffre de clés**, entrez un nom dans le champ **Nom du coffre de clés**.
5. Vérifiez les valeurs par défaut, puis sélectionnez **Vérifier + créer**.
6. Sélectionnez **Créer**.

Le coffre de clés est créé en arrière-plan.

### <a name="create-an-iot-hub-resource"></a>Créer une ressource hub IoT

Pour créer une ressource hub IoT, procédez comme suit :

1. Créez ou accédez à un groupe de ressources.
2. Sélectionnez **Ajouter**.
3. Sur la page **Nouveau**, entrez **Hub IoT** dans le champ de recherche. Ensuite, sélectionnez **Créer**.
4. Entrez un nom dans le champ **Nom du hub IoT**.
5. Vérifiez les valeurs par défaut, puis sélectionnez **Vérifier + créer**.
6. Sélectionnez **Créer**.

Le hub IoT est créé en arrière-plan.

> [!NOTE]
> Nous vous recommandons de créer une seule ressource hub IoT par environnement.

### <a name="create-a-redis-cache-resource"></a>Créer une ressource de cache Redis

Pour créer une ressource de cache Redis, procédez comme suit :

1. Créez ou accédez à un groupe de ressources.
2. Sélectionnez **Ajouter**.
3. Sur la page **Nouveau**, entrez **Cache Azure pour Redis** dans le champ de recherche. Ensuite, sélectionnez **Créer**.
4. Entrez un nom dans le champ **Nom DNS**.
5. Vérifiez les valeurs par défaut, puis sélectionnez **Créer**.

Le cache Redis est créé en arrière-plan.

> [!NOTE]
> Nous vous recommandons de créer un seul cache Redis par environnement.

Toutes les ressources sont maintenant créées.

## <a name="configure-the-azure-resources"></a>Configurer les ressources Azure

### <a name="configure-the-iot-hub"></a>Configurer le hub IoT

Procédez comme suit pour configurer le hub IoT.

1. Dans vos ressources, sélectionnez la ressource hub IoT.
2. Dans le volet de navigation de gauche, sélectionnez **Points de terminaison intégrés**.
3. Collez les groupes de consommateurs suivants sous **Groupes de consommateurs**. Ces groupes de consommateurs correspondent aux scénarios prêts à l’emploi.

    + microsoft.dynamics.iotintelligence-1
    + microsoft.dynamics.iotintelligence-2
    + microsoft.dynamics.iotintelligence-3

### <a name="configure-the-key-vault"></a>Configurer le coffre de clés

Procédez comme suit pour configurer le coffre de clés.

1. Sélectionnez la ressource de coffre de clés parmi vos ressources.
2. Sélectionnez **Stratégies d’accès** dans le volet de navigation de gauche.
3. Sélectionnez **Ajouter une stratégie d’accès**.
4. Sur la page **Ajouter une stratégie d’accès**, dans le champ **Autorisations secrètes**, sélectionnez **Obtenir** et **Liste**.
5. Cliquez dans le **Sélectionner le principal**.
6. Dans la boîte de dialogue **Principal**, recherchez et sélectionnez **Microservices ERP Microsoft Dynamics**. Cliquez ensuite sur **Sélectionner**.
7. Sélectionnez **Ajouter**.
8. Sélectionnez **Enregistrer**.

L’application a désormais accès aux secrets du coffre de clés.

### <a name="save-the-iot-hub-connection-string-secret"></a>Enregistrer le secret de la chaîne de connexion du hub IoT

Pour enregistrer le secret de la chaîne de connexion du hub IoT, procédez comme suit.

1. Dans vos ressources, sélectionnez la ressource hub IoT.
2. Dans le volet de navigation de gauche, sélectionnez **Points de terminaison intégrés**.
3. Copiez la valeur dans le champ **Point de terminaison compatible avec Event Hub**.
4. Accédez à la ressource de coffre de clés.
5. Dans le volet de navigation de gauche, sélectionnez **Secrets**.
6. Sélectionnez **Générer/Importer**.
7. Dans le champ **Nom**, entrez un nom.
8. Dans le champ **Valeur**, collez la valeur de point de terminaison que vous avez copiée précédemment.
9. Sélectionnez **Créer**.

### <a name="save-the-redis-cache-connection-string-secret"></a>Enregistrer le secret de la chaîne de connexion du cache Redis

Pour enregistrer le secret de la chaîne de connexion du cache Redis, procédez comme suit.

1. Sélectionnez la ressource de cache Redis parmi vos ressources.
2. Sélectionnez **Clés d’accès**.
3. Copiez la valeur dans le champ **Chaîne de connexion principale**.
4. Accédez à la ressource de coffre de clés.
5. Dans le volet de navigation de gauche, sélectionnez **Secrets**.
6. Sélectionnez **Générer/Importer**.
7. Dans le champ **Nom**, entrez un nom.
8. Dans le champ **Valeur**, collez la chaîne de connexion que vous avez copiée précédemment.
9. Sélectionnez **Créer**.

> [!NOTE]
> Chaque fois que vous mettez à jour l’une des chaînes de connexion, vous devez également mettre à jour les valeurs secrètes.

Vous avez maintenant terminé de provisionner les ressources Azure requises. La prochaine étape consiste à [installer le complément Intelligence IoT dans Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).
