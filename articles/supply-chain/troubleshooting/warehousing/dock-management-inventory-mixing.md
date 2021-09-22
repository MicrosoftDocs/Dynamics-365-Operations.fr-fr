---
title: Types de stock mixtes lors de l'utilisation du profil de gestion des quais
description: Pour qu'un profil de gestion des quais gère efficacement le mélange des stocks, il convient de mettre en place un saut d’en-tête de travail. Cette page explique comment procéder.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: cc660a2f9839e886240c97a7f60d2e264653074a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476320"
---
# <a name="inventory-types-are-being-mixed-when-using-a-dock-management-profile"></a>Les types de stock sont mélangés lors de l'utilisation d'un profil de gestion des quais

## <a name="symptoms"></a>Symptômes

Vous utilisez des *stratégies de regroupement d’expéditions*. Vous avez mis en place un *profil de gestion des quais* pour un *profil d’emplacement*, mais lorsque le travail est créé, les types de stock sont mélangés à l’emplacement final.

## <a name="resolution"></a>Résolution

Les profils de gestion des quais nécessitent que le travail soit fractionné à l’avance. En d’autres termes, le profil de gestion de quai s’attend à ce qu’un en-tête de travail n’ait pas plusieurs emplacements de placement.

Pour que le profil de gestion des quais gère efficacement le mélange des stocks, un saut d’en-tête de travail doit être mis en place.

Dans cet exemple, notre profil de gestion de quai est configuré de telle sorte que **Types d’inventaire qui ne doivent pas être mélangés** est réglé sur *ID d’expédition*, et nous allons mettre en place un saut d’en-tête de travail pour cela :

1. Allez dans **Gestion des entrepôts \> Configuration \> Travail \> Modèles de travail**.
1. Sélectionnez le **Type d’ordre de travail** à modifier (par exemple, *Commandes fournisseur*).
1. Sélectionnez le modèle de travail à modifier.
1. Dans le volet Actions, sélectionnez **Modifier une requête**.
1. Ouvrez l’onglet **Tri** et ajoutez une ligne avec les paramètres suivants :
    - **Table** - *Transactions de travail temporaire*
    - **Table dérivée** - *Transactions de travail temporaire*
    - **Champ** - *ID expédition*
1. Cliquez sur **OK**.
1. Vous revenez à la page **Modèles de travail**. Dans le volet Actions, sélectionnez **Décompositions de l’en-tête de travail**.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Cochez la case associée au **Nom de champ** *ID d’expédition*.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
