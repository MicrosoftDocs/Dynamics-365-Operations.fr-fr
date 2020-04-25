---
title: Confirmation de produit pour la sélection du groupement
description: Cette rubrique décrit comment vous paramétrez la vérification d'article avec la sélection du groupement.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e6493afb64acb4d7644aac8dad71a0917c76549
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205780"
---
[!include [banner](../includes/banner.md)]

# <a name="product-confirmation-for-cluster-picking"></a>Confirmation de produit pour la sélection du groupement
La sélection du groupement vous permet de regrouper des articles pour plusieurs commandes simultanément. Lorsque la sélection du groupement est appliqué, la confirmation d'article est cruciale pour vérifier les articles qui sont ajoutés aux clusters. Vous pouvez vérifier les articles de la sélection du groupement lors du processus de sélection du groupement.

## <a name="where-it-applies"></a>Dans ce cas
La vérification d'article pour la sélection du groupement fonctionne de la même manière que pour la vérification des articles dans les processus de non sélection du groupement. Le paramétrage est basé sur le paramétrage de code-barres de produit.

## <a name="set-up-item-verification-with-cluster-picking"></a>Paramétrage de la vérification d'article avec la sélection du groupement
1.  Dans une option de menu de l'appareil mobile, ouvrez l'écran de paramétrage pour la confirmation du travail : **Gestion des entrepôts** > **Gestion des entrepôts** > **Paramétrage** > **Appareil mobile** > **Options de menu d'appareil mobile**.
2.  Dans l'option de menu de l'appareil mobile, ouvrez **Paramétrage de la confirmation du travail**.

|        Option        |                                    Description                                    |
|----------------------|-----------------------------------------------------------------------------------|
| Confirmation du produit | Permet de confirmer chaque pièce du stock de l'appareil mobile lors de la lecture. |

