---
title: Prise en main de l'administration du service du module complémentaire de facturation électronique
description: Cette rubrique explique comment démarrer avec le module complémentaire de facturation électronique.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
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
ms.openlocfilehash: 05b00380cec7511adad2467d3f252799a4aaee5c
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592524"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a>Prise en main de l'administration du service du module complémentaire de facturation électronique

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a>Conditions préalables

Avant d’effectuer les étapes de cette rubrique, les conditions préalables suivantes doivent être remplies :

- Vous devez avoir accès à votre compte Microsoft Dynamics Lifecycle Services (LCS).
- Vous devez avoir un projet LCS qui inclut la version 10.0.17 ou ultérieure de Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management. En outre, ces applications doivent être déployées dans l'une des zones géographiques Azure suivantes :

    - Est des États-Unis
    - Ouest des États-Unis
    - Nord de l'UE
    - Ouest de l'UE

- Vous devez avoir accès à votre compte Dynamics 365 Regulatory Configuration Services (RCS).
- Vous devez activer la fonctionnalité de globalisation pour votre compte RCS via le module Gestion des fonctionnalités. Pour plus d’informations, voir [Regulatory Configuration Services (RCS) - Fonctionnalités de globalisation](rcs-globalization-feature.md).
- Vous devez créer un coffre de clés et d’un compte de stockage dans Azure. Pour plus d’informations, voir [Créer un compte de stockage Azure et un coffre de clés](e-invoicing-create-azure-storage-account-key-vault.md).

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a>Installer le module complémentaire pour les microservices dans Lifecycle Services

1. Connectez-vous à votre compte LCS.
2. Sélectionnez la vignette **Gestion des fonctionnalités d'aperçu**.
3. Dans la section **Fonctionnalités de version préliminaire**, sélectionnez **Service de facturation électronique**.
4. Veillez à ce que l'option **Fonctionnalité de version préliminaire activée** soit définie sur **Oui**.
5. Sur votre tableau de bord LCS, sélectionnez votre projet de déploiement LCS. Le projet LCS doit être en cours d’exécution.
7. Dans l’onglet **Compléments d’environnement**, sélectionnez **Installer un nouveau complément**.
8. Sélectionnez **Services de facturation électronique** et dans le champ **ID application AAD**, entrez **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Cette valeur est une valeur fixe.
10. Dans le champ **ID client AAD**, entrez l’ID client de votre compte d’abonnement Azure.
11. Passez en revue les conditions générales, puis cochez la case.
12. Sélectionnez **Installer**.


## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a>Définir les paramètres pour l’intégration RCS avec le module complémentaire de facturation électronique

1. Connectez-vous à votre compte RCS.
2. Dans l’espace de travail **Génération d’états électroniques**, dans la section **Liens connexes**, sélectionnez **Paramètres de la gestion des états électroniques**.
3. Sur l'onglet **Service de facturation électronique**, dans le champ **URI du point de terminaison de service**, entrez le point de terminaison de service approprié pour la zone géographique Azure, comme indiqué dans le tableau suivant.

    | Zone géographique Azure Datacenter | URI du point de terminaison de service                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Est des États-Unis                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | Ouest des États-Unis                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | Nord de l'UE                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | Ouest de l'UE                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. Vérifiez que le champ **ID candidature** est bien défini sur **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Cette valeur est une valeur fixe.
5. Dans le champ **ID environnement LCS**, entrez l’ID de votre compte d’abonnement LCS.
6. Sélectionnez **Sauvegarder**, puis fermez la page.

## <a name="create-key-vault-secret"></a>Créer un secret Key Vault

1. Connectez-vous à votre compte RCS.
2. Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Environnement**, sélectionnez la vignette **Module complémentaire de facturation électronique**.
3. Sur la page **Configurations d'environnement**, dans le volet Actions, sélectionnez **Environnement de service**, puis sélectionnez **Paramètres Key Vault**.
4. Sélectionnez **Nouveau** pour créer un secret de Key Vault.
5. Dans le champ **Nom**, entrez le nom du secret Key Vault. Entrez une description dans le champ **Description**.
6. Dans le champ **URI Key Vault**, collez le secret à partir d'Azure Key Vault.
7. Sélectionnez **Enregistrer**.

## <a name="create-storage-account-secret"></a>Créer un secret de compte de stockage

1. Accédez à **Administration du système** > **Paramétrage** > **Paramètres du coffre de clés** et sélectionnez un secret pour le coffre de clés.
2. Dans la section **Certificats**, sélectionnez **Ajouter**.
3. Dans le champ **Nom**, entrez le nom du secret du compte de stockage et dans le champ **Description**, entrez une description.
4. Dans le champ **Type**, sélectionnez **Certificat**.
5. Sélectionnez **Sauvegarder**, puis fermez la page.

## <a name="create-a-digital-certificate-secret"></a>Créer un secret de certificat numérique

1. Accédez à **Administration du système** > **Paramétrage** > **Paramètres du coffre de clés** et sélectionnez un secret pour le coffre de clés.
2. Dans la section **Certificats**, sélectionnez **Ajouter**.
3. Dans le champ **Nom**, entrez le nom du secret du certificat numérique et dans le champ **Description**, entrez une description.
4. Dans le champ **Type**, sélectionnez **Certificat**.
5. Sélectionnez **Sauvegarder**, puis fermez la page.

## <a name="create-an-electronic-invoicing-add-on-environment"></a>Créer un environnement complémentaire de facturation électronique

1. Connectez-vous à votre compte RCS.
2. Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Environnement**, sélectionnez la vignette **Module complémentaire de facturation électronique**.

## <a name="create-a-service-environment"></a>Créer un environnement de service

1. Sur la page **Configurations d’environnement**, dans le volet Actions, sélectionnez **Environnement de service**.
2. Sélectionnez **Nouveau** pour créer un environnement de service.
3. Dans le champ **Nom**, entrez le nom de l’environnement de facturation électronique. Entrez une description dans le champ **Description**.
4. Dans le champ **Secret de jeton SAS de stockage**, sélectionnez le secret du compte de stockage qui doit être utilisé pour authentifier l’accès au compte de stockage.
5. Dans la section **Utilisateurs**, sélectionnez **Ajouter** pour ajouter un utilisateur autorisé à soumettre des factures électroniques via l'environnement et à se connecter également au compte de stockage.
6. Entrez l'alias de l'utilisateur dans le champ **Identifiant utilisateur**. Entrez l'adresse e-mail de l'utilisateur dans le champ **E-mail**.
7. Sélectionnez **Enregistrer**.
8. Si les factures spécifiques à votre pays/région nécessitent une chaîne de certificats pour appliquer des signatures numériques, dans le volet Actions, sélectionnez **Paramètres Key Vault**, puis **Chaîne de certificats**, et suivez ces étapes :

    1. Sélectionnez **Nouveau** pour créer une chaîne de certificats.
    2. Dans le champ **Nom**, entrez le nom de l’environnement de la chaîne de certificats. Entrez une description dans le champ **Description**.
    3. Dans la section **Certificats**, sélectionnez **Ajouter** pour ajouter un certificat à la chaîne.
    4. Utilisez le bouton **Vers le haut** ou **Vers le bas** pour changer la position du certificat dans la chaîne.
    5. Sélectionnez **Sauvegarder**, puis fermez la page.
    6. Fermez la page.
9. Sur la page **Environnement de service**, dans le volet Actions, sélectionnez **Publier** pour publier l’environnement dans le Cloud. La valeur du champ **Statut** est remplacée par **Publié**.

## <a name="create-a-connected-application"></a>Créer une application connectée

1. Sur la page **Configurations d'environnement**, dans le volet Actions, sélectionnez **Applications connectées**.
2. Sélectionnez **Nouveau** pour créer une application connectée.
3. Dans le champ **Nom**, entrez le nom de l’application à connecter.
4. Dans le champ **Application**, entrez l'URL de l'environnement Finance et Supply Chain Management à connecter.
4. Dans le champ **Client**, entrez le client de l'environnement Finance et Supply Chain Management.
5. Sélectionnez **Enregistrer**.
6. Dans le volet Actions, sélectionnez **Vérifier la connexion** pour tester la connexion avec l'environnement. Fermez ensuite la page.

## <a name="link-connected-applications-to-environments"></a>Lier les applications connectées aux environnements

1. Sur la page **Configurations d'environnement**, sélectionnez **Nouveau** pour affecter une application connectée à un environnement.
2. Sélectionnez une application connectée dans le champ **Application connectée**.
3. Sélectionnez un environnement de service dans le champ **Environnement de service**.
4. Sélectionnez **Sauvegarder**, puis fermez la page.

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a>Paramétrer l’intégration du module complémentaire de facturation électronique dans Finance et Supply Chain Management

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a>Activer la fonctionnalité d’intégration du module complémentaire de facturation électronique

1. Connectez-vous à l'instance Finance ou Supply Chain Management.
2. Dans l’espace de travail **Gestion des fonctionnalités**, recherchez la fonctionnalité **Intégration du module complémentaire de facturation électronique**. Si cette fonctionnalité n'apparaît pas sur la page, sélectionnez **Rechercher des mises à jour**.
3. Sélectionnez la fonctionnalité, puis sélectionnez **Activer maintenant**.

### <a name="set-up-the-service-endpoint-url"></a>Paramétrer l’URL du point de terminaison de service

1. Allez dans **Administration de l’organisation \> Paramétrage \> Paramètres des documents électroniques**.
2. Sur l'onglet **Service d'envoi**, dans le champ **URL du point de terminaison de service**, entrez le point de terminaison de service approprié pour la zone géographique Azure, comme indiqué dans le tableau suivant.

    | Zone géographique Azure Datacenter | URL du point de terminaison de service                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Est des États-Unis                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | Ouest des États-Unis                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | Nord de l'UE                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | Ouest de l'UE                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. Dans le champ **Environnement**, entrez le nom de l’environnement complémentaire de facturation électronique.
4. Sélectionnez **Sauvegarder**, puis fermez la page.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
