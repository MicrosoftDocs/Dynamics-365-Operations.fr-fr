---
title: Vous ne pouvez pas supprimer la dimension de prévision de la demande d'entrepôt des lignes de prévision
description: Vous ne pouvez pas supprimer la dimension de prévision de la demande d'entrepôt des lignes de prévision.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6b643c4fe51ae6ce73b34ab81d4e458dcd5032df
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026510"
---
# <a name="you-cant-remove-the-warehouse-demand-forecast-dimension-from-forecast-lines"></a>Vous ne pouvez pas supprimer la dimension de prévision de la demande d'entrepôt des lignes de prévision

Numéro de la base de connaissances : 4614408

## <a name="symptoms"></a>Symptômes

Ce problème se produit lorsque la dimension **Entrepôt** n'est pas attribuée sur l'onglet **Dimensions de prévision** de la page **Paramètre de prévision de la demande**. Néanmoins, la colonne **Entrepôt** est affichée sur la page **Prévision de la demande** (**Planification générale \> Prévision \> Entité de prévision manuelle \> Lignes de prévision de la demande**).

## <a name="resolution"></a>Résolution

Les paramètres sur l'onglet **Dimensions de prévision** de la page **Paramètre de prévision de la demande** n'affecte pas la page **Prévision de la demande**. Ils contrôlent la prévision de base qui est générée et affichée dans la prévision de demande ajustée. Cependant, ils ne contrôlent pas les dimensions requises pour la prévision de la demande "réelle". En autorisant les enregistrements affichés sur la page **Prévision de la demande ajustée**, vous pouvez les convertir en entrées de prévision "réelles" pour un modèle de prévision. Ce modèle peut ensuite être utilisé pour la planification générale.

Sur la page **Prévision de la demande**, les dimensions de la prévision "réelle" qui sont affichées sur les lignes de prévision de la demande font partie des dimensions du stock. (Ce comportement ressemble au comportement des lignes de commande client.) Si votre système n'est pas configuré pour utiliser **Entrepôt** en tant que dimension de stock obligatoire, vous pouvez personnaliser la page pour masquer la colonne.
