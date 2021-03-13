---
title: Informations de paiement du client (Aperçu)
description: Cette rubrique décrit la fonctionnalité d’informations de paiement qui vous aident à mieux comprendre les pratiques de paiement typiques d’un client individuel. La fonctionnalité peut vous aider à identifier les circonstances qui justifient de démarrer les processus de collecte plus tôt que vous ne pourriez les démarrer autrement.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/06/2019
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
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: d01f15223b4665caec16d6a4e51a5121a0ed94ea
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5012162"
---
# <a name="customer-payment-insights-preview"></a>Informations de paiement du client (Aperçu)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cette rubrique décrit la fonctionnalité d’informations de paiement qui vous aident à mieux comprendre les pratiques de paiement typiques d’un client individuel. La fonctionnalité peut vous aider à identifier les circonstances qui justifient de démarrer les processus de collecte plus tôt que vous ne pourriez les démarrer autrement. 

## <a name="overview"></a>Vue d’ensemble

Il est difficile de prévoir quand les clients paieront leurs factures. Ce niveau d’informations entraîne des prévisions de flux de trésorerie moins précises, des processus de collecte qui commencent trop tard et des commandes envoyées à des clients avec des défauts de paiement potentiels. Les informations de paiement client (version préliminaire) aident les organisations à prédire quand une facture client sera payée. Ces informations peuvent aider les organisations à créer des stratégies de recouvrement qui améliorent la probabilité d’être payé à temps. 

## <a name="predictions"></a>Prédictions

Les prévisions de paiement permettront aux organisations d’améliorer leurs processus d’entreprise en les aidant à identifier facilement les factures qui sont susceptibles d’être payées en retard, et de prendre des mesures appropriées qui contribuent à améliorer leurs chances d’être payées dans les temps.

Avec un modèle d’apprentissage machine, qui optimise les factures historiques, les paiements et les données des clients, Informations de paiement du client (version préliminaire) prédit avec plus de précision lorsqu’un client paiera une facture en cours.

Pour chaque facture en cours, Informations de paiement du client (version préliminaire) peut prédire trois probabilités de paiement :

-   Probabilité de paiement effectué dans les temps 
-   Probabilité de paiement effectué en retard
-   Probabilité de paiement effectué très en retard

Informations de paiement du client (version préliminaire) offre également une vue cumulée des paiements attendus pouvant aider les organisations à comprendre le montant total du paiement auquel elles peuvent s’attendre d’un client selon une des trois options, Dans les temps, En retard, Très en retard.

[![Vue cumulée des prévisions de paiement](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

En outre, chaque facture se voit attribuer une probabilité de paiement dans les temps. Si la probabilité de paiement dans les temps est inférieure à 50 %, les factures sont marquées avec un cercle rouge pour indiquer que ces factures peuvent exiger une attention particulière en termes de recouvrement. 

[![Liste des probabilités de paiement](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

Informations de paiement du client (version préliminaire) offre également des informations contextuelles pour expliquer les prévisions, comme les facteurs principaux ayant influencé les prévisions, l’état actuel de l’entreprise avec le client et les détails concernant l’historique du comportement de paiement du client. Dans de nombreuses entreprises, le processus de recouvrement est une activité réactive ; le processus de recouvrement ne commence pas tant que les factures ne sont pas échues. 

Avec Informations de paiement du client (version préliminaire), les organisations peuvent être plus proactives en matière de recouvrement. Elles ne doivent plus avoir à attendre que les transactions soient échues pour lancer le processus de recouvrement. Au contraire, elles peuvent utiliser la fonctionnalité de prévision de paiement afin de déterminer si le recouvrement proactif améliorera la probabilité d’être payées dans les temps. La prévision de paiement permet également aux entreprises d’avoir les informations dont elles ont besoin pour justifier le processus de recouvrement anticipé.

## <a name="methodology"></a>Méthodologie

Développer et déployer une solution AI est complexe. Cela nécessite une équipe de scientifiques des données, d’experts en la matière et d’ingénieurs, collaborant pendant un temps donné pour formuler, développer, déployer et mettre à jour une solution AI utilisable. Nous simplifions le déploiement et l’utilisation de solutions AI dans Finance. Nous pré-emballons des solutions AI dans Finance qui sont intégrées dans Microsoft AI Builder. Un utilisateur final, d’un simple clic de bouton, peut déployer la solution AI et commencer à optimiser les avantage des prévisions intelligentes. Si une organisation n’est pas satisfaite de la précision des prévisions, un utilisateur autorisé, à nouveau d’un simple clic, peut saisir l’expérience d’extension AI builder et sélectionner ou désélectionner les champs utilisés pour générer les prévisions. Une fois prêt, il peut essayer et publier les modifications, et le modèle récemment formé sera automatiquement sélectionné pour les prévisions dans Finance.

## <a name="how-to-get-customer-payment-insights-preview"></a>Comment obtenir Informations de paiement du client (version préliminaire)

Envoyer un e-mail à [Informations de paiement du client (version préliminaire)](mailto:fiap@microsoft.com) si vous souhaitez essayer les informations de paiement du client (version préliminaire).

## <a name="privacy-notice"></a>Avis de confidentialité

Les aperçus (1) peuvent utiliser moins de mesures de confidentialité et de sécurité que le service Dynamics 365 Finance and Operations, (2) ne sont pas inclus dans le contrat de niveau de service pour ce service, (3) ne doivent pas être utilisés pour traiter des données personnelles ou autres données soumises à des exigences de conformité juridique ou réglementaire, et (4) bénéficient d’un support limité.


