---
title: Calculer la charge maximale sur les ordres de travail planifiés
description: Cet article explique comment calculer la charge maximale sur les ordres de travail planifiés dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 53b147198f6aa9e0254312e5ea48b9ae616a79a9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857951"
---
# <a name="calculate-capacity-load-on-scheduled-work-orders"></a>Calculer la charge maximale sur les ordres de travail planifiés

[!include [banner](../../includes/banner.md)]

 

Vous pouvez calculer la charge maximale sur les ordres de travail planifiés pour obtenir une vue d’ensemble de la charge de travail sur les ressources pour une période spécifique. Les calculs peuvent être effectués pour les ressources suivantes : agents de maintenance, groupes de collaborateurs, outils et actifs.

1. Cliquez sur **Gestion des actifs** > **Recherches** > **Planification** > **Charge maximale**.

2. Dans la boîte de dialogue **Calculer la charge maximale** > champ **Afficher**, sélectionnez le type de charge à calculer : **Capacité**, **Réservé** ou **Solde**.

3. Sélectionnez **Oui** sur le bouton bascule **Ignorer lignes nulles** si vous ne souhaitez pas afficher les résultats à zéro.

4. Sélectionnez les types de ressources pour lesquels vous souhaitez calculer la charge maximale en sélectionnant **Oui** sur les boutons bascule appropriés : **Collaborateur**, **Groupe d’agents de maintenance**, **Outil** et **Actif**.

5. Sélectionnez la date de début pour le calcul dans le champ **Date de début**.

6. Dans le champ **Type d’intervalle**, sélectionnez l’intervalle pour le calcul : **Jour**, **Semaine**, **Mois** ou **Trimestre**.

7. Dans le champ **Fréquence**, insérez le nombre d’intervalles que vous souhaitez calculer. Par exemple, si vous avez sélectionné **Jour** comme type d’intervalle, et que vous entrez le chiffre « 5 » dans ce champ, un calcul sur cinq jours à compter de la date de début est effectué.

8. Cliquez sur **OK** pour démarrer le calcul.

L’illustration ci-dessous indique le résultat d’un calcul sur trois semaines pour le type de charge **Réservé**.

![Figure 1.](media/08-work-order-scheduling.png)

[!NOTE]
Si vous sélectionnez les types de charge **Capacité** ou **Solde** pour votre calcul, le même résultat sera affiché si aucune réservation n’est effectuée pour les ressources dans la période sélectionnée.

Pour plus d’informations sur le calcul de la charge maximale sur les lignes du programme de maintenance et non sur les ordres de travail planifiés, reportez-vous à [Calculer la charge maximale](../capacity-planning/calculate-capacity-load.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]