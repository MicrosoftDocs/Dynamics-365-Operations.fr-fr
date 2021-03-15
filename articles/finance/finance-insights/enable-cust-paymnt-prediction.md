---
title: Activer les prédictions de paiement des clients (version préliminaire)
description: Cette rubrique explique comment activer et configurer la fonctionnalité de Prédictions de paiement des clients dans Finance Insights.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 584c1af5f9252a4b8c88a8866a64184bd0595b2e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009416"
---
# <a name="enable-customer-payment-predictions-preview"></a>Activer les prédictions de paiement des clients (version préliminaire)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cette rubrique explique comment activer et configurer la fonctionnalité de Prédictions de paiement des clients dans Finance Insights. Vous activez la fonction dans l’espace de travail **Gestion des fonctionnalités** et entrez les paramètres de configuration sur la page **Paramètres Finance insights**. Cette rubrique comprend également des informations qui peuvent vous aider à utiliser efficacement la fonctionnalité.

> [!NOTE]
> Avant d’effectuer les étapes suivantes, assurez-vous de suivre les étapes prérequises dans la rubrique [Configurer pour Finance insights](configure-for-fin-insites.md).

1. Utilisez les informations de la page d’environnement dans Microsoft Dynamics Lifecycle Services (LCS) pour se connecter à l’instance principale d’Azure SQL pour cet environnement. Exécutez la commande Transact-SQL (T-SQL) suivante pour activer les déploiements en mode Flighting pour l’environnement sandbox. (Vous devrez peut-être activer l’accès pour votre adresse IP dans LCS avant de pouvoir vous connecter à distance à Application Object Server \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED, PARTITION) VALUES ('PayPredEnableFeature', 1, 5637144576)`

    > [!NOTE]
    > Si votre déploiement de Microsoft Dynamics 365 Finance est un déploiement Service Fabric, vous pouvez ignorer cette étape. L’équipe Finance Insights devrait déjà avoir activé le déploiement en mode Flighting pour vous. Si vous ne voyez pas la fonctionnalité dans l’espace de travail **Gestion des fonctionnalités**, ou si vous rencontrez des problèmes lorsque vous essayez de l’activer, contactez <fiap@microsoft.com>.

2. Activez la fonctionnalité Informations sur les paiements des clients :

    1. Accédez à **Administration système \> Espaces de travail \> Gestion des fonctionnalités**.
    2. Trouvez la fonctionnalité nommée **Informations sur les paiements des clients (version préliminaire)**.
    3. Sélectionnez **Activer maintenant**.

    La fonctionnalité Informations sur les paiements des clients est maintenant activée et prête à être configurée.

3. Configurez la fonctionnalité Informations sur les paiements des clients :

    1. Aller à **Crédits et collections \> Configurer \> Finance Insights \> Paramètres Finance Insights**.

        [![Page de paramètres Finance Insights avant la configuration de la fonctionnalité](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)

    2. Sur la page **Paramètres Finance Insights**, sur l’onglet **Informations sur les paiements des clients**, sélectionnez le lien **Afficher les champs de données utilisés dans le modèle de prédiction** pour ouvrir la page **Champs de données pour le modèle de prédiction**. Là, vous pouvez afficher la liste par défaut des champs qui sont utilisés pour créer le modèle de prédiction d’intelligence artificielle (IA) pour les prédictions de paiement des clients.

        Pour utiliser la liste de champs par défaut pour créer le modèle de prédiction, fermez la page **Champs de données pour le modèle de prédiction**, puis sur la page **Paramètres Finance Insights**, définissez l’option **Activer la fonctionnalité** sur **Oui**.

    3. Spécifiez la période de transaction "très tardive" pour définir ce que le compartiment de prédiction **Très tard** signifie pour votre entreprise.

        Pour chaque facture ouverte, le système prédit la probabilité de paiement en trois catégories : **À temps**, **En retard**, et **Très tard**.

        - **À temps** – Ce compartiment comprend les paiements qui devraient être payés au plus tard à la date d’échéance de la transaction.
        - **En retard** – Ce compartiment comprend les paiements dont le paiement est prévu après la date d’échéance de la transaction mais avant le début de la période de transaction "très tardive".
        - **Très tard** – Ce compartiment comprend les paiements dont le paiement est prévu après la date d’échéance de la transaction mais avant le début de la période de transaction "très tardive".

        > [!NOTE]
        > Si vous modifiez la période de transaction "très tardive" et sélectionnez **Modifier le seuil de retard** une fois que le modèle de prédiction IA pour les paiements des clients a été créé, le modèle de prédiction existant est supprimé et un modèle est créé. Le nouveau modèle de prédiction déplacera les transactions dans la période "très tardive", en fonction des paramètres qui ont été saisis pour la définir.

    4. Après avoir défini la période de transaction "très tardive", sélectionnez **Créer un modèle de prédiction** pour créer le modèle de prédiction. La section **Modèle de prédiction** sur la page **Paramètres Finance Insights** affiche l’état du modèle de prédiction.

        > [!NOTE]
        > A tout moment pendant la création du modèle de prédiction, vous pouvez sélectionner **Réinitialiser la création du modèle** pour redémarrer le processus.

    La fonction a maintenant été configurée et est prête à être utilisée.

Une fois que la fonction a été activée et configurée, et que le modèle de prédiction a été créé et fonctionne, la section **Modèle de prédiction** de la page **Paramètres Finance Insights** montre la précision du modèle, comme indiqué dans l’illustration suivante.

[![Précision du modèle de prédiction sur la page de paramètres Financial insights](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)

## <a name="release-details"></a>Détails du lancement

La version préliminaire publique de Finance Insights est disponible pour les déploiements d’essai aux États-Unis, en Europe et au Royaume-Uni. Microsoft ajoute progressivement la prise en charge de plusieurs régions.

Les fonctionnalités en version préliminaire publiques peuvent et doivent être activées uniquement dans les environnements sandbox de niveau 2. Les modèles de configuration et IA créés dans un environnement sandbox ne peuvent pas être migrés vers un environnement de production. Pour plus d’informations, voir [Conditions d’utilisation supplémentaires pour les versions préliminaires de Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).

## <a name="privacy-notice"></a>Avis de confidentialité

Les versions préliminaires (1) peuvent utiliser moins de mesures de confidentialité et de sécurité que le service Dynamics 365 Finance and Operations, (2) ne sont pas inclus dans le contrat de niveau de service (SLA) pour ce service, (3) ne doivent pas être utilisés pour traiter des données personnelles ou autres données soumises à des exigences de conformité juridique ou réglementaire, et (4) bénéficient d’un support limité.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]