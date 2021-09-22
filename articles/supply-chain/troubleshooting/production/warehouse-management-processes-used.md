---
title: Les processus de gestion des entrepôts sont actuellement utilisés
description: Lors de la réservation ou de la libération du travail, vous pouvez recevoir un message indiquant que les processus de gestion des entrepôts sont actuellement utilisés. Résolvez le problème avec l’une de ces étapes.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bfda2fae824cdc64d722310d20cf16e6306d766c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476288"
---
# <a name="cant-reserve-or-release-work-because-processes-are-currently-being-used"></a>Impossible de réserver ou de libérer le travail, car les processus sont actuellement utilisés

## <a name="symptoms"></a>Symptômes

Lorsque vous travaillez avec la fabrication discrète, vous recevez l’erreur suivante :

> Les processus de gestion des entrepôts sont actuellement utilisés. Si les lignes de travail ne sont pas encore enregistrées, vous pouvez annuler le travail créé et toutes les lignes de chargement ou d’expédition, puis poursuivre le processus de retrait ou d’expédition.

## <a name="cause"></a>Cause

Ce problème se produit si vous essayez de réserver ou de libérer du travail pour une ligne, mais que la transaction de stock a un statut de *Retiré*, ce qui indique que le matériel a été retiré.

## <a name="resolution"></a>Résolution

Pour régler ce problème, exécutez l’une des étapes ci-dessous.

- Redéfinissez le statut de l’ordre de fabrication sur *Estimé* ou *Libéré*.
- Ouvrez la page de détails de la l’ordre de fabrication concerné. Dans le volet Actions, sur l’onglet **Entrepôt**, dans le groupe **Arrêt**, sélectionnez **Arrêter et annuler le retrait** pour annuler el retrait de toutes les transactions retirées. Puis sélectionnez **Supprimer l’arrêt** pour traiter l’ordre de fabrication.

Voici une explication des fonctions *Annuler le retrait* et *Arrêter* :
  
- **Annuler le retrait** – Cette fonction inverse le statut des mouvements de stock pour les lignes de nomenclature (BOM) et les lignes de formule qui ont un statut de *Retiré* par le biais de *En commande*. Lorsque le travail de prélèvement des matières premières est terminé, le statut des lignes est défini sur *Retiré*. Ce statut empêche la remise à zéro de l’ordre de fabrication sur le statut *Créé*. Dans ce cas, vous pouvez utiliser la fonction *Annuler le retrait* pour annuler les transactions du statut *Retiré*, puis réinitialisez l’ordre de fabrication sur le statut *Créé*.
- **Arrêter** – Cette fonction définit un indicateur **Arrêté** sur l’ordre de fabrication pour empêcher toute mise à jour du statut de la commande. Vous pouvez trouver l’indicateur **Arrêté** sur le raccourci **Entrepôt** de la page de détails de l’ordre de fabrication.

> [!NOTE]
>
> - Les boutons ne sont visibles que lorsque l’ordre de fabrication est créé pour les articles activés pour les processus d’entrepôt.
> - Le groupe **Arrêter** est visible uniquement sur l’onglet **Entrepôt** du volet Actions de la page des détails de l’ordre de fabrication. Ce n’est pas visible sur le raccourci **Entrepôt** de la page de liste **Ordres de fabrication**.
