---
title: Temps d'arrêt pour maintenance
description: Cette rubrique explique les temps d'arrêt pour maintenance dans le module Gestion des actifs.
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
ms.openlocfilehash: c035f54e833b9bc25b4502901cf307213789b439
ms.sourcegitcommit: 6476f27c8d3dced7c2e9a7344a4e378b51a1983e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/27/2019
ms.locfileid: "1922181"
---
# <a name="maintenance-downtime"></a>Temps d'arrêt pour maintenance

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Les temps d'arrêt pour maintenance sont utilisés pour obtenir une vue d'ensemble de la capacité requise pour effectuer les tâches de maintenance sur des actifs spécifiques pendant une période spécifique. Par exemple, vous pouvez créer un enregistrement des temps d'arrêt pour maintenance pour la ligne de production 10 dans le hall de production 29-A du site de production 02. L'enregistrement des temps d'arrêt pour maintenance a une heure de début et de fin indiquant la période au cours de laquelle les actifs associés à l'arrêt de la maintenance ne sont pas disponibles pour production.

Le champ **Activités des temps d'arrêt pour maintenance** désigne une vue d'ensemble des lignes du programme maintenance et des tâches de maintenance des ordres de travail sur les actifs associés au cours d'une période spécifiée. Les lignes associées aux tâches de maintenance des ordres de travail ont toutes une date de début prévue dans la période d'arrêt pour maintenance. Vous pouvez extraire de précieuses informations et faire des ajustements aux tâches de maintenance planifiées :

- Obtenez une vue d'ensemble des périodes d'arrêt requises pour l'équipement de production (actifs).  
- Obtenez une vue d'ensemble de la maintenance planifiée (heures), regroupée par compétences (groupes d'agents de maintenance ou agents de maintenance responsables), par exemple la charge maximale pour les électriciens, les forgerons ou d'autres groupes de travail de maintenance requis pour exécuter les tâches de maintenance planifiées.  
- Apportez des ajustements aux lignes du programme de maintenance ou aux tâches de maintenance des ordres de travail associées aux actifs, par exemple, modifiez les heures de début et de fin sur une ligne, ou sélectionnez d'autres agents de maintenance pour optimiser le flux de travail pour les agents de maintenance et les groupes d'agents de maintenance.

Une fois les actifs sélectionnés sur un enregistrement des temps d'arrêt de maintenance, toutes les lignes du programme de maintenance ouvertes et les tâches de maintenance des ordres de travail associées aux ordres de travail actifs sont comprises dans l'enregistrement des temps d'arrêt pour maintenance.

## <a name="maintenance-downtime-activities"></a>Activités de temps d'arrêt pour maintenance

Cliquez sur **Gestion des actifs** > **Commun** > **Activités des temps d'arrêt pour maintenance** > **Toutes les activités de temps d'arrêt pour maintenance** pour ouvrir une liste de toutes les activités des temps d'arrêt pour maintenance et afficher une partie des informations relatives aux activités. Cliquez sur un lien dans la colonne **Activités des temps d'arrêt pour maintenance** pour ouvrir la vue détaillée. L'illustration ci-dessous présente un exemple de la liste **Activités de temps d'arrêt pour maintenance**.

![Figure 1](media/19-preventive-maintenance.png)


## <a name="create-a-maintenance-downtime-activity"></a>Créer une activité de temps d'arrêt pour maintenance

1. Cliquez sur **Gestion des actifs** > **Commun** > **Activités de temps d'arrêt pour maintenance** > **Toutes les activités de temps d'arrêt pour maintenance** ou **Activités de temps d'arrêt pour maintenance actives**.

2. Cliquez sur **Nouveau**.

3. Insérez un ID dans le champ **Activités des temps d'arrêt pour maintenance**, et un nom de compteur dans le champ **Nom**.

4. Insérez la période pour l'arrêt de maintenance dans les champs **Date/heure de début** et **Date/heure de fin**.

5. Dans l'organisateur **Actifs d'activités de temps d'arrêt pour maintenance** > cliquez sur **Ajouter une ligne** pour ajouter des actifs, un à la fois, à l'activité de temps d'arrêt pour maintenance.

6. Cliquez sur **Enregistrer** lorsque tous les actifs ont été ajoutés. L'illustration ci-dessous présente un exemple d'une activité de temps d'arrêt pour maintenance à des actifs et des tâches de maintenance associés.

7. Les tâches de maintenance des ordres de travail et les lignes du programme de maintenance ouvertes associées aux actifs sélectionnés sont affichées sous **Tâches de maintenance des ordres de travail résultantes** et les organisateurs **Lignes du programme de maintenance**. Dans l'organisateur **Général** > groupe **Ordres de travail** champ > **Heures des prévisions en matière de maintenance** et organisateur **Général** > groupe **Heures de prévisions en matière de maintenance** > champ **Heures de prévisions en matière de maintenance**, vous voyez le nombre total d'heures prévues pour les tâches de maintenance des ordres de travail et les lignes du programme de maintenance.

L'illustration ci-dessous présente un exemple de la vue des détails **Activités de temps d'arrêt pour maintenance**.

![Figure 2](media/20-preventive-maintenance.png)

>[!NOTE]
>Les tâches de maintenance des ordres de travail et les lignes du programme de maintenance associées aux actifs sélectionnés sont automatiquement mises à jour si les nouveaux ordres de travail ou les lignes du programme de maintenance sont créés une fois l'activité des temps d'arrêt pour maintenance créée. Par exemple, si vous programmez des plans de maintenance ou des visites de maintenance sur les actifs associés deux jours après la création de l'activité des temps d'arrêt pour maintenance, de nouvelles lignes du programme de maintenance sont automatiquement ajoutées à l'activité des temps d'arrêt pour maintenance.

8. Dans **Toutes les activités de temps d'arrêt pour maintenance** > **Activités de temps d'arrêt pour maintenance** > sélectionnez une activité de temps d'arrêt pour maintenance dans la liste et cliquez sur **Charge maximale** pour ouvrir la boîte de dialogue **Calculer la charge maximale**. Utilisez cette boîte de dialogue pour obtenir une vue d'ensemble de la charge maximale, par exemple, les dates, actifs, types d'actif et types de tâche de maintenance. Notez que les dates affichées dans la boîte de dialogue sont les dates de début et de fin sélectionnées dans **Activités de temps d'arrêt pour maintenance**. Ce calcul comprend les actifs associés à l'activité de temps d'arrêt pour maintenance.

9. Dans la boîte de dialogue **Calculer la charge maximale**, modifiez les heures de début et de fin, le cas échéant, et sélectionnez si vous souhaitez inclure des ordres de travail et des programmes de maintenance dans le calcul. Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans le calcul de charge maximale en fonction des postes techniques. Par exemple, si vous insérez le chiffre 1 dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, tous les actifs pour un poste technique, qui sont sélectionnés sur l'activité de temps d'arrêt pour maintenance, s'affichent dans le niveau supérieur et il est donc possible d'ajouter des heures sur une ligne à partir des postes techniques situés à un niveau inférieur. Par exemple, si vous insérez le chiffre « 0 » dans le champ **Niveau**, un résultat détaillé s'affiche et indique toutes les lignes de la charge maximale sur tous les niveaux du poste technique auxquels ils sont liés.

10. Cliquez sur **OK** pour démarrer le calcul. Le nombre total d'heures s'affiche dans la vue d'ensemble **Charge maximale**. Dans l'onglet **Charge maximale** > les groupes de volet Actions **Regroupement par…**, cliquez sur les boutons appropriés pour obtenir une vue d'ensemble plus détaillée de la répartition des heures prévues. L'illustration ci-dessous affiche les résultats d'un calcul **Charge de la capacité**.

![Figure 3](media/21-preventive-maintenance.png)

11. Une fois que vous obtenez une vue d'ensemble de la charge maximale, si vous souhaitez procéder à des ajustements des tâches de maintenance des ordres de travail ou des lignes du programme de maintenance, revenez à la vue détaillée **Activités de temps d'arrêt pour maintenance** et sélectionnez les lignes à ajuster dans les organisateurs **Tâches de maintenance des ordres de travail résultantes** et **Lignes du programme de maintenance**.

12. Cliquez sur le bouton **Ajuster** et mettez à jour les dates de début/fin, le niveau de service, ou les agents de maintenance responsables pour les tâches de maintenance des ordres de travail ou les lignes du programme de maintenance sélectionnées.

13. Cliquez sur **OK** lorsque vous avez effectué les ajustements nécessaires. 

>[!NOTE]
>Les tâches de maintenance des ordres de travail et les lignes du programme de maintenance qui ne sont pas incluses dans la période de temps d'arrêt pour maintenance une fois les ajustements supprimés automatiquement des **Activités de temps d'arrêt pour maintenance**.

14. Dans **Toutes les activités de temps d'arrêt pour maintenance** > **Activités de temps d'arrêt pour maintenance** > sélectionnez une activité de temps d'arrêt pour maintenance dans la liste et cliquez sur **Prévisions des articles** pour ouvrir la boîte de dialogue **Calculer les prévisions des articles**. Utilisez cette boîte de dialogue pour calculer les prévisions pour les articles (pièces détachées et autres articles requis) et les regrouper pour obtenir une vue d'ensemble, par exemple, par date, actif, type d'actif et type de tâche de maintenance. Notez que les dates affichées dans la boîte de dialogue sont les dates de début et de fin sélectionnées dans **Activités de temps d'arrêt pour maintenance**. Ce calcul comprend les pièces détachées et les articles associés aux actifs qui sont sélectionnés sous l'activité de temps d'arrêt pour maintenance.

15. Dans la boîte de dialogue **Calculer les prévisions des articles**, modifiez les heures de début et de fin, le cas échéant, et sélectionnez si vous souhaitez inclure des ordres de travail et des programmes de maintenance dans le calcul. Vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans le calcul de charge maximale en fonction des postes techniques. Par exemple, si vous insérez le chiffre 1 dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, tous les actifs pour un poste technique, qui sont sélectionnés sur l'activité de temps d'arrêt pour maintenance, s'affichent dans le niveau supérieur et il est donc possible d'ajouter des heures sur une ligne à partir des postes techniques situés à un niveau inférieur. Par exemple, si vous insérez le chiffre « 0 » dans le champ **Niveau**, un résultat détaillé s'affiche et indique toutes les lignes de la charge maximale sur tous les niveaux du poste technique auxquels ils sont liés.

16. Cliquez sur **OK** pour démarrer le calcul. Le nombre total de prévisions des articles s'affiche dans la vue d'ensemble **Prévisions des articles**. Dans l'onglet **Prévisions des articles** > les groupes de volet Actions **Regroupement par…**, cliquez sur les boutons appropriés pour obtenir une vue d'ensemble plus détaillée de la répartition des articles prévus. L'illustration ci-dessous affiche les résultats d'un calcul **Charge de la capacité**.

![Figure 4](media/22-preventive-maintenance.png)

- Vous pouvez copier des actifs d'une activité de temps d'arrêt pour maintenance à une autre. Dans **Toutes les activités de temps d'arrêt pour maintenance**, sélectionnez le bouton **Copier les activités de temps d'arrêt pour maintenance**, puis effectuez vos sélections dans les champs **Des activités de temps d'arrêt pour maintenance** et **Aux activités de temps d'arrêt pour maintenance**, puis cliquez sur **OK**.
- Dans **Toutes les activités de temps d'arrêt pour maintenance**, cliquez sur le bouton **Lignes du programme de maintenance** ou le bouton **Ordres de travail actifs** pour ouvrir les listes associées et afficher les lignes associées à l'activité de temps d'arrêt pour maintenance sélectionnée.

