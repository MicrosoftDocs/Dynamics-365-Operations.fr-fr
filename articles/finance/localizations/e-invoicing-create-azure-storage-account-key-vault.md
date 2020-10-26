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
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: b8e39539f767cc2944a9a7fdda09121921c64763
ms.sourcegitcommit: 025561f6a21fe8705493daa290f3f6bfb9f1b962
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "3835956"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a>Créer un compte de stockage Azure et un coffre de clés

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]


Le service complémentaire de facturation électronique prend la responsabilité de stocker toutes vos données métier dans les ressources Microsoft Azure appartenant à votre société. Pour vous assurer que le service fonctionne correctement et que toutes les données métier nécessaires et générées par le module complémentaire de facturation électronique ne sont accessibles que par ce dernier, vous devez créer deux ressources Azure principales :

- Un compte de stockage Azure (stockage Blob) pour stocker les factures électroniques
- Un coffre de clés Azure pour stocker les certificats et l'Uniform Resource Identifier (URI) du compte de stockage

> [!NOTE]
> Une ressource de coffre de clés dédiée et un stockage Blob client doivent être alloués spécifiquement pour une utilisation avec le module complémentaire de facturation électronique.

## <a name="prerequisites"></a>Conditions préalables

Avant de pouvoir effectuer les étapes de cette rubrique, vous devez vérifier que les tâches suivantes ont été réalisées :

- Créer une ressource de coffre de clés dans Azure. Pour plus d'informations, voir [À propos de Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/overview).
- Créer un compte de stockage Azure (stockage Blob). Pour plus d'informations, voir [Gestion du compte de stockage Azure](https://docs.microsoft.com/azure/storage/blobs/).

## <a name="overview"></a>Vue d’ensemble

Dans cette rubrique, vous effectuerez deux étapes principales :

- Configurer le compte de stockage Azure pour obtenir l'URI du compte de stockage.
- Configurer le coffre de clés pour stocker l'URI du compte de stockage.

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a>Configurer le compte de stockage Azure pour obtenir l'URI du compte de stockage

1. Ouvrez le compte de stockage que vous prévoyez d'utiliser avec le module complémentaire de facturation électronique.
2. Allez dans **Service Blob** \> **Conteneurs** et créez un nouveau conteneur.
3. Entrez un nom pour le conteneur et définissez le champ **Niveau d'accès public** sur **Privé (pas d'accès anonyme)**.
4. Ouvrez le conteneur et accédez à **Paramètres \> Stratégie d'accès**.
5. Sélectionnez **Ajouter une stratégie** pour ajouter une stratégie d'accès stockée.
6. Définissez les champs **Identifiant** et **Autorisations** au besoin. Dans le champ **Autorisations**, vous devez sélectionner toutes les autorisations.

    ![Octroi de l'autorisation de stockage Blob](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. Entrez les dates de début et d'expiration. La date d'expiration doit être dans le futur.
8. Cliquez sur **OK** pour enregistrer la stratégie, puis enregistrez vos modifications du conteneur.
9. Revenez au compte de stockage et ouvrez l'**Explorateur de stockage (version préliminaire)**.
10. Cliquez avec le bouton droit sur le conteneur, puis sélectionnez **Obtenir la signature d'accès partagé**.
11. Dans la boîte de dialogue **Signature d'accès partagé**, copiez et stockez la valeur dans le champ **URI**. Cette valeur sera utilisée dans la procédure suivante et sera appelée *URI de la signature d'accès partagé*.

    ![Sélection et copie de la valeur de l'URI](media/e-Invoicing-services-create-azure-resources-select-and-copy-uri.png)

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a>Configurer le coffre de clés pour stocker l'URI du compte de stockage

1. Ouvrez le coffre de clés que vous souhaitez utiliser avec le module complémentaire de facturation électronique.
2. Allez dans **Paramètres** \> **Secrets**, puis sélectionnez **Générer/Importer** pour créer un nouveau secret.
3. Sur la page **Créer un secret**, dans le champ **Options de téléchargement**, sélectionnez **Manuel**.
4. Entrez le nom du secret. Ce nom sera utilisé lors de la configuration du service dans Regulatory Configuration Service (RCS) et sera appelé *nom du secret du coffre de clés*.
5. Dans le champ **Valeur**, sélectionnez **URI de la signature d'accès partagé**, puis sélectionnez **Créer**.
6. Configurez la stratégie d'accès pour accorder au module complémentaire de facturation électronique le niveau correct d'accès sécurisé au secret que vous avez créé. Allez dans **Paramètres \> Stratégie d'accès** et sélectionnez **Ajouter une stratégie d'accès**.
7. Définissez les autorisations du secret pour les opérations **Obtenir** et **Lister**.

    ![Autorisation de l'accès au service](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. Définissez les autorisations du certificat pour les opérations **Obtenir** et **Lister**.

    ![Octroi de l'autorisation de certificat](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. Dans la boîte de dialogue **Principal**, sélectionnez le principal en ajoutant **Module complémentaire de facturation électronique**.
10. Sélectionnez **Ajouter**, puis sélectionnez **Enregistrer les modifications du coffre de clés**.
11. Sur la page **Vue d'ensemble**, copiez la valeur **Nom DNS** du coffre de clés. Cette valeur sera utilisée lors de la configuration du service dans RCS et sera désignée sous le nom *URI du coffre de clés*.