---
title: Profils de certificat définis par l’utilisateur pour les magasins de vente au détail
description: Cet article offre une vue d’ensemble de l’utilisation des certificats dans les magasins de détail.
author: josaw
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: epopov
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1b40c74efa56a6e18af907e000554b9ab269bb31
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873027"
---
# <a name="user-defined-certificate-profiles-for-retail-stores"></a>Profils de certificat définis par l’utilisateur pour les magasins de vente au détail

[!include [banner](../includes/banner.md)]


## <a name="overview"></a>Présentation

Cet article fournit une vue d’ensemble des profils de certificat disponibles dans Microsoft Dynamics 365 Commerce. Cette fonctionnalité étend la fonctionnalité [Gérer les secrets pour les canaux Retail](../dev-itpro/manage-secrets.md) en ajoutant la prise en charge des certificats locaux.

Pendant que le point de vente (PDV) fonctionne en mode hors ligne, il ne peut pas accéder aux certificats stockés dans le coffre de clés. Le certificat local doit être utilisé à la place. Les capacités suivantes sont prises en charge :

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

La procédure suivante explique comment configurer des profils de certificat. Avant d’utiliser des profils de certificat dans les canaux de Commerce, procédez comme suit pour configurer les paramètres.

1. Dans l’espace de travail **Gestion des fonctionnalités**, activez la fonctionnalité **Profils de certificat définis par l’utilisateur pour les magasins de vente au détail**.
2. Accédez à **Administration système \> Paramétrage \> Profils de certificat**.
3. Créez un enregistrement et définissez les champs **Profil de certificat**, **Nom** et **Description** champs pour cet enregistrement.

    > [!NOTE]
    > Le profil de certificat est un identificateur unique d’un certificat dans l’ensemble des entreprises et des composants de Commerce.

3. Dans l’onglet **Entités juridiques**, ajoutez une ligne et sélectionnez l’entité juridique (société) pour laquelle le profil de certificat actuel doit être utilisé. Si le profil de certificat doit être utilisé pour plusieurs entités juridiques, répétez cette étape pour ajouter une ligne pour chaque entité juridique supplémentaire.
4. Sélectionnez **Paramètres** pour ouvrir la page **Paramètres du profil de certificat**, dans laquelle vous pouvez entrer les paramètres spécifiques à l’entreprise pour le profil de certificat.

### <a name="certificate-profile-settings"></a>Paramètres du profil de certificat

Lorsque vous sélectionnez **Paramètres** pour les lignes de profil de certificat, la page **Paramètres du profil de certificat** s’affiche. Cette page vous permet de spécifier quels certificats peuvent être utilisés lorsque le profil de certificat actuel est appelé dans les canaux de Commerce. Vous pouvez également spécifier l’ordre dans lequel les certificats doivent être recherchés.

> [!NOTE]
> Le champ **Priorité** est automatiquement défini. La valeur **1** représente la priorité la plus élevée. Lorsqu’une nouvelle ligne est ajoutée sur la page **Paramètres du profil de certificat**, sa priorité est définie sur la priorité de la ligne précédente plus un. Pour modifier la priorité d’une ligne spécifique, sélectionnez la ligne, puis sélectionnez soit **Déplacer vers le haut** pour augmenter la priorité ou **Déplacer vers le bas** pour diminuer la priorité.

Lorsque vous ajoutez une nouvelle ligne à la page **Paramètres du profil de certificat**, définissez les champs suivants :

- **Type d’emplacement** - Sélectionnez l’emplacement où le certificat est stocké. Deux valeurs sont possibles pour ce champ : **Certificat local** et **Coffre de clés**.
- **Certificat de coffre de clés** - Ce champ est obligatoire si vous définissez le champ **Type d’emplacement** sur **Coffre de clés**. Utilisez-le pour spécifier un secret de certificat de coffre de clés.

    > [!NOTE]
    > Avant d’utiliser un certificat de coffre de clés dans les profils de certificat, assurez-vous de télécharger un certificat dans le stockage de coffre de clés et suivez les instructions de [Configurer le client Azure Key Vault](../../finance/localizations/setting-up-azure-key-vault-client.md).

- **Nom du magasin** - Ce champ est facultatif et n’est disponible que si vous définissez le champ **Type d’emplacement** sur **Certificat local**. Utilisez-le pour spécifier un nom de magasin par défaut à utiliser pour rechercher des certificats locaux.
- **Emplacement du magasin** - Ce champ est facultatif et n’est disponible que si vous définissez le champ **Type d’emplacement** sur **Certificat local**. Utilisez-le pour spécifier un emplacement de magasin par défaut à utiliser pour rechercher des certificats locaux.

    > [!NOTE]
    > Le nom et l’emplacement du magasin par défaut sont ajoutés pour simplifier le processus de recherche des certificats locaux dans Commerce Runtime. X509StoreProvider comporte une liste de dossiers dans lesquels les certificats sont stockés. Si le nom du magasin par défaut et l’emplacement du magasin par défaut ne sont pas spécifiés, X509StoreProvider essaie de trouver un certificat dans les autres dossiers de sa liste.

- **Empreinte** - Ce champ est obligatoire et n’est disponible que si vous définissez le champ **Type d’emplacement** sur **Certificat local**. Utilisez-le pour spécifier l’empreinte numérique du certificat.
- **Commentaires** - Ce champ est facultatif et permet aux utilisateurs de saisir des notes.

### <a name="workflow-searching-certificates-in-the-commerce-runtime"></a>Workflow : recherche de certificats dans Commerce Runtime

Voici le workflow de base utilisé pour rechercher un certificat lorsqu’un profil de certificat est appelé dans Commerce Runtime.

1. Le système identifie si le profil du certificat comporte des paramètres spécifiques à l’entreprise pour l’entité juridique actuelle.
1. Le système essaie de trouver le certificat en utilisant les valeurs de la page **Paramètres du profil de certificat** pour la ligne où le champ **Priorité** est défini sur **1**.

    - Si le champ **Type d’emplacement** est défini sur **Coffre de clés**, la valeur du champ **Secret du certificat du coffre de clés** est utilisée pour rechercher le certificat sur la page **Paramètres du coffre de clés**. Le certificat est ensuite recherché dans le stockage du coffre de clés.
    - Si le champ **Type d’emplacement** est défini sur **Certificat local**, X509StoreProvider commence par rechercher le certificat en utilisant le nom et l’emplacement du magasin par défaut, si ces paramètres sont spécifiés. Il recherche ensuite dans tous les autres dossiers de sa liste de dossiers.

1. Si le certificat n’est pas trouvé, le processus est répété pour la ligne où le champ **Priorité** est défini sur **2**, etc.

> [!NOTE]
> Si le profil de certificat n’a pas de paramètres pour l’entité juridique actuelle, ou si la recherche de certificat échoue pour toutes les lignes de la page **Paramètres du profil de certificat**, le certificat est introuvable.

#### <a name="caching-the-results-of-certificate-searches"></a>Mise en cache des résultats des recherches de certificats

Les résultats des recherches de certificats sont mis en cache. Le délai d’expiration par défaut d’un cache est d’une heure. Cependant, ce délai peut être personnalisé et défini sur une valeur maximale de 24 heures.

### <a name="gradual-update"></a>Mise à jour graduelle

Si une nouvelle version du certificat est lancée, mais qu’elle ne peut pas être mise à jour dans tous les magasins en même temps, la fonctionnalité de profils de certificat permet au certificat d’être mis à jour progressivement.

1. Recherchez un profil de certificat et la ligne à mettre à jour, puis sélectionnez **Paramètres**.
1. Ajoutez une ligne et spécifiez les paramètres correspondant à la dernière version du certificat.
1. Augmentez la valeur de **Priorité** de la nouvelle ligne. Utilisez le bouton **Déplacer vers le haut** pour déplacer la ligne afin qu’elle se situe au-dessus de la ligne de la version précédente du même certificat.

> [!NOTE]
> Dans Commerce Runtime, la nouvelle version du certificat sera appelée en premier. Si le certificat n’a pas encore été mis à jour dans un magasin spécifique ou sur un terminal spécifique, la version précédente sera appelée.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]