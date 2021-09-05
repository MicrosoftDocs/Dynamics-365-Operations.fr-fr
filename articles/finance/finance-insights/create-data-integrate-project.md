---
title: Créer un projet d’intégrateur de données
description: Cette rubrique explique comment créer un projet d’intégrateur de données.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: b08af906c18f6c0790ca56c69a833733f48cd88c
ms.sourcegitcommit: 822aea26c5da259efe11ff3b3dc4cf1598425689
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2021
ms.locfileid: "7386360"
---
# <a name="create-a-data-integrator-project"></a>Créer un projet d’intégrateur de données

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment créer un projet d’intégrateur de données.

1. Connectez-vous à Microsoft Dynamics 365 Finance.
2. Accédez à **Espaces de travail \> Gestion des données** et sélectionnez **Entités de données**. Attendez que toutes les entités de données aient été actualisées avant de passer à l’étape suivante.
3. Ouvrez le [portail Power Apps](https://make.powerapps.com/) et suivez ces étapes :

    1. Sélectionnez l’environnement approprié.
    2. Sélectionnez **Données \> Connexions** dans le volet de navigation de gauche.
    3. Connectez-vous aux instances appropriées des éléments suivants :

        - Dynamics 365
        - Dynamics 365 for Fin & Ops

4. Ouvrez les [environnements Power Apps](https://admin.powerapps.com/environments) et suivez ces étapes :

    1. Sélectionnez **Intégrateur de données**.
    2. Sélectionnez **Ensembles de connexions**.
    3. Sélectionnez **Nouvel ensemble de connexions**.
    4. Entrez un nom pour la connexion.
    5. Sélectionnez les connexions appropriées pour les éléments suivants :

        - Dynamics 365
        - Dynamics 365 for Fin & Ops

    6. Sélectionnez le mappage d’organisation approprié.
    7. Sélectionnez **Créer**.

5. Ouvrez les [environnements Power Apps](https://admin.powerapps.com/environments) et suivez ces étapes :  

    1. Créez des projets d’intégration de données pour les modèles suivants à l’aide du jeu de connexions que vous venez de créer :

        - Résultats des analyses de paiement client (CDS à Fin and Ops)
            - Si vous utilisez la version 10.0.17 ou une version ultérieure, vous devez utiliser le modèle nommé Résultats des analyses de paiement client (CDS à Fin and Ops 10.0.17 +).
        - Résultats des séries chronologiques de flux de trésorerie (CDS à Fin et Ops)
        - Résultats des séries chronologiques de budget (CDS à Fin et Ops)

    2. Définissez la planification appropriée pour chaque projet.

> [!NOTE]
> Si vous ne voyez pas les entités requises dans CDS, allez à **Crédits et recouvrements > configuration > Informations financières> paramètres de Informations financières**, activez la fonction de prédiction de paiement client et cliquez sur le bouton **Créer un modèle de prédiction**. Lorsque le déploiement du modèle d’IA est terminé (réussi ou échoué), les entités CDS nécessaires pour créer l’intégration seront déployées dans CDS.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
