---
title: Détecter les paniers abandonnés et envoyer des notifications aux clients
description: Cette rubrique décrit comment personnaliser l’exemple d’application de connecteur de panier abandonné Microsoft Dynamics 365 Commerce pour détecter les paniers abandonnés et envoyer des notifications par e-mail de rappel aux clients.
author: bicyclingfool
ms.date: 02/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 82848f1ff068cea0adfc6ec1b33fc4bb035f78dc
ms.sourcegitcommit: 374bbdde90fc9a68c0799158a50409bfbe8ca64e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353360"
---
# <a name="detect-abandoned-carts-and-send-notifications-to-customers"></a>Détecter les paniers abandonnés et envoyer des notifications aux clients

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment personnaliser l’exemple d’application de connecteur de panier abandonné Microsoft Dynamics 365 Commerce pour détecter les paniers abandonnés et envoyer des notifications par e-mail de rappel aux clients.

La capacité de récupérer des revenus et de fidéliser les clients grâce aux notifications de panier abandonné est une capacité importante prise en charge par Dynamics 365 Commerce. En personnalisant l’exemple d’application de connecteur de panier abandonné Commerce, les détaillants peuvent accéder aux paniers d’achat sur Retail Server qui n’ont pas été modifiés pendant une plage de temps définie par les détaillants. Ces paniers peuvent ensuite être récupérés, complétés par des données sur les produits et les clients, et transmis à un fournisseur tiers de marketing par e-mail qui peut générer des notifications par e-mail et les envoyer aux clients.

La notification par e-mail de panier abandonné que les clients reçoivent peut contenir les informations suivantes :

- Prénom du client.
- Nom du client.
- Adresse e-mail du client.
- URL qui renvoie le client à son panier.
- Devise de la transaction.
- Liste de produits dans le panier du client. Pour chaque produit, les informations suivantes sont incluses :

    - Nom d’affichage du produit
    - Identifiant du produit (utilisé pour assembler une URL vers la page de description du produit)
    - Image de produit qui peut être automatiquement redimensionnée pour s’adapter à différentes tailles de fenêtres
    - Texte de remplacement de l’image du produit
    - Prix unitaire du produit

## <a name="abandoned-cart-connector-sample"></a>Exemple de connecteur de panier abandonné

Un modèle de connecteur fourni par Microsoft via le kit de développement logiciel (SDK) Retail permet de récupérer et d’envoyer les informations sur les paniers abandonnés à un fournisseur tiers de marketing par e-mail. Ce connecteur gère la communication avec Retail Server, utilise Azure Key Vault pour la sécurité, gère la planification de la récupération du panier pour une fenêtre de temps spécifiée et récupère les données de commande et de produit. Il fournit également un exemple d’implémentation pour une intégration avec un fournisseur tiers de marketing par e-mail. Le connecteur est conçu pour communiquer avec [Emarsys](https://emarsys.com) dès son activation. Cependant, il peut facilement être personnalisé pour s’intégrer à d’autres solutions, telles que Constant Contact, Mailchimp et SendGrid.

L’illustration suivante montre les composants de l’exemple d’application de connecteur de panier abandonné.

![Composants de l’exemple d’application de connecteur de panier abandonné](media/AbandonedCartConnector.png)

> [!IMPORTANT]
> Certaines régions exigent que les clients puissent refuser que les données de leur panier soient transmises à un fournisseur de marketing par e-mail ou demandent que leurs données soient supprimées. Cependant, Microsoft ne propose pas ces options aux clients. Par conséquent, si vous envisagez de faire des affaires dans des régions qui les imposent, vous devez fournir l’infrastructure et les personnalisations requises pour suivre les préférences des clients et, en fonction de celles-ci, empêcher que les données des clients ne soient transmises à votre plateforme de messagerie. Vous devez également définir un processus de purge des données client de votre fournisseur de marketing par e-mail à la demande du client.

## <a name="obtain-the-code-sample"></a>Obtenir l’exemple de code

L’exemple d’application de connecteur de panier abandonné est inclus dans le kit de développement logiciel Retail à partir de la version 10.0.16. Le code est disponible sous **\\RetailSDK\\Code\\SampleExtensions\\RetailServer\\Extensions.AbandonedCartSample**. Pour en savoir plus sur la manière d’installer et d’utiliser le kit de développement logiciel de Retail, voir [Kit de développement logiciel Retail](retail-sdk/retail-sdk-overview.md).

> [!NOTE]
> Bien que l’exemple de code ait été mis à disposition pour la première fois dans les versions 10.0.16, il est compatible avec la version 10.0.13 et les versions ultérieures de Retail Server.

## <a name="prerequisites-and-dependencies"></a>Conditions requises et dépendances

Avant de pouvoir déployer et configurer l’exemple de code du connecteur de panier abandonné, les conditions préalables suivantes doivent être remplies.

### <a name="access-to-commerce-resources"></a>Accès aux ressources Commerce

Pour configurer et déployer l’application de connecteur de panier abandonné, vous devez avoir accès aux ressources Commerce suivantes :

- Accès administrateur au siège de Commerce pour votre environnement
- Accès au projet Microsoft Dynamics Lifecycle Services (LCS) pour votre environnement

### <a name="azure-cosmos-db"></a>Azure Cosmos DB

L’application de connecteur de panier abandonné utilise Azure Cosmos DB pour suivre les identifiants et les horodatages des paniers qui ont été précédemment récupérés. Vous pouvez utiliser Azure Cosmos DB pour conserver ces données, ou vous pouvez personnaliser l’exemple de code pour l’intégrer à une autre option de stockage de données. Pour plus d’informations sur Azure Cosmos DB, voir [Bienvenue dans Azure Cosmos DB](/azure/cosmos-db/introduction).

Si vous utilisez Azure Cosmos DB, les conditions requises suivantes doivent être satisfaites avant de pouvoir exécuter l’exemple :

- Vous devez avoir un compte Azure Cosmos DB actif. Si vous n’avez pas de compte, consultez [Créer un compte de base de données](/azure/cosmos-db/create-sql-api-dotnet#create-a-database-account).
- Vous devez récupérer les valeurs **URI** et **CLÉ PRIMAIRE** (ou **CLÉ SECONDAIRE**) du panneau **Clés** de votre compte Azure Cosmos DB dans le portail Azure. Pour plus d’informations sur la façon de récupérer les informations sur les points de terminaison et les clés pour votre compte Azure Cosmos DB compte, [Afficher, copier et régénérer les clés d’accès et les mots de passe](/azure/cosmos-db/manage-account#keys).

### <a name="azure-key-vault"></a>Azure Key Vault

L’application de connecteur de panier abandonné utilise Key Vault pour stocker les noms et les clés secrètes des différents composants qui nécessitent un accès sécurisé.

Pour paramétrer un coffre de clés, procédez comme suit.

1. Suivez les instructions dans [Gérer Key Vault dans Azure Stack Hub à l’aide du portail](/azure-stack/user/azure-stack-key-vault-manage-portal?view=azs-2002&preserve-view=true).
2. Créez des clés secrètes pour les informations suivantes :

    - Nom d’utilisateur et clé secrète API de l’API Emarsys
    - ID et clé secrète de l’application de panier abandonné

L’exemple de code du connecteur de panier abandonné utilise les informations d’identification par défaut d’Azure pour accéder à Key Vault. Vous devez fournir les autorisations **Liste** et **Lecture** à l’identité que vous prévoyez d’utiliser pour accéder à Key Vault.

Pour plus d’informations sur les informations d’identification par défaut d’Azure, consultez [Classe DefaultAzureCredential](/dotnet/api/azure.identity.defaultazurecredential?view=azure-dotnet&preserve-view=true).

## <a name="create-an-abandoned-cart-connector-sample-app-application-id-for-the-azure-ad-tenant"></a>Créer un ID d’application d’exemple d’application de connecteur de panier abandonné pour le client Azure AD

Vous devez créer un ID d’application d’exemple d’application de connecteur de panier abandonné pour le client Azure Active Directory (AD). Pour plus d’informations sur la création d’un ID d’application, voir [Utiliser le portail pour créer une application Azure AD et un principal de service pouvant accéder aux ressources](/azure/active-directory/develop/howto-create-service-principal-portal).

## <a name="add-the-abandoned-cart-connector-sample-app-application-id-to-the-allow-list-for-the-retail-server-api"></a>Ajoutez l’ID d’application de l’exemple d’application de connecteur de panier abandonné à la liste d’autorisation de l’API Retail Server

Ensuite, vous devez ajouter l’ID d’application de l’exemple d’application de connecteur de panier abandonné à la liste d’autorisation de l’API Retail Server. Pour plus d’informations sur l’ajout d’un ID d’application à la liste d’autorisation dans Azure, voir [Prise en charge de l’authentification de service à service dans Retail Server](https://community.dynamics.com/ax/b/axforretail/posts/support-for-service-to-service-authentication-in-retail-server).

## <a name="configure-the-abandoned-cart-connector-sample-app"></a>Configurer l’exemple d’application de connecteur de panier abandonné

Pour configurer l’exemple d’application de connecteur de panier abandonné, modifiez le fichier de configuration **appSettings.json** situé à la racine du répertoire **AbandonedCartDetectionSample**. Les tableaux suivants décrivent les propriétés du fichier de configuration.

### <a name="keyvaultoptions"></a>KeyVaultOptions

| Propriété    | Description |
| ----------- | ----------- |
| KeyVaultURI | Nom DNS du coffre de clés que vous utilisez dans le portail Azure. |

### <a name="retailserverclientoptions"></a>RetailServerClientOptions

| Propriété                                      | Description |
| --------------------------------------------- | ----------- |
| TenantId                                      | ID client Azure AD de votre client Azure. |
| RetailServerAudienceId                        | ID d’audience de Retail Server. Vous pouvez laisser la valeur par défaut. |
| AppIdKeyVaultSecretName                       | Nom de la clé secrète créée par vos soins pour l’ID d’application de l’exemple d’application de connecteur de panier abandonné. |
| AppSecretKeyVaultSecretName                   | Nom de la clé secrète qui mémorise la clé secrète de l’application pour l’ID d’application de l’exemple d’application de connecteur de panier abandonné. |
| RetailServerUrl                               | URL de votre instance Retail Server. Vous pouvez trouver cette valeur dans LCS. |
| OperatingUnitNumber                           | Numéro d’unité opérationnelle. Vous pouvez trouver cette valeur dans Commerce Headquarters. |
| IncludeAbandonedCartsModifiedSinceLastMinutes | Le début de la fenêtre de temps pour les paniers abandonnés que vous souhaitez récupérer. La valeur est exprimée en nombre de minutes avant l’heure actuelle. Par exemple, définissez cette propriété sur **120** pour récupérer tous les paniers qui ont été modifiés pour la dernière fois il y a 120 minutes et la fin de la fenêtre de temps définie par la propriété **ExcludeAbandonedCartsModifiedSinceLastMinutes**. |
| ExcludeAbandonedCartsModifiedSinceLastMinutes | La fin de la fenêtre de temps pour les paniers abandonnés que vous souhaitez récupérer. La valeur est exprimée en nombre de minutes avant l’heure actuelle. Par exemple, si la propriété **IncludeAbandonedCartsModifiedSinceLastMinutes** est définie sur **120**, définissez cette propriété sur **30** pour récupérer tous les paniers qui ont été modifiés entre 120 minutes et 30 minutes. En pratique, cette propriété définit le temps que vous souhaitez attendre avant qu’un panier ne soit déclaré abandonné. |
| ReturnToCartUrl                               | L’URL du panier sur votre site e-commerce, au format utilisé dans le fichier **app.config**. |

### <a name="azurecosmosoptions"></a>AzureCosmosOptions

Le statut de la tâche de récupération du panier abandonné, les ID de panier et les horodatages modifiés sont stockés dans Azure Cosmos DB. Par défaut, les paramètres du fichier de configuration pointent vers l’instance d’émulateur local d’Azure Cosmos DB. Lorsque vous déployez le connecteur en production, vous devez mettre à jour ces paramètres afin qu’ils pointent vers l’instance Azure Cosmos DB dans votre abonnement Azure. Pour les tests locaux ou en bac à sable, vous pouvez utiliser l’[émulateur Azure Cosmos](/azure/cosmos-db/local-emulator).

| Propriété    | Description |
| ----------- | ----------- |
| EndPointUri | URI de point de terminaison fourni par Azure ou l’émulateur. |
| PrimaryKey  | Clé primaire fournie par Azure ou l’émulateur. |
| DatabaseId  | ID de base de données. Vous pouvez laisser la valeur par défaut ou fournir la vôtre. |
| ContainerId | ID conteneur. Vous pouvez laisser la valeur par défaut ou fournir la vôtre. |

### <a name="emarsysclientoptions"></a>EmarsysClientOptions

> [!NOTE]
> Si vous vous intégrez à un fournisseur d’email marketing autre qu’Emarsys, vous devez étendre l’interface **IEmailProvider** appropriée pour communiquer avec ce fournisseur.

| Propriété                      | Description |
| ----------------------------- | ----------- |
| ApiUrl                        | `https://api.emarsys.net/api/v2/event/{0}/trigger` |
| ExternalEventId               | ID de l’enregistrement d’événement externe créé dans Emarsys. Vous pouvez trouver la valeur sous **Paramètres de déclenchement** dans la campagne que vous avez créée pour envoyer des notifications par e-mail de panier abandonné. |
| ApiUserNameKeyVaultSecretName | Nom de la clé où le nom d’utilisateur de l’API Emarsys est stocké. |
| ApiSecretKeyVaultSecretName   | Nom de la clé où la clé secrète de l’API Emarsys est stockée. |
| EmarsysContactKeyId           | ID de la colonne email dans la base de données de contacts Emarsys. La valeur par défaut est **3** et ne devrait pas être modifiée. |

### <a name="mediaoptions"></a>MediaOptions

Si vous utilisez les fonctionnalités de commerce électronique dans Commerce, vous pouvez utiliser la gestion des actifs numériques de Commerce pour récupérer des images de produits. Pour plus d’informations sur les fonctionnalités de redimensionnement d’image dans la gestion des actifs numériques, voir [Configuration de la fenêtre d’affichage ImageSettings =](../e-commerce-extensibility/image-component.md#imagesettings-viewport-configuration).

| Propriété                             | Description |
| ------------------------------------ | ----------- |
| ImageServerUrl                       | URL racine du gestionnaire de ressources numériques de votre site. Vous pouvez trouver la valeur dans la clé de propriété **URL de base du serveur multimédia** à l’emplacement **Retail et Commerce \> Configuration du canal \> Profils de canal** dans Commerce Headquarters. |
| ImageViewPorts                       | Nœud de conteneur pour les configurations de fenêtres d’affichage individuelles. |
| ImageViewPorts/viewport              | Définition de la fenêtre d’affichage. Utilisez cette propriété pour spécifier les plages de largeur de la fenêtre d’affichage, en pixels. Pour un exemple de la façon dont cette propriété est utilisée, voir le fichier de configuration **appSettings.json**. |
| ImageViewPorts/imageWidth            | Largeur de l’image de la fenêtre d’affichage, en pixels. |
| imageViewPorts/imageHeight           | Hauteur de l’image de la fenêtre d’affichage, en pixels. |
| imageViewPorts/useForDefaultImageTag | Une valeur **true**/**false** qui indique si les dimensions de l’image définies par la fenêtre d’affichage doivent être utilisées si la balise HTML `<picture>` n’est pas prise en charge pour un navigateur Web ou un client de messagerie. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
