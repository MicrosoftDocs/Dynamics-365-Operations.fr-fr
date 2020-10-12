---
title: Plans de maintenance
description: Cette rubrique explique les plans de maintenance dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 28c00b5a2485ffcc01a316d2a39e7259fb563d1d
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889047"
---
# <a name="maintenance-plans"></a>Plans de maintenance

[!include [banner](../../includes/banner.md)]

 

Un plan de maintenance définit le moment de l'exécution d'une tâche de maintenance préventive pré-planifiée sur un actif. Les plans de maintenance peuvent être associés aux actifs, aux types d'actifs, aux postes techniques ou aux types de postes techniques. Cependant, vous devez tout d'abord créer les plans de maintenance à utiliser dans votre société.

Un plan de maintenance peut avoir plusieurs lignes de plan de maintenance. Le type de tâche de maintenance et les intervalles sont précisés sur la ligne du plan de maintenance. Il y a deux types de lignes de plan de maintenance :

- Heure  
- Compteur  

Les lignes de plan de maintenance de type « Heure » sont utilisées pour la maintenance planifiée récurrente basée sur un intervalle fixe. Les lignes de plan de maintenance de type « Compteur » sont utilisées pour la maintenance prévue ou la maintenance réactive selon les enregistrements de compteur d'actifs. Un plan de maintenance peut être constitué de plusieurs lignes des deux types.

>[!NOTE]
>Si aucune contre-valeur n'a été enregistrée pour un type de compteur sur un actif, les lignes du plan de maintenance sont omises.

Tout d'abord, créez les plans de maintenance dont vous avez besoin pour vos tâches de maintenance préventive et sélectionnez les types d'actif, les actifs, les types de poste technique et les postes techniques qui doivent être associés à chaque plan de maintenance. Ensuite, le cas échéant, vous pouvez également ajouter des plans de maintenance à un actif ou un poste technique. Pour cela, accédez à **Tous les actifs** > sélectionnez l'actif > organisateur **Plans de maintenance des actifs** ou **Tous les postes techniques** > sélectionnez le poste technique > organisateur **Plans de maintenance**.

Si vous ajoutez un plan de maintenance aux types d'actif ou aux types de poste technique, cela signifie que lorsque vous créez de nouveaux actifs ou postes techniques avec ces types d'actif ou de poste technique, l'actif ou le poste technique sera automatiquement ajouté au plan de maintenance. La date de début de la relation à un plan de maintenance sera la date actuelle, qui nécessitera peut-être un ajustement.

## <a name="set-up-maintenance-plans"></a>Définir des plans de maintenance

Cette section décrit comment configurer des lignes de plan de maintenance et offrir des exemples sur la manière dont elles peuvent être utilisées.

1. Cliquez sur **Gestion des actifs** > **Paramétrage** > **Maintenance préventive** > **Plans de maintenance**.

2. Cliquez sur **Nouveau** pour créer une séquence.

3. Insérez un ID dans le champ **Séquence de maintenance**, et un nom de compteur dans le champ **Nom**.

4. Dans le champ **Date de planification**, insérez la date de début de la planification sur le plan de maintenance. Notez que les lignes de plan de maintenance basées sur les heures peuvent avoir d'autres dates de plan.

5. Sélectionnez » Oui » dans le bouton à bascule **Actif** pour activer le plan de maintenance.

>[!NOTE]
>Si vous désactivez un plan de maintenance, aucune publication de programme ne sera créée dans le programme de maintenance lorsque vous exécutez une tâche du plan de maintenance programmé.

6. Les champs **Jours de tolérance avant** et **Jours de tolérance après** font référence aux lignes du plan de maintenance sur lesquelles la case **Supprimer les tâches de maintenance qui se chevauchent** est cochée (consultez l'étape 17). Les champs « Tolérance » sont utilisés pour étendre l'intervalle en jours pendant lesquels, en cas de chevauchement de plusieurs plans de maintenance, la tâche la plus complète/importante est créée comme ligne de programme de maintenance pendant la planification du plan de maintenance, même si des tâches plus fréquentes qui se chevauchent sont omises pendant la planification du plan de maintenance. Saisissez le nombre de jours dans le champ **Jours de tolérance avant**, par exemple « 2 ».

7. Si vous avez créé une valeur dans champ **Jours de tolérance avant**, insérez également le nombre de jours dans le champ **Jours de tolérance après**, par exemple « 2 ».

>[!NOTE]
>L'exemple décrit dans cette étape, et dans la précédente, signifie que si plusieurs lignes du plan de maintenance se chevauchent, et si la case **Supprimer les tâches de maintenance qui se chevauchent** est cochée pour une ou plusieurs lignes, la période d'omission des lignes du programme de maintenance est étendue à un total de cinq jours (la date de début prévue sur la ligne du programme de maintenance *et* deux jours avant *et* deux jours après cette date).

8. Les champs du groupe **Détails** sur l'organisateur **Détails** affichent plusieurs lignes du plan de maintenance configurées sur le plan de maintenance et le nombre d'actifs et de postes techniques associés au plan de maintenance.

9. Dans l'organisateur **Lignes**, cliquez sur **Ajouter une ligne d'heure** ou **Ajouter une ligne de compteur d'actifs** pour créer une ligne du plan de maintenance.

10. Saisissez une description pour la ligne dans le champ **Description de l'ordre de travail**. La description est transférée vers les ordres de travail associés.

11. Dans le champ **Type de tâche de maintenance**, sélectionnez le type de tâche auquel la ligne du plan de maintenance est associée.

12. Dans les champs **Variante du type de tâche de maintenance** et **Transaction**, sélectionnez la variante et la transaction associées au type de tâche de maintenance.

13. Dans les champs **Délai de fin en jours** et **Délai de fin en heures**, vous pouvez saisir une date de fin prévue en jours ou en heures. La date de fin prévue est saisie par rapport à la date de début prévue, qui est calculée lorsque les lignes du programme de maintenance sont créées. Par exemple, vous pouvez insérer « 7 » dans le champ **Délai de fin en jours** pour indiquer que la tâche associée doit être terminée sous une semaine à compter de la date de début prévue.

14. Dans le champ **Type d'intervalle**, sélectionnez le type d'intervalle à utiliser sur la ligne du plan de maintenance, par exemple, « Répété… » ou « Une fois… ». Consultez le tableau [Vue d'ensemble des types d'intervalle](## Interval types overview) ci-dessous pour une description de la relation entre les types d'intervalle et les types de ligne.

15. Le champ **Période** est associé uniquement aux lignes de type basées sur l'heure. Sélectionnez le type de période associé à la fréquence de la période.

16. Dans le champ **Fréquence de la période**, insérez le nombre de fois où la ligne doit être utilisée pour planifier les tâches de maintenance préventive. Exemple : si vous avez créé une ligne de type « Compteur » et si votre compteur désigne la quantité en production, et si vous saisissez le numéro « 20 000 » dans ce champ, de nouvelles lignes de séquence de maintenance sont créées pendant la planification de la maintenance préventive chaque fois que vous devez produire 20 000 articles en plus.

17. La case à cocher **Supprimer les tâches de maintenance qui se chevauchent** fait référence aux lignes de type basées sur l'heure et basées sur le compteur. Cochez la case pour supprimer les entrées du programme de maintenance qui sont créées à la même date. Cela est utile si, par exemple, vous avez créé une ligne d'inspection d'un mois, une ligne d'inspection de 6 mois et une ligne d'inspection d'un an. Pour l'inspection d'un an, vous souhaitez uniquement que cette inspection soit effectuée, et pas les deux autres inspections, qui conviendraient également dans la période indiquée. Afin de paramétrer cet exemple correctement, vous paramétrez la ligne d'inspection annuelle comme la première ligne, la ligne d'inspection bi-annuelle comme deuxième ligne et la ligne d'inspection mensuelle comme troisième ligne, et vous cochez la case **Supprimer les tâches de maintenance qui se chevauchent** pour les lignes d'inspection mensuelle et bi-annuelle. De cette façon, vous veillez à ce que lorsque vous atteignez la marque annuelle, les inspections mensuelle et bi-annuelle sont omises, et une ligne du programme de maintenance est créée uniquement pour la ligne de l'inspection annuelle.

>[!NOTE]
>L'exemple décrit dans cette étape indique que la tâche la plus complète, qui contient le plus grand nombre de tâches, et qui n'est pas effectuée si souvent, doit toujours être saisie sur la première ligne. Les tâches plus fréquentes sont ensuite saisies sur des lignes distinctes dans l'ordre de fréquence, plaçant la tâche la plus fréquente en bas de la liste.

18. Le champ **Compteur** est associé uniquement aux lignes de type basées sur le compteur. Sélectionnez le type compteur à utiliser sur la ligne. Si un type compteur n'est pas actif sur un actif associé, la ligne du plan de maintenance est omise.

19. Le champ **Plage de gestion du compteur d'actif en jours** fait uniquement référence aux types de ligne basée sur compteur. Saisissez un numéro qui définit combien de jours en arrière les enregistrements de compteur sont vérifiés lorsque la planification du plan de maintenance est effectuée. Autrement dit, jusqu'à quelle date il convient de remonter pour l'utilisation des données (enregistrements de compteur existants) comme base du calcul de la tendance à déterminer combien de lignes du programme de maintenance sont créées.

>*Exemple :* Si des enregistrements de compteur sont prévus une fois par mois, vous pouvez insérer le numéro « 365 » dans ce champ, car la planification du plan de maintenance sera toujours basée sur les 12 derniers mois et par conséquent, créer des lignes du programme de maintenance selon la tendance de l'année précédente. D'autre part, si vous insérez le numéro « 10 » dans ce champ, vous prévoyez des enregistrements de compteur plus réguliers, par exemple, au quotidien. En d'autres termes, lorsque vous planifiez un plan de maintenance, les enregistrements de compteur pour les 10 derniers jours sont utilisés comme la base de la planification des lignes du programme de maintenance.

20. Le champ **Date de plan** est associé uniquement aux lignes de type basées sur l'heure. Si la ligne du plan de maintenance a une autre date de planification que le plan de maintenance entier, sélectionnez une date dans le champ **Date de plan** sur la ligne.

21. Dans le champ **Niveau de service**, vous pouvez sélectionner un niveau de service de l'ordre de travail comme une autre délimitation sur la ligne du plan de maintenance (à utiliser comme niveau de service sur les ordres de travail).

22. Cochez la case **Création automatique** si vous souhaitez qu'un ordre de travail soit créé automatiquement selon la ligne du plan de maintenance sélectionné lors de la planification des plans de maintenance.

23. Si vous avez coché la case **Création automatique**, vous pouvez sélectionner un type d'ordre de travail pour l'ordre de travail créé automatiquement dans le champ **Type d'ordre de travail**. Si vous avez coché la case **Création automatique**, et si vous ne sélectionnez pas un type d'ordre de travail dans ce champ, le type d'ordre de travail sélectionné dans **Gestion des actifs** > **Paramétrage** > **Paramètres de gestion des actifs** > **Ordres de travail** lien > champ **Type d'ordre de travail préventif** est utilisé.

24. Utilisez les champs **Saison de** et **Saison à** pour créer une ligne de plan de maintenance basée sur le temps répétée dans une période de 12 mois. *Exemple :* l'équipement utilisé pour préserver les espaces verts exige des opérations de maintenance chaque printemps dans un laps de temps prédéfini. Saisissez la date de début de la période à répéter dans le champ **Saison de**.

25. Saisissez la date de fin de la période à répéter dans le champ **Saison à**.

26. Dans le champ **Période résultante**, la période actuelle à répéter s'affiche. Une fois la période actuelle écoulée, et au début d'une nouvelle année, la période indiquée dans ce champ est mise à jour pour refléter la période suivante dans la séquence de répétition.

27. Dans l'organisateur **Actifs**, sélectionnez les actifs qui doivent être associés au plan de maintenance.

28. Dans l'organisateur **Types d'actif**, sélectionnez les types d'actif qui doivent être associés au plan de maintenance.

29. Dans l'organisateur **Postes techniques**, sélectionnez les postes techniques qui doivent être associés au plan de maintenance. Le cas échéant, vous pouvez rendre la configuration plus spécifique en sélectionnant un type d'actif, un fabricant et un modèle spécifiques.

30. Dans l'organisateur **Types de postes techniques**, sélectionnez les types de postes techniques qui doivent être associés au plan de maintenance.

>[!NOTE]
>Lorsque les ordres de travail sont créés manuellement sur les actifs couverts par une garantie fournisseur, une boîte de dialogue s'affiche pour indiquer la garantie à l'utilisateur. La création de l'ordre de travail peut être ensuite annulée. La vérification d'une relation de garantie est ignorée pour les ordres de travail qui sont automatiquement créés.

## <a name="interval-types-overview"></a>Vue d'ensemble des types d'intervalle

| Type et description de l'intervalle                                                                                                                                                                                                                                                                                                                                                                                                       | Type de ligne : heure                                                                                                                                                                                                                                                                                                                                                           | Type de ligne : compteur                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Type d'intervalle : répété depuis la date du plan** Le décompte commence à partir de la date de plan utilisée. Lorsque vous programmez des plans de maintenance, les lignes du programme de maintenance sont créées une fois l'intervalle atteint.                                                                                                                                                                                                                | La **Date du plan** sur la ligne du plan de maintenance est utilisée. Si aucune date de plan n'est sélectionnée sur la ligne, la **Date du plan** est utilisée pour le plan de maintenance. Exemple : Si le nombre « 3 » est inséré dans le champ **Fréquence de la période**, et si « Année » est sélectionné dans le champ **Période**, une nouvelle ligne du programme de maintenance est créée une fois tous les 3 ans.                             | La **Date du plan** pour le plan de maintenance est utilisée. Si le compteur a été remplacé, la date du dernier remplacement est utilisée comme date de plan.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Type d'intervalle : répété à partir de la date de début** Le décompte débute depuis la date de début sur la relation de l'actif. La date est sélectionnée dans la vue des détails **Tous les actifs** > organisateur **Plans de maintenance des actifs** > champ **Date de début**, ou dans la vue détaillée **Tous les postes techniques** > organisateur **Plans de maintenance** > champ **Date de début**. Lorsque vous programmez des plans de maintenance, une ligne du programme de maintenance est créée une fois l'intervalle atteint. | La date de début de la ligne du plan de maintenance sur l'actif ou le poste technique est utilisée. Si ce champ est vide, le champ **Date du plan** pour le plan de maintenance est utilisé.                                                                                                                                                                                                 | La date de début de la ligne du plan de maintenance sur l'actif ou le poste technique est utilisée. Si ce champ est vide, le champ **Date du plan** pour le plan de maintenance est utilisé.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Type d'intervalle : répété depuis le dernier ordre de travail** Le décompte commence à partir de la date de fin réelle et de l'heure à laquelle le dernier ordre de travail a été exécuté sur l'actif avec ce type de tâche de maintenance spécifique/la variante du type de tâche de maintenance/la combinaison des transactions. Cette date et cette heure sont affichées dans le champ **Fin réelle** dans la vue détaillée **Tous les ordres de travail**.                                                                                                                                 | La date de fin réelle et l'heure à laquelle l'ordre de travail a été effectué sur l'actif avec cette combinaison type de tâche de maintenance/variante du type de tâche de maintenance/transaction. Si aucun ordre de travail exécuté n'est disponible, une des dates utilisées dans le type d'intervalle « Répété depuis la date de début » décrite ci-dessus est utilisée à la place.                                                                                             | La date de fin réelle et l'heure à laquelle l'ordre de travail a été effectué sur l'actif *et* la combinaison type de tâche de maintenance/variante du type de tâche de maintenance/transaction. est utilisé. Si la date de fin et l'heure ne sont pas renseignées sur l'ordre de travail, une des dates utilisées dans le type d'intervalle « Répété depuis la date de début » décrite ci-dessus est utilisée à la place.                                                                                                                                                                                                                                                                                                                                                                           |
| **Type d'intervalle : une fois à partir de la date du plan** Voir la description pour le type d'intervalle « Répété depuis la date du plan » ci-dessus. La seule différence est que ce type d'intervalle doit être utilisé une seule fois.                                                                                                                                                                                                                                                   | Voir la description pour le type d'intervalle « Répété depuis la date de plan » ci-dessus. Cet intervalle est utilisé généralement pour une maintenance ou une tâche de service unique.                                                                                                                                                                                                                             | Voir la description pour le type d'intervalle « Répété depuis la date de plan » ci-dessus. Cet intervalle est utilisé généralement pour une maintenance ou une tâche de service unique. **Remarque 1 :** Ce type d'intervalle est pertinent uniquement si le compteur est remplacé chaque fois que vous exécutez une maintenance ou une tâche de service. Si, pour une quelconque raison, un compteur est remplacé avant la fin de l'intervalle planifié, une nouvelle heure est calculée pour la tâche depuis l'heure du remplacement du compteur. **Remarque 2 :** Si le compteur est remplacé lors de l'exécution de la maintenance ou de la tâche de service, ce type d'intervalle fonctionne comme le type d'intervalle « Répété depuis la date du plan » ci-dessus.                                             |
| **Type d'intervalle : une fois à partir de la date du début** Voir la description pour le type d'intervalle « Répété depuis la date de début » ci-dessus. La seule différence est que ce type d'intervalle doit être utilisé une seule fois.                                                                                                                                                                                                                                                 | Voir la description pour le type d'intervalle « Répété depuis la date de début » ci-dessus. Cet intervalle est utilisé généralement pour une maintenance ou une tâche de service unique.                                                                                                                                                                                                                            | Voir la description pour le type d'intervalle « Répété depuis la date de début » ci-dessus. Cet intervalle est utilisé généralement pour une maintenance ou une tâche de service unique. La **Remarque 1** s'applique ci-dessus à ce type d'intervalle. **Remarque 3 :** Si le compteur est remplacé lors de l'exécution de la maintenance ou de la tâche de service, ce type d'intervalle fonctionne comme le type d'intervalle « Répété depuis la date de début » ci-dessus.                                                                                                                                                                                                                                                                                                |
| **Type d'intervalle : Atteint une fois ci-dessus** Ce type d'intervalle a trait uniquement aux compteurs et est utilisé pour indiquer une limite supérieure configurée sur la ligne du plan de maintenance. Les entrées du programme de maintenance auront la date de début prévue et l'heure de l'enregistrement de compteur, ce qui signifie que ces entrées seront créées avec une date de début prévue équivalente ou antécédente à la date du système.                                                | N/A                                                                                                                                                                                                                                                                                                                                                                       | L'intervalle du compteur indique une limite supérieure. Si cette limite est dépassée lorsque vous créez un enregistrement de compteur, une ligne du programme de maintenance est créée lorsque vous programmez la maintenance préventive.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Type d'intervalle : Atteint une fois ci-dessous** Ce type d'intervalle a trait uniquement aux compteurs et est utilisé pour indiquer une limite inférieure configurée sur la ligne du plan de maintenance. Les entrées du programme de maintenance auront la date de début prévue et l'heure de l'enregistrement de compteur, ce qui signifie que ces entrées seront créées avec une date de début prévue équivalente ou antécédente à la date du système.                                                 | N/A                                                                                                                                                                                                                                                                                                                                                                       | L'intervalle du compteur indique une limite inférieure. Si cette limite est dépassée lorsque vous créez un enregistrement de compteur, une ligne du programme de maintenance est créée lorsque vous programmez la maintenance préventive.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Type d'intervalle : lié à la date de début** Ce type d'intervalle crée une seule ligne de programme de maintenance une seule fois. Un plan de maintenance peut contenir plusieurs lignes à l'aide de ce type d'intervalle, et ces lignes sont associées. Généralement, vous allez créer un plan de maintenance qui contient des lignes de ce type d'intervalle uniquement. Les lignes du programme de maintenance sont créées en identifiant la ligne du plan de maintenance qui a la date de début et l'heure prévues initialement.                                                                                                                                                                                                                                                                                                                                                                                           | Voir la description pour « Une fois depuis la date de début » ci-dessus. Exemple : vous créez deux lignes dans un plan de maintenance pour une tâche de service sur une voiture : une ligne basée sur l'heure avec une période d'un an, et une ligne basée sur le compteur avec une limite de 25 000 km. Une ligne du programme de maintenance est créée pour la limite atteinte initialement. Pour ce type de ligne, vous créez la ligne avec la période d'un an.                                                                                                                                                                                   | Voir la description pour « Une fois depuis la date de début » ci-dessus. Exemple : vous créez deux lignes dans un plan de maintenance pour une tâche de service sur une voiture : une ligne basée sur l'heure avec une période d'un an, et une ligne basée sur le compteur avec une limite de 25 000 km. Une ligne du programme de maintenance est créée pour la limite atteinte initialement. Pour ce type de ligne, vous créez la ligne avec la limite de 25 000 km. Exemple créant deux lignes de compteur : vous pouvez également configurer un plan de maintenance avec deux lignes basées sur le compteur, associées dans lesquelles la première ligne a une limite de 10 000 articles produits, et la seconde ligne a trait à la machine ou au centre de travail exigeant un service après 3 000 heures d'exploitation.                                                                                                                                                           |
| **Type d'intervalle : lié à partir du dernier ordre de travail** Ce type d'intervalle crée des lignes de programme à l'issue de chaque ordre de travail. Un plan de maintenance peut contenir plusieurs lignes à l'aide de ce type d'intervalle, et ces lignes sont associées. Généralement, vous allez créer un plan de maintenance qui contient des lignes de ce type d'intervalle uniquement. Les lignes du programme de maintenance sont créées en identifiant la ligne du plan de maintenance qui a la date de début et l'heure prévues initialement.                                                                                                                                                                                                                                                                        | Ce type d'intervalle fonctionne fondamentalement comme « Associé depuis la date de début » décrit ci-dessus. Seule la différence est la date sur laquelle le type d'intervalle est basé. La date utilisée est la date et l'heure réelles auxquelles l'ordre de travail a été effectué sur l'actif *et* la combinaison type de tâche de maintenance/variante du type de tâche de maintenance/transaction.                                                                                                                                                                                                                                                           | Ce type d'intervalle fonctionne fondamentalement comme « Associé depuis la date de début » décrit ci-dessus. Seule la différence est la date sur laquelle le type d'intervalle est basé. La date utilisée est la date et l'heure réelles auxquelles l'ordre de travail a été effectué sur l'actif *et* la combinaison type de tâche de maintenance/variante du type de tâche de maintenance/transaction.                                                                                                                   |


>[!NOTE]
>Lorsque les lignes du programme de maintenance sont créées pour les lignes du plan de maintenance basées sur l'heure, l'heure prévue est toujours au début de la journée. Pour les lignes du plan de maintenance basées sur le compteur, l'heure prévue peut être n'importe quelle heure de la journée.

Ci-dessous, vous trouverez des exemples de la configuration des lignes du plan de maintenance basées sur l'heure et sur le compteur :

**Exemple 1 - Ligne du plan de maintenance basée sur l'heure :** Une tâche de lubrification peut être configurée dans un intervalle fixe, survenant une fois par semaine. À ce titre, sélectionnez « Répété à partir de la date du plan » dans le champ **Type d'intervalle**. Découvrez un exemple dans l'illustration suivante.

![Figure 1](media/02-preventive-maintenance.png)

**Exemple 2 - Ligne du plan de maintenance basée sur l'heure :** une tâche d'inspection peut être configurée pour être exécutée environ une fois par semaine. À ce titre, sélectionnez « Répété à partir du dernier ordre de travail » dans le champ **Type d'intervalle**. Découvrez un exemple dans l'illustration suivante.

![Figure 2](media/03-preventive-maintenance.png)

**Exemple 3 - Ligne du plan de maintenance basée sur le compteur :** L'illustration graphique suivante présente un compteur horaire pour lequel une nouvelle ligne de programme de maintenance est créée toutes les 250 heures. Le type d'intervalle pour cette ligne basée sur le compteur est « Répété depuis la date de début ». La date de début est la date de début des actifs associés dans la vue des détails **Tous les actifs** > organisateur **Plans de maintenance des actifs** > champ **Date de début**, ou dans la vue détaillée **Poste technique** > organisateur **Plans de maintenance** > champ **Date de début**. C'est un exemple d'un plan de maintenance *préventive*, car la ligne du programme de maintenance est automatiquement créée chaque fois que le seuil (+ 250) est atteint.

![Figure 3](media/04-preventive-maintenance.png)


**Exemple 4 - Ligne du plan de maintenance basée sur le compteur :** L'illustration graphique suivante présente une baisse de la contre-valeur, mesurant l'usure des plaquettes de frein. Une ligne du programme de maintenance est créée lorsqu'un enregistrement de compteur inférieur à 20 mm est créé sur les plaquettes de frein. Le type d'intervalle pour cette ligne basée sur le compteur est « Une fois atteint en dessous » ou « Une fois depuis la dernière date de début ». C'est un exemple d'un plan de maintenance *réactive*, car la ligne du programme de maintenance n'est pas créée tant qu'une mesure inférieure à 20 mm n'est pas enregistrée.

![Figure 4](media/05-preventive-maintenance.png)


**Exemple 5 - Ligne du plan de maintenance basée sur le compteur :** l'illustration graphique suivante présente un compteur avec un seuil de -18° Celsius. Une ligne du programme de maintenance est créée lors d'un enregistrement de compteur au-dessus de -18° Celsius. Le type d'intervalle pour cette ligne basée sur le compteur est « Une fois atteint au-dessus ». C'est un exemple d'un plan de maintenance *réactive*, car la ligne du programme de maintenance n'est pas créée tant qu'une mesure supérieure à -18° Celsius n'est pas enregistrée.

![Figure 5](media/06-preventive-maintenance.png)

- Lorsque vous créez un actif, et lorsque cet actif utilise un type d'actif associé à un plan de maintenance, le plan de maintenance est automatiquement inséré dans l'organisateur **Tous les objets** > **Plans de maintenance des actifs**.' De plus, dans **Valeurs par défaut du type d'actif**, sous l'organisateur **Plans de maintenance**, les plans de maintenance associés sont automatiquement insérés.  
- Si vous ajoutez ou supprimez des types d'actif ou de poste technique dans **Plans de maintenance**, cette modification réfléchira uniquement aux nouveaux actifs créés après avoir apporté la modification.  
- Si vous ajoutez ou supprimez les actifs ou les postes techniques dans **Plans de maintenance**, cette modification est automatiquement mise à jour dans l'organisateur **Tous les actifs** > **Plans de maintenance des actifs**, ou dans l'organisateur **Tous les postes techniques** > **Plans de maintenance**.  

L'illustration suivante présente un exemple d'un plan de maintenance « Service du camion » sur la page **Plans de maintenance**.

![Figure 6](media/07-preventive-maintenance.png)


## <a name="add-a-maintenance-plan-to-an-asset"></a>Ajouter un plan de maintenance à un actif

1. Cliquez sur **Gestion des actifs** > **Commun** > **Actifs** > **Tous les actifs** ou **Actifs actifs**.

2. Sélectionnez l'actif pour lequel vous souhaitez paramétrer un plan de maintenance et cliquez sur **Modifier**.

3. Dans l'organisateur **Plans de maintenance des actifs**, cliquez sur **Ajouter une ligne** pour ajouter un plan de maintenance à l'actif.

4. Dans le champ **Plan de maintenance**, sélectionnez le plan de maintenance approprié.

5. Dans le champ **Date de début**, sélectionnez la date à partir de laquelle la planification des tâches de maintenance peut être exécutée. 

6. Cliquez sur **Enregistrer**. Le champ **Actif** est mis à jour automatiquement.

L'illustration suivante présente un exemple d'un plan de maintenance configuré sur un actif sur la page **Tous les actifs**.

![Figure 7](media/08-preventive-maintenance.png)

