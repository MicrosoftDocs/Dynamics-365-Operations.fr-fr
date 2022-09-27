---
title: Profils de certificat définis par l’utilisateur pour les magasins de vente au détail
description: Cet article fournit une vue d’ensemble des profils de certificat disponibles dans Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 09/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: v-chgriffin
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.search.industry: Retail
ms.search.form: RetailFormLayout, RetailParameters
ms.openlocfilehash: 5baf043a43210d819b605546089e981c86922ca9
ms.sourcegitcommit: 4f28f262cfb8f047cb5c0070261aa0748835e74b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2022
ms.locfileid: "9558435"
---
# <a name="user-defined-certificate-profiles-for-retail-stores"></a>Profils de certificat définis par l’utilisateur pour les magasins de vente au détail

[!include [banner](../includes/banner.md)]

Cet article fournit une vue d’ensemble des profils de certificat disponibles dans Microsoft Dynamics 365 Commerce. Cette fonctionnalité étend la fonctionnalité [Gérer les secrets pour les canaux Retail](../dev-itpro/manage-secrets.md) en ajoutant la prise en charge des certificats locaux.

Pendant que le point de vente (PDV) fonctionne en mode hors ligne, il ne peut pas accéder aux certificats stockés dans le coffre de clés Microsoft Azure. Le certificat local doit être utilisé à la place. Les capacités suivantes sont prises en charge :

- Utilisation de certificats locaux dans les scénarios de secours de coffre de clés
- Utilisation de certificats locaux sans coffre de clés (par exemple dans une installation sur site)
- Mise à jour progressive des certificats, dans laquelle certains magasins et terminaux utilisent une nouvelle version du certificat alors que d’autres magasins et terminaux continuent d’utiliser la version précédente

La fonctionnalité de profils de certificat vous permet de spécifier un certificat par défaut et de définir l’ordre dans lequel les certificats du même profil de certificat sont recherchés. Cette fonctionnalité fournit également une approche de configuration similaire pour les certificats locaux et les certificats de coffre de clés. Vous pouvez ajouter des paramètres spécifiques à l’entreprise pour les certificats, mais l’identifiant intersociétés unique pour chaque certificat peut être utilisé dans les canaux de Commerce.

### <a name="scenarios"></a>Scénarios

La fonctionnalité de profils de certificat prend en charge les scénarios suivants dans les canaux de Commerce :

- Utilisation d’un certificat local dans les scénarios de secours de coffre de clés. Voici quelques exemples de ces scénarios de secours :

    - Le stockage du coffre de clés n’est pas accessible.
    - Un certificat est introuvable dans le stockage du coffre de clés.
    - Le PDV fonctionne en mode hors connexion.

- Utilisation de certificats locaux, mais sans stockage dans le coffre de clés (par exemple, dans une installation sur site).
- Mise à jour progressive des certificats, lors de laquelle une nouvelle version du certificat n’est utilisée que dans les magasins ou sur les terminaux où la nouvelle version est déjà disponible.
- Utilisation du même certificat dans plusieurs entreprises.

## <a name="set-up-certificate-profiles"></a>Configurer des profils de certificat

La procédure suivante explique comment configurer des profils de certificat.

### <a name="set-up-key-vault"></a>Configurer le coffre de clés

Les étapes suivantes doivent être effectuées avant d’utiliser un certificat numérique enregistré dans le stockage Key Vault.

1. Créez un compte de stockage du coffre de clés. Il est recommandé de déployer le compte de stockage dans la même zone géographique que Commerce Scale Unit.
1. Chargez le certificat numérique vers le compte de stockage du coffre de clés.
1. Laissez l’application Serveur d’objets d’application (AOS) lire les secrets du compte de stockage du coffre de clés.

Pour plus d’informations sur l’utilisation du coffre de clés, voir [Prise en main d’Azure KeyVault](/azure/key-vault/key-vault-get-started).

### <a name="set-up-system-parameters"></a>Définir les paramètres du système

Avant de configurer des profils de certificat dans les canaux Commerce, vous devez activer Commerce pour utiliser à la fois les certificats stockés dans le coffre de clés et les profils de certificat.

Pour configurer les paramètres système dans Commerce headquarters, procédez comme suit.

1. Sur la page **Paramètres système**, définissez l’option **Utiliser le magasin de certificats avancé** sur **Oui**.
1. Dans l’espace de travail **Gestion des fonctionnalités**, activez la fonctionnalité **Profils de certificat définis par l’utilisateur pour les magasins de vente au détail**.

### <a name="set-up-key-vault-parameters"></a>Paramétrer le coffre de clés

Sur la page **Paramètres du coffre de clés**, vous devez spécifier les paramètres suivants d’accès au stockage du coffre de clés :

- **Nom** et **Description** – Nom et description du compte de stockage du coffre de clés.
- **URL du coffre de clés** – URL du compte de stockage du coffre de clés.
- **Client du coffre de clés** – ID client interactif de l’application Azure Active Directory (Azure AD) associée au compte de stockage du coffre de clés à des fins d’authentification. Ce client doit avoir accès en lecture aux secrets du compte de stockage.
- **Clé secrète du coffre de clés** – Clé secrète associée à l’application Azure AD utilisée pour l’authentification dans le compte de stockage du coffre de clés.
- **Nom**, **Description**, et **Référence secrète** – Nom, description, et référence secrète du certificat.

Pour plus d’informations, voir [Configurer le client Azure Key Vault](../../finance/localizations/setting-up-azure-key-vault-client.md).

### <a name="configure-a-certificate-profile"></a>Configurer un profil certificat

Pour configurer un profil de certificat dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Administration système \> Paramétrage \> Profils de certificat**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un enregistrement.
1. Entrez des valeurs dans les champs **Profil de certificat**, **Nom** et **Description**.

    > [!NOTE]
    > Le profil de certificat est un identificateur unique d’un certificat dans l’ensemble des entreprises et des composants de Commerce.

1. Dans l’organisateur **Entités juridiques**, sélectionnez **Ajouter** pour ajouter une ligne.
1. Sous l’onglet **Entité juridique**, ajoutez une ligne et sélectionnez l’entité juridique (société) pour laquelle le profil de certificat actuel doit être utilisé.

    Si le profil de certificat doit être utilisé pour plusieurs entités juridiques, répétez les étapes 4 et 5 pour ajouter une ligne pour chaque entité juridique supplémentaire.

1. Sélectionnez **Paramètres** pour ouvrir la page **Paramètres du profil de certificat**, dans laquelle vous pouvez entrer les paramètres spécifiques à l’entreprise pour le profil de certificat. Spécifiez quels certificats peuvent être utilisés lorsque le profil de certificat actuel est appelé dans les canaux de Commerce. Ajoutez autant de certificats que vous le souhaitez et définir des priorités pour eux. Si un certificat qui a une priorité plus élevée n’est pas disponible, le certificat suivant est utilisé, en fonction de la priorité. Pour plus d’informations, consultez la section [Flux de travail : rechercher des certificats dans l’environnement Commerce Runtime](#workflow-searching-certificates-in-the-commerce-runtime).

    > [!NOTE]
    > Le champ **Priorité** est automatiquement défini. La valeur **1** représente la priorité la plus élevée. Lorsqu’une nouvelle ligne est ajoutée sur la page **Paramètres du profil de certificat**, sa priorité est définie sur la priorité de la ligne précédente plus un. Pour modifier la priorité d’une ligne spécifique, sélectionnez la ligne, puis sélectionnez soit **Déplacer vers le haut** pour augmenter la priorité ou **Déplacer vers le bas** pour diminuer la priorité.

1. Lorsque vous ajoutez une nouvelle ligne à la page **Paramètres du profil de certificat**, définissez les champs suivants :

    - **Type d’emplacement** - Sélectionnez l’emplacement où le certificat est stocké. Deux valeurs sont possibles pour ce champ : **Certificat local** et **Coffre de clés**.
    - **Certificat de coffre de clés** - Ce champ est obligatoire si vous définissez le champ **Type d’emplacement** sur **Coffre de clés**. Utilisez-le pour spécifier un secret de certificat de coffre de clés.
    - **Nom du magasin** - Ce champ est facultatif et n’est disponible que si vous définissez le champ **Type d’emplacement** sur **Certificat local**. Utilisez-le pour spécifier un nom de magasin par défaut à utiliser pour rechercher des certificats locaux.
    - **Emplacement du magasin** - Ce champ est facultatif et n’est disponible que si vous définissez le champ **Type d’emplacement** sur **Certificat local**. Utilisez-le pour spécifier un emplacement de magasin par défaut à utiliser pour rechercher des certificats locaux.

        > [!NOTE]
        > Le nom et l’emplacement du magasin par défaut sont ajoutés pour simplifier le processus de recherche des certificats locaux dans Commerce Runtime. X509StoreProvider comporte une liste de dossiers dans lesquels les certificats sont stockés. Si le nom du magasin par défaut et l’emplacement du magasin par défaut ne sont pas spécifiés, X509StoreProvider essaie de trouver un certificat dans les autres dossiers de sa liste. Pour plus d’informations sur les valeurs disponibles pour le nom et l’emplacement du magasin, consultez [StoreName Enum](/dotnet/api/system.security.cryptography.x509certificates.storename) et [StoreLocation Enum](//dotnet/api/system.security.cryptography.x509certificates.storelocation).

    - **Empreinte** - Ce champ est obligatoire et n’est disponible que si vous définissez le champ **Type d’emplacement** sur **Certificat local**. Utilisez-le pour spécifier l’empreinte numérique du certificat.

        > [!IMPORTANT]
        > Vous devez vous assurer que l’utilisateur qui exécute l’application qui doit utiliser le certificat local (par exemple, Modern POS en mode hors ligne) dispose au moins d’un accès en lecture seule à la clé privée du certificat.

    - **Commentaires** - Ce champ est facultatif et permet aux utilisateurs de saisir des notes.

## <a name="workflow-searching-certificates-in-the-commerce-runtime"></a>Workflow : recherche de certificats dans Commerce Runtime

Voici le workflow de base utilisé pour rechercher un certificat lorsqu’un profil de certificat est appelé dans Commerce Runtime.

1. Le système identifie si le profil du certificat comporte des paramètres spécifiques à l’entreprise pour l’entité juridique actuelle.
1. Le système essaie de trouver le certificat en utilisant les valeurs de la page **Paramètres du profil de certificat** pour la ligne où le champ **Priorité** est défini sur **1**.

    - Si le champ **Type d’emplacement** est défini sur **Coffre de clés**, la valeur du champ **Secret du certificat du coffre de clés** est utilisée pour rechercher le certificat sur la page **Paramètres du coffre de clés**. Le certificat est ensuite recherché dans le stockage du coffre de clés.
    - Si le champ **Type d’emplacement** est défini sur **Certificat local**, X509StoreProvider commence par rechercher le certificat en utilisant le nom et l’emplacement du magasin par défaut, si ces paramètres sont spécifiés. Il recherche ensuite dans tous les autres dossiers de sa liste de dossiers.

1. Si le certificat n’est pas trouvé, le processus est répété pour la ligne où le champ **Priorité** est défini sur **2**, etc.

> [!NOTE]
> Si le profil de certificat n’a pas de paramètres pour l’entité juridique actuelle, ou si la recherche de certificat échoue pour toutes les lignes de la page **Paramètres du profil de certificat**, le certificat est introuvable.

### <a name="caching-the-results-of-certificate-searches"></a>Mise en cache des résultats des recherches de certificats

Les résultats des recherches de certificats sont mis en cache. Le délai d’expiration par défaut d’un cache est d’une heure. Cependant, ce délai peut être personnalisé et défini sur une valeur maximale de 24 heures.

## <a name="gradual-update"></a>Mise à jour graduelle

Si une nouvelle version du certificat est lancée, mais qu’elle ne peut pas être mise à jour dans tous les magasins en même temps, la fonctionnalité de profils de certificat permet au certificat d’être mis à jour progressivement.

1. Recherchez un profil de certificat et la ligne à mettre à jour, puis sélectionnez **Paramètres**.
1. Ajoutez une ligne et spécifiez les paramètres correspondant à la dernière version du certificat.
1. Augmentez la valeur de **Priorité** de la nouvelle ligne. Utilisez le bouton **Déplacer vers le haut** pour déplacer la ligne afin qu’elle se situe au-dessus de la ligne de la version précédente du même certificat.
> [!NOTE]
> Dans Commerce Runtime, la nouvelle version du certificat sera appelée en premier. Si le certificat n’a pas encore été mis à jour dans un magasin spécifique ou sur un terminal spécifique, la version précédente sera appelée.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
