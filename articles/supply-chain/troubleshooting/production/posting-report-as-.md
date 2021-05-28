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
# <a name="error-when-the-report-as-finished-journal-is-posted"></a><span data-ttu-id="8b867-103">Erreur lorsque le journal Déclarer comme terminé est validé</span><span class="sxs-lookup"><span data-stu-id="8b867-103">Error when the Report as finished journal is posted</span></span>

<span data-ttu-id="8b867-104">Numéro de la base de connaissances : 4612891</span><span class="sxs-lookup"><span data-stu-id="8b867-104">KB number: 4612891</span></span>

## <a name="symptoms"></a><span data-ttu-id="8b867-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="8b867-105">Symptoms</span></span>

<span data-ttu-id="8b867-106">Lorsque vous validez le journal **Signaler comme terminé**, une erreur se produit et vous recevez le message d'erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="8b867-106">When you post the **Report as finished** journal, an error occurs, and you receive the following error message:</span></span>

> <span data-ttu-id="8b867-107">Impossible de réduire la quantité commandée car il n'y a pas assez de mouvements de stock en cours dotés du statut Commandé.</span><span class="sxs-lookup"><span data-stu-id="8b867-107">Quantity ordered cannot be reduced because there are not enough open inventory transactions with the ordered status.</span></span> <span data-ttu-id="8b867-108">Les articles sont achetés, reçus ou enregistrés.</span><span class="sxs-lookup"><span data-stu-id="8b867-108">The items are Purchased, Received or Registered.</span></span>

<span data-ttu-id="8b867-109">Cette erreur se produit uniquement lorsque le champ **Quantité d'erreurs** est défini sur la première ligne du journal **Signaler comme terminé**, et le champ **Bonne quantité** est défini sur la dernière ligne.</span><span class="sxs-lookup"><span data-stu-id="8b867-109">This error occurs only when the **Error quantity** field is set on the first line of the **Report as finished** journal, and the **Good quantity** field is set on the last line.</span></span> <span data-ttu-id="8b867-110">Si la **Quantité d'erreurs** est définie sur la dernière ligne, aucune erreur ne se produit.</span><span class="sxs-lookup"><span data-stu-id="8b867-110">If the **Error quantity** field is set on the last line, no error occurs.</span></span>

## <a name="resolution"></a><span data-ttu-id="8b867-111">Résolution</span><span class="sxs-lookup"><span data-stu-id="8b867-111">Resolution</span></span>

<span data-ttu-id="8b867-112">Pour éviter cette erreur, ouvrez la page **Paramètres de contrôle de production**, puis dans l'onglet **Général**, définissez l'option **Augmenter la quantité restante avec la quantité d'erreurs** sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="8b867-112">To prevent this error, open the **Production control parameters** page, and then, on the **General** tab, set the **Increase remain qty with error qty** option to *Yes*.</span></span>
