---
title: Inspecter la qualité des marchandises
description: Cette rubrique explique comment traiter des ordres de qualité.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ceb5547b6c1d4c44e53faba0d6e2c1f0368fb95768a2520ecc39066ff73a03d2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755360"
---
# <a name="inspect-the-quality-of-goods"></a>Inspecter la qualité des marchandises

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment traiter des ordres de qualité. Les inspections de qualité sont généralement réalisées par un adjoint au contrôle de la qualité.

Si les données de démonstration standard sont installées, vous pouvez les utiliser pour exécuter les procédures de cette rubrique. Pour utiliser les données de démonstration, vous devez sélectionner l’entité juridique *USMF* avant de commencer. Vous devez ensuite confirmer le bon de commande *000016* et afficher un accusé de réception de marchandises. Un ordre de qualité est généré automatiquement.

## <a name="step-1-select-a-quality-order"></a>Étape 1: Sélectionner un ordre de qualité

Pour sélectionner un ordre de qualité, procédez comme suit :

1. Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Ordres de qualité**.
1. Sélectionnez l’ordre de qualité généré avant d’avoir commencé cette procédure.

## <a name="step-2-record-test-results"></a>Étape 2 : Enregistrer les résultats de test

Pour enregistrer les résultats de test, procédez comme suit :

1. Sélectionnez **Résultats**.
1. Sélectionnez **Modifier**.
1. Dans le champ **Quantité du résultat**, entrez un nombre.
1. Sélectionnez le dossier souhaité dans le champ **Résultat**. Dans cet exemple, le résultat est basé sur un résultat prédéfini. Vous devez normalement enregistrer un résultat de test plus spécifique, par exemple une taille ou autre dimension.
1. Sélectionnez **Enregistrer**.
1. Fermez la page.

## <a name="step-3-validate-the-quality-order"></a>Étape 3 : Contrôler l’ordre de qualité

Pour contrôler l'ordre de qualité, procédez comme suit :

1. Sélectionnez **Valider**.
1. Dans le champ **Validé par**, sélectionnez l'utilisateur qui effectue l'inspection.
1. Cliquez sur **Sélectionner**.
1. Cliquez sur **OK**.
1. Fermez la page.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
