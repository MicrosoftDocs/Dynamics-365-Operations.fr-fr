---
title: Calculer la charge maximale sur les ordres de travail planifiés
description: Cette rubrique explique comment calculer la charge maximale sur les ordres de travail planifiés dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7b7e4a20ed56b1eac29d16d527693d6e455cdc37
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021652"
---
# <a name="calculate-capacity-load-on-scheduled-work-orders"></a>Calculer la charge maximale sur les ordres de travail planifiés

[!include [banner](../../includes/banner.md)]

 

Vous pouvez calculer la charge maximale sur les ordres de travail planifiés pour obtenir une vue d'ensemble de la charge de travail sur les ressources pour une période spécifique. Les calculs peuvent être effectués pour les ressources suivantes : agents de maintenance, groupes de collaborateurs, outils et actifs.

1. Cliquez sur **Gestion des actifs** > **Recherches** > **Planification** > **Charge maximale**.

2. Dans la boîte de dialogue **Calculer la charge maximale** > champ **Afficher**, sélectionnez le type de charge à calculer : **Capacité**, **Réservé** ou **Solde**.

3. Sélectionnez **Oui** sur le bouton bascule **Ignorer lignes nulles** si vous ne souhaitez pas afficher les résultats à zéro.

4. Sélectionnez les types de ressources pour lesquels vous souhaitez calculer la charge maximale en sélectionnant **Oui** sur les boutons bascule appropriés : **Collaborateur**, **Groupe d'agents de maintenance**, **Outil** et **Actif**.

5. Sélectionnez la date de début pour le calcul dans le champ **Date de début**.

6. Dans le champ **Type d'intervalle**, sélectionnez l'intervalle pour le calcul : **Jour**, **Semaine**, **Mois** ou **Trimestre**.

7. Dans le champ **Fréquence**, insérez le nombre d'intervalles que vous souhaitez calculer. Par exemple, si vous avez sélectionné **Jour** comme type d'intervalle, et que vous entrez le chiffre « 5 » dans ce champ, un calcul sur cinq jours à compter de la date de début est effectué.

8. Cliquez sur **OK** pour démarrer le calcul.

L'illustration ci-dessous indique le résultat d'un calcul sur trois semaines pour le type de charge **Réservé**.

![Figure 1](media/08-work-order-scheduling.png)

[!NOTE]
Si vous sélectionnez les types de charge **Capacité** ou **Solde** pour votre calcul, le même résultat sera affiché si aucune réservation n'est effectuée pour les ressources dans la période sélectionnée.

Pour plus d'informations sur le calcul de la charge maximale sur les lignes du programme de maintenance et non sur les ordres de travail planifiés, reportez-vous à [Calculer la charge maximale](../capacity-planning/calculate-capacity-load.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]