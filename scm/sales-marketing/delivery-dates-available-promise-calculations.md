---
title: Promesse de commande
description: "Cet article fournit des informations sur les promesses de commande. Les promesses de commandes vous permettent de promettre de manière fiable des dates de livraison à vos clients et vous offre une certaine flexibilité pour pouvoir respecter ces dates."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SalesATP, SalesAvailableDlvDates
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 193933
ms.assetid: 676fc53a-fa25-4688-9f26-1005316763b8
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 8aa0a58b03ee18e42ca7770ea3e22311c1ddba67
ms.lasthandoff: 03/31/2017


---

# <a name="order-promising"></a>Promesse de commande

Cet article fournit des informations sur les promesses de commande. Les promesses de commandes vous permettent de promettre de manière fiable des dates de livraison à vos clients et vous offre une certaine flexibilité pour pouvoir respecter ces dates.

La promesse de commande calcule les premières dates d'expédition et de réception, et est basée sur la méthode de contrôle de la date de livraison et les jours de transport. Vous pouvez sélectionner parmi quatre méthodes de contrôle de la date de livraison :

-   ** Délai de vente ** – Le délai de vente est l'intervalle entre la création de la commande client et l'expédition d'articles. Le calcul de la date de livraison est basé sur un nombre de jours par défaut, et ne tient pas compte de la disponibilité en actions, la demande connue, ou l'approvisionnement prévisionnel.
-   ** À la vente (DAV) ** – Le DAV est la quantité d'un article disponible et peut être promis à un client une date spécifique. Le calcul de DAV inclut le stock non engagé, les délais, les réceptions et les sorties prévues.
-   **DAV + Marge de sortie **– La date d'expédition correspond à la date DAV plus la marge de sortie de l'article. La marge de sortie est le temps nécessaire pour préparer les articles pour l'expédition.
-   **CTP (capable-to-promise) **– La disponibilité est calculée par le biais de l'éclatement.

## <a name="atp-calculations"></a>Calculs DAV
La quantité disponible à la vente est calculée en utilisant « DAV cumulé avec de la méthode de lecture anticipée ». L'avantage principal de ce mode de calcul DAV est qu'il peut traiter les cas où la somme de problèmes entre les réceptions est supérieur à la dernière réception (par exemple, lorsqu'une quantité d'une réception antérieure doit être utilisée pour répondre à une exigence). « Le DAV cumulé avec le mode de calcul de lecture anticipée » inclut tous les problèmes jusqu'à ce que la quantité de cumul à recevoir dépasse la quantité cumulée pour publier. Par conséquent, la méthode de calcul DAV évalue si une partie de la quantité d'une période antérieure peut être utilisée pour une période ultérieure.  

La quantité DAV est le solde non engagé de stock de la première période. Généralement, elle est calculée pour chaque période pour laquelle une réception est prévue. Le programme calcule la période DAV en jours et la date actuelle comme la première date pour la quantité disponible à la vente. Au cours de cette première période, la quantité disponible à la vente inclut le stock disponible moins les commandes client qui sont dues et en retard.  

DAC est calculé à l'aide des formules suivantes :  

DAV = DAV pour la période précédente + les réceptions pour la période actuelle – Affiche pour la période actuelle – quantité nette de sortie pour chaque future période jusqu'à la période où la somme des réceptions pour toutes les périodes futures, jusqu'à la future période, dépasse la somme des sorties jusqu'à la future période.  

Lorsqu'il n'y a plus de sorties ou de réceptions à examiner, la quantité disponible à la vente pour les dates suivantes est la même que la dernière quantité disponible à la vente calculée.  

Si toutes les dimensions utilisées pour un article ne sont pas données lorsque la vérification DAV est terminée, elles peuvent toujours être spécifiées sur les sorties et les réceptions. Dans ce cas, dans le calcul de la quantité disponible à la vente, les réceptions et les sorties doivent être regroupées dans les dimensions existantes, afin de réduire le nombre de lignes de réception et de sortie utilisées dans le calcul de la quantité disponible à la vente.  

La quantité DAV indiquée est toujours supérieure ou égale à 0 (zéro). Si le calcul renvoie une quantité disponible à la vente négative (par exemple, si la quantité qui a été précédemment promise est supérieure à la quantité disponible), le programme définit automatiquement la quantité à **0**.

### <a name="example"></a>Exemple

Le champ **Plage de gestion de demande en arrière DAV** contrôle jusqu'où dans le temps la recherche doit remonter pour les commandes de demandes ou les sorties de stock retardées. Le champ **Plage de gestion d'approvisionnement en arrière DAV** contrôle jusqu'où dans le temps la recherche doit remonter pour les commandes d'approvisionnement ou les réceptions de stock retardées. Par exemple, si des commandes qui sont retardées de seulement sept jours doivent être prises en compte dans le calcul DAV, les deux champs doivent être définis à **7**.  

Les champs **DAV a retardé le temps de compensation de la demande** et **DAV a retardé le temps de compensation d'approvisionnement** lorsque la demande ou l'approvisionnement retardé seront pris en compte dans le calcul DAV. Par exemple, si l'offre et la demande retardées doivent être prises en compte dans le calcul DAV après-demain, les deux champs doivent être définis sur **2**. Une valeur de **2** signifie que la quantité d'un article sur une commande fournisseur retardée qui doit être prise en compte dans le calcul DAV sera vue comme disponible deux jours après la date actuelle.  

Pour l'exemple suivant, la valeur **7** est entrée dans les champs **Plage de gestion de demande en arrière DAV** et **Plage de gestion d'approvisionnement en arrière DAV**, et la valeur **1** est entrée dans les champs **DAV a retardé le temps de compensation de la demande** et **DAV a retardé le temps de compensation d'approvisionnement**.  

Une commande fournisseur pour 200 pièces d'un produit qui aurait dû avoir été reçue il y a trois jours n'est pas encore arrivée. Par conséquent, une ligne de commande client pour 75 pièces du même produit qui aurait dû avoir été expédiée la veille n'a pas été expédiée.  

Un client appelle et souhaite commander 150 pièces du même produit. Lorsque vous vérifiez la disponibilité du produit, vous constatez qu'une autre commande fournisseur pour 100 pièces du produit sera livrée 10 jours plus tard.  

Vous créez une ligne de commande client pour le produit et entrez la valeur **150** pour la quantité.  

Étant donné que le contrôle de la date de livraison est DAV, les données DAV sont calculées de sorte à rechercher la date d'expédition la plus proche possible. En fonction de les paramètres, la commande fournisseur retardée et la commande client sont considérés, et la quantité résultant de la vente pour la date actuelle est 0. Demain, lorsque la commande fournisseur retardée doit être reçu, la quantité disponible est calculée comme plus de 0 (dans ce cas, elle est calculé comme 125). Toutefois, 10 jours entre la mise à jour, où la commande fournisseur supplémentaire pour 100 pièces est reçue, la quantité disponible est supérieure à 150.  

Par conséquent, la date d'expédition est de 10 jours entre la mise à jour, selon le calcul DAV. Vous devez donc informer le client que la quantité demandée peut être livrée dans 10 jours.


