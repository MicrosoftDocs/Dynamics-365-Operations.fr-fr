---
title: Appliquer automatiquement les acomptes aux factures fournisseur
description: Cette rubrique décrit la possibilité d’appliquer automatiquement des acomptes aux factures fournisseur.
author: sunfzam
ms.date: 10/19/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 5b07c1d4c2189184b2ad29d46ec2aef0ee03c1c0
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7985360"
---
# <a name="automatically-apply-to-vendor-invoices"></a>Appliquer automatiquement aux factures fournisseur

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la possibilité d’appliquer automatiquement des acomptes aux factures fournisseur. Un acompte peut être créé pour une commande fournisseur dans le cadre d’un contrat d’achat. Une fois la facture fournisseur reçue, l’acompte peut être utilisé pour régler la comptabilité fournisseur à partir de la facture fournisseur. La nouvelle fonctionnalité permet au système d’utiliser automatiquement les numéros de commande fournisseur sur une facture fournisseur pour rechercher les acomptes correspondants lorsque la facture fournisseur est importée.

Si des acomptes sont trouvés et peuvent être appliqués, des lignes sont ajoutées aux lignes de facture existantes afin d’appliquer les acomptes. Les lignes d’acompte ne sont jamais prises en compte lors du processus de rapprochement de factures.

Les points suivants décrivent comment les acomptes sont appliqués lorsque différents processus d’achat sont suivis :

- **Une facture fournisseur par commande fournisseur** – L’acompte sur le bon de commande sera appliqué à la facture fournisseur.
- **Une facture fournisseur pour plusieurs commandes fournisseur** – Les acomptes sur toutes les commandes fournisseur seront appliqués à la facture fournisseur.
- **Plusieurs factures fournisseur par commande fournisseur** – L’acompte sur la commande fournisseur sera appliqué à la première facture fournisseur importée. Si le montant de l’acompte dépasse le montant de la facture, l’application de l’acompte échoue et vous devez appliquer manuellement l’acompte.
- **Plusieurs factures fournisseur pour plusieurs commandes fournisseur** – Les acomptes sur les commandes fournisseur seront appliqués à la première facture concernée. Si le montant de l’acompte dépasse le montant de la facture, l’application de l’acompte échoue et vous devez appliquer manuellement les acomptes. S’il reste des acomptes après l’application des acomptes à la première facture, ils peuvent être appliqués aux factures suivantes.

Si le système essaie d’appliquer un acompte mais que l’application échoue, le comportement dépend du paramétrage de l’option **Bloquer le processus d’automatisation du suivi en cas d’échec de l’application d’acompte** :

- **Oui** – Le message d’erreur « Application automatique de l’acompte : Échec » est ajouté dans l’historique d’automatisation, et la facture reste dans la liste des factures fournisseur en attente. La facture restera bloquée jusqu’à ce que vous appliquiez manuellement l’acompte.

    Pour appliquer manuellement les acomptes, accédez à la facture fournisseur en attente. Sur la page **Détails de la facture**, définissez l’option **Inclure dans le traitement automatisé** pour la facture bloquée sur **Non**. Vous pouvez maintenant appliquer manuellement l’acompte. Une fois l’acompte appliqué, redéfinissez l’option **Inclure dans le traitement automatisé** sur **Oui** afin que la facture puisse être traitée automatiquement.

    Vous pouvez également contourner l’application automatique de l’acompte en définissant l’option **Inclure dans le traitement automatisé** sur **Non**, puis la redéfinissant sur **Oui**. Le message suivant s’affichera : « Il existe déjà un acompte pour la commande fournisseur. Voulez-vous l’ignorer pour la facture fournisseur sélectionnée ? » Cliquez sur **Oui**. Le message « L’application de l’acompte a été ignorée manuellement » est ajouté dans l’historique d’automatisation et la facture fournisseur ne sera pas bloquée lorsque le processus automatisé sera à nouveau exécuté.

- **Non** – Les processus d’automatisation du suivi se poursuivront. Vous pouvez toujours appliquer l’acompte lors du règlement.
