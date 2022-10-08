---
title: Instructions de déploiement de caisses enregistreuses pour la Norvège
description: Cet article fournit des conseils sur la façon d’activer la fonctionnalité de caisse enregistreuse pour la localisation de Microsoft Dynamics 365 Commerce pour la Norvège.
author: EvgenyPopovMBS
ms.date: 10/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-03-01
ms.openlocfilehash: 0e66ef93e65fecaca23f0434c386507a0672d251
ms.sourcegitcommit: 2bc6680dc6b12d20532d383a0edb84d180885b62
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2022
ms.locfileid: "9631313"
---
# <a name="deployment-guidelines-for-cash-registers-for-norway"></a>Instructions de déploiement de caisses enregistreuses pour la Norvège

[!include[banner](../includes/banner.md)]

> [!IMPORTANT]
> Vous ne devez mettre en oeuvre les étapes décrites dans cet article que si vous utilisez Microsoft Dynamics 365 Commerce version 10.0.29 ou ultérieure. Dans la version 10.0.28 ou antérieure de Commerce, vous devez utiliser la version précédente du Kit de développement logiciel (SDK) Retail sur une machine virtuelle de développeur (VM) dans Microsoft Dynamics Lifecycle Services (LCS). Pour plus d’informations, voir [Directives de déploiement des caisses enregistreuses pour la Norvège (héritage)](./emea-nor-loc-deployment-guidelines.md). Si vous utilisez la version 10.0.28 ou une version antérieure de Commerce et que vous migrez vers la version 10.0.29 ou une version ultérieure, vous devez suivre les étapes décrites dans [Migrer de la fonctionnalité héritée de Commerce pour la Norvège](./emea-nor-fi-migration.md).

Cet article fournit des conseils sur la façon d’activer la fonctionnalité de caisse enregistreuse pour la localisation de Commerce pour la Norvège. La localisation consiste en plusieurs extensions qui vous permettent d’effectuer des actions comme imprimer des champs personnalisés sur les reçus, enregistrer des événements d’audit supplémentaires, des transactions de vente et des transactions de paiement au point de vente, de signer numériquement les transactions de vente et d’imprimer des rapports dans des formats locaux. Pour plus d’informations sur la localisation pour la Norvège, voir [Fonctionnalité de caisse enregistreuse pour la Norvège](./emea-nor-cash-registers.md). Pour plus d’informations sur la configuration de Commerce pour la Norvège, consultez [Configurer Commerce pour la Norvège](./emea-nor-cash-registers.md#setting-up-commerce-for-norway).

## <a name="set-up-fiscal-registration-for-norway"></a>Paramétrer l’enregistrement fiscal pour la Norvège

L’échantillon d’enregistrement fiscal pour la Norvège est basé sur la [fonctionnalité d’intégration fiscale](fiscal-integration-for-retail-channel.md) et fait partie du Kit de développement logiciel (SDK) de Commerce. L’échantillon se trouve dans le dossier **src\\FiscalIntegration\\SequentialSignatureNorway** du référentiel des [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). L’échantillon [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) en un fournisseur de documents fiscaux et un connecteur fiscal, qui sont des extensions de Commerce Runtime (CRT). Pour plus d’informations sur l’utilisation du SDK de Commerce, consultez [Télécharger des exemples et des packages de référence du SDK de Commerce à partir de GitHub et NuGet](../dev-itpro/retail-sdk/sdk-github.md) et [Configurer un pipeline de build pour le SDK de packaging indépendant](../dev-itpro/build-pipeline.md).

Suivez les étapes de configuration de l’enregistrement fiscal décrites dans [Configurer l’intégration fiscale pour les canaux Commerce](./setting-up-fiscal-integration-for-retail-channel.md) :

1. [Configurer un processus d’enregistrement fiscal](./setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Assurez-vous de noter les paramètres du processus d’enregistrement fiscal qui sont [spécifiques à la Norvège](#configure-the-fiscal-registration-process).
1. [Définir les paramètres de traitement des erreurs](./setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Activer l’exécution manuelle d’un enregistrement fiscal différé](./setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-deferred-fiscal-registration).
1. [Configurer des composants de canal](#configure-channel-components).

### <a name="configure-the-fiscal-registration-process"></a>Configurer le processus d’enregistrement fiscal

Pour activer le processus d’enregistrement fiscal pour la Norvège dans Commerce Headquarters, procédez comme suit.

1. Téléchargez les fichiers de configuration du fournisseur de documents fiscaux et du connecteur fiscal à partir du SDK Commerce :

    1. Ouvrez le référentiel [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Ouvrez la dernière branche de version disponible.
    1. Ouvrez **src \> FiscalIntegration \> SequentialSignatureNorway \> CommerceRuntime**.
    1. Téléchargez le fichier de configuration du fournisseur de document fiscal sur **DocumentProvider.SequentialSignNorway \> Configuration \> DocumentProviderSequentialSignatureNorwaySample.xml**.
    1. Téléchargez le fichier de configuration du connecteur fiscal sur **Connector.SequentialSignNorway \> Configuration \> ConnectorSequentialSignatureNorwaySample.xml**.

1. Accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres partagés**. Dans l’onglet **Général**, définissez l’option **Activer l’intégration fiscale** sur **Oui**.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Connecteurs fiscaux**, et téléchargez le fichier de configuration du connecteur fiscal téléchargé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Fournisseurs de documents fiscaux** et chargez le fichier de configuration du fournisseur de documents fiscaux téléchargé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Profils fonctionnels des connecteurs**. Créez un profil fonctionnel de connecteur et sélectionnez le fournisseur de documents et le connecteur chargé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Profils techniques des connecteurs**. Créez un profil technique de connecteur et sélectionnez le connecteur chargé précédemment. Définissez le type de connecteur sur **Interne**.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Groupes de connecteurs fiscaux**, et créez un groupe de connecteurs fiscaux pour le profil fonctionnel de connecteur créé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Processus d’enregistrement fiscal**. Créez un processus d’enregistrement fiscal et une étape du processus d’enregistrement fiscal et sélectionnez le groupe de connecteurs fiscaux créé précédemment.
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage POS \> Profils POS \> Profils de fonctionnalité**. Sélectionnez un profil de fonctionnalité lié au magasin où le processus d’enregistrement doit être activé. Sur le raccourci **Processus d’enregistrement fiscal**, sélectionnez le processus d’enregistrement fiscal que vous avez créé précédemment. Sur le raccourci **Services fiscaux**, sélectionnez le profil technique du connecteur que vous avez créé précédemment. 
1. Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**. Ouvrez le planning de distribution et sélectionnez les tâches **1070** et **1090** pour transférer des données vers la base de données des canaux.

### <a name="configure-the-digital-signature-parameters"></a>Configurer les paramètres de signature numérique

Vous devez configurer les certificats qui seront utilisés pour la signature numérique des transactions de vente dans un magasin. Un certificat numérique enregistré dans Azure Key Vault est utilisé pour la signature. Pour le mode hors ligne de Modern POS, la signature peut également être effectuée à l’aide d’un certificat numérique stocké en local sur la machine sur laquelle Modern POS est installé.

Avant d’utiliser un certificat numérique enregistré dans le stockage Key Vault, les étapes suivantes doivent être effectuées.

1. Le stockage du coffre de clés doit être créé. Il est recommandé de déployer le stockage dans la même zone géographique que l’Unité d’échelle commerciale.
1. Le certificat doit être téléchargé vers le stockage du coffre de clés en tant que secret de chaîne Base64.
1. L’application Serveur d’objets d’application (AOS) doit être autorisée pour lire les secrets du stockage du coffre de clés.

Pour plus d’informations sur l’utilisation du coffre de clés, voir [Prise en main d’Azure KeyVault](/azure/key-vault/key-vault-get-started).

Puis, sur la page **Paramètres du coffre de clés**, vous devez spécifier les paramètres d’accès au stockage Key Vault :

- **Nom** et **Description** – Nom et description du stockage du coffre de clés.
- **URL du coffre de clés** – URL du stockage du coffre de clés.
- **Client du coffre de clés** – ID client interactif de l’application Azure Active Directory (Azure AD) associée au stockage du coffre de clés à des fins d’authentification. Ce client doit avoir accès en lecture aux secrets du stockage.
- **Clé secrète du coffre de clés** – Clé secrète associée à l’application Azure AD utilisée pour l’authentification dans le stockage du coffre de clés.
- **Nom**, **Description**, et **Référence secrète** – Nom, description, et référence secrète du certificat.

Ensuite, vous devez configurer un connecteur pour vos certificats stockés dans Key Vault ou dans le stockage de certificats local. Ce connecteur est utilisé pour la signature côté canal.

1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Intégration fiscale \> Profils techniques des connecteurs**.
1. Sur le raccourci **Paramètres**, spécifiez les paramètres suivants pour les signatures numériques :

    - **Nom secret** – Sélectionnez le nom secret que vous avez configuré précédemment sur la page **Paramètres Key Vault**.
    - **Certificat local empreinte** – Fournit une empreinte pour un certificat stocké localement.
    - **Algorithme de hachage** : spécifiez l’un des algorithmes de hachage cryptographique pris en charge par Microsoft .NET, tel que **SHA1**.
    - **Nom du magasin de certificats** – Ce champ est facultatif. Utilisez-le pour spécifier un nom de magasin par défaut à utiliser pour rechercher des certificats locaux.
    - **Emplacement du magasin de certificats** – Ce champ est facultatif. Utilisez-le pour spécifier un emplacement de magasin par défaut à utiliser pour rechercher des certificats locaux.
    - **Essayer d’abord le certificat local** – Sélectionnez cette option pour utiliser le certificat du magasin local par défaut pour signer les données, au lieu du certificat de Key Vault.
    - **Activer le contrôle d’intégrité** : pour plus d’informations sur la procédure de contrôle d’intégrité, voir [Contrôle d’intégrité d’enregistrement fiscal](./fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

> [!NOTE]
> - Seul l’algorithme de hachage de chiffrement **SHA1** est actuellement acceptable pour la Norvège.
> - Le nom et l’emplacement du magasin par défaut sont ajoutés pour simplifier le processus de recherche des certificats locaux dans CRT. X509StoreProvider comporte une liste de dossiers dans lesquels les certificats sont stockés. Si le nom du magasin par défaut et l’emplacement du magasin par défaut ne sont pas spécifiés, X509StoreProvider essaie de trouver un certificat dans tous les dossiers de sa liste.

### <a name="configure-channel-components"></a>Configurer des composants de canal

#### <a name="development-environment"></a>Environnement de développement

Suivez ces étapes pour configurer un environnement de développement afin de pouvoir tester et étendre l’exemple.

1. Clonez ou téléchargez le référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Sélectionnez une version de branche de publication correcte en fonction de votre version de Kit de développement logiciel (SDK). Pour plus d’information, voir [Télécharger les exemples et les packages de référence du SDK de Commerce sur GitHub et NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Ouvrez la solution **SequentialSignatureNorway.sln** sous **Dynamics365Commerce.Solutions\\FiscalIntegration\\SequentialSignatureNorway**, et la générer.
1. Installer les extensions CRT :

    1. Recherchez le programme d’installation de l’extension CRT :

        - **Commerce Scale Unit :** Dans le dossier **SequentialSignatureNorway\\ScaleUnit\\ScaleUnit.SequentialSignNorway.Installer\\bin\\Debug\\net461**, recherchez le programme d’installation **ScaleUnit.SequentialSignNorway.Installer**.
        - **CRT local sur le PDV moderne :** Dans le dossier **SequentialSignatureNorway\\ModernPOS\\ModernPos.SequentialSignNorway.Installer\\bin\\Debug\\net461**, recherchez le programme d’installation **ModernPos.SequentialSignNorway.Installer**.

    1. Démarrez le programme d’installation de l’extension CRT à partir de la ligne de commande :

        - **Commerce Scale Unit :**

            ```Console
            ScaleUnit.SequentialSignNorway.Installer.exe install --verbosity 0
            ```

        - **CRT local sur le PDV moderne :**

            ```Console
            ModernPOS.SequentialSignNorway.Installer.exe install --verbosity 0
            ```

#### <a name="production-environment"></a>Environnement de production

Suivez les étapes de [Configurer un pipeline de génération pour un exemple d’intégration fiscale](fiscal-integration-sample-build-pipeline.md) pour générer et lancer Cloud Scale Unit et les packages pouvant être déployés en libre-service pour l’exemple d’intégration fiscale. Le modèle de fichier YAML **SequentialSignatureNorway build-pipeline.yaml** se trouve dans le dossier **Pipeline\\YAML_Files** du référentiel [Solutions Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

### <a name="enable-the-digital-signature-in-offline-mode-for-modern-pos"></a>Activer la signature numérique en mode hors connexion pour le PDV moderne

Pour activer la signature numérique en mode hors connexion pour le PDV moderne, vous devez suivre ces étapes après avoir activé le PDV moderne sur un nouvel appareil.

1. Connectez-vous à POS.
1. Sur la page **Statut de la connexion à la base de données**, assurez-vous que la base de données hors connexion est entièrement synchronisée. Lorsque la valeur du champ **Téléchargements en attente** est **0** (zéro), la base de données est entièrement synchronisée.
1. Déconnectez-vous du PDV.
1. Attendez que la base de données hors connexion soit entièrement synchronisée.
1. Connectez-vous à POS.
1. Sur la page **Statut de la connexion à la base de données**, assurez-vous que la base de données hors connexion est entièrement synchronisée. Lorsque la valeur du champ **Transactions en attente dans la base de données hors connexion** est **0** (zéro), la base de données est entièrement synchronisée.
1. Rouvrir le point de vente moderne.
