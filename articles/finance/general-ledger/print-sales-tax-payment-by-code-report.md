---
title: Imprimer l’état de paiement de taxe de vente par code
description: Cet article fournit des informations sur les paramètres et les actions nécessaires pour imprimer l’état de paiement de taxe de vente par code dans la devise du code comptable ou fiscal.
author: AdamTrukawka
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.search.form: ''
ms.openlocfilehash: ea11826d21b66e6283abf24b3f7b0945e6eb9192
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272366"
---
# <a name="print-the-sales-tax-payment-by-code-report"></a>Imprimer l’état de paiement de taxe de vente par code 

[!include [banner](../includes/banner.md)]

Pour imprimer l’état **Paiement de taxe de vente par code**, accédez à **Taxe** \> **Recherches et états** \> **Déclarations de taxe de vente** \> **Déclaration de taxe de vente par code**. Par défaut, les montants prédéfinis sont générés dans la devise comptable de l’entité juridique pour tous les codes de déclaration configurés sur la page **Codes déclaration de taxe de vente**.

Vous pouvez également générer ce rapport afin qu’il affiche les montants de paiement de la taxe de vente dans les devises des codes de taxe de vente pour tous les codes de déclaration affectés aux codes de taxe de vente sur la page **Codes taxe**.

## <a name="turn-on-the-feature"></a>Activer la fonctionnalité

Dans l’espace de travail **Gestion des fonctionnalités**, activez la fonction suivante : **Générer l’état Déclaration de taxe de vente par code dans la devise du code taxe**.

## <a name="run-the-report"></a>Exécuter le rapport

1. Accédez à **Taxe** \> **Recherches et états** \> **États de taxe de vente** \> **Paiement de taxe de vente par code**.
2. Dans le champ **Devise du rapport**, sélectionnez l’une des valeurs suivantes :

    - **Devise comptable** – Imprimez les montants du rapport dans la devise comptable.
    - **Devise du code taxe de vente** – Imprimer les montants du rapport dans les devises des codes taxe de vente.

    ![Boîte de dialogue Déclaration de taxe de vente par code.](media/Sales-tax-payment-by-code.png)

L’illustration suivante présente un exemple de l’état généré. Le rapport montre que le code de déclaration de taxe **101** a la devise **EUR** si le champ **Devise de la taxe de vente** est défini sur **EUR** pour le code taxe de vente auquel le code de déclaration est affecté.

![Exemple de l’état de déclaration de taxe de vente par code.](media/Sales-tax-payment-by-code-2.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
