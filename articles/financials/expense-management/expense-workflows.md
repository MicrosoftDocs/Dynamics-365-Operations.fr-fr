---
title: "Définir des workflows pour les dépenses"
description: "Vous pouvez paramétrer un processus de workflow utilisé pour réviser et approuver les documents de déplacement et de dépenses."
author: saraschi2
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi2
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: eb8ff11a03ba18b78595cd04f63b2456aec53bf2
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-workflows-for-expense"></a>Définir des workflows pour les dépenses

[!include[banner](../includes/banner.md)] Vous pouvez paramétrer un processus de workflow utilisé pour réviser et approuver les documents de déplacement et de dépenses. Les documents pour lesquels des workflows peuvent être définis incluent les états de dépenses, les demandes de voyage et les demandes d'avance de disponibilités.

Un workflow représente un processus entreprise. Il définit le transfert d'un document dans le système et indique qui doit traiter une tâche ou approuver un document. L'utilisation du système de workflow dans votre organisation présente plusieurs avantages :

-   **Processus cohérents** — Vous pouvez définir le processus d'approbation pour des documents spécifiques, tels que des demandes d'achat ou des états de dépenses. Le système de workflow permet de s'assurer que les documents sont traités et approuvés de manière cohérente et efficace.

-   Visibilité de processus — Vous pouvez suivre le statut, l'historique et les mesures de performance d'une instance de workflow spécifique. Vous pouvez ainsi déterminer si des modifications doivent être apportées au workflow afin d'en optimiser l'efficacité.

-   Liste de travail centralisée — Les utilisateurs peuvent afficher une liste de travail centralisée pour consulter les tâches et les approbations de workflow qui leur sont affectées. 

**Types de workflows qu'il est possible de créer**

Le tableau suivant répertorie les types de workflows que vous pouvez créer dans le module **Budgétisation**.

| **Type**                           | **Utilisation**                                                 |     
|------------------------------------|----------------------------------------------------------------------|
| **État de dépenses**                 | Créer des workflows d'approbation pour les états de dépenses.                       |      
| **Validation automatique de l'état de dépenses**    | Créer des workflows de validation automatique pour les états de dépenses.              |     
| **Article de ligne de dépense**              | Créer des workflows d'approbation pour les lignes des états de dépenses.         |     
| **Validation automatique des lignes de dépense** | Créer des workflows de validation automatique pour les lignes des états de dépenses.|
| **Demande d'achat de déplacement**             | Créer des workflows d'approbation pour les demandes de voyage.                   |    
| **Demande d'avance de disponibilités**           | Créer des workflows d'approbation pour les demandes d'avance de disponibilités.                 |     
| **Recouvrement fiscal de la TVA**               | Créer des workflows d'approbation pour la récupération de la taxe sur la valeur ajoutée (VAT). |       

