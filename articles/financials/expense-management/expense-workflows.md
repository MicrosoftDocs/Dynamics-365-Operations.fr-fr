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
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: cf35406b43c1ec40a7c248b970559b65fcd8a6c6
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="set-up-workflows-for-expense"></a>Définir des workflows pour les dépenses

[!include [banner](../includes/banner.md)]

 Vous pouvez paramétrer un processus de workflow utilisé pour réviser et approuver les documents de déplacement et de dépenses. Les documents pour lesquels des workflows peuvent être définis incluent les états de dépenses, les demandes de voyage et les demandes d'avance de disponibilités.

Un workflow représente un processus entreprise. Il définit le transfert d'un document dans le système et indique qui doit traiter une tâche ou approuver un document. L'utilisation du système de workflow dans votre organisation présente plusieurs avantages :

-   **Processus cohérents** — Vous pouvez définir le processus d'approbation pour des documents spécifiques, tels que des demandes d'achat ou des états de dépenses. Le système de workflow permet de s'assurer que les documents sont traités et approuvés de manière cohérente et efficace.

-   Visibilité de processus — Vous pouvez suivre le statut, l'historique et les mesures de performance d'une instance de workflow spécifique. Vous pouvez ainsi déterminer si des modifications doivent être apportées au workflow afin d'en optimiser l'efficacité.

-   Liste de travail centralisée — Les utilisateurs peuvent afficher une liste de travail centralisée pour consulter les tâches et les approbations de workflow qui leur sont affectées. 

**Types de workflows qu'il est possible de créer**

Le tableau suivant répertorie les types de workflows que vous pouvez créer dans le module **Budgétisation**.


|              <strong>Type</strong>              |                   <strong>Utilisation</strong>                   |
|-------------------------------------------------|-----------------------------------------------------------------------|
|         <strong>État de dépenses</strong>         |            Créer des workflows d'approbation pour les états de dépenses.             |
|  <strong>Validation automatique de l'état de dépenses</strong>   |        Créer des workflows de validation automatique pour les états de dépenses.        |
|       <strong>Article de ligne de dépense</strong>        |     Créer des workflows d'approbation pour les lignes des états de dépenses.      |
| <strong>Validation automatique des lignes de dépense</strong> | Créer des workflows de validation automatique pour les lignes des états de dépenses. |
|       <strong>Demande d'achat de déplacement</strong>       |          Créer des workflows d'approbation pour les demandes de voyage.           |
|      <strong>Demande d'avance de disponibilités</strong>      |         Créer des workflows d'approbation pour les demandes d'avance de disponibilités.          |
|        <strong>Recouvrement fiscal de la TVA</strong>        | Créer des workflows d'approbation pour la récupération de la taxe sur la valeur ajoutée (VAT).  |


