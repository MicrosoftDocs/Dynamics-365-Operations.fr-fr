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
ms.openlocfilehash: 50a11aba46519a3a81c313aa1f685d45dcf35f64b50bc921d93968efab13b7b9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750928"
---
# <a name="error-when-the-report-as-finished-journal-is-posted"></a>Erreur lorsque le journal Déclarer comme terminé est validé

Numéro de la base de connaissances : 4612891

## <a name="symptoms"></a>Symptômes

Lorsque vous validez le journal **Signaler comme terminé**, une erreur se produit et vous recevez le message d'erreur suivant :

> Impossible de réduire la quantité commandée car il n'y a pas assez de mouvements de stock en cours dotés du statut Commandé. Les articles sont achetés, reçus ou enregistrés.

Cette erreur se produit uniquement lorsque le champ **Quantité d'erreurs** est défini sur la première ligne du journal **Signaler comme terminé**, et le champ **Bonne quantité** est défini sur la dernière ligne. Si la **Quantité d'erreurs** est définie sur la dernière ligne, aucune erreur ne se produit.

## <a name="resolution"></a>Résolution

Pour éviter cette erreur, ouvrez la page **Paramètres de contrôle de production**, puis dans l'onglet **Général**, définissez l'option **Augmenter la quantité restante avec la quantité d'erreurs** sur *Oui*.
