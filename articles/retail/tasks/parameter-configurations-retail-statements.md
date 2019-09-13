---
title: Configurer les paramètres des ventes au détail qui affectent les relevés de la vente au détail
description: Cette rubrique illustre les configurations de paramètres des ventes au détail qui affectent la manière dont les relevés de vente au détail sont créés et validés.
author: josaw1
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b9a0386a4d61395903e82d988244dd131c1febaf
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867269"
---
# <a name="configure-retail-parameters-that-affect-retail-statements"></a>Configurer les paramètres des ventes au détail qui affectent les relevés de la vente au détail

[!include[task guide banner](../includes/task-guide-banner.md)]

Cette rubrique illustre les configurations de paramètres des ventes au détail qui affectent la manière dont les relevés de vente au détail sont créés et validés. La société fictive USRT sert d'exemple dans cette procédure.

1. Dans le volet de navigation, accédez à **Modules > Commerce et vente au détail > Configuration du siège > Paramètres > Paramètres des ventes au détail**.
2. Sélectionnez l'onglet **Validation**.
    - Sélectionnez **Oui** si vous souhaitez valider les montants de remise exceptionnelle spécifiquement.  
    - Sélectionnez **Standard** pour utiliser des comptes par défaut, ou sélectionnez **Périodique** si vous souhaitez définir le compte à utiliser pour chaque remise exceptionnelle.  
      - Sélectionnez **Récapitulatif** si les lignes de stock doivent être agrégées dès lors que cela est possible.  
      - Sélectionnez **Oui** si les factures et les paiements doivent être automatiquement réglées dans le cadre du processus de validation de relevé.  
      - Sélectionnez **Oui** si les transactions de mise en coffre-fort doivent être agrégées.  
      - Sélectionnez **Oui** si les transactions de remise en banque doivent être agrégées.  
      - Sélectionnez **Oui** pour activer l'agrégation pour la validation de relevé.  
      - Sélectionnez **Oui** pour créer et traiter les commandes en parallèle lorsque les relevés sont validés.  
      - Spécifiez le nombre maximum de commandes à traiter dans chaque tâche de traitement par lots.  
3. Sélectionnez **Enregistrer**.

