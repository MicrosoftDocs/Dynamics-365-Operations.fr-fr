---
title: Configurer Regulatory Configuration Service (RCS)
description: Cet article explique comment configurer Regulatory Configuration Service (RCS).
author: gionoder
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 63a4f77d6e80133947dff678cef3885167ec55be
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285785"
---
# <a name="set-up-regulatory-configuration-service-rcs"></a>Configurer Regulatory Configuration Service (RCS)

[!include [banner](../includes/banner.md)]

Cet article explique comment configurer Regulatory Configuration Service (RCS).

## <a name="turn-on-globalization-features"></a>Activer les fonctionnalités de globalisation

1. Connectez-vous à votre compte RCS.
2. Sélectionnez la vignette **Gestion des fonctionnalités**.
3. Dans l’espace de travail **Gestion des fonctionnalités**, sélectionnez **Fonctionnalités de globalisation** dans la liste, puis sélectionnez **Activer maintenant**.

Une vignette pour l’espace de travail **Fonctionnalités de globlisation** doit maintenant s’afficher sur le principal tableau de bord RCS.

## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a>Définir les paramètres pour l’intégration RCS avec la Facturation électronique

1. Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Paramètres associés**, sélectionnez **Paramètres de la gestion des états électroniques**.
2. Sur l’onglet **Facturation électronique**, dans le champ **URI du point de terminaison de service**, entrez le point de terminaison de service approprié pour la zone géographique Microsoft Azure, comme indiqué dans le tableau suivant.

    | Zone géographique Azure Datacenter | URI du point de terminaison de service |
    |----------------------------|----------------------|
    | Etats-Unis              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Europe                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Royaume-Uni             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Asie                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Japon                      | <p>`https://gw.jp-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Suisse                | <p>`https://gw.ch-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Brésil                     | <p>`https://gw.br-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.br-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Émirats arabes unis       | <p>`https://gw.ae-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Australie                  | <p>`https://gw.au-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.au-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Canada                     | <p>`https://gw.ca-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.ca-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | France                     | <p>`https://gw.fr-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Inde                      | <p>`https://gw.in-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

3. Vérifiez que le champ **ID d’application** est bien défini sur **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Cette valeur est une valeur fixe. Veillez à ce qu’un seul identificateur global unique (GUID) soit saisi, et que la valeur n’inclut aucun autre symbole que des espaces, des virgules, des points ou des points d’interrogation.
4. Dans le champ **ID environnement LCS**, entrez l’ID de votre environnement Microsoft Dynamics Lifecycle Services (LCS). Cette valeur est la référence à l’environnement Finance ou Supply Chain Management que vous utiliserez avec le service de facturation électronique. Pour obtenir votre identifiant, connectez-vous à [LCS](https://lcs.dynamics.com/), ouvrez votre projet, puis, sur l’onglet **Gérer l’environnement**, dans la section **Détails de l’environnement**, regardez dans le champ **Identifiant d’environnement**.

    > [!IMPORTANT]
    > Si le module complémentaire de facturation électronique est installé dans plusieurs environnements Finance ou Supply Chain Management dans LCS, utilisez toujours l’ID d’environnement de l’environnement le plus récemment installé. Si vous décidez d’installer le complément dans un nouvel environnement après avoir configuré et utilisé la fonctionnalité de facturation électronique, mettez à jour le champ **ID d’environnement LCS** dans RCS à la dernière valeur.

5. Sélectionnez **Sauvegarder**, puis fermez la page.

## <a name="configuration-providers"></a>Fournisseurs de configuration

Vous pouvez utiliser des fournisseurs de configuration pour distinguer les propriétaires des configurations de gestion des états électroniques (ER) utilisées dans les processus de facturation électronique et les propriétaires des fonctionnalités de globalisation. Pour toutes les fonctionnalités de globalisation fournies par Microsoft et publiées dans le référentiel global, le fournisseur de configuration est défini sur **Microsoft** (`http://microsoft.com`).

Vous pouvez ajuster uniquement les configurations de gestion des états électroniques (ER) et les fonctionnalités de globalisation qui appartiennent au fournisseur de configuration actif. Vous pouvez utiliser ces configurations et fonctionnalités comme modèles pour créer des configurations et des fonctionnalités appartenant au fournisseur de configuration actif, afin de pouvoir les ajuster.

Tout d’abord, créez les fournisseurs de configuration. Ensuite, définissez l’un d’entre eux comme actif. Vous ne pouvez pas définir le fournisseur de configuration **Microsoft** comme actif.

### <a name="create-a-configuration-provider"></a>Créer un fournisseur de configuration

1. Dans l’espace de travail **Génération d’états électroniques**, dans la section **Liens connexes**, sélectionnez **Fournisseurs de configuration**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Nom**, entrez un nom unique pour le fournisseur de configuration.
4. Dans le champ **Adresse Internet**, entrez l’URL unique du fournisseur de configuration.
5. Sélectionnez **Sauvegarder**, puis fermez la page.

### <a name="select-a-configuration-provider-as-active"></a>Sélectionnez un fournisseur de configuration comme actif

1. Dans la liste des fournisseurs de configuration, sélectionnez le fournisseur de configuration que vous souhaitez définir comme actif.
2. Sélectionnez **Activer**.

## <a name="import-er-configurations-from-the-global-repository"></a>Importer les configurations de gestion des états électroniques (ER) depuis le référentiel global

1. Dans l’espace de travail **Génération d’états électroniques**, dans la section **Liens connexes**, sélectionnez **Fournisseurs de configuration**.
2. Dans la liste des fournisseurs de configuration, sélectionnez **Microsoft**, puis **Référentiels**.
3. Sélectionnez **Global**, puis dans le volet Actions, sélectionnez **Ouvrir**.
4. Importez les modèles de gestion des états électroniques (ER) suivants :

    - **Modèle de contexte de facture client**
    - **Modèle de facture**
    - **Documents fiscaux** (pour les scénarios brésiliens, si nécessaire)
    - **Modèle de message de réponse**

5. Si **Cartographie du modèle de facture** n’a pas été importé automatiquement, importez-le.
6. Fermez la page.
