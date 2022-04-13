---
title: Supprimer les valeurs hors norme des données de transaction historiques lors du calcul d’une prévision de la demande
description: Cette article décrit la procédure d’exclusion des valeurs hors norme des données historiques utilisées pour calculer une prévision de la demande. En excluant des les valeurs hors normes, vous pouvez améliorer la précision de prévision.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup, ReqDemPlanOutlierQueryPreview
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 99ce8a5bb633cbe8f019299f15650e3ccd5f4314
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469026"
---
# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a>Supprimer les valeurs hors norme des données de transaction historiques lors du calcul d’une prévision de la demande

[!include [banner](../includes/banner.md)]

Cette article décrit la procédure d’exclusion des valeurs hors norme des données historiques utilisées pour calculer une prévision de la demande. En excluant des les valeurs hors normes, vous pouvez améliorer la précision de prévision.

Vous pouvez exclure les valeurs hors normes pour améliorer la précision de prévision. Cette tâche est facultative. Vue d’ensemble du processus :

1.  Cliquez sur **Planification** &gt; **Paramétrage** &gt; **Prévision de la demande** &gt; **Suppression des valeurs hors norme** pour ouvrir la page **Suppression des valeurs hors norme**, dans laquelle vous pouvez utiliser une requête pour sélectionner les transactions à exclure.
2.  Sélectionnez la société à laquelle la requête s’applique, puis entrez un nom et une description. Le champ **Date de la requête** est automatiquement défini sur la date actuelle.
3.  Cochez la case **Actif** pour exclure les transactions trouvées par la requête dans les données historiques. Ce paramètre entrera en effet lorsque vous créerez une prévision de base.
4.  Sur la page **Requête de suppression des valeurs hors norme**, vous pouvez ajouter, supprimer et sélectionner les critères qui définissent les transactions exclues lorsque la prévision de base est calculée. Par exemple, sélectionnez un article ou une transaction de commande spécifique à exclure.
5.  Cliquez sur **Afficher les transactions**. La page **Transactions de valeurs hors norme** répertorie les transactions qui correspondent aux critères que vous avez définis dans la requête et qui seront exclues des données historiques lors du calcul de la prévision de la demande.

**Remarque :** vous pouvez également créer une requête basée sur une requête existante. Sélectionnez la requête à copier, puis cliquez sur **Dupliquer**. Le champ **Date de la requête** identifie la version. Vous pouvez utiliser la requête telle qu’elle est, ou vous pouvez cliquer sur **Modifier la requête** pour modifier les critères. Vous pouvez également, si vous le souhaitez, modifier le nom et la description de la nouvelle requête.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la prévision de la demande](introduction-demand-forecasting.md)

[Contrôler la précision de la prévision](monitor-forecast-accuracy.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]