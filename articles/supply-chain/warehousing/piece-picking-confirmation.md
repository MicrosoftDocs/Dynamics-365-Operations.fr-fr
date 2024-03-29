---
title: Confirmation de prélèvement de pièces
description: Le prélèvement de pièces vous permet de confirmer chaque pièce du stock via le travail de prélèvement d’inventaire sur un appareil mobile.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a925685b80c635cf036f19748e16d415953ed5fdda7b81498baeade35ccbfcab
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6766000"
---
# <a name="piece-picking-confirmation"></a>Confirmation de prélèvement de pièces

[!include [banner](../includes/banner.md)]

Le prélèvement de pièces vous permet de confirmer chaque pièce du stock via le travail de prélèvement d’inventaire sur un appareil mobile. Pour les prélèvements, vous pouvez confirmer la quantité de travail à traiter jusqu’à la quantité spécifiée dans le travail à prélever. Pour le travail d’inventaire, vous pouvez analyser le stock que vous comptez et suivre la quantité totale.

Lorsque vous activez le prélèvement de pièce, la confirmation de produit est automatiquement activée. Pour les prélèvements de type travail, vous pouvez définir un nombre maximal de pièces. Cela vous permet de définir un maximum dans le nombre de pièces qui doivent être confirmées lors du processus de travail. La quantité maximale est basée sur l’unité de travail actuelle qui est traitée. Le type de travail d’inventaire n’autorise pas un nombre maximum.

Vous pouvez également utiliser la quantité et l’unité de mesure (UOM) associée à un code-barres scanné. Cela fonctionnera pour recevoir des flux entrants, y compris la réception du contenant mixte, l’article de commande fournisseur, l’article d’ordre de transfert et l’élément de chargement. Ces options fonctionnent également pour le prélèvement de pièces où la lecture du code-barres permet d’ajouter la quantité au nombre total de pièces confirmées avec une conversion entre l’UM sur le code-barres et l’unité de travail. Lors du comptage de l’UM sur le code à barres, s’il est confirmé que la quantité est autorisée pour compter le groupe de séquences, la quantité sera ajoutée au nombre total.

## <a name="where-it-applies"></a>Dans ce cas

Les travaux de prélèvement des pièces fonctionnent dans le cadre du travail d’inventaire et du prélèvement d’origine pour les types de travail. Le prélèvement de pièce ne s’applique pas si l’article est contrôlé par des numéros de série ou s’il s’agit d’une production ou d’un prélèvement de kanban à partir d’un emplacement de contenant et que l’article est défini à l’échelonnement.

## <a name="set-up-piece-picking"></a>Définir le prélèvement de pièces

1.  Dans une option de menu de l’appareil mobile, ouvrez l’écran de paramétrage pour la confirmation du travail : Gestion des entrepôts > **Gestion des entrepôts** > **Paramétrage** > **Appareil mobile** > **Options de menu d’appareil mobile**. 
2. Dans l’option de menu de l’appareil mobile, ouvrez Paramétrage de la confirmation du travail.

Les options suivantes sont disponibles pour la sélection lorsque le type de travail est prélèvement ou comptage.


|           Option           |                                                                            Description                                                                            |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Confirmation de prélèvement de pièces | Disponible pour les types de travail de prélèvement et d’inventaire. La confirmation de produit est automatiquement activée. Permet de confirmer chaque pièce du stock de l’appareil mobile. |
|  Nombre maximal de pièces  |                   Disponible pour le travail de prélèvement si la confirmation de prélèvement de pièce est activée. Fixe une limite au nombre de pièces que vous devez confirmer.                   |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]