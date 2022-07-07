---
title: Ajoutez une erreur à l’ordre de travail
description: Cet article décrit comment ajouter des enregistrements de défaillance aux ordres de travail dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 210db3259a6c64a508119b30598a34dbda2d2dd2
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9014996"
---
# <a name="add-fault-to-work-order"></a>Ajoutez une erreur à l’ordre de travail

[!include [banner](../../includes/banner.md)]



Vous pouvez ajouter les défaillances configurées dans le concepteur de défaillance d’un ordre de travail. Un ou plusieurs enregistrements de défaillance associés doivent être connectés aux types d’actifs utilisé pour l’actif sélectionné dans l’ordre de travail. Pour plus d’informations sur la configuration, voir [Gestion des défaillances](../setup-for-work-orders/fault-management.md).

1. Sélectionnez **Gestion des actifs** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.

2. Sélectionnez l’ordre de travail sur lequel faire un enregistrement de défaillance, puis, dans le volet Actions, sous l’onglet **Ordre de travail**, dans le groupe **Actif**, sélectionnez **Défaillance des actifs**.

3. Dans l’organisateur **Symptômes**, sélectionnez **Ajouter une ligne**. Un numéro séquentiel de défaillance est automatiquement entré dans le champ **Défaillance**.

4. Dans le champ **Symptôme de défaillance**, sélectionnez le symptôme approprié.

5. Dans les champs **Zone de défaillance** et **Type de défaillance**, sélectionnez les valeurs appropriées.

6. Dans le champ **Date de la défaillance**, la date du jour est automatiquement insérée. Vous pouvez sélectionner une date différente comme vous le souhaitez.

7. Dans l’organisateur **Causes du symptôme sélectionné**, ajoutez une ligne pour décrire la cause du problème.

8. Dans l’organisateur **Solutions pour le symptôme sélectionné**, ajoutez une ligne pour décrire une solution possible pour le problème.

9. Sélectionnez **Enregistrer**.

L’illustration ci-dessous présente un exemple d’enregistrement de défaillance.

![Figure 1.](media/19-work-orders.png)


## <a name="view-asset-faults"></a>Afficher les défaillances des actifs

Dans la liste **Défaillances des actifs**, vous pouvez obtenir une vue d’ensemble de toutes les défaillances enregistrées sur les actifs.

Sur la page de liste **Défaillances des actifs**, vous pouvez obtenir une vue d’ensemble de toutes les défaillances enregistrées sur les actifs. Pour ouvrir la page, sélectionnez **Gestion des actifs** > **Recherches** > **Défaillances des actifs** > **Défaillances des actifs**.


## <a name="print-asset-fault-report"></a>Imprimer l’état de défaillance de l’actif

Dans la page de liste **Tous les actifs**, vous pouvez imprimer un état de défaillance de l’actif qui affiche tous les enregistrements de défaillance ainsi qu’une vue d’ensemble graphique des statistiques de défaillance.

1. Sélectionnez **Gestion des actifs** > **Actifs** > **Tous les actifs**.

2. Sélectionner l’actif pour lequel imprimer un état.

3. Dans le volet Actions, sous l’onglet **Général**, dans le groupe **États**, cliquez sur **Défaillance des actifs**.

4. Entrez une période spécifique ou sélectionnez un type de défaillance.

5. Sélectionnez **OK** pour imprimer l’état.

>[!NOTE]
>Pour imprimer un état de défaillance pour plusieurs actifs ou types d’actifs, sélectionnez **Gestion des actifs** > **États** > **Actifs** > **Défaillance des actifs**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]