---
title: Informations sur le paiement client (aperçu)
description: Cette rubrique décrit comment les informations sur le paiement client peuvent vous aider à prévoir quand une facture sera payées et permettre aux organisations de créer des stratégies d'optimisation pour améliorer la probabilité d'être payées à temps.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-04-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 9e722db6302d7ef51c01601cde245d4f4a333eba
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566240"
---
# <a name="customer-payment-insights-preview"></a>Informations sur le paiement client (aperçu)

[!include[banner](../includes/banner.md)]

> [!IMPORTANT]
> Cette fonctionnalité fait partie d'une version ciblée et n'est disponible que pour les utilisateurs qui ont choisi l'aperçu privé. Cette fonctionnalité sera incluse dans une prochaine version à disponibilité générale.

# <a name="overview"></a>Vue d'ensemble

Les organisations trouvent souvent difficiles de prévoir quand un client paiera ses factures. Ce manque d'informations peut entraîner des prévisions de flux de trésorerie inexactes, des processus de collecte inefficaces et la possibilité de commandes effectuées avec des clients susceptibles d'entraîner un risque de crédit. Les informations sur le paiement client (aperçu) utilisent le Machine Learning pour prévoir quand une facture sera payée. Elle fournissent également des stratégies d'optimisation qui peuvent être personnalisées pour optimiser la probabilité que les clients paient à temps.

## <a name="predictions"></a>Prédictions

Les prédictions de paiement permettent aux organisations d'améliorer leurs processus d'entreprise en les aidant à :

-   Identifier facilement les factures prévues pour être payées en retard.
-   Prendre des mesures appropriées pour améliorer les chances d'obtenir un paiement dans les temps.

Les informations sur le paiement client (aperçu) utilisent le Machine Learning pour prévoir quand une facture sera payée. Elles utilisent les données de facture, de paiement et de client historiques pour créer un modèle de Machine Learning utilisé pour prédire quand une facture sera payée.

Pour chaque facture en cours, les informations sur le paiement client (aperçu) prédit trois probabilités de paiement :

-  Probabilité du paiement effectué dans les temps (avant la date d'échéance de la facture).
-  Probabilité de paiement effectué au cours des 30 jours précédant la date d'échéance de la facture.
-  Probabilité de paiement effectué au cours des 30 jours suivant la date d'échéance de la facture.

La probabilité des paiements peut être affichée dans la section des prédictions.

[![Prédictions de paiement](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)

Chaque facture reçoit également une probabilité d'obtention de paiement à l'aide de l'un des trois scénarios de probabilités de paiement prédits défini ci-dessus. Le scénario avec la probabilité la plus élevé de paiement est le scénario d'obtention.


Par exemple, prenons une facture la prévision indique une probabilité de 71 % que la facture soit payée dans les délais, une probabilité de 13 % que la facture soit payée au cours des 30 jours précédant la date d'échéance, et une probabilité de 16 % que la facture soit payée au delà des 30 jours précédant la date d'échéance. La probabilité la plus élevée indique que la facture sera dans le scénario de paiement dans les délais, ce qui signifie que la facture sera marquée par la probabilité d'être payée à temps.

[![Prédictions de paiement](./media/payment-predict.png)](./media/payment-predict.png)

## <a name="optimization-strategies"></a>Stratégies d'optimisation

Outre les prévisions de paiement, les informations sur le paiement client (aperçu) peuvent utiliser des stratégies d'optimisation pour améliorer les chances d'obtention du paiement à temps. Cela permet aux organisations d'effectuer des analyses prévisionnelles permettant aux utilisateurs d'ajuster les paramètres de facture et client puis de comparer l'effet correspondant à la probabilité de recevoir le paiement des factures à temps.

Par exemple, une organisation peut souhaiter évaluer l'effet de la mise à jour de l'escompte de règlement sur les factures en fonction de la probabilité de recevoir le paiement dans les délais. Lorsque les factures sont optimisées pour utiliser la nouvelle remise, les utilisateurs peuvent analyser l'effet de l'application de la remise à la probabilité de recevoir des paiements pour ces factures à temps. Si le coût d'application de la remise est minimal une fois comparé à l'avantage de collecter le paiement dans les délais, l'organisation peut choisir d'appliquer la remise sélectionnée à toutes les futures commandes en cours.

> [!NOTE] 
> Actuellement, seule la remise est disponible comme stratégie d'optimisation des analyses de paiement client (aperçu).

[![Prédictions optimisées](./media/optimized-pay.png)](./media/optimized-pay.png)

## <a name="how-to-get-customer-payment-insights-preview"></a>Comment obtenir des informations sur le paiement client (aperçu)

Si vous souhaitez pour tester les informations sur le paiement client (aperçu), envoyez un message e-mail à [l'équipe d'aperçu des informations financières](mailto:fiap@microsoft.com). 

## <a name="privacy-statement"></a>Déclaration de confidentialité

Les aperçus stockent les données client aux États-Unis. En outre, les aperçus (1) peuvent utiliser moins de mesures de confidentialité et de sécurité que le service Dynamics 365 for Finance and Operations, (2) ne sont pas inclus dans le contrat de niveau de service pour ce service, (3) ne doivent pas être utilisés pour traiter des données personnelles ou autres données soumises à des exigences de conformité juridique ou réglementaire, et (4) bénéficient d'un support limité.
