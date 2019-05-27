---
title: Dépannage de la budgétisation de poste
description: Cet article contient les réponses aux questions que vous vous posez lorsque vous configurez la budgétisation du poste. Elle répond aux questions fréquemment posées sur la création des éléments de coût budgétaire, des groupes de rémunération, et des grilles de rémunération.
author: ryansandness
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmBudgetPurposeType, HcmPositionForecast
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 88253
ms.assetid: c44df01b-8700-4022-b4c6-c4b1cb84d31d
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0800a4a7c92a1a5f4d4f66bb37032eacccc4cb4e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569007"
---
# <a name="position-budgeting-troubleshooting"></a>Dépannage de la budgétisation de poste

[!include [banner](../includes/banner.md)]

Cet article contient les réponses aux questions que vous vous posez lorsque vous configurez la budgétisation du poste. Elle répond aux questions fréquemment posées sur la création des éléments de coût budgétaire, des groupes de rémunération, et des grilles de rémunération. 

<a name="why-cant-i-find-the-forecast-position-page-in-human-resources"></a>Pourquoi est-ce que je ne parviens pas à trouver la page de poste de prévision du module Ressources humaines ?
---------------------------------------------------------------

Les postes de prévision ont été déplacées vers le département Budget.

## <a name="why-cant-i-delete-a-budget-cost-element"></a>Pourquoi est-ce que je ne peux pas supprimer un élément de coût budgétaire ?
Vous ne pouvez pas supprimer un élément de coût budgétaire affecté à un poste de prévision. Avant de supprimer un élément de coût budgétaire, vous devez le supprimer de tous les postes de prévision. **Conseil :** Pour rechercher tous les postes auxquels un élément de coût budgétaire est affecté, sélectionnez l'élément de coût dans la page **Éléments de coût budgétaire**, puis cliquez sur **Mettre à jour des postes**. Les postes utilisant l'élément de coût sont répertoriés dans la grille supérieure.

## <a name="how-can-i-remove-a-cost-element-from-multiple-forecast-positions-without-opening-each-one"></a>Comment est-ce que je peux supprimer un élément de coût de plusieurs postes de prévision sans ouvrir chaque poste ?
Vous ne pouvez pas supprimer un élément de coût. Toutefois, si vous modifiez les dates de début et de fin afin qu'elles se situent en dehors des dates du cycle de planification budgétaire, l'élément de coût ne sera plus affecté aux postes de prévision dans ce cycle de planification budgétaire. Pour effectuer cette modification, ouvrez l'élément de coût budgétaire, puis, dans l'organisateur **Calcul des coûts**, cliquez sur **Modifier les dates**, puis modifiez la date d'effet ou la date d'expiration. Cliquez enfin sur **OK** pour mettre automatiquement à jour tous les postes de prévision auxquels l'élément de coût est affecté. **Conseil :** Si vous utilisez cette méthode, notez qu'elle supprime l'élément de coût budgétaire de **tous** les postes de prévision dans lesquels les dates de début et de fin ne figurent plus dans la plage concernée. Si ce n'est pas ce que vous vouliez faire, vous devez ouvrir chaque poste de prévision duquel vous souhaitez supprimer l'élément de coût budgétaire et apporter manuellement la modification.

## <a name="why-cant-i-enter-an-annual-amount-on-the-cost-calculation-fasttab-for-the-budget-cost-element"></a>Pourquoi est-ce que je ne peux pas entrer un montant annuel sous l'organisateur Calcul des coûts pour l'élément de coût budgétaire ?
Vous ne pouvez pas entrer de montant annuel s'il existe des éléments de coût budgétaire sous l'organisateur **Base de calcul** car le système a besoin d'un pourcentage afin de calculer la valeur. Pour changer la valeur, supprimez tous les éléments de coût budgétaire de l'organisateur **Base de calcul** pour modifier cette valeur.

## <a name="why-cant-i-change-the-budget-cost-type-from-earning-to-another-budget-cost-type"></a>Pourquoi est-ce que je ne peux pas modifier le type de coût budgétaire de bénéfice en un autre type de coût budgétaire ?
Certains éléments de coût budgétaire utilisent l'élément de coût bénéfice comme base de calcul. Pour modifier le champ **Type de coût budgétaire**, supprimez l'élément de coût de bénéfice de l'organisateur **Base de calcul** de tous les éléments de coût de budget.

## <a name="why-cant-i-change-the-date-on-budget-cost-element-lines-for-a-budget-cost-element"></a>Pourquoi est-ce que je ne peux pas modifier la date sur les lignes d'élément de coût budgétaire pour un élément de coût budgétaire ?
Vous ne pouvez pas modifier la ligne d'élément de coût budgétaire lorsqu'un élément de coût budgétaire est utilisé par un poste de prévision. Cette limitation permet de garantir que les postes de prévision respectent toujours les instructions de l'élément de coût budgétaire. Pour modifier la date, dans l'organisateur **Calcul des coûts**, cliquez sur **Changer les dates**, puis entrez les nouvelles dates. Cliquez enfin sur **OK** pour mettre automatiquement à jour les postes auxquels l'élément de coût est affecté.

## <a name="why-cant-i-change-the-costs-for-a-budget-cost-element-on-the-compensation-group-page"></a>Pourquoi est-ce que je ne peux pas modifier les coûts d'un élément de coût budgétaire dans la page Groupe de rémunération ?
Créez et modifiez des éléments de coût budgétaire uniquement dans la page **Éléments de coût budgétaire**.

## <a name="why-do-i-receive-an-error-message-when-i-change-the-dates-for-a-cost-element-on-a-forecast-position"></a>Pourquoi est-ce que j'obtiens un message d'erreur lorsque je modifie les dates d'un élément de coût dans un poste de prévision ?
Les dates de la ligne d'élément de coût du poste de prévision doivent se trouver dans les plages suivantes :

-   Les dates d'activation et de suppression du poste.
-   Les dates d'activation et d'expiration de l'élément de coût budgétaire.
-   Les dates de début et de fin du cycle budgétaire associé au processus de planification budgétaire du poste de prévision.




