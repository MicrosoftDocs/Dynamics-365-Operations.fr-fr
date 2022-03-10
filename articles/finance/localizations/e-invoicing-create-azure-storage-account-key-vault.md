---
title: Créer un compte de stockage Azure et un coffre de clés
description: Cette rubrique explique comment créer un compte de stockage Azure et un coffre de clés.
author: gionoder
ms.date: 08/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 23fec7a00d800719e1a7d2c90f9d0977d56be038
ms.sourcegitcommit: baf82100f0aa7d5f5f47c7f54bc155d8a07beab5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/31/2021
ms.locfileid: "7463855"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a>Créer un compte de stockage Azure et un coffre de clés

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a>Conditions préalables

Avant de pouvoir effectuer les étapes de cette rubrique, vous devez vérifier que les tâches suivantes ont été réalisées :

- Créer une ressource de coffre de clés dans Azure. Pour plus d’informations, voir [À propos de Azure Key Vault](/azure/key-vault/general/overview).
- Créer un compte de stockage Azure (stockage Blob). Pour plus d’informations, voir [Gestion du compte de stockage Azure](/azure/storage/blobs/).

## <a name="overview"></a>Vue d’ensemble

Dans cette rubrique, vous effectuerez deux étapes principales :

- Configurer le compte de stockage Azure pour obtenir l’URI du compte de stockage.
- Configurer le coffre de clés pour stocker l’URI du compte de stockage.

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a>Configurer le compte de stockage Azure pour obtenir l’URI du compte de stockage

1. Ouvrez le compte de stockage que vous prévoyez d’utiliser avec la Facturation électronique.
2. Accédez à **Stockage de données** > **Conteneurs** et créez un nouveau conteneur.
3. Entrez un nom pour le conteneur et définissez le champ **Niveau d’accès public** sur **Privé (pas d’accès anonyme)**.
4. Ouvrez le conteneur et accédez à **Paramètres** > **Stratégie d’accès**.
5. Sélectionnez **Ajouter une stratégie** pour ajouter une stratégie d’accès stockée.
6. Définissez les champs **Identifiant** et **Autorisations** au besoin. Dans le champ **Autorisations**, vous devez sélectionner toutes les autorisations.

    ![Octroi de l’autorisation de stockage Blob.](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. Entrez les dates de début et d’expiration. La date d’expiration doit être dans le futur.
8. Cliquez sur **OK** pour enregistrer la stratégie, puis enregistrez vos modifications du conteneur.
9. Accédez à **Paramètres** > **Jetons d'accès partagés** et définissez les valeurs de champ. 
10. Entrez les dates de début et de fin. La date de fin doit être dans le futur.
11. Dans le champ **Autorisations**, sélectionnez les autorisations suivantes : **Lire**, **Ajouter**, **Créer**, **Écrire**, **Supprimer** et **Répertorier**. 
12. Sélectionnez **Générer un jeton SAS et une URL**.
13. Copiez et stockez la valeur dans le champ **URL SAS du blob**. Cette valeur sera utilisée dans la procédure suivante et sera appelée *URI de la signature d’accès partagé*.

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a>Configurer le coffre de clés pour stocker l’URI du compte de stockage

1. Ouvrez le coffre de clés que vous souhaitez utiliser avec la Facturation électronique.
2. Allez dans **Paramètres** \> **Secrets**, puis sélectionnez **Générer/Importer** pour créer un nouveau secret.
3. Sur la page **Créer un secret**, dans le champ **Options de téléchargement**, sélectionnez **Manuel**.
4. Entrez le nom du secret. Ce nom sera utilisé lors de la configuration du service dans Regulatory Configuration Service (RCS) et sera appelé *nom du secret du coffre de clés*.
5. Dans le champ **Valeur**, entrez l'URI de la signature d'accès partagé que vous avez copiée dans la procédure précédente, puis sélectionnez **Créer**.
6. Configurez la stratégie d’accès pour accorder à la Facturation électronique le niveau correct d’accès sécurisé au secret que vous avez créé. Allez dans **Paramètres \> Stratégie d’accès** et sélectionnez **Ajouter une stratégie d’accès**.
7. Définissez les autorisations du secret pour les opérations **Obtenir** et **Lister**.

    ![Autorisation de l’accès au service.](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. Définissez les autorisations du certificat pour les opérations **Obtenir** et **Lister**.

    ![Octroi de l’autorisation de certificat.](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. Dans le champ **Sélectionnez le principal**, sélectionnez **Aucune sélection**.
10. Dans la boîte de dialogue **Principal**, sélectionnez le principal en ajoutant **Service de facturation électronique**.
11. Sélectionnez **Ajouter**, puis sélectionnez **Enregistrer**.
12. Sur la page **Vue d’ensemble**, copiez la valeur **Nom DNS** du coffre de clés. Cette valeur sera utilisée lors de la configuration du service dans RCS et sera désignée sous le nom *URI du coffre de clés*.

> [!NOTE]
> Pour une sécurité supplémentaire sur le compte de stockage, configurez Azure Defender pour le stockage.
> 
> Pour plus d'informations, consultez [Introduction à Azure Defender pour le stockage](/azure/security-center/defender-for-storage-introduction).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
