---
title: Workflows d’approvisionnement
description: Certaines organisations demandent que les demandes d’achat et les commandes fournisseur soient approuvées par un utilisateur autre que celui qui a saisi la transaction. Pour paramétrer un processus d’approbation, vous pouvez créer un workflow.
author: mkirknel
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 22602911fa5d395d439242746f2fe8a27c656bcf
ms.sourcegitcommit: d9bffbeae2ba14f06294dd275383077d4d65c4fa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/01/2020
ms.locfileid: "4654146"
---
# <a name="procurement-and-sourcing-workflows"></a>Workflows d’approvisionnements

[!include [banner](../includes/banner.md)]

Certaines organisations demandent que les demandes d’achat et les commandes fournisseur soient approuvées par un utilisateur autre que celui qui a saisi la transaction. Pour paramétrer un processus d’approbation, vous pouvez créer un workflow.

Un workflow représente un processus entreprise. Il définit le transfert d’un document dans le système et indique qui doit traiter une tâche ou approuver un document. L’utilisation du système de workflow dans votre organisation présente plusieurs avantages :

- **Processus cohérents** — Vous pouvez définir le processus d'approbation pour des documents spécifiques, tels que des demandes d'achat ou des états de dépenses. Le système de workflow permet de s’assurer que les documents sont traités et approuvés de manière cohérente et efficace.
- **Visibilité de processus** — Vous pouvez suivre le statut, l’historique et les mesures de performance d’une instance de workflow spécifique. Vous pouvez ainsi déterminer si des modifications doivent être apportées au workflow afin d’en optimiser l’efficacité.
- **Liste de travail centralisée** — Les utilisateurs peuvent afficher une liste de travail centralisée pour consulter les tâches et les approbations de workflow qui leur sont affectées dans l’ensemble des workflows auxquels ils participent. Cette option est disponible dans la page Éléments de travail.

## <a name="the-types-of-workflows-that-you-can-create"></a>Types de workflows qu’il est possible de créer

Les types de workflows suivants sont disponibles pour le module Approvisionnements.

| Type | Utilisation |
|---|---|
| Révision de la demande d’achat | Permet de créer des workflows de révision et d’approbation pour les demandes d’achat. |
| Analyse de la ligne de demande d’achat | Permet de créer des workflows de révision et d’approbation pour les lignes de demande d’achat. |
| Workflow de commande fournisseur | Permet de créer des workflows de révision et d’approbation pour les commandes fournisseur. |
| Workflow de ligne de commande fournisseur | Permet de créer des workflows de révision et d’approbation pour les lignes de commande fournisseur. |
| Workflow d’application d’ajout de fournisseur | Permet de créer des workflows de révision et d’approbation pour ajouter de nouveaux fournisseurs via les demandes fournisseur. |

> [!IMPORTANT]
> Lorsque vous ajoutez un nouveau workflow, vous pouvez également voir les workflows obsolètes suivants répertoriés dans la boite de dialogue **Créer un workflow**. Ceux-ci sont liés à la fonctionnalité *confirmation de réception* disponible dans [Dynamique AX 2012](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-procurement-and-sourcing-workflows), mais qui est désormais obsolète. Ces workflows ne sont actuellement pas pris en charge.
> 
> - Flux de travail de notification de date d'échéance de livraison
> - Flux de travail de notification de réception de facture
> - Accusé de réception de marchandises - Flux de travail de notification d'échec
> - Flux de travail de notification de rejet de l'accusé de réception de marchandises non confirmé

## <a name="creating-a-workflow"></a>Création d’un workflow

Pour créer un workflow, accédez à Approvisionnements &gt; Paramétrage &gt; Workflows d’approvisionnement, puis créez un workflow en sélectionnant le type de workflow à créer. 

Dans le canevas de workflow, vous pouvez faire glisser des éléments de workflow dans le concepteur et lier les éléments dans un flux. Les éléments de workflow doivent être configurés. Pour les éléments de workflow d’approbation et de tâche, vous pouvez configurer le participant qui doit effectuer l’action.

## <a name="types-of-participants"></a>Types de participants

Vous pouvez affecter une étape d’approbation aux groupes suivants de participants.

| Groupe d’utilisateurs | Description |
|---|---|
| Participant | Permet d’affecter l’étape d’approbation aux membres d’un groupe ou rôle. |
| Hiérarchie | Permet d’affecter l’étape d’approbation aux utilisateurs d’une hiérarchie d’organisation spécifique. |
| Utilisateur du workflow | Permet d’affecter l’étape d’approbation aux utilisateurs de ce workflow. |
| File d’attente | Permet d’affecter l’étape d’approbation à une file d’attente des éléments de travail. |
| Utilisateur | Permet d’affecter l’étape d’approbation à des utilisateurs spécifiques. |

## <a name="additional-resources"></a>Ressources supplémentaires

- [Définition des flux de travail de processus entreprise pour les demandes d’achat (livre blanc)](https://www.microsoft.com/download/details.aspx?id=101821)
- [Workflow de demande d’achat](purchase-requisitions-workflow.md)
- [Intégrer des fournisseurs](vendor-onboarding.md)
