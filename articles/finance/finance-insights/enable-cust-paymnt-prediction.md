---
title: Activer les prédictions de paiement des clients
description: Cette rubrique explique comment activer et configurer la fonctionnalité de Prédictions de paiement des clients dans Informations financières.
author: ShivamPandey-msft
ms.date: 11/03/2021
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
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 16ccd7f2e11f0b46aaa646de272e668d29ccc0c0
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "7752926"
---
# <a name="enable-customer-payment-predictions"></a>Activer les prédictions de paiement des clients

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cette rubrique explique comment activer et configurer la fonctionnalité de Prédictions de paiement des clients dans Informations financières. Vous activez la fonction dans l’espace de travail **Gestion des fonctionnalités** et entrez les paramètres de configuration sur la page **Configuration de Finance Insights**. Cette rubrique comprend également des informations qui peuvent vous aider à utiliser efficacement la fonctionnalité.

> [!NOTE]
> Avant d’effectuer les étapes suivantes, assurez-vous de suivre les étapes prérequises dans la rubrique [Configurer pour Informations financières](configure-for-fin-insites.md).

1. Activez la fonctionnalité Prédictions de paiement des clients :

    1. Ouvrez l’espace de travail **Gestion des fonctionnalités**.
    2. Sélectionnez **Rechercher des mises à jour**.
    3. Sur l’onglet **Tous**, recherchez **Prédictions de paiement des clients**. Si vous ne trouvez pas cette fonctionnalité, recherchez **(Version préliminaire) Prédictions de paiement des clients**. 
    4. Activer la fonctionnalité.

    La fonctionnalité Prédictions de paiement des clients est maintenant activée et prête à être configurée.

2. Configurez la fonctionnalité Informations sur les paiements des clients :

    1. Aller à **Crédits et collections \> Configurer \> Finance Insights \> Prédictions de paiement des clients**.
    2. Sur la page **Configuration de Finance Insights**, sur l’onglet **Prédictions de paiement des clients**, sélectionnez le lien **Afficher les champs de données utilisés dans le modèle de prédiction** pour ouvrir la page **Champs de données pour le modèle de prédiction**. Là, vous pouvez afficher la liste par défaut des champs qui sont utilisés pour créer le modèle de prédiction d’intelligence artificielle (IA) pour les prédictions de paiement des clients.

        Pour utiliser la liste de champs par défaut pour créer le modèle de prédiction, fermez la page **Champs de données pour le modèle de prédiction**, puis sur la page **Configuration de Finance Insights**, définissez l’option **Activer la fonctionnalité** sur **Oui**.

    3. Spécifiez la période de transaction "très tardive" pour définir ce que le compartiment de prédiction **Très tard** signifie pour votre entreprise.

        Pour chaque facture ouverte, le système prédit la probabilité de paiement en trois catégories : **À temps**, **En retard**, et **Très tard**.

        - **À temps** – Ce compartiment comprend les paiements qui devraient être payés au plus tard à la date d’échéance de la transaction.
        - **En retard** – Ce compartiment comprend les paiements dont le paiement est prévu après la date d’échéance de la transaction mais avant le début de la période de transaction "très tardive".
        - **Très tard** – Ce compartiment comprend les paiements dont le paiement est prévu après la date d’échéance de la transaction mais avant le début de la période de transaction "très tardive".

        > [!NOTE]
        > Si vous modifiez la période de transaction "très tardive" et sélectionnez **Modifier le seuil de retard** une fois que le modèle de prédiction IA pour les paiements des clients a été créé, le modèle de prédiction existant est supprimé et un modèle est créé. Le nouveau modèle de prédiction déplacera les transactions dans la période "très tardive", en fonction des paramètres qui ont été saisis pour la définir.

    4. Après avoir défini la période de transaction "très tardive", sélectionnez **Créer un modèle de prédiction** pour créer le modèle de prédiction. La section **Modèle de prédiction** sur la page **Configuration de Finance Insights** affiche l’état du modèle de prédiction.

        > [!NOTE]
        > A tout moment pendant la création du modèle de prédiction, vous pouvez sélectionner **Réinitialiser la création du modèle** pour redémarrer le processus.

    La fonction a maintenant été configurée et est prête à être utilisée.

Une fois que la fonction a été activée et configurée, et que le modèle de prédiction a été créé et fonctionne, la section **Modèle de prédiction** de la page **Configuration de Finance Insights** montre la précision du modèle.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
