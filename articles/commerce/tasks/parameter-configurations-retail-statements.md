---
title: Configurer les paramètres qui affectent les relevés de vente au détail
description: Cette rubrique illustre les configurations de paramètres pour Commerce qui affectent la création et la validation des relevés de vente au détail.
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
ms.openlocfilehash: d8cae6d2fa7c469f50fa92141a6cb5a0af1df4b0
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022507"
---
# <a name="configure-parameters-that-affect-retail-statements"></a>Configurer les paramètres qui affectent les relevés de vente au détail

[!include[task guide banner](../includes/task-guide-banner.md)]

Cette rubrique illustre les configurations de paramètres pour Commerce qui affectent la création et la validation des relevés de vente au détail. La société fictive USRT sert d'exemple dans cette procédure.

1. Dans le volet de navigation, accédez à **Modules > Retail et Commerce > Configuration du siège > Paramètres > Paramètres de commerce**.
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

