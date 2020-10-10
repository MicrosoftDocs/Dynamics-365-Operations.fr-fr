---
title: Contrôle de temps de travail
description: Cette rubrique explique le contrôle de temps de travail dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetHourControl
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0d2f4e86b5dec84d4a24db6a4f9f9f16f6a765bd
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889192"
---
# <a name="work-hour-control"></a>Contrôle de temps de travail

[!include [banner](../../includes/banner.md)]

 

Dans le module Gestion des actifs, vous pouvez calculer des heures pour obtenir une vue d'ensemble des heures réelles comparées aux heures budgétaires des actifs, des postes techniques ou des ordres de travail. Les heures réelles sont basées sur des transactions validées.

## <a name="work-hour-control-for-assets-functional-locations-and-work-orders"></a>Contrôle des heures de travail pour des actifs, des postes techniques et des ordres de travail

Les calculs effectués pour les actifs, les postes techniques et les ordres de travail sont quasiment identiques. L'unique différence réside dans le fait que pour les actifs et les postes techniques, vous pouvez également inclure les sous-actifs et les sous-postes dans votre calcul. La date est la date de transaction à laquelle l'enregistrement a été enregistré.

1. Cliquez sur **Gestion des actifs** > **Recherches** > **Actifs** > **Contrôle des heures d'actif** ou **Contrôle des heures du poste technique** ou **Gestion des actifs** > **Recherches** > **Ordres de travail** > **Contrôle des heures des ordres de travail**.

2. Dans la boîte de dialogue **Contrôle des heures de l'actif**.

3. Dans la boîte de dialogue **Contrôle des heures d'actif** / **Contrôle des heures de poste technique** / **Contrôle des heures de l'ordre de travail**, sélectionnez une période à calculer dans les champs **Date de début** et **Date de fin**.

4. Si nécessaire, sélectionnez un **ensemble de dimensions financières** à inclure dans le calcul.

5. Sélectionnez « Oui » sur le bouton bascule **Ignorer lignes nulles** si vous ne souhaitez pas afficher les résultats ne contenant pas d'heure.

6. Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes de contrôle des heures en fonction des postes techniques. 

    Par exemple, si vous insérez le chiffre « 1 » dans le champ, et que vous avez une hiérarchie de postes techniques à plusieurs niveaux, toutes les lignes de contrôle des heures pour un poste technique s'affichent dans le niveau supérieur et il est donc possible d'ajouter les heures sur une ligne à partir des postes techniques situés à un niveau inférieur. 
    
    Par exemple, si vous insérez le chiffre « 0 » dans le champ **Niveau**, un résultat détaillé s'affiche et indique toutes les lignes de contrôle des heures sur tous les niveaux du poste technique auxquels elles sont liées.

7. Sélectionnez « Oui » sur le bouton à bascule **Inclure les sous-actifs** pour afficher les coûts associés aux sous-actifs comme lignes distinctes.

8. Pour limiter la recherche, vous pouvez sélectionner des actifs/postes techniques/ordres de travail sur l'organisateur **Enregistrements à inclure**.

9. Cliquez sur **OK** pour démarrer le calcul.

10. Sur la page **Contrôle des heures de l'actif**, cliquez sur le bouton **Grouper par**, cliquez sur les boutons appropriés à afficher le niveau requis de détail du calcul. Les boutons **Grouper par** sélectionnés sont mis en surbrillance. Cliquez sur un bouton pour l'activer ou le désactiver.

## <a name="example"></a>Exemple

La capture d'écran suivante présente un exemple de calcul de **contrôle des heures d'actif**.

- Le champ **Budget d'origine** indique les heures budgétaires à partir des prévisions de l'ordre de travail. 
- Le champ **Heures réelles** indique les heures validées sur les ordres de travail. 
- Le champ **Heures engagées** indique les totaux horaires dans lesquels votre société s'engage en termes d'ordres de travail.

![Exemple de calcul de contrôle des heures de l'actif](media/04-controlling-and-reporting.png)

Une autre manière d'effectuer un calcul d'heures est de choisir plusieurs actifs dans **Tous les actifs** ou **Actifs actifs**. Ensuite vous cliquez sur le bouton **Contrôle d'heure** sur l'organisateur **Général**. Les actifs sélectionnés sont insérés automatiquement dans le champ **Actif** sur l'organisateur **Enregistrements à inclure**. Cliquez sur **OK** dans la boîte de dialogue **Contrôle des heures d'actif**, et le calcul pour les actifs sélectionnés s'affiche. La même procédure peut être effectuée pour les postes techniques dans **Tous les postes techniques** ou **Postes techniques actifs**, et pour les ordres de travail dans **Tous les ordres de travail** ou **Ordres de travail actifs**.


