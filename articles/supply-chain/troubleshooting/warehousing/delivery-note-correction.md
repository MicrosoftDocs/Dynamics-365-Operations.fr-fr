---
title: La correction de la note de livraison ne peut pas être traitée
description: Si vous essayez de corriger une note de livraison après sa validation, vous recevez une erreur. Cette page explique comment corriger les bons de livraison validés pour les articles activés pour la WMS.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bb0d827adff8abd8762bf2de844cad5574628e4b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476362"
---
# <a name="delivery-note-correction-cant-be-processed"></a>La correction de la note de livraison ne peut pas être traitée

## <a name="symptoms"></a>Symptômes

Après avoir publié une note de livraison, vous ne pouvez pas l’annuler, car le bouton **Annuler** n’est pas disponible. Vous ne pouvez pas non plus corriger la note de livraison. Si vous essayez, vous recevez le message d’erreur suivant :

> La correction de la note de livraison ne peut pas être traitée. La note de livraison ne contient que les articles soumis aux processus de gestion d’entrepôt, car ils ne sont pas pris en charge par la correction de la note de livraison.

## <a name="resolution"></a>Résolution

Pour corriger les bons de livraison validés pour les articles qui sont activés pour la gestion des entrepôts avancées (WMS), vous devez effectuer la validation à partir du chargement et non directement à partir de la commande.
