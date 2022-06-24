---
title: Créer un projet d’intégration de données
description: Cet article explique comment créer un projet d’intégration de données.
author: ShivamPandey-msft
ms.date: 05/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 4ff4f88c6c5d55d853aebd7d437bfb107292fb2f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876238"
---
# <a name="create-a-data-integration-project"></a>Créer un projet d’intégration de données

[!include [banner](../includes/banner.md)]

Cet article explique comment créer un projet d’intégration de données.

1. Connectez-vous à Microsoft Dynamics 365 Finance.
2. Accédez à **Espaces de travail \> Gestion des données** et sélectionnez **Entités de données**. Attendez que toutes les entités de données aient été actualisées avant de passer à l’étape suivante.
3. Ouvrez le [portail Power Apps](https://make.powerapps.com/) et suivez ces étapes :

    1. Sélectionnez l’environnement approprié.
    2. Dans le volet de navigation de gauche, sélectionnez **Dataverse \> Connexions**.
    3. Connectez-vous aux instances appropriées des éléments suivants :

        - Dynamics 365
        - Dynamics 365 for Fin & Ops

4. Ouvrez les [environnements Power Apps](https://admin.powerapps.com/environments) et suivez ces étapes :

    1. Sélectionnez **Intégration des données**.
    2. Sélectionnez **Ensembles de connexions**.
    3. Sélectionnez **Nouvel ensemble de connexions**.
    4. Entrez un nom pour la connexion.
    5. Sélectionnez les connexions appropriées pour les éléments suivants :

        - Dynamics 365
        - Dynamics 365 for Fin & Ops

    6. Sélectionnez le mappage d’organisation approprié.
    7. Cliquez sur **Créer**.

5. Ouvrez les [environnements Power Apps](https://admin.powerapps.com/environments) et suivez ces étapes :  

    1. Créez un seul projet d’intégration de données pour chacun des modèles suivants à l’aide de l’ensemble de connexion que vous venez de créer :

        - Résultats des informations de paiement du client (CDS vers Fin and Ops 10.0.17+)
        - Résultats des séries chronologiques de flux de trésorerie (CDS à Fin et Ops)
        - Résultats des séries chronologiques de budget (CDS à Fin et Ops)

      > [!NOTE]
      > La création de plusieurs projets d’intégration de données pour chaque modèle peut provoquer des erreurs qui bloqueront les mises à jour.

    2. Définissez la planification appropriée pour chaque projet.

> [!NOTE]
> Si vous ne voyez pas les entités requises dans Dataverse, accédez aux paramètres **Crédits et recouvrements** > **Configuration** > **Finance Insights** > **Finance Insights**, activez la fonctionnalité, **Prédictions de paiement client**, puis sélectionnez **Créer un modèle de prédiction**. Lorsque le déploiement du modèle d’IA est terminé, les entités Dataverse nécessaires pour créer l’intégration seront déployées dans CDS.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
