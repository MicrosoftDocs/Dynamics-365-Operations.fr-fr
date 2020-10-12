---
title: Statut de maintenance
description: Cette rubrique explique comment calculer le statut de maintenance dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetStatusCalculate, EntAssetStatus
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 43389db93032ec29adb805f86ae04a686803176f
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889575"
---
# <a name="maintenance-status"></a>Statut de maintenance

[!include [banner](../../includes/banner.md)]

 

Dans le module Gestion des actifs, vous pouvez effectuer un calcul de vue d'ensemble pendant une période spécifique des demandes de maintenance et des ordres de travail inédits, actifs et terminés, et des activités des temps d'arrêt pour maintenance. Vous pouvez également voir le nombre des évaluations des conditions terminées pour la même période. Utilisez ce calcul pour obtenir une vue d'ensemble de la charge de travail pour les demandes de maintenance et les ordres de travail entrants et terminés.

## <a name="make-a-maintenance-status-calculation"></a>Effectuer un calcul du statut de maintenance

1. Cliquez sur **Gestion des actifs** > **Recherches** > **Statut de maintenance**.

2. Dans la boîte de dialogue **Calculer le statut**, sélectionnez la plage horaire pendant laquelle vous souhaitez faire le calcul dans les champs **Du** et **Au**.

3. Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes de maintenance en fonction des postes techniques. 

  Par exemple, si vous insérez le chiffre « 1 » dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, toutes les lignes de maintenance pour un poste technique s'affichent dans le niveau supérieur et il est donc possible d'ajouter le statut sur une ligne à partir des postes techniques situés à un niveau inférieur. 
  
  Par exemple, si vous insérez le chiffre « 0 » dans le champ **Niveau**, un résultat détaillé s'affiche et indique toutes les lignes de maintenance sur tous les niveaux du poste technique auxquels elles sont liées.

4. Cliquez sur **OK** pour démarrer le calcul.

5. Cliquez sur les boutons **Grouper par** pour afficher le niveau requis de détail du calcul. Les boutons **Grouper par** sélectionnés sont mis en surbrillance. Cliquez sur un bouton pour l'activer ou le désactiver.

6. N'oubliez pas de cliquer sur le bouton **Mettre à jour** pour mettre le calcul à jour chaque fois que vous apportez des modifications en activant ou en désactivant les boutons **Grouper par**, ou en choisissant un calcul pour une nouvelle période.

7. Cliquez sur **Statut** si vous souhaitez créer un nouveau calcul de statut de maintenance.

>[!NOTE]
>Les résultats affichés dans **Statut de maintenance** incluent uniquement les demandes de maintenance et les ordres de travail ayant une date et une heure de début réelles. La date de fin peut être vide.

## <a name="example-1"></a>Exemple 1

Dans la capture d'écran ci-dessous, les boutons **Année** et **Mois** ont été actionnés. Avec ces options **Grouper par** sélectionnées, vous obtenez une vue d'ensemble générale sur une base mensuelle de charge de travail et le débit associé aux demandes de maintenance et aux ordres de travail. 

![Exemple de charge de travail mensuelle](media/13-controlling-and-reporting.png)

## <a name="example-2"></a>Exemple 2

Dans la capture d'écran ci-dessous, les informations concernant les postes techniques ont été ajoutées. À présent il est possible de comparer la charge de travail et le débit entre les postes techniques, qui peuvent représenter les emplacements géographiques, les usines ou les espaces de travail. 

![Exemple de charge de travail mensuelle avec des postes techniques](media/14-controlling-and-reporting.png)

