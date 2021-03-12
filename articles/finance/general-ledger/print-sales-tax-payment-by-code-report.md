---
title: Imprimer l’état de déclaration de taxe par code
description: Cette rubrique fournit des informations sur les paramètres et les actions nécessaires pour imprimer l’état de déclaration de taxe par code dans la devise du code comptable ou fiscal.
author: anasyash
manager: AnnBe
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: dd490663e66d1eda0eb0ea052e5b54fb867f81df
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990291"
---
# <a name="print-the-sales-tax-payment-by-code-report"></a>Imprimer l’état de déclaration de taxe par code 

[!include [banner](../includes/banner.md)]

Pour imprimer l’état **Déclaration de taxe par code**, accédez à **Taxe** \> **Recherches et états** \> **Déclarations de taxe** \> **Déclaration de taxe par code**. Par défaut, les montants prédéfinis sont générés dans la devise comptable de l’entité juridique pour tous les codes de déclaration configurés sur la page **Codes déclaration de taxe**.

Vous pouvez également générer ce rapport afin qu’il affiche les montants de paiement de la taxe de vente dans les devises des codes de taxe de vente pour tous les codes de déclaration affectés aux codes de taxe de vente sur la page **Codes taxe**.

## <a name="turn-on-the-feature"></a>Activer la fonctionnalité

Dans l’espace de travail **Gestion des fonctionnalités**, activez la fonction suivante : **Générer l’état Déclaration de taxe par code dans la devise du code taxe**.

## <a name="run-the-report"></a>Exécuter le rapport

1. Accédez à **Taxe** \> **Recherches et états** \> **États de taxe** \> **Paiement de taxe par code**.
2. Dans le champ **Devise du rapport**, sélectionnez l’une des valeurs suivantes :

    - **Devise comptable** - Imprimez les montants du rapport dans la devise comptable.
    - **Devise du code taxe** - Imprimer les montants du rapport dans les devises des codes taxe.

    ![Boîte de dialogue Déclaration de taxe par code](media/Sales-tax-payment-by-code.png)

L’illustration suivante présente un exemple de l’état généré. Le rapport montre que le code de déclaration de taxe **101** a la devise **EUR** si le champ **Devise de la taxe** est défini sur **EUR** pour le code taxe auquel le code de déclaration est affecté.

![Exemple de l’état de déclaration de taxe par code](media/Sales-tax-payment-by-code-2.png)
