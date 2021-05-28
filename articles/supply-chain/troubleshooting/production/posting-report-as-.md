---
title: Erreur lorsque le journal Déclarer comme terminé est validé
description: Lorsque vous validez le rapport en tant que journal terminé, vous recevez un message d'erreur indiquant que la quantité commandée commandée ne peut pas être réduite.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTableListPage, ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 55db7d0033dd66c1b973abf96671a20ab05d61d8
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026496"
---
# <a name="error-when-the-report-as-finished-journal-is-posted"></a>Erreur lorsque le journal Déclarer comme terminé est validé

Numéro de la base de connaissances : 4612891

## <a name="symptoms"></a>Symptômes

Lorsque vous validez le journal **Signaler comme terminé**, une erreur se produit et vous recevez le message d'erreur suivant :

> Impossible de réduire la quantité commandée car il n'y a pas assez de mouvements de stock en cours dotés du statut Commandé. Les articles sont achetés, reçus ou enregistrés.

Cette erreur se produit uniquement lorsque le champ **Quantité d'erreurs** est défini sur la première ligne du journal **Signaler comme terminé**, et le champ **Bonne quantité** est défini sur la dernière ligne. Si la **Quantité d'erreurs** est définie sur la dernière ligne, aucune erreur ne se produit.

## <a name="resolution"></a>Résolution

Pour éviter cette erreur, ouvrez la page **Paramètres de contrôle de production**, puis dans l'onglet **Général**, définissez l'option **Augmenter la quantité restante avec la quantité d'erreurs** sur *Oui*.
