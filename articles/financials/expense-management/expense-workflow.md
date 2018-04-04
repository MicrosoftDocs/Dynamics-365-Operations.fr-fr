---
title: "Workflow des dépenses"
description: "Cette rubrique explique comment utiliser le système de flux de travail dans Microsoft Dynamics 365 for Finance and Operations pour configurer un processus de révision des notes de frais dans la Gestion des dépenses."
author: saraschi2
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 6ee607f723659a5b6ecd655ba4fdfca35a4c582d
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="expense-workflow"></a>Workflow des dépenses

[!include[banner](../includes/banner.md)]

Vous pouvez utiliser le système de flux de travail dans Microsoft Dynamics 365 for Finance and Operations pour configurer un processus de révision des notes de frais dans la Gestion des dépenses. Vous pouvez paramétrer un workflow qui utilise les critères suivants pour déterminer qui approuve les états de dépenses :

- La hiérarchie de génération d'états des employés et le plafond autorisé prédéfinis
- Approbation à plusieurs niveaux qui prend en charge les approbateurs intermédiaires et un approbateur final
- Les dimensions financières et la responsabilité du projet
- L'affectation à des utilisateurs ou groupes d'utilisateurs spécifiques

Les approbations de workflow peuvent être créées pour les états de dépenses, les demandes de voyage, les avances de disponibilités et la récupération de la taxe sur la valeur ajoutée (TVA).

**Exemple**

Le processus suivant est un exemple de workflow de gestion des dépenses pour un état de dépenses.

1. Un employé crée et enregistre un état de dépenses.
2. L'employé soumet l'état de dépenses pour approbation. L'approbateur est identifié en fonction des règles qui ont été définies lors du paramétrage du workflow.
3. L'approbateur reçoit une notification lui signalant qu'un état de dépenses est prêt pour approbation. L'approbateur révise l'état de dépenses et vérifie que les conditions suivantes sont remplies :

    - Les dépenses ne violent aucune stratégie des dépenses. Si une dépense viole une stratégie, l'approbateur vérifie que l'état de dépenses comprend une justification commerciale valide.
    - Des reçus électroniques sont joints à l'état de dépenses.

4. L'approbateur approuve l'état de dépenses.
5. L'état de dépenses est affecté au coordinateur de la Comptabilité fournisseur pour validation.
6. L'une des étapes suivantes se produit, selon que la validation automatique est configurée :

    - Si la validation automatique est configurée, l'état de dépenses est traité pour le paiement et le statut de l'état de dépenses est mis à jour.
    - Si la validation automatique n'est pas configurée, le coordinateur de la Comptabilité fournisseur vérifie que toutes les réceptions originales ont été envoyées, et que les réceptions correspondent aux dépenses indiquées dans l'état de dépenses. L'exactitude de tous les codes taxe qui sont entrés dans l'état de dépenses doit également être vérifiée.

Une fois ces conditions vérifiées, l'état de dépenses est validé.

Une fois l'état de dépenses validé, le paiement est autorisé pour l'état de dépenses et l'employé est remboursé.

