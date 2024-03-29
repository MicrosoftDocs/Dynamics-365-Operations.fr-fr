---
title: Coût du programme de maintenance
description: Cet article explique le coût du programme de maintenance dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 08/27/2019
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
ms.openlocfilehash: 91481f9bcb778796255fad006c6187916d8e6bb2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908741"
---
# <a name="maintenance-schedule-cost"></a>Coût du programme de maintenance

[!include [banner](../../includes/banner.md)]

 

Dans le module Gestion des actifs, vous pouvez calculer les coûts budgétaires sur les lignes du programme de maintenance. Cela est utile si vous souhaitez obtenir une vue d’ensemble des coûts prévisionnels, par exemple, les coûts associés aux tâches de maintenance préventive planifiées pour l’an prochain. Les calculs sont basés sur les lignes de programme de maintenance du type « Plans de maintenance » et « Visites de maintenance » et « Demandes de maintenance ».

1. Cliquez sur **Gestion des actifs** > **Recherches** > **Actifs** > **Coût du programme de maintenance**.

2. Dans la boîte de dialogue **Coût du programme de maintenance**, vous pouvez sélectionner un **Ensemble de dimensions financières** si vous souhaitez afficher les coûts regroupés dans les dimensions financières.

>[!NOTE]
>Les ensembles de dimensions financières sont paramétrés dans **Comptabilité générale** > **Plan de comptes** > **Dimensions** > **Ensembles de dimensions financières**.

3. Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes du programme de maintenance en fonction des postes techniques. Par exemple, si vous insérez le chiffre « 1 » dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, toutes les lignes du programme de maintenance pour un poste technique s’affichent dans le niveau supérieur et il est donc possible d’ajouter des heures sur une ligne à partir des postes techniques situés à un niveau inférieur. Par exemple, si vous insérez le chiffre « 0 » dans le champ **Niveau**, un résultat détaillé s’affiche et indique toutes les lignes du programme de maintenance sur tous les niveaux du poste technique auxquels ils sont liés.

4. Si vous souhaitez effectuer un calcul pour les actifs spécifiques, cliquez sur **Filtre** sur l’organisateur **Enregistrements à inclure**, et sélectionnez les actifs appropriés. Si nécessaire, vous pouvez également spécifier une date de **Début prévu** pour le calcul du coût ou sélectionner un autre **Statut** pour le calcul du coût

5. Cliquez sur **OK** pour démarrer le calcul des coûts.

6. Sur l’onglet **Coût du programme de maintenance** des groupes du volet Actions **Regrouper par…**, cliquez sur les boutons appropriés pour afficher le niveau requis de détail du calcul des coûts. Les boutons sélectionnés du groupe du volet Actions sont mis en surbrillance. Cliquez sur un bouton pour l’activer ou le désactiver.

7. Cliquez sur le bouton **Calculez le coût** si vous souhaitez effectuer un nouveau calcul des coûts.

L’illustration ci-dessous affiche les résultats d’un calcul de coût du programme de maintenance.

![Figure 1.](media/17-preventive-maintenance.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]