---
title: Importer et tenir à jour les transactions de carte de crédit
description: Cette rubrique décrit la procédure d'importation et de gestion des transactions de carte de crédit liées aux dépenses. Ces transactions peuvent être configurées en vue d'être importées automatiquement dans un calendrier récurrent, ou elles peuvent être importées manuellement en fonction des besoins.
author: KimANelson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvPbsMainDataLines
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 4484ea6fa446c73b8854e7822237bb3c6b9f9023
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840935"
---
# <a name="import-and-maintain-credit-card-transactions"></a>Importer et tenir à jour les transactions de carte de crédit

[!include [banner](../includes/banner.md)]

Les transactions par carte de crédit liées aux dépenses peuvent être configurées de manière à être automatiquement importées selon un calendrier récurrent. Sinon, les transactions peuvent être importées manuellement lorsqu'elles sont requises. Les transactions de carte de crédit sont importées via l'entité de données de transactions de carte de crédit.

Pour plus d'informations sur les entités de données, voir la rubrique [Entités de données](../../dev-itpro/data-entities/data-entities.md).

## <a name="import-credit-card-transactions"></a>Importer les transactions de carte de crédit

1. Sur la page **Transactions de carte de crédit**, sélectionnez **Importer les transactions**. Si vous ouvrez le module Gestion des données pour la première fois, le système doit mettre à jour la liste des entités de données avant de continuer.
2. Dans le champ **Nom**, entrez une description unique de la tâche d'importation.
3. Dans le champ **Format de données source**, sélectionnez le format du fichier contenant les transactions de carte de crédit à importer.
4. Sélectionnez **Charger**, puis recherchez et sélectionnez le fichier à importer.
5. Une fois que le fichier a été téléchargé, validez la mise en correspondance du fichier de transactions de carte de crédit et les colonnes de l'entité de données de transactions de carte de crédit en sélectionnant le lien **Afficher le mappage** sur la vignette. En cas d'erreurs de mise en correspondance, ou si vous devez modifier la mise en correspondance, effectuez les modifications de mise en correspondance à partir de l'onglet **Visualisation de la mise en correspondance** ou de l'onglet **Détails de la mise en correspondance**.
6. Pour automatiser les transactions de carte de crédit, sélectionnez **Créer une tâche de données répétitive**. Vous pouvez alors définir la récurrence qui définit la fréquence à laquelle les transactions de carte de crédit doivent être importées. Lorsque vous avez terminé, sélectionnez **OK**.
7. Pour importer le fichier sélectionné maintenant, sélectionnez **Importer**.
8. Si des erreurs surviennent lors de l'importation, vous pouvez afficher le journal des exécutions ou les données intermédiaires pour voir les erreurs que vous devez corriger pour garantir une importation réussie.

> [!NOTE]
> Si vous devez importer plusieurs formats de fichier, vous devez créer des tâches d'importation distinctes pour chaque type de format.

## <a name="reassign-the-credit-card-transactions-for-terminated-employees"></a>Réaffecter les transactions de carte de crédit pour les employés dont le contrat est terminé

Une fois qu'un enregistrement d'employé est terminé, le compte des services de domaine Active Directory (AD DS) de l'employé est désactivé. Toutefois, il peut y avoir des transactions de carte de crédit actives qui doivent encore faire l'objet d'une dépense et d'un remboursement. Dans la page **Transactions de carte de crédit**, vous pouvez réaffecter à l'employé toute transaction de carte de crédit pour laquelle le contrat de l'employé associé a pris fin.

Sélectionnez une ou plusieurs transactions de carte de crédit, puis sélectionnez **Réaffecter les transactions**. Vous pouvez ensuite sélectionner un autre employé auquel affecter les transactions de carte de crédit. Une fois les transactions de carte de crédit réaffectées, elles peuvent être sélectionnées pour un rapport de dépenses et payées selon le processus habituel de remboursement des dépenses.
