---
title: Créer un compte de stockage Azure et un coffre de clés
description: Cette rubrique explique comment créer un compte de stockage Azure et un coffre de clés.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: d076aa5230437d1ef90f6b46d49ee4dea526db24
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104227"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a>Créer un compte de stockage Azure et un coffre de clés

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a>Conditions préalables

Avant de pouvoir effectuer les étapes de cette rubrique, vous devez vérifier que les tâches suivantes ont été réalisées :

- Créer une ressource de coffre de clés dans Azure. Pour plus d’informations, voir [À propos de Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/overview).
- Créer un compte de stockage Azure (stockage Blob). Pour plus d’informations, voir [Gestion du compte de stockage Azure](https://docs.microsoft.com/azure/storage/blobs/).

## <a name="overview"></a>Vue d’ensemble

Dans cette rubrique, vous effectuerez deux étapes principales :

- Configurer le compte de stockage Azure pour obtenir l’URI du compte de stockage.
- Configurer le coffre de clés pour stocker l’URI du compte de stockage.

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a>Configurer le compte de stockage Azure pour obtenir l’URI du compte de stockage

1. Ouvrez le compte de stockage que vous prévoyez d’utiliser avec le module complémentaire de facturation électronique.
2. Allez dans **Service Blob** \> **Conteneurs** et créez un nouveau conteneur.
3. Entrez un nom pour le conteneur et définissez le champ **Niveau d’accès public** sur **Privé (pas d’accès anonyme)**.
4. Ouvrez le conteneur et accédez à **Paramètres \> Stratégie d’accès**.
5. Sélectionnez **Ajouter une stratégie** pour ajouter une stratégie d’accès stockée.
6. Définissez les champs **Identifiant** et **Autorisations** au besoin. Dans le champ **Autorisations**, vous devez sélectionner toutes les autorisations.

    ![Octroi de l’autorisation de stockage Blob](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. Entrez les dates de début et d’expiration. La date d’expiration doit être dans le futur.
8. Cliquez sur **OK** pour enregistrer la stratégie, puis enregistrez vos modifications du conteneur.
9. Revenez au compte de stockage et ouvrez l’**Explorateur de stockage (version préliminaire)**.
10. Cliquez avec le bouton droit sur le conteneur, puis sélectionnez **Obtenir la signature d’accès partagé**.
11. Dans la boîte de dialogue **Signature d’accès partagé**, copiez et stockez la valeur dans le champ **URI**. Cette valeur sera utilisée dans la procédure suivante et sera appelée *URI de la signature d’accès partagé*.

    ![Sélection et copie de la valeur de l’URI](media/e-Invoicing-services-create-azure-resources-select-and-copy-uri.png)

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a>Configurer le coffre de clés pour stocker l’URI du compte de stockage

1. Ouvrez le coffre de clés que vous souhaitez utiliser avec le module complémentaire de facturation électronique.
2. Allez dans **Paramètres** \> **Secrets**, puis sélectionnez **Générer/Importer** pour créer un nouveau secret.
3. Sur la page **Créer un secret**, dans le champ **Options de téléchargement**, sélectionnez **Manuel**.
4. Entrez le nom du secret. Ce nom sera utilisé lors de la configuration du service dans Regulatory Configuration Service (RCS) et sera appelé *nom du secret du coffre de clés*.
5. Dans le champ **Valeur**, sélectionnez **URI de la signature d’accès partagé**, puis sélectionnez **Créer**.
6. Configurez la stratégie d’accès pour accorder au module complémentaire de facturation électronique le niveau correct d’accès sécurisé au secret que vous avez créé. Allez dans **Paramètres \> Stratégie d’accès** et sélectionnez **Ajouter une stratégie d’accès**.
7. Définissez les autorisations du secret pour les opérations **Obtenir** et **Lister**.

    ![Autorisation de l’accès au service](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. Définissez les autorisations du certificat pour les opérations **Obtenir** et **Lister**.

    ![Octroi de l’autorisation de certificat](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. Dans la boîte de dialogue **Principal**, sélectionnez le principal en ajoutant **Module complémentaire de facturation électronique**.
10. Sélectionnez **Ajouter**, puis sélectionnez **Enregistrer les modifications du coffre de clés**.
11. Sur la page **Vue d’ensemble**, copiez la valeur **Nom DNS** du coffre de clés. Cette valeur sera utilisée lors de la configuration du service dans RCS et sera désignée sous le nom *URI du coffre de clés*.
