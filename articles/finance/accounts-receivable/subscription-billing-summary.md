---
title: Présentation de la facturation de l’abonnement
description: Cette rubrique décrit la facturation de l’abonnement dans Microsoft Dynamics 365 Finance.
author: JodiChristiansen
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-02-09
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: b94ac36e49d55ad42909877d77903cd40cb22cbe
ms.sourcegitcommit: 6102f70d4595d01b90afe5b23dfd8ec2ea030653
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8182684"
---
# <a name="subscription-billing-overview"></a>Présentation de la facturation de l’abonnement

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

La facturation des abonnements permet aux organisations de gérer les opportunités de revenus d’abonnement et la facturation récurrente via des calendriers de facturation. Les modèles de tarification et de facturation complexes et la répartition des revenus sont facilement gérés et sont facturés et reconnus au niveau de la ligne. L’allocation des revenus multi-éléments permet d’allouer les revenus conformément aux normes comptables internationales (norme internationale d’information financière 15 \[IFRS 15\]) et les principes comptables généralement reconnus (US GAAP) (Accounting Standards Codification Topic 606 \[ASC 606\]).

La solution comporte trois modules qui peuvent être utilisés indépendamment. Alternativement, les trois modules peuvent être utilisés ensemble.

- **Facturation contractuelle récurrente** – Ce module permet la facturation récurrente et la gestion des prix afin de contrôler les paramètres de tarification et de facturation, le renouvellement des contrats et la facturation consolidée.
- **Reports de revenus et de dépenses** – Ce module élimine les processus manuels et la dépendance vis-à-vis des systèmes externes en gérant les revenus et en permettant un aperçu en temps réel des revenus récurrents mensuels.
- **Répartition des revenus multi-éléments** – Ce module aide à la conformité des revenus en gérant la tarification et la répartition des revenus sur plusieurs éléments.

La facturation de l’abonnement est activée via **Gestion des fonctionnalités**. Cependant, il ne peut pas être utilisé avec la fonctionnalité **Prise en compte des revenus**. Par conséquent, vous devez désactiver cette fonctionnalité avant d’activer la facturation de l’abonnement.

1. Dans l’espace de travail **Gestion des fonctionnalités**, sous l’onglet **Tous**, entrez **Prise en compte des revenus** dans le filtre, puis sélectionnez le nom de la fonction comme filtre.
2. Sélectionnez la fonctionnalité **Prise en compte des revenus**, puis cliquez sur le bouton **Désactiver**.
3. Dans le filtre **Nom de la fonctionnalité**, entrez **Facturation de l’abonnement**, puis sélectionnez le filtre de module.
4. Sélectionnez la fonctionnalité **Facturation de l’abonnement**, puis sélectionnez **Activer**.
5. Sélectionnez l’un des trois modules de la liste précédente, puis sélectionnez **Activer**. Répétez cette étape pour chacun des deux autres modules.

    > [!IMPORTANT]
    > La fonctionnalité **Facturation de l’abonnement** doit être activée avant de pouvoir activer l’un des trois modules.
