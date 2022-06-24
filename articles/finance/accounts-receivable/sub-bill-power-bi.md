---
title: Contenu Power BI de la facturation de l’abonnement
description: Cet article décrit les données incluses dans le contenu Microsoft Power BI de la facturation de l’abonnement.
author: JodiChristiansen
ms.date: 04/13/2022
ms.topic: article
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-04-13
ms.openlocfilehash: 6cee01eb5b8bb8296b6e7f638b565c999ccc023e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849958"
---
# <a name="subscription-billing-power-bi-content"></a>Contenu Power BI de la facturation de l’abonnement

[!include[banner](../includes/banner.md)]

Cet article décrit les données incluses dans le contenu Microsoft Power BI de la facturation de l’abonnement. Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu. 

## <a name="overview"></a>Présentation

Le contenu Power BI de la facturation de l’abonnement a été créé pour les commis et les responsables de la facturation des abonnements. Il fournit des métriques de facturation de l’abonnement clés, telles que les revenus récurrents mensuels (MRR) pour les échéanciers de facturation, ainsi que les informations sur le solde dégressif et la cascade pour les échéanciers de reports. Il utilise les données des échéanciers de facturation et des échéanciers de report pour fournir un aperçu des revenus et des revenus récurrents.

Le contenu Power BI contient les trois onglets suivants qui fournissent un total de quatre rapports analytiques : 

- **Analytique – MRR** – Cet onglet fournit le rapport **Facturation récurrente mensuelle** et le rapport **Détails de l’échéancier de facturation**.
- **Analytique – Cascade** – Cet onglet fournit le rapport **Cascade de revenus**.
- **Analytique – Solde dégressif** – Cet onglet fournit le rapport **Solde dégressif**.

## <a name="view-data-on-the-analytical-reports"></a>Afficher les données sur les rapports analytiques

Avant de pouvoir afficher les données des rapports analytiques, vous devez exécuter un processus périodique qui génère les données de rapport pour chaque rapport. Ces données requises par les rapports doivent être générées car elles ne sont pas stockées directement dans la base de données. 

1. Aller à **Facturation de l’abonnement \> Facturation contractuelle récurrente \> Tâches périodiques \> Traitement par lots des rapports analytiques MRR**, et suivez ces étapes :

    1. Saisissez une plage de dates ne dépassant pas trois ans.
    2. Facultatif : configurez une tâche de traitement par lots récurrente pour actualiser périodiquement les données.
    3. Cliquez sur **OK**.

2. Une fois l’exécution du travail par lots terminée, accédez à **Administration système \> Configurer \> Magasin d’entités**, et actualisez la mesure agrégée **Rapport RMP**. 
3. Aller à **Facturation de l’abonnement \> Reports des produits et des dépenses \> Tâches périodiques \> Traitement par lots des rapports analytiques en cascade**, et suivez ces étapes :

    1. Entrez une date de début et une date de fin qui ne couvrent pas plus de 26 périodes. 
    2. Si vous souhaitez afficher le nombre prévu de périodes passées dans la période en cours, définissez l’option **Prévision des montants passés dans la période en cours** sur **Oui**.
    3. Facultatif : configurez une tâche de traitement par lots récurrente pour actualiser périodiquement les données.
    4. Cliquez sur **OK**. 

4. Une fois l’exécution du travail par lots terminée, accédez à **Administration système \> Configurer \> Magasin d’entités**, et actualisez la mesure agrégée **Rapport de cascade**.
5. Aller à **Facturation de l’abonnement \> Reports des produits et des dépenses \> Tâches périodiques \> Traitement par lots des rapports analytiques du solde dégressif**, et suivez ces étapes :

    1. Entrez une date de début et une date de fin qui ne couvrent pas plus de 26 périodes. 
    2. Si vous souhaitez afficher le nombre prévu de périodes passées dans la période en cours, définissez l’option **Prévision des montants passés dans la période en cours** sur **Oui**.
    3. Facultatif : configurez une tâche de traitement par lots récurrente pour actualiser périodiquement les données.
    4. Cliquez sur **OK**.

6. Une fois l’exécution du travail par lots terminée, accédez à **Administration système \> Configurer \> Magasin d’entités**, et actualisez la mesure agrégée **Rapport du solde dégressif**.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI

Le contenu Power BI de la facturation de l’abonnement est affiché dans l’espace de travail **Facturation de l’abonnement**.
