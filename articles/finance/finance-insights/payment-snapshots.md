---
title: Présentation des instantanés (version préliminaire)
description: Cette rubrique décrit la fonction d’instantanés, qui vous permet d’enregistrer une prévision de flux de trésorerie pour une analyse ou une comparaison avec les chiffres réels ultérieurement. Lorsque vous générez une prévision de flux de trésorerie, vous pouvez enregistrer cette prévision sous la forme d’un "instantané". Vous pouvez ensuite utiliser ces instantanés pour modifier les comptes inclus dans la prévision, ou comparer la prévision dans l’instantané aux chiffres réels.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 593d6fa8efdecf1b64ef802e6861783d6f85489c
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186588"
---
# <a name="snapshots-overview-preview"></a>Présentation des instantanés (version préliminaire)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Les instantanés permettent aux organisations de modifier et d’enregistrer des informations sur leur position de trésorerie et leurs prévisions de trésorerie à un moment donné. Vous pouvez comparer l’instantané avec les données financières réelles, examiner l’écart et utiliser ces informations pour améliorer les prévisions de flux de trésorerie au fil du temps. Plus spécifiquement, les instantanés peuvent être utilisés comme suit :

- Suivre la position de trésorerie et les prévisions de trésorerie au fil du temps.
- Filtrer les données pour afficher un sous-ensemble d’entités juridiques pour lesquelles l’instantané a été créé.
- Modifier la position de trésorerie et les prévisions de trésorerie générées par le système.
- Effectuer une analyse hypothétique pour prendre en compte les points de vue optimistes, pessimistes et les plus probables du flux de trésorerie.
- Comparer les performances financières réelles avec les prévisions enregistrées dans l’instantané.

Vous pouvez créer un instantané en sélectionnant **Nouvel instantané** soit sur l’onglet **Position de trésorerie** ou l’onglet **Prévisions de trésorerie** sur l’espace de travail **Prévisions de trésorerie**. Après la création d’un instantané, les entrées et sorties qu’il contient peuvent être modifiées et enregistrées. Tous les instantanés enregistrés sont disponibles sur l’onglet **Instantanés**. Pour ouvrir un instantané, sélectionnez son nom.

Les entrées et sorties de trésorerie dans les instantanés peuvent être modifiées à tout moment. Lorsqu’un montant d’entrée ou un montant de sortie est modifié, le montant mis à jour est calculé au prorata des comptes de liquidité qui ont constitué le solde d’origine. Lorsque vous avez terminé de modifier un instantané, cliquez sur **Enregistrer** pour enregistrer vos modifications.

Pour comparer plusieurs instantanés, sélectionnez **Comparer des instantanés**. Vous pouvez comparer deux instantanés à la fois. Sélectionnez les deux instantanés à comparer, puis sélectionnez **OK**. La page **Comparer un instantané** affichera une comparaison des instantanés sélectionnés. Le graphique dans la section supérieure de la page montre une comparaison des entrées de trésorerie, des sorties de trésorerie et des soldes bancaires au cours des périodes qui se chevauchent entre les deux instantanés. La grille de la partie inférieure montre une comparaison détaillée des deux prévisions pour chaque montant de liquidité. La colonne **Écart** de la grille montre la différence entre les soldes d’une période.

Pour comparer les résultats financiers réels avec une prévision enregistrée sous forme d’instantané, sélectionnez **Comparer avec les chiffres réels**. La page **Comparer un instantané** affichera une comparaison des montants réels et des prévisions. Le graphique dans la section supérieure de la page montre une comparaison des entrées de trésorerie, des sorties de trésorerie et des soldes bancaires au cours des périodes qui se chevauchent entre les deux instantanés. La grille de la partie inférieure montre une comparaison détaillée des deux soldes réels par période et le solde prévisionnel pour chaque montant de liquidité. La colonne **Écart** de la grille montre la différence entre le solde réel d’une période et le solde prévisionnel.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
