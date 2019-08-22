---
title: Définir des workflows pour les dépenses
description: Vous pouvez paramétrer un processus de workflow utilisé pour réviser et approuver les documents de déplacement et de dépenses.
author: ShylaThompson
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86cadf7277fbb7e08dad4b5dc2a46e1c6ce5a888
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840959"
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

