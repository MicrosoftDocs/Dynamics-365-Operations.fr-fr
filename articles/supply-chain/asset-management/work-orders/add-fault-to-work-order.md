---
title: Ajouter une défaillance à un bon de travail
description: Cette rubrique décrit comment ajouter des enregistrements de défaillance aux ordres de travail dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7c86973ca44d9113d14e180e27cc51343da5d2c0
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875656"
---
# <a name="add-fault-to-work-order"></a>Ajouter une défaillance à un bon de travail

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Vous pouvez ajouter le paramétrage des défaillances dans le concepteur de défaillance d'un bon de travail. L'actif sélectionné dans l'ordre de travail doit contenir des types d'actif ayant un ou plusieurs enregistrements de défaillance associés. En savoir plus sur le paramétrage dans la section [Gestion des défaillances](../setup-for-work-orders/fault-management.md).

1. Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Dans la liste, sélectionnez l'ordre de travail dans lequel vous souhaitez effectuer un enregistrement de défaillance et cliquez sur **Défaillance des actifs**.

3. Dans l'organisateur **Symptômes**, cliquez sur **Ajouter une ligne**. Un numéro séquentiel de défaillance est automatiquement inséré dans le champ **Problème**.

4. Sélectionnez le symptôme approprié dans le champ **Symptôme de défaillance**.

5. Sélectionnez **Zone de défaillance** et **Type de défaillance**.

6. Dans le champ **Date de la défaillance**, la date du jour est automatiquement insérée. Si nécessaire, vous pouvez sélectionner une autre date.

7. Dans l'organisateur **Causes du symptôme sélectionné**, ajoutez une ligne décrivant la cause du problème.

8. Dans l'organisateur **Solutions pour le symptôme sélectionné**, ajoutez une ligne décrivant une solution possible pour le problème.

9. Cliquez sur **Enregistrer**.

![Figure 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a>Afficher les défaillances des actifs

Dans la liste **Défaillances des actifs**, vous pouvez obtenir une vue d'ensemble de toutes les défaillances enregistrées sur les actifs.

Cliquez sur **Gestion des actifs** > **Recherches** > **Défaillances des actifs** > **Défaillances des actifs** pour ouvrir la liste.


## <a name="print-asset-fault-report"></a>Imprimer l'état de défaillance de l'actif

Dans la page de liste **Tous les actifs**, vous pouvez imprimer un état de défaillance de l'actif affichant tous les enregistrements de défaillance ainsi qu'une vue d'ensemble graphique des statistiques de défaillance.

1. Cliquez sur **Gestion des actifs** > **Commun** > **Actifs** > **Tous les actifs**.

2. Dans la liste **Actifs**, sélectionnez l'actif pour lequel vous souhaitez imprimer l'état de défaillance.

3. Dans l'onglet **Général** > section **États**, cliquez sur **Défaillance des actifs**.

4. Insérez une période spécifique ou sélectionnez un type de défaillance.

5. Cliquez sur **OK** pour imprimer l'état.

>[!NOTE]
>Vous pouvez également imprimer un état de défaillance pour plusieurs actifs ou types d'actif en cliquant sur **Gestion des actifs** > **États** > **Actifs** > **Défaillance des actifs**.

