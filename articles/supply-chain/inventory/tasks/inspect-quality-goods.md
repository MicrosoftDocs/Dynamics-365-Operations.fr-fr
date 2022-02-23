---
title: Inspecter la qualité des marchandises
description: Cette rubrique explique comment traiter un ordre de qualité.
author: perlynne
manager: tfehr
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee5f83b2dad60567341f33a73ce63d01e9da8289
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428149"
---
# <a name="inspect-the-quality-of-goods"></a>Inspecter la qualité des marchandises

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment traiter un ordre de qualité. Vous pouvez exécuter ce guide dans les données de démonstration de la société fictive USMF. Avant de commencer cet procédure d'exemple, vous devez confirmer la commande fournisseur « 000016 » et valider un accusé de réception de marchandises. Cette opération crée automatiquement un ordre de qualité. Les inspections de qualité sont généralement effectuées par un commis au contrôle de la qualité.


## <a name="select-a-quality-order"></a>Sélectionnez un ordre de qualité.
1. Dans le volet de navigation, accédez à **Modules > Gestion des stocks > Tâches périodiques > Gestion de la qualité > Ordres de qualité**.
2. Sélectionnez l'ordre de qualité créé avant d'avoir commencé cette procédure.  

## <a name="record-test-results"></a>Enregistrement des résultats de test
1. Sélectionnez **Résultats**.
2. Sélectionnez **Modifier**.
3. Dans le champ **Quantité du résultat**, entrez un nombre.
4. Dans le champ **Résultat**, sélectionnez l'enregistrement souhaité dans le menu déroulant.  
- Dans cet exemple, le résultat est basé sur les résultats prédéfinis. Normalement vous devez enregistrer un résultat de test plus spécifique, par exemple une taille ou autre dimension.  
5. Sélectionnez **Enregistrer**.
6. Fermez la page.

## <a name="validate-the-quality-order"></a>Contrôler l'ordre de qualité
1. Sélectionnez **Valider**.
2. Dans le champ **Validé par**, sélectionnez l'utilisateur effectuant l'inspection dans le menu déroulant.  
3. Cliquez sur **Sélectionner**.
4. Cliquez sur **OK**.
5. Fermez la page.

