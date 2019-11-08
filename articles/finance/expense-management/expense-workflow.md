---
title: Workflow des dépenses
description: Cette rubrique explique comment utiliser le système de flux de travail dans Microsoft Dynamics 365 Finance pour configurer un processus de révision des notes de frais dans la Gestion des dépenses.
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
ms.openlocfilehash: c52915860709e38013ec06204c52bb06de417eb1
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187588"
---
# <a name="expense-workflow"></a>Workflow des dépenses

[!include [banner](../includes/banner.md)]

Vous pouvez utiliser le système de workflow pour paramétrer un processus de révision pour les états de dépenses dans Gestion des dépenses. Vous pouvez paramétrer un workflow qui utilise les critères suivants pour déterminer qui approuve les états de dépenses :

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