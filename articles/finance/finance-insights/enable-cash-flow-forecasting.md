---
title: Activer la prévision des flux de trésorerie
description: Cette rubrique explique comment activer la fonctionnalité de prévisions de flux de trésorerie dans Informations financières.
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
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: cfcdbe76d640d1786b4622febf9157f5fb1c42f9
ms.sourcegitcommit: 133aa728b8a795eaeaef22544f76478da2bd1df9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2022
ms.locfileid: "7969135"
---
# <a name="enable-cash-flow-forecasting"></a>Activer la prévision des flux de trésorerie

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment activer la fonctionnalité de prévisions de flux de trésorerie dans Finance Insights.

> [!NOTE]
> Pour utiliser les prévisions de paiement dans le flux de trésorerie, vous devez configurer la fonction de prévision de paiement client comme décrit dans [Activer les prédictions de paiement des clients](enable-cust-paymnt-prediction.md).
  
1. Ouvrez l’espace de travail **Gestion des fonctionnalités** et procédez comme suit :

    1. Sélectionnez **Rechercher des mises à jour**.
    2. Sur l’onglet **Tous**, recherchez **Prévisions de flux de trésorerie**. Si vous ne trouvez pas cette fonctionnalité, recherchez **(Version préliminaire) Prévisions de flux de trésorerie**. 
    3. Activer la fonctionnalité.

2. Aller à **Gestion de la trésorerie et de la banque \> Configuration des prévisions de trésorerie**, et ajoutez les comptes de liquidité à inclure dans les prévisions. Configurez également le compte de liquidité pour les paiements sur les onglets **Comptabilité client** et **Comptabilité fournisseur**. Assurez-vous de recalculer les prévisions de flux de trésorerie.

    > [!NOTE]
    > Si les comptes de liquidité ne sont pas configurés, le flux de trésorerie ne peut pas être généré.
    >
    > Pour plus d’informations sur la configuration des prévisions de flux de trésorerie, voir [Prévisions de flux de trésorerie](../cash-bank-management/cash-flow-forecasting.md).

3. Aller à **Gestion de la trésorerie et de la banque \> Configurer \> Informations financières (version préliminaire) \> Prévisions de flux de trésorerie (version préliminaire)** et suivez ces étapes :

    1. Sur l’onglet **Prévisions de trésorerie**, sélectionnez **Activer la fonctionnalité**.
    2. Sélectionner **Créer un modèle de prédiction**.

Pour plus d’informations sur la fonctionnalité des prévisions de flux de trésorerie, voir [Prévisions de flux de trésorerie](cash-flow-forecast-intro.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
