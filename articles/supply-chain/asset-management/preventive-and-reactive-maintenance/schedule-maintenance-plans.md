---
title: Planifier les plans de maintenance
description: Cette rubrique explique la planification des plans de maintenance dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
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
ms.openlocfilehash: b9efd5bccdccf6ea19b105f3518bb2ef35ec857e
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571275"
---
# <a name="schedule-maintenance-plans"></a>Planifier les plans de maintenance

[!include [banner](../../includes/banner.md)]

 

La planification de maintenance préventive génère des entrées de calendrier sur les actifs, en fonction de la configuration des plans de maintenance sur les actifs. Vous pouvez planifier des entrées de calendrier selon les plans de maintenance, les types d'actifs et les actifs sélectionnés.

1. Cliquez sur **Gestion des actifs** > **Périodique** > **Maintenance préventive** > **Planifier les plans de maintenance**.

2. Vous pouvez sélectionner un intervalle dans les champs **Période** et **Fréquence de période**.

>[!NOTE]
>Les champs **Période** et **Fréquence de période** indiquent combien à l'avance vous pouvez créer des lignes du programme de maintenance, selon les plans de maintenance que vous avez créés (selon l'heure ou le compteur). Dans la figure ci-dessous, les lignes du programme de maintenance (= propositions de l'ordre de travail) sont créées depuis la date actuelle et trois mois à l'avance.

3. Sélectionnez « Oui » sur le bouton à bascule **Créer automatiquement si indiqué dans la ligne** si les ordres de travail doivent être créés automatiquement en fonction de la ligne du plan de maintenance.

>[!NOTE]
>Si ce bouton à bascule est défini sur « Oui » *et* si la case à cocher **Créer automatiquement** est également sélectionnée sur les lignes du plan de maintenance dans **Plans de maintenance**, les ordres de travail sont créés selon les lignes du plan de maintenance et les lignes du programme de maintenance sont également créées avec le statut « Ordre de travail créé ». Si une seule option est sélectionnée (le bouton à bascule **Créer automatiquement si indiqué dans la ligne** dans cette boîte de dialogue ou la case à cocher **Créer automatiquement** sur l'écran **Plans de maintenance**), seules les lignes du programme de maintenance sont créées avec le statut « Créé ». Dans ce cas, aucun ordre de travail n'est créé.

4. Vous pouvez générer des entrées de calendrier selon les plans de maintenance (heure et compteur), les actifs, les types d'actifs, les postes techniques et les types de postes techniques. Cliquez sur le bouton **Filtre** et effectuez vos sélections, si nécessaire.

- Concernant la planification des plans de maintenance sur les postes techniques : si vous mettez à jour le paramétrage des types d'actifs, des fabricants et des modèles d’actifs dans les plans de maintenance dans l'organisateur **Tous les postes techniques** > **Plans de maintenance** après avoir affecté des plans de maintenance, les entrées existantes du programme de maintenance associées à ce poste technique sont automatiquement supprimées. Pour créer des entrées de calendrier qui correspondent au paramétrage du plan de maintenance mis à jour dans le poste technique, vous devez exécuter un nouveau programme de plan de maintenance pour ce poste technique. Lisez-en davantage sur la configuration des types d'actifs, des fabricants et des modèles sur les postes techniques dans [Créer des emplacements fonctionnels](../functional-locations/create-functional-locations.md).

>*Exemple :* vous voulez créer un plan de maintenance pour un poste technique spécifique, ce qui signifie que tous les actifs paramétrées pour ce poste technique à tout moment donné sera inclus lorsque vous planifiez le plan de maintenance. Dans ce cas, vous créez un plan de maintenance et sélectionnez le poste technique spécifique, mais vous n'ajoutez PAS d'actif dans le plan de maintenance. Le résultat est que lorsque vous planifiez le plan de maintenance, les lignes du programme de maintenance sont créées pour tous les actifs associés au poste technique à la fois.

- Si vous apportez des modifications aux types d'actifs, aux fabricants et aux modèles dans **Types d'actifs**, ces modifications affectent uniquement les nouveaux actifs utilisant le type d'actifs mis à jour. Découvrez-en davantage sur la configuration du type d'actifs dans [Types d'actifs](../setup-for-objects/object-types.md).  

5. Cliquez sur **OK** pour commencer la génération des entrées du programme de maintenance sur les actifs. Les entrées générées sont affichées sur la page de liste **Tout le programme de maintenance**. L'illustration suivante présente un exemple de la boîte de dialogue **Planifier les plans de maintenance**.

![Figure 1](media/09-preventive-maintenance.png)

- Dans la boîte de dialogue **Planifier les plans de maintenance**, vous pouvez paramétrer des traitements par lots sur l'organisateur **Exécuter à l'arrière-plan** pour générer automatiquement des entrées de calendrier à intervalles réguliers.  
- Lorsque vous planifiez la maintenance préventive, les lignes du programme de maintenance avec des date et heure de début prévues antérieures à la date et à l'heure du système ne seront pas créées.  

La figure ci-dessous propose une illustration graphique d'un calcul du plan de maintenance basé sur les heures.  

![Figure 2](media/10-preventive-maintenance.jpg)

Concernant les plans de maintenance basés sur le compteur : dans les figures ci-dessous, deux cycles d'enregistrement de compteur différents sont présentés. Ils sont basés sur un plan de maintenance paramétré pour l'actif « V0001 », prévoyant que l'actif (un véhicule) effectue environ 2 000 km chaque mois.

Dans le premier exemple, les 2 000 kilomètres planifiés ne sont pas atteints tous les mois. En fonction du plan de maintenance basé sur le compteur, le seuil est 2 000 km. Autrement dit, lorsque vous exécutez une planification du plan de maintenance, une ligne du programme de maintenance doit être créée chaque fois que le seuil de 2 000 km est atteint. Dans l'exemple 1, il y a 4 lignes d'enregistrement, mais le seuil de 2 000 kilomètres n'est atteint une seule fois. Autrement dit, lorsque vous planifiez des plans de maintenance pour cet actif, par exemple, une période de 3 mois, seule une ligne du programme de maintenance sera créée.

Sur la figure suivante, 2 000 km ou plus sont enregistrés chaque mois. Par conséquent, trois lignes de maintenance sont créées si vous planifiez des plans de maintenance pour cet actif pour une période de 3 mois. 

Les exemples décrits ici indiquent que tous les enregistrements de compteur effectués sur un actif présentent une tendance décrivant l'usure de l'actif. Cette tendance est utilisée pour calculer le moment de la planification du plan de maintenance.

![Figure 3](media/11-preventive-maintenance.png)

![Figure 4](media/12-preventive-maintenance.png)

