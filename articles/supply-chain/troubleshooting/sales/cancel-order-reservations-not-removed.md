---
title: Les réservations ne peuvent pas être supprimées lors de l'annulation d'une commande
description: 'Vous ne pouvez pas annuler une commande client tant que le travail qui y est associé n’est pas annulé et contrepassé. Pour ce faire, suivez les trois étapes ci-après :'
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a8d947e64568246dba5eff3c21fd3920b6494b73
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476347"
---
# <a name="reservations-cannot-be-removed-when-canceling-an-order"></a>Les réservations ne peuvent pas être supprimées lors de l'annulation d'une commande

## <a name="symptoms"></a>Symptômes

Si le travail est associé à une commande client et que vous essayez d'annuler cette commande, vous recevez le message d'erreur suivant :

> Impossible de supprimer les réservations, car un travail qui a été créé repose sur celles-ci.

Vous ne pouvez pas annuler la commande client tant que le travail n’est pas annulé et contrepassé. Cette exigence s’applique même si le travail associé à la commande client est clôturé.

## <a name="resolution"></a>Résolution

Pour régler ce problème, procédez comme suit :

1. Annulez le travail et remettez le stock à l’emplacement souhaité. Accédez au chargement approprié de la commande client et sélectionnez soit **Réduisez la quantité prélevée** sur la ligne de chargement ou **Contrepasser le travail** sur le volet Actions.

    Le travail a maintenant un statut *Annulé*, et un nouveau travail de mouvement de stock est automatiquement créé et traité pour remettre le stock à l’emplacement qui a été décrit au moment de l’annulation.

2. Supprimez le chargement. L’expédition est également supprimée.

3. Vous devriez maintenant pouvoir accéder à la commande client et l’annuler.
