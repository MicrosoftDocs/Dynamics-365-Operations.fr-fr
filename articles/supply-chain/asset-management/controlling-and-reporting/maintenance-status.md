---
title: Statut de maintenance
description: Cette rubrique explique comment calculer le statut de maintenance dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 516607c056125a16e075c33f3c2ad069efb396d9
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918347"
---
# <a name="maintenance-status"></a>Statut de maintenance

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Dans le module Gestion des actifs, vous pouvez effectuer un calcul pour obtenir une vue d'ensemble des demandes de maintenance et des ordres de travail inédits, actifs et terminés et des activités des temps d'arrêt pour maintenance pour une période donnée. Vous pouvez également voir le nombre des évaluations des conditions terminées pour la même période. Utilisez ce calcul pour obtenir une vue d'ensemble de la charge de travail concernant les demandes de maintenance et les ordres de travail entrants et terminés.

## <a name="make-a-maintenance-status-calculation"></a>Effectuer un calcul du statut de maintenance

1. Cliquez sur **Gestion des actifs** > **Recherches** > **Statut de maintenance**.

2. Dans la boîte de dialogue **Calculer le statut**, sélectionnez la période pendant laquelle vous souhaitez faire le calcul dans les champs **Du** et **Au**.

3. Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes de maintenance en fonction des postes techniques. Par exemple, si vous insérez le chiffre « 1 » dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, toutes les lignes de maintenance pour un poste technique s'affichent dans le niveau supérieur et il est donc possible d'ajouter le statut sur une ligne à partir des postes techniques situés à un niveau inférieur. Par exemple, si vous insérez le chiffre « 0 » dans le champ **Niveau**, un résultat détaillé s'affiche et indique toutes les lignes de maintenance sur tous les niveaux du poste technique auxquels elles sont liées.

4. Cliquez sur **OK** pour démarrer le calcul.

5. Dans les groupes de volet Actions **Grouper par…**, cliquez sur les boutons appropriés à afficher le niveau requis de détail du calcul. Les boutons sélectionnés du volet Actions sont mis en surbrillance. Cliquez sur un bouton pour l'activer ou le désactiver.

6. N'oubliez pas de cliquer sur le bouton **Mettre à jour** pour mettre le calcul à jour chaque fois que vous apportez des modifications en activant ou en désactivant les boutons **Regrouper par…**, ou en choisissant un calcul pour une nouvelle période.

7. Cliquez sur **Statut** si vous souhaitez créer un nouveau calcul de statut de maintenance.

>[!NOTE]
>Les résultats affichés dans **Statut de maintenance** incluent uniquement les demandes de maintenance et les ordres de travail ayant une date et une heure de début réelles. La date de fin peut être vide.

*Exemple 1 :*

Dans le graphique ci-dessous, les boutons **Année** et **Mois** ont été actionnés. Ici, vous obtenez une vue d'ensemble générale sur une base mensuelle de charge de travail et le débit associé aux demandes de maintenance et aux ordres de travail. 

![Figure 1](media/13-controlling-and-reporting.png)

*Exemple 2 :*

Dans la figure ci-dessous, les informations concernant les postes techniques ont été ajoutées. À présent, il est possible de comparer la charge de travail et le débit entre les postes techniques, qui peuvent représenter les emplacements géographiques, les usines ou les espaces de travail. 

![Figure 2](media/14-controlling-and-reporting.png)

