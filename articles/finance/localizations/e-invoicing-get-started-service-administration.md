---
title: Mise en route de l’administration du service de Facturation électronique
description: Cette rubrique explique comment démarrer avec la Facturation électronique.
author: gionoder
ms.date: 05/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 8adbe577e5111a6a4afdba6aed32855b2e30b39b
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2021
ms.locfileid: "6335688"
---
# <a name="get-started-with-electronic-invoicing-service-administration"></a>Mise en route de l’administration du service de Facturation électronique

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a>Conditions préalables

Avant d’effectuer les étapes de cette rubrique, les conditions préalables suivantes doivent être remplies :

- Vous devez avoir accès à votre compte Microsoft Dynamics Lifecycle Services (LCS).
- Vous devez avoir un projet LCS qui inclut la version 10.0.17 ou ultérieure de Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management. En outre, ces applications doivent être déployées dans l’une des zones géographiques Azure suivantes :

    - Etats-Unis
    - Europe
    - Royaume-Uni
    - Asie

- Vous devez avoir accès à votre compte Dynamics 365 Regulatory Configuration Services (RCS).
- Vous devez activer la fonctionnalité de globalisation pour votre compte RCS via le module Gestion des fonctionnalités. Pour plus d’informations, voir [Regulatory Configuration Services (RCS) – Fonctionnalités de globalisation](rcs-globalization-feature.md).
- Vous devez créer un coffre de clés et d’un compte de stockage dans Azure. Pour plus d’informations, voir [Créer un compte de stockage Azure et un coffre de clés](e-invoicing-create-azure-storage-account-key-vault.md).

## <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a>Installer le module complémentaire pour les microservices dans Lifecycle Services

1. Connectez-vous à votre compte LCS et, sur le tableau de bord du projet LCS, sélectionnez un projet LCS.
2. Dans le projet, sur le tableau de bord de l’environnement, sélectionnez votre projet de déploiement LCS. Le projet que vous sélectionnez doit être en cours d’exécution.
3. Dans l'onglet **Intégration Power Platform**, dans le groupe de champs **Compléments d'environnement**, sélectionnez **Installer un nouveau complément**.
4. Sélectionnez **Facturation électronique**.
5. Dans le champ **ID d’application AAD**, entrez **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Cette valeur est une valeur fixe.
6. Dans le champ **ID client AAD**, entrez l’ID client de votre compte d’abonnement Azure.
7. Passez en revue les conditions générales, puis cochez la case.
8. Sélectionnez **Installer**.


## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a>Définir les paramètres pour l’intégration RCS avec la Facturation électronique

1. Connectez-vous à votre compte RCS.
2. Dans l’espace de travail **Génération d’états électroniques**, dans la section **Liens connexes**, sélectionnez **Paramètres de la gestion des états électroniques**.
3. Sur l’onglet **Service de facturation électronique**, dans le champ **URI du point de terminaison de service**, entrez le point de terminaison de service approprié pour la zone géographique Azure, comme indiqué dans le tableau suivant.

    | Zone géographique Azure Datacenter | URI du point de terminaison de service                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Etats-Unis              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Europe                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Royaume-Uni             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Asie                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

4. Vérifiez que le champ **ID candidature** est bien défini sur **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Cette valeur est une valeur fixe.
5. Dans le champ **ID environnement LCS**, entrez l’ID de votre environnement LCS.
6. Sélectionnez **Sauvegarder**, puis fermez la page.

## <a name="create-key-vault-references"></a>Créer des références Key Vault

1. Connectez-vous à votre compte RCS.
2. Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Environnement**, sélectionnez la vignette **Facturation électronique**.
3. Sur la page **Configurations d’environnement**, dans le volet Actions, sélectionnez **Environnement de service**, puis sélectionnez **Paramètres Key Vault**.
4. Sélectionnez **Nouveau** pour créer une référence Key Vault.
5. Dans le champ **Nom**, entrez le nom de la référence Key Vault. Entrez une description dans le champ **Description**.
6. Dans le champ **URI Key Vault**, collez le secret du coffre de clés à partir d’Azure Key Vault. Pour plus d’informations, voir [Créer un compte de stockage Azure et un coffre de clés](e-invoicing-create-azure-storage-account-key-vault.md).
7. Sélectionnez **Enregistrer**.

## <a name="create-storage-account-secret"></a>Créer un secret de compte de stockage

1. Sur la page **Configurations d’environnement**, dans le volet Actions, sélectionnez **Environnement de service** > **Paramètres Key Vault**.
2. Sélectionnez une **Référence Key Vault** et, dans la section **Certificats**, sélectionnez **Ajouter**.
3. Dans le champ **Nom**, entrez le nom du secret du compte de stockage. Pour plus d’informations, voir [Créer un compte de stockage Azure et un coffre de clés](e-invoicing-create-azure-storage-account-key-vault.md).
4. Entrez une description dans le champ **Description**.
5. Dans le champ **Type**, sélectionnez **Secret**.
6. Sélectionnez **Sauvegarder**, puis fermez la page.

## <a name="create-a-digital-certificate-secret"></a>Créer un secret de certificat numérique

1. Sur la page **Configurations d’environnement**, dans le volet Actions, sélectionnez **Environnement de service**, puis sélectionnez **Paramètres Key Vault**.
2. Sélectionnez une **Référence Key Vault** puis, dans la section **Certificats**, sélectionnez **Ajouter**.
3. Dans le champ **Nom**, entrez le nom du secret de certificat numérique. Pour plus d’informations, voir [Créer un compte de stockage Azure et un coffre de clés](e-invoicing-create-azure-storage-account-key-vault.md).
4. Entrez une description dans le champ **Description**.
5. Dans le champ **Type**, sélectionnez **Certificat**.
6. Sélectionnez **Sauvegarder**, puis fermez la page.

## <a name="create-a-service-environment"></a>Créer un environnement de service

1. Connectez-vous à votre compte RCS.
2. Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Environnement**, sélectionnez la vignette **Facturation électronique**.
3. Sur la page **Configurations d’environnement**, dans le volet Actions, sélectionnez **Environnement de service**.
4. Sélectionnez **Nouveau** pour créer un environnement de service.
5. Dans le champ **Nom**, entrez le nom de l’environnement de facturation électronique. Entrez une description dans le champ **Description**.
6. Dans le champ **Secret de jeton SAS de stockage**, sélectionnez le secret du compte de stockage qui doit être utilisé pour authentifier l’accès au compte de stockage.
7. Dans la section **Utilisateurs**, sélectionnez **Ajouter** pour ajouter un utilisateur autorisé à soumettre des factures électroniques via l’environnement et à se connecter également au compte de stockage.
8. Entrez l’alias de l’utilisateur dans le champ **Identifiant utilisateur**. Entrez l’adresse e-mail de l’utilisateur dans le champ **E-mail**.
9. Sélectionnez **Enregistrer**.
10. Si les factures spécifiques à votre pays/région nécessitent une chaîne de certificats pour appliquer des signatures numériques, dans le volet Actions, sélectionnez **Paramètres Key Vault**, puis **Chaîne de certificats**, et suivez ces étapes :
    1. Sélectionnez **Nouveau** pour créer une chaîne de certificats.
    2. Dans le champ **Nom**, entrez le nom de l’environnement de la chaîne de certificats. Entrez une description dans le champ **Description**.
    3. Dans la section **Certificats**, sélectionnez **Ajouter** pour ajouter un certificat à la chaîne.
    4. Utilisez le bouton **Vers le haut** ou **Vers le bas** pour changer la position du certificat dans la chaîne.
    5. Sélectionnez **Sauvegarder**, puis fermez la page.
    6. Fermez la page.
11. Sur la page **Environnement de service**, dans le volet Actions, sélectionnez **Publier** pour publier l’environnement dans le Cloud. La valeur du champ **Statut** est remplacée par **Publié**.

## <a name="create-a-connected-application"></a>Créer une application connectée

1. Sur la page **Configurations d’environnement**, dans le volet Actions, sélectionnez **Applications connectées**.
2. Sélectionnez **Nouveau** pour créer une application connectée.
3. Dans le champ **Nom**, entrez le nom de l’application à connecter.
4. Dans le champ **Application**, entrez l’URL de l’environnement Finance et Supply Chain Management à connecter.
4. Dans le champ **Client**, entrez le client de l’environnement Finance et Supply Chain Management.
5. Sélectionnez **Enregistrer**.
6. Dans le volet Actions, sélectionnez **Vérifier la connexion** pour tester la connexion avec l’environnement. Fermez ensuite la page.

## <a name="link-connected-applications-to-environments"></a>Lier les applications connectées aux environnements

1. Sur la page **Configurations d’environnement**, sélectionnez **Nouveau** pour affecter une application connectée à un environnement.
2. Sélectionnez une application connectée dans le champ **Application connectée**.
3. Sélectionnez un environnement de service dans le champ **Environnement de service**.
4. Sélectionnez **Sauvegarder**, puis fermez la page.

## <a name="set-up-electronic-invoicing-integration-in-finance-and-supply-chain-management"></a>Paramétrer l’intégration de la Facturation électronique dans Finance et Supply Chain Management

### <a name="turn-on-the-electronic-invoicing-integration-feature"></a>Activer la fonctionnalité d’intégration de la Facturation électronique

1. Connectez-vous à l’instance Finance ou Supply Chain Management.
2. Dans l’espace de travail **Gestion des fonctionnalités**, recherchez la fonctionnalité **Intégration de la Facturation électronique**. Si cette fonctionnalité n’apparaît pas sur la page, sélectionnez **Rechercher des mises à jour**.
3. Sélectionnez la fonctionnalité, puis sélectionnez **Activer maintenant**.

### <a name="set-up-the-service-endpoint-url"></a>Paramétrer l’URL du point de terminaison de service

1. Allez dans **Administration de l’organisation \> Paramétrage \> Paramètres des documents électroniques**.
2. Sur l’onglet **Service d’envoi**, dans le champ **URL du point de terminaison de service**, entrez le point de terminaison de service approprié pour la zone géographique Azure, comme indiqué dans le tableau suivant.

    | Zone géographique Azure Datacenter | URI du point de terminaison de service                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Etats-Unis              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Europe                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Royaume-Uni             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Asie                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

3. Dans le champ **Environnement**, entrez le nom de l’environnement de service publié dans la Facturation électronique.
4. Sélectionnez **Sauvegarder**, puis fermez la page.

### <a name="enable-flighting-keys"></a>Activer les clés de distribution de version d’évaluation

Activez les clés de distribution de version d’évaluation pour Microsoft Dynamics 365 Finance ou Microsoft Dynamics 365 Supply Chain Management, versions 10.0.17 ou antérieures. 
1. Exécutez la commande SQL suivante :

    INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES (’BusinessDocumentSubmissionServiceEnabled’, 1)
    
    INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES (’ElectronicInvoicingServiceIntegrationFeature’, 1)

2. Exécutez une commande IISreset pour tous les AOS.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
