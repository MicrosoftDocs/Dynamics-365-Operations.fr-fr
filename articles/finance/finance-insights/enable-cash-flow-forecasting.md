---
title: Activer la prévision des flux de trésorerie (version préliminaire)
description: Cette rubrique explique comment activer la fonctionnalité de prévisions de flux de trésorerie dans Informations financières.
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
ms.openlocfilehash: 29118557a1de4d3521f8125395b26471f7f48f3e
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638619"
---
# <a name="enable-cash-flow-forecasting-preview"></a>Activer la prévision des flux de trésorerie (version préliminaire)

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment activer la fonctionnalité de prévisions de flux de trésorerie dans Informations financières.

> [!NOTE]
> Pour utiliser les prévisions de paiement dans le flux de trésorerie, vous devez configurer la fonction de prévision de paiement client comme décrit dans [Activer les prédictions de paiement des clients](enable-cust-paymnt-prediction.md).

1. Utilisez les informations de la page d’environnement dans Microsoft Dynamics Lifecycle Services (LCS) pour se connecter à l’instance principale d’Azure SQL pour cet environnement. Exécutez la commande Transact-SQL (T-SQL) suivante pour activer les déploiements en mode Flighting pour l’environnement sandbox. (Vous devrez peut-être activer l’accès pour votre adresse IP dans LCS avant de pouvoir vous connecter à distance à Application Object Server \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > Ignorez cette étape si vous utilisez la version 10.0.20 ou ultérieure, ou si vous utilisez un déploiement Service Fabric. L’équipe Informations financières devrait déjà avoir activé le déploiement en mode Flighting pour vous. Si vous ne voyez pas la fonctionnalité dans l’espace de travail **Gestion des fonctionnalités**, ou si vous rencontrez des problèmes lorsque vous essayez de l’activer, contactez <fiap@microsoft.com>.
  
2. Ouvrez l’espace de travail **Gestion des fonctionnalités** et procédez comme suit :

    1. Sélectionnez **Rechercher des mises à jour**.
    2. Activer les fonctionnalités suivantes :

        - Nouveau contrôle de grille
        - Regroupement en grilles (version préliminaire) 
        - Prévisions de paiement client (version préliminaire)
        - Prévisions de flux de trésorerie (version préliminaire)

3. Aller à **Gestion de la trésorerie et de la banque \> Configuration des prévisions de trésorerie**, et ajoutez les comptes de liquidité à inclure dans les prévisions.

    > [!NOTE]
    > Si les comptes de liquidité ne sont pas configurés, le flux de trésorerie ne peut pas être généré.

4. Aller à **Gestion de la trésorerie et de la banque \> Configurer \> Informations financières (version préliminaire) \> Prévisions de flux de trésorerie (version préliminaire)** et suivez ces étapes :

    1. Sur l’onglet **Prévisions de trésorerie**, sélectionnez **Activer la fonctionnalité**.
    2. Sélectionner **Créer un modèle de prédiction**.

Pour plus d’informations sur la fonctionnalité des prévisions de flux de trésorerie, voir [Prévisions de flux de trésorerie](cash-flow-forecast-intro.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
