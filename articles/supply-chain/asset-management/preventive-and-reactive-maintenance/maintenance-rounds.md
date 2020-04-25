---
title: Visites de maintenance
description: Cette rubrique explique les visites de maintenance dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 97f1984b71ab60519f81bb1f6ab38278a0e5aa43
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206102"
---
# <a name="maintenance-rounds"></a>Visites de maintenance

[!include [banner](../../includes/banner.md)]

 

Dans **Gestion des actifs**, vous pouvez créer des visites de maintenance pour divers actifs sur lesquels vous devez effectuer une tâche similaire à intervalles réguliers. Par exemple, des tâches de lubrification ou de contrôle de sécurité qui doivent être effectuées sur un certain nombre de machines dans les mêmes intervalles. La première étape consiste à créer une visite de maintenance, y compris les actifs nécessitant la même forme de tâche de maintenance. Ensuite, vous planifiez les visites de maintenance. Lorsque vous avez terminé le programme des visites de maintenance, vous pouvez voir tous les enregistrements de tâches concernant la visite dans les champs **Tout le programme de maintenance** et **Ouvrir les lignes du programme de maintenance**.

>[!NOTE]
>Les visites de maintenance peuvent être également configurées sur les postes techniques à exécuter sur les actifs installés sur le poste technique au moment de la création de l'ordre de travail basé sur une visite. Consultez [Créer des postes techniques](../functional-locations/create-functional-locations.md) pour en savoir plus sur la configuration des visites de maintenance sur les postes techniques.

## <a name="set-up-a-maintenance-round"></a>Configurer une visite de maintenance

1. Cliquez sur **Gestion des actifs** > **Paramétrage** > **Maintenance préventive** > **Visites de maintenance**.

2. Cliquez sur **Nouveau** pour créer une visite de maintenance.

3. Saisissez un ID dans le champ **Visite de maintenance**, et un nom pour la visite de maintenance dans le champ **Nom**.

4. Sélectionnez une date de début pour la visite dans le champ **Date de début**.

5. Dans les champs **Délai de fin en jours** et **Délai de fin en heures**, vous pouvez saisir une date de fin prévue en jours ou en heures. La date de fin prévue est calculée par rapport à la date de début, qui est calculée lorsque les lignes du programme de maintenance sont créées. Par exemple, vous pouvez insérer « 7 » dans le champ **Délai de fin en jours** pour indiquer que la tâche associée doit être terminée sous une semaine à compter de la date de début.

6. Sélectionnez « Oui » sur le bouton à bascule **Création automatique** si les ordres de travail doivent automatiquement être créés depuis les lignes du programme de maintenance créées depuis cette visite de maintenance.

7. Dans le champ **Type d'ordre de travail**, sélectionnez le type d'ordre de travail à utiliser sur les ordres de travail créés depuis cette visite de maintenance.

8. Dans le champ **Niveau de service**, sélectionnez le niveau de service de l'ordre de travail à utiliser sur les ordres de travail créés depuis cette visite de maintenance.

9. Dans l'organisateur **Lignes des actifs**, cliquez sur **Ajouter** pour ajouter un actif à la visite de maintenance.

10. Un numéro de ligne est inséré automatiquement dans le champ **Numéro de ligne** pour indiquer la séquence des actifs dans la visite de maintenance.

11. Sélectionnez l'actif dans le champ **Actif**.

12. Sélectionnez le type de tâche de maintenance pour l'actif dans le champ **Type de tâche de maintenance**.

13. Le cas échéant, sélectionnez **Variante du type de tâche de maintenance** et **Transaction** associés au type de tâche de maintenance.

14. Sélectionnez la récurrence (jour, semaine, etc.) dans le champ **Type de période**.

15. Dans le champ **Fréquence de période**, insérez le nombre de répétitions pour la visite de maintenance. Exemple : Si vous avez sélectionné « Jour » dans le champ **Type de période**, et si vous insérez le nombre « 7 » dans ce champ, de nouvelles lignes de visite de maintenance sont créées lors de la planification de la maintenance préventive une fois par semaine.

16. Sélectionnez une date de début pour l'actif à inclure dans la visite de maintenance dans le champ **Date de début**. Cette date peut être différente du début de date définie sur la visite de maintenance.

17. Répétez les étapes 9 à 16 pour ajouter plus d'actifs à la visite de maintenance.

18. Dans l'organisateur **Lignes des postes techniques**, cliquez sur **Ajouter** pour ajouter un poste technique à la visite de maintenance. Consultez la description des champs associés ci-dessus. Les mêmes champs sont disponibles pour créer une ligne d'actif, mais vous pouvez également sélectionner **Fabricant** et **Modèle** pour un poste technique, le cas échéant. Si vous sélectionnez uniquement un poste technique sur une ligne, mais si vous n'effectuez aucune sélection dans **Type d'actif**, **Fabricant**, **Modèle**, **Type de tâche de maintenance**, **Variante du type de tâche de maintenance** et **Transaction**, tous les actifs associés à ce poste technique au moment de la planification de maintenance seront inclus dans la visite de maintenance.

19. Dans l'organisateur **Regroupements**, cliquez sur **Ajouter** pour sélectionner un regroupement d'ordres de travail à inclure dans la visite de maintenance. Plusieurs regroupements d'ordres de travail peuvent être liés à une visite de maintenance.

20. Enregistrez votre configuration.

>[!NOTE]
>Les champs **Actifs** et **Lignes** situés dans le groupe **Détails** de l'organisateur **En-tête** présentent le nombre total d'actifs et de lignes associés à la visite de maintenance sélectionnée.

L'illustration ci-après présente l'exemple d'une tâche de maintenance contenant trois actifs.

![Figure 1](media/13-preventive-maintenance.png)


## <a name="schedule-maintenance-rounds"></a>Planifier les visites de maintenance

Lorsque vous avez paramétré une visite de maintenance, vous exécutez une tâche de programme pour planifier toutes les tâches relatives à la visite de maintenance.

1. Cliquez sur **Gestion des actifs** > **Périodique** > **Maintenance préventive** > **Visites de maintenance du programme**, ou **Gestion des actifs** > **Commun** > **Programme de maintenance** > **Tout le programme de maintenance** ou **Ouvrir les lignes du programme de maintenance** ou **Ouvrir les regroupements du programme de maintenance** > sélectionnez la ligne du programme de maintenance dans la liste > bouton **Visites de maintenance**.

2. Dans le champ **Période**, sélectionnez le type de période à utiliser pour la tâche de planification.

3. Dans le champ **Fréquence de période**, insérez le nombre de périodes à inclure dans la tâche de planification. Le début de la planification est la date actuelle.

4. Sélectionnez « Oui » sur le bouton à bascule **Créer automatiquement** si un ordre de travail doit être automatiquement créé sur la base d'une visite de maintenance.

>[!NOTE]
>Si ce bouton à bascule est défini sur « Oui » et si le bouton à bascule **Créer automatiquement** est également défini sur « Oui » sur la visite de maintenance dans le formulaire **Visites de maintenance**, les ordres de travail sont créés selon les lignes de la visite de maintenance et les lignes du programme de maintenance sont également créées avec le statut « Ordre de travail créé ». Si un seul des boutons à bascule **Créer automatiquement** est défini sur « Oui », dans cette liste déroulante ou dans **Visites de maintenance**, seules les lignes du programme de maintenance sont créées avec le statut « Créé ». Dans ce cas, aucun ordre de travail n'est créé.

5. Si nécessaire, vous pouvez sélectionner des visites spécifiques ou une autre date de début pour la tâche de planification. Cliquez sur **Filtre**, puis ajoutez les visites à inclure.

6. Cliquez sur **OK**.

7. Vous pouvez à présent voir les tâches de visite de maintenance dans **Gestion des actifs** > **Commun** > **Programme de maintenance** > **Tout le programme de maintenance** ou **Ouvrir les lignes du programme de maintenance**. Si les visites planifiées sont connectées à un regroupement d'ordres de travail, vous pouvez également voir des lignes du programme de maintenance dans **Ouvrir les regroupements du programme de maintenance**. Les lignes du programme de maintenance créées depuis une visite ont le type de référence « Visites de maintenance ».

Les deux illustrations ci-dessous présentent une tâche de programme dans la boîte de dialogue **Programmer les tâches de maintenance**, et les lignes de programme de maintenance créées dans **Tout le programme de maintenance** selon cette tâche programmée.

![Figure 2](media/14-preventive-maintenance.png)

![Figure 3](media/15-preventive-maintenance.png)

- Lorsque les ordres de travail sont créés manuellement sur les actifs couverts par une garantie fournisseur, une boîte de dialogue s'affiche pour indiquer la garantie à l'utilisateur. La création de l'ordre de travail peut être ensuite annulée. La vérification d'une relation de garantie est ignorée pour les ordres de travail qui sont automatiquement créés.  
- Vous pouvez paramétrer un traitement par lots sur l'organisateur **Exécuter en arrière-plan** pour planifier les visites à des intervalles réguliers.  
- Si une visite est incluse dans plusieurs regroupements d'ordres de travail (consultez [Regroupements des ordres de travail](../work-orders/work-order-pools.md)), un enregistrement est indiqué pour chaque regroupement dans **Ouvrir les regroupements du programme de maintenance**. Cela permet d'optimiser les options de filtrage pour les regroupements des ordres de travail.

