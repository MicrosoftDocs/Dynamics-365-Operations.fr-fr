---
title: Utiliser les prédictions de paiement des clients
description: Cet article décrit les conditions préalables et les étapes générales requises pour utiliser une version d’essai de Finance Insights.
author: ShivamPandey-msft
ms.date: 11/03/2021
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
ms.search.validFrom: 2020-11-16
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 330642624b55a6772ef149b70873021401a6bd83
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901400"
---
# <a name="use-customer-payment-predictions"></a>Utiliser les prédictions de paiement des clients

[!include [banner](../includes/banner.md)]

Cet article explique comment utiliser les prédictions de paiement du client. Avant d’utiliser cette fonctionnalité, assurez-vous que vous avez terminé les étapes de configuration correspondantes. Pour plus d’informations, voir [Activer les prédictions de paiement client](enable-cust-paymnt-prediction.md).

Vous pouvez afficher les prévisions de paiement des clients dans l’espace de travail **Gérer le crédit client et les recouvrements** et sur deux nouvelles pages de liste : **Prédictions de paiement par transaction** et **Prédictions de paiement par client**.

### <a name="manage-customer-credit-and-collections-workspace"></a>Gérer l’espace de travail de crédit et recouvrements client

L’espace de travail **Gérer le crédit client et les recouvrements** comprend deux nouvelles vignettes : **Prédictions de paiement par transaction** et **Prédictions de paiement par le client**.

### <a name="transaction-payment-predictions-list-page"></a>Page de liste Prédictions de paiement par transaction

Sur la liste **Prédictions de paiement par transaction**, vous pouvez afficher la probabilité de paiement pour les transactions ouvertes dans les compartiments **À temps**, **Tard**, et **Très tard**. Pour chaque transaction de la grille, la colonne **Probabilité à l’heure** indique la probabilité que la facture soit payée au plus tard à la date d’échéance. Si la probabilité d’un paiement à temps est inférieure à 50 %%, un cercle rouge apparaît à côté du pourcentage dans la colonne **Probabilité à temps** pour indiquer le risque de retard de paiement.

[![Prédiction de paiement par page de transactions.](./media/payment-predictions-per-transaction.png)](./media/payment-predictions-per-transaction.png)

Le volet **Informations connexes** sur le côté droit de la page affiche plus de détails sur les prédictions :

- Pour la transaction sélectionnée dans la grille, le raccourci **Prédiction de paiement** affiche les détails des prévisions de paiement dans les compartiments **À temps**, **Tard**, et **Très tard**. La section **Principaux facteurs** montre les principaux facteurs qui ont influencé les prévisions. Les principaux facteurs sont les attributs de la transaction sélectionnée et/ou du client pour cette transaction.
- Le raccourci **Customer Insights** affiche les statistiques de facturation, de paiement et de recouvrement en cours pour le client pour la transaction sélectionnée.
- Le raccourci **Historique client** affiche l’historique de paiement du client dans les compartiments **À temps**, **Tard**, et **Très tard**.

Les données dans la section **Principaux facteurs**, et sur les raccourcis **Customer Insights** et **Historique client**, aide à expliquer les prévisions de paiement. Cela peut vous aider à accroître votre confiance dans l’efficacité des prédictions.

[![Indicateurs graphiques pour les prévisions de paiement dans le volet Informations connexes.](./media/payment-prediction-gauges.png)](./media/payment-prediction-gauges.png)

### <a name="customer-payment-predictions-list-page"></a>Page de liste Prédictions de paiements par client

La page de liste **Prédictions de paiement par client** affiche le solde ouvert total et le montant qui devrait être payé dans les compartiments **À temps**, **Tard** et **Très tard**.

[![Page Prédictions de paiements par client.](./media/payment-predictions-per-transaction-02.png)](./media/payment-predictions-per-transaction-02.png)

Le montant du paiement dans chaque compartiment est calculé comme la somme de la moyenne pondérée du solde de la transaction. Ce montant est calculé en fonction des probabilités de paiement dans chaque compartiment.

Par exemple, un client a trois transactions ouvertes qui ont les probabilités de paiement suivantes dans chaque compartiment.

| Transaction | Montant | Probabilité de paiement à temps | Probabilité de paiement tardif | Probabilité de paiement très tardif |
|-------------|--------|-----------------------------|--------------------------|-------------------------------|
| T1          | 100    | 10 pourcent                  | 50 pourcent               | 40 pourcent                    |
| T2          | 1 000  | 50 pourcent                  | 30 pourcent               | 20 pourcent                    |
| T3          | 10,000 | 1 pourcent                   | 4 pourcent                | 95 pourcent                    |

Dans ce cas, les paiements sont projetés pour chaque tranche de la manière suivante.

| Compartiments   | Transaction T1      | Transaction T2         | Transaction T3            | Total |
|-----------|---------------------|------------------------|---------------------------|-------|
| Dans les délais   | 100 × 10 ÷ 100 = 10 | 1 000 × 50 ÷ 100 = 500 | 10 000 × 1 ÷ 100 = 100    | 610   |
| En retard      | 100 × 50 ÷ 100 = 50 | 1 000 × 30 ÷ 100 = 300 | 10 000 × 4 ÷ 100 = 400    | 750   |
| Très en retard | 100 × 40 ÷ 100 = 40 | 1 000 × 20 ÷ 100 = 200 | 10 000 × 95 ÷ 100 = 9 500 | 9,740 |

La section **Informations connexes** sur le côté droit de la page affiche plus de détails sur les prédictions :

- Pour la transaction sélectionnée dans la grille, le raccourci **Prédictions de paiement** affiche les détails des prévisions de paiement dans les compartiments **À temps**, **Tard**, et **Très tard**.
- Le raccourci **Customer Insights** affiche les statistiques de facturation, de paiement et de recouvrement en cours pour le client pour la transaction sélectionnée.
- Le raccourci **Historique client** affiche l’historique de paiement du client dans les compartiments **À temps**, **Tard**, et **Très tard**.

Les données sur les raccourcis **Customer Insights** et **Historique client** aident à expliquer les prédictions de paiement. Cela peut vous aider à accroître votre confiance dans l’efficacité des prédictions.

## <a name="improving-the-accuracy-of-payment-predictions"></a>Améliorer la précision des prévisions de paiement

Vous pouvez voir l’exactitude des prévisions de paiement en accédant à **Crédits et collections \> Configurer \> Informations financières \> Paramètres des informations financières**. Sur l’onglet **Informations sur les paiements client**, la section **Modèle de prédiction** montre la précision du modèle de prédiction sous forme de pourcentage.

Si vous n’êtes pas satisfait de la précision, sélectionnez le lien **Améliorer la précision du modèle** pour ouvrir l’expérience d’extension AI Builder. Dans l’expérience d’extension AI Builder, vous pouvez sélectionner ou annuler la sélection de champs jusqu’à ce que vous ayez sélectionné les champs qui vous semblent les plus importants pour prédire avec précision les probabilités de paiement. Lorsque vous avez terminé, vous pouvez facilement recycler le modèle de prédiction et publier vos modifications. Le modèle de prédiction nouvellement formé sera automatiquement sélectionné pour les prédictions dans Dynamics 365 Finance.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
