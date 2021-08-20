---
title: Plans de maintenance
description: Cette rubrique explique les plans de maintenance dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan, EntAssetObjectType, EntAssetCounterType, EntAssetWorkOrderLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7c74505c1771354aba42ddd9df2b7eaff8f5bc4653675244be99c4ef8afa73f6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740741"
---
# <a name="maintenance-plans"></a>Plans de maintenance

[!include [banner](../../includes/banner.md)]

Un plan de maintenance définit le moment de l’exécution d’une tâche de maintenance préventive pré-planifiée sur un actif. Les plans de maintenance peuvent être associés aux actifs, aux types d’actifs, aux postes techniques ou aux types de postes techniques. Cependant, vous devez tout d’abord créer les plans de maintenance à utiliser dans votre société.

Un plan de maintenance peut avoir plusieurs lignes de plan de maintenance. Le type de tâche de maintenance et les intervalles sont précisés sur la ligne du plan de maintenance. Il y a deux types de lignes de plan de maintenance :

- Heure
- Compteur

Les lignes de plan de maintenance de type « Heure » sont utilisées pour la maintenance planifiée récurrente basée sur un intervalle fixe. Les lignes de plan de maintenance de type « Compteur » sont utilisées pour la maintenance prévue ou la maintenance réactive selon les enregistrements de compteur d’actifs. Un plan de maintenance peut être constitué de plusieurs lignes des deux types.

>[!NOTE]
>Si aucune contre-valeur n’a été enregistrée pour un type de compteur sur un actif, les lignes du plan de maintenance sont omises.

Tout d’abord, créez les plans de maintenance dont vous avez besoin pour vos tâches de maintenance préventive et sélectionnez les types d’actif, les actifs, les types de poste technique et les postes techniques qui doivent être associés à chaque plan de maintenance. Ensuite, le cas échéant, vous pouvez également ajouter des plans de maintenance à un actif ou un poste technique. Pour cela, accédez à **Tous les actifs** \> Sélectionner un actif \> raccourci **Plans de maintenance des actifs** ou à **Tous les postes techniques** \> Sélectionner un poste technique \> raccourci **Plans de maintenance**.

Si vous ajoutez un plan de maintenance aux types d’actif ou aux types de poste technique, cela signifie que lorsque vous créez de nouveaux actifs ou postes techniques avec ces types d’actif ou de poste technique, l’actif ou le poste technique sera automatiquement ajouté au plan de maintenance. La date de début de la relation à un plan de maintenance sera la date actuelle, qui nécessitera peut-être un ajustement.

## <a name="set-up-maintenance-plans"></a>Définir des plans de maintenance

Cette section décrit comment configurer des lignes de plan de maintenance et offrir des exemples sur la manière dont elles peuvent être utilisées.

1. Accédez à **Gestion des actifs \> Paramétrage \> Maintenance préventive \> Plans de maintenance**.

1. Sélectionnez **Nouveau** pour créer une séquence.

1. Insérez un ID dans le champ **Séquence de maintenance**, et un nom de compteur dans le champ **Nom**.

1. Dans le champ **Date de planification**, insérez la date de début de la planification sur le plan de maintenance. Notez que les lignes de plan de maintenance basées sur les heures peuvent avoir d’autres dates de plan.

1. Sélectionnez » Oui » dans le bouton à bascule **Actif** pour activer le plan de maintenance.

    >[!NOTE]
    >Si vous désactivez un plan de maintenance, aucune publication de programme ne sera créée dans le programme de maintenance lorsque vous exécutez une tâche du plan de maintenance du programme.

1. Les champs **Jours de tolérance avant** et **Jours de tolérance après** font référence aux lignes du plan de maintenance dans lesquelles la case **Supprimer les tâches de maintenance qui se chevauchent** est cochée (consultez l’étape 17). Les champs « Tolérance » sont utilisés pour étendre l’intervalle en jours pendant lesquels, en cas de chevauchement de plusieurs plans de maintenance, la tâche la plus complète/importante est créée comme ligne de programme de maintenance pendant la planification du plan de maintenance, même si des tâches plus fréquentes qui se chevauchent sont omises pendant la planification du plan de maintenance. Saisissez le nombre de jours dans le champ **Jours de tolérance avant**, par exemple « 2 ».

1. Si vous avez créé une valeur dans champ **Jours de tolérance avant**, insérez également le nombre de jours dans le champ **Jours de tolérance après**, par exemple « 2 ».

    >[!NOTE]
    >L’exemple décrit dans cette étape, et dans la précédente, signifie que si plusieurs lignes du plan de maintenance se chevauchent, et si la case **Supprimer les tâches de maintenance qui se chevauchent** est cochée pour une ou plusieurs lignes, la période d’omission des lignes du programme de maintenance est étendue à un total de cinq jours (la date de début prévue sur la ligne du programme de maintenance *et* deux jours avant *et* deux jours après cette date).

1. Les champs du groupe **Détails** sur l’organisateur **Détails** affichent plusieurs lignes du plan de maintenance configurées sur le plan de maintenance et le nombre d’actifs et de postes techniques associés au plan de maintenance.

1. Dans le raccourci **Lignes**, sélectionnez **Ajouter une ligne d’heure** ou **Ajouter une ligne de compteur d’actifs** pour créer une ligne du plan de maintenance.

1. Saisissez une description pour la ligne dans le champ **Description de l’ordre de travail**. La description est transférée vers les ordres de travail associés.

1. Dans le champ **Type de tâche de maintenance**, sélectionnez le type de tâche auquel la ligne du plan de maintenance est associée.

1. Dans les champs **Variante du type de tâche de maintenance** et **Transaction**, sélectionnez la variante et la transaction associées au type de tâche de maintenance.

1. Dans les champs **Délai de fin en jours** et **Délai de fin en heures**, vous pouvez saisir une date de fin prévue en jours ou en heures. La date de fin prévue est saisie par rapport à la date de début prévue, qui est calculée lorsque les lignes du programme de maintenance sont créées. Par exemple, vous pouvez insérer « 7 » dans le champ **Délai de fin en jours** pour indiquer que la tâche associée doit être terminée sous une semaine à compter de la date de début prévue.

1. Dans le champ **Type d’intervalle**, sélectionnez le type d’intervalle à utiliser sur la ligne du plan de maintenance, par exemple, « Répété… » ou « Une fois… ». Consultez le tableau [Vue d’ensemble des types d’intervalle](#interval-types) ci-dessous pour une description de la relation entre les types d’intervalle et les types de ligne.

1. Le champ **Période** est associé uniquement aux lignes de type basées sur l’heure. Sélectionnez le type de période associé à la fréquence de la période.

1. Dans le champ **Fréquence de la période**, insérez le nombre de fois où la ligne doit être utilisée pour planifier les tâches de maintenance préventive. Exemple : si vous avez créé une ligne de type « Compteur » et si votre compteur désigne la quantité en production, et si vous saisissez le numéro « 20 000 » dans ce champ, de nouvelles lignes de séquence de maintenance sont créées pendant la planification de la maintenance préventive chaque fois que vous devez produire 20 000 articles en plus.

1. La case à cocher **Supprimer les tâches de maintenance qui se chevauchent** fait référence aux types de lignes basées sur l’heure et basées sur le compteur. Cochez la case pour supprimer les entrées du programme de maintenance qui sont créées à la même date. Cela est utile si, par exemple, vous avez créé une ligne d’inspection d’un mois, une ligne d’inspection de 6 mois et une ligne d’inspection d’un an. Pour l’inspection d’un an, vous souhaitez uniquement que cette inspection soit effectuée, et pas les deux autres inspections, qui conviendraient également dans la période indiquée. Afin de paramétrer cet exemple correctement, vous paramétrez la ligne d’inspection annuelle comme la première ligne, la ligne d’inspection bi-annuelle comme deuxième ligne et la ligne d’inspection mensuelle comme troisième ligne, et vous cochez la case **Supprimer les tâches de maintenance qui se chevauchent** pour les lignes d’inspection mensuelle et bi-annuelle. De cette façon, vous veillez à ce que lorsque vous atteignez la marque annuelle, les inspections mensuelle et bi-annuelle sont omises, et une ligne du programme de maintenance est créée uniquement pour la ligne de l’inspection annuelle.

    >[!NOTE]
    >L’exemple décrit dans cette étape indique que la tâche la plus complète, qui contient le plus grand nombre de tâches, et qui n’est pas effectuée si souvent, doit toujours être saisie sur la première ligne. Les tâches plus fréquentes sont ensuite saisies sur des lignes distinctes dans l’ordre de fréquence, plaçant la tâche la plus fréquente en bas de la liste.

1. Le champ **Compteur** est associé uniquement aux lignes de type basées sur le compteur. Sélectionnez le type compteur à utiliser sur la ligne. Si un type compteur n’est pas actif sur un actif associé, la ligne du plan de maintenance est omise.

1. Le champ **Plage de gestion du compteur d’actif en jours** fait uniquement référence aux types de ligne basée sur compteur. Saisissez un numéro qui définit combien de jours en arrière les enregistrements de compteur sont vérifiés lorsque la planification du plan de maintenance est effectuée. Autrement dit, jusqu’à quelle date il convient de remonter pour l’utilisation des données (enregistrements de compteur existants) comme base du calcul de la tendance à déterminer combien de lignes du programme de maintenance sont créées.

    >*Exemple :* Si des enregistrements de compteur sont prévus une fois par mois, vous pouvez insérer le numéro « 365 » dans ce champ, car la planification du plan de maintenance sera toujours basée sur les 12 derniers mois et par conséquent, créer des lignes du programme de maintenance selon la tendance de l’année précédente. D’autre part, si vous insérez le numéro « 10 » dans ce champ, vous prévoyez des enregistrements de compteur plus réguliers, par exemple, au quotidien. En d’autres termes, lorsque vous planifiez un plan de maintenance, les enregistrements de compteur pour les 10 derniers jours sont utilisés comme la base de la planification des lignes du programme de maintenance.

1. Le champ **Date de plan** est associé uniquement aux lignes de type basées sur l’heure. Si la ligne du plan de maintenance a une autre date de planification que le plan de maintenance entier, sélectionnez une date dans le champ **Date de plan** sur la ligne.

1. Dans le champ **Niveau de service**, vous pouvez sélectionner un niveau de service de l’ordre de travail comme une autre délimitation sur la ligne du plan de maintenance (à utiliser comme niveau de service sur les ordres de travail).

1. Cochez la case **Création automatique** si vous souhaitez qu’un ordre de travail soit créé automatiquement selon la ligne du plan de maintenance sélectionné lors de la planification des plans de maintenance.

1. Si vous avez coché la case **Création automatique**, vous pouvez sélectionner un type d’ordre de travail pour l’ordre de travail créé automatiquement dans le champ **Type d’ordre de travail**. Si vous avez coché la case **Création automatique** et si vous ne sélectionnez pas un type d’ordre de travail dans ce champ, le type d’ordre de travail sélectionné dans **Gestion des actifs \> Paramétrage \> Paramètres de gestion des actifs \> Ordres de travail** lien \> champ **Type d’ordre de travail préventif** est utilisé.

1. Utilisez les champs **Saison de** et **Saison à** pour créer une ligne de plan de maintenance basée sur le temps répétée dans une période de 12 mois. *Exemple :* l’équipement utilisé pour préserver les espaces verts exige des opérations de maintenance chaque printemps dans un laps de temps prédéfini. Saisissez la date de début de la période à répéter dans le champ **Saison de**.

1. Saisissez la date de fin de la période à répéter dans le champ **Saison à**.

1. Dans le champ **Période résultante**, la période actuelle à répéter s’affiche. Une fois la période actuelle écoulée, et au début d’une nouvelle année, la période indiquée dans ce champ est mise à jour pour refléter la période suivante dans la séquence de répétition.

1. Dans l’organisateur **Actifs**, sélectionnez les actifs qui doivent être associés au plan de maintenance.

1. Dans l’organisateur **Types d’actif**, sélectionnez les types d’actif qui doivent être associés au plan de maintenance.

1. Dans l’organisateur **Postes techniques**, sélectionnez les postes techniques qui doivent être associés au plan de maintenance. Le cas échéant, vous pouvez rendre la configuration plus spécifique en sélectionnant un type d’actif, un fabricant et un modèle spécifiques.

1. Dans l’organisateur **Types de postes techniques**, sélectionnez les types de postes techniques qui doivent être associés au plan de maintenance.

>[!NOTE]
>Lorsque les ordres de travail sont créés manuellement sur les actifs couverts par une garantie fournisseur, une boîte de dialogue s’affiche pour indiquer la garantie à l’utilisateur. La création de l’ordre de travail peut être ensuite annulée. La vérification d’une relation de garantie est ignorée pour les ordres de travail qui sont automatiquement créés.

<a id="interval-types"></a>

## <a name="interval-types-overview"></a>Vue d’ensemble des types d’intervalle

| Type et description de l’intervalle | Type de ligne : heure | Type de ligne : compteur |
|---|---|---|
| **Type d’intervalle : répété depuis la date du plan** Le décompte commence à partir de la date de plan utilisée. Lorsque vous programmez des plans de maintenance, les lignes du programme de maintenance sont créées une fois l’intervalle atteint. | La **Date du plan** sur la ligne du plan de maintenance est utilisée. Si aucune date de plan n’est sélectionnée sur la ligne, la **Date du plan** est utilisée pour le plan de maintenance. Exemple : Si le nombre « 3 » est inséré dans le champ **Fréquence de la période**, et si « Année » est sélectionné dans le champ **Période**, une nouvelle ligne du programme de maintenance est créée une fois tous les 3 ans. | La **Date du plan** pour le plan de maintenance est utilisée. Si le compteur a été remplacé, la date du dernier remplacement est utilisée comme date de plan. |
| **Type d’intervalle : répété à partir de la date de début** Le décompte débute depuis la date de début sur la relation de l’actif. La date est sélectionnée dans la vue détaillée **Tous les actifs** \> raccourci **Plans de maintenance des actifs** \> champ **Date de début**, ou dans la vue détaillée **Tous les postes techniques** \> raccourci **Plans de maintenance** \> champ **Date de début**. Lorsque vous programmez des plans de maintenance, une ligne du programme de maintenance est créée une fois l’intervalle atteint. | La date de début de la ligne du plan de maintenance sur l’actif ou le poste technique est utilisée. Si ce champ est vide, le champ **Date du plan** pour le plan de maintenance est utilisé. | La date de début de la ligne du plan de maintenance sur l’actif ou le poste technique est utilisée. Si ce champ est vide, le champ **Date du plan** pour le plan de maintenance est utilisé. |
| **Type d’intervalle : répété depuis le dernier ordre de travail** Le décompte commence à partir de la date de fin réelle et de l’heure à laquelle le dernier ordre de travail a été exécuté sur l’actif avec ce type de tâche de maintenance spécifique/la variante du type de tâche de maintenance/la combinaison des transactions. Cette date et cette heure sont affichées dans le champ **Fin réelle** dans la vue détaillée **Tous les ordres de travail**. | La date de fin réelle et l’heure à laquelle l’ordre de travail a été effectué sur l’actif avec cette combinaison type de tâche de maintenance/variante du type de tâche de maintenance/transaction. Si aucun ordre de travail exécuté n’est disponible, une des dates utilisées dans le type d’intervalle « Répété depuis la date de début » décrite ci-dessus est utilisée à la place. | La date de fin réelle et l’heure à laquelle l’ordre de travail a été effectué sur l’actif *et* la combinaison type de tâche de maintenance/variante du type de tâche de maintenance/transaction. est utilisé. Si la date de fin et l’heure ne sont pas renseignées sur l’ordre de travail, une des dates utilisées dans le type d’intervalle « Répété depuis la date de début » décrite ci-dessus est utilisée à la place. |
| **Type d’intervalle : une fois à partir de la date du plan** Voir la description pour le type d’intervalle « Répété depuis la date du plan » ci-dessus. La seule différence est que ce type d’intervalle doit être utilisé une seule fois. | Voir la description pour le type d’intervalle « Répété depuis la date de plan » ci-dessus. Cet intervalle est utilisé généralement pour une maintenance ou une tâche de service unique. | Voir la description pour le type d’intervalle « Répété depuis la date de plan » ci-dessus. Cet intervalle est utilisé généralement pour une maintenance ou une tâche de service unique. **Remarque 1 :** Ce type d’intervalle est pertinent uniquement si le compteur est remplacé chaque fois que vous exécutez une maintenance ou une tâche de service. Si, pour une quelconque raison, un compteur est remplacé avant la fin de l’intervalle planifié, une nouvelle heure est calculée pour la tâche depuis l’heure du remplacement du compteur. **Remarque 2 :** Si le compteur est remplacé lors de l’exécution de la maintenance ou de la tâche de service, ce type d’intervalle fonctionne comme le type d’intervalle « Répété depuis la date du plan » ci-dessus. |
| **Type d’intervalle : une fois à partir de la date du début** Voir la description pour le type d’intervalle « Répété depuis la date de début » ci-dessus. La seule différence est que ce type d’intervalle doit être utilisé une seule fois. | Voir la description pour le type d’intervalle « Répété depuis la date de début » ci-dessus. Cet intervalle est utilisé généralement pour une maintenance ou une tâche de service unique. | Voir la description pour le type d’intervalle « Répété depuis la date de début » ci-dessus. Cet intervalle est utilisé généralement pour une maintenance ou une tâche de service unique. La **Remarque 1** s’applique ci-dessus à ce type d’intervalle. **Remarque 3 :** Si le compteur est remplacé lors de l’exécution de la maintenance ou de la tâche de service, ce type d’intervalle fonctionne comme le type d’intervalle « Répété depuis la date de début » ci-dessus. |
| **Type d’intervalle : Atteint une fois ci-dessus** Ce type d’intervalle a trait uniquement aux compteurs et est utilisé pour indiquer une limite supérieure configurée sur la ligne du plan de maintenance. Les entrées du programme de maintenance auront la date de début prévue et l’heure de l’enregistrement de compteur, ce qui signifie que ces entrées seront créées avec une date de début prévue équivalente ou antécédente à la date du système. | Non applicable | L’intervalle du compteur indique une limite supérieure. Si cette limite est dépassée lorsque vous créez un enregistrement de compteur, une ligne du programme de maintenance est créée lorsque vous programmez la maintenance préventive. |
| **Type d’intervalle : Atteint une fois ci-dessous** Ce type d’intervalle a trait uniquement aux compteurs et est utilisé pour indiquer une limite inférieure configurée sur la ligne du plan de maintenance. Les entrées du programme de maintenance auront la date de début prévue et l’heure de l’enregistrement de compteur, ce qui signifie que ces entrées seront créées avec une date de début prévue équivalente ou antécédente à la date du système. | Non applicable | L’intervalle du compteur indique une limite inférieure. Si cette limite est dépassée lorsque vous créez un enregistrement de compteur, une ligne du programme de maintenance est créée lorsque vous programmez la maintenance préventive. |
| **Type d’intervalle : lié à la date de début** Ce type d’intervalle crée une seule ligne de programme de maintenance une seule fois. Un plan de maintenance peut contenir plusieurs lignes à l’aide de ce type d’intervalle, et ces lignes sont associées. Généralement, vous allez créer un plan de maintenance qui contient des lignes de ce type d’intervalle uniquement. Les lignes du programme de maintenance sont créées en identifiant la ligne du plan de maintenance qui a la date de début et l’heure prévues initialement. | Voir la description pour « Une fois depuis la date de début » ci-dessus. Exemple : vous créez deux lignes dans un plan de maintenance pour une tâche de service sur une voiture : une ligne basée sur l’heure avec une période d’un an, et une ligne basée sur le compteur avec une limite de 25 000 km. Une ligne du programme de maintenance est créée pour la limite atteinte initialement. Pour ce type de ligne, vous créez la ligne avec la période d’un an. | Voir la description pour « Une fois depuis la date de début » ci-dessus. Exemple : vous créez deux lignes dans un plan de maintenance pour une tâche de service sur une voiture : une ligne basée sur l’heure avec une période d’un an, et une ligne basée sur le compteur avec une limite de 25 000 km. Une ligne du programme de maintenance est créée pour la limite atteinte initialement. Pour ce type de ligne, vous créez la ligne avec la limite de 25 000 km. Exemple créant deux lignes de compteur : vous pouvez également configurer un plan de maintenance avec deux lignes basées sur le compteur, associées dans lesquelles la première ligne a une limite de 10 000 articles produits, et la seconde ligne a trait à la machine ou au centre de travail exigeant un service après 3 000 heures d’exploitation. |
| **Type d’intervalle : lié à partir du dernier ordre de travail** Ce type d’intervalle crée des lignes de programme à l’issue de chaque ordre de travail. Un plan de maintenance peut contenir plusieurs lignes à l’aide de ce type d’intervalle, et ces lignes sont associées. Généralement, vous allez créer un plan de maintenance qui contient des lignes de ce type d’intervalle uniquement. Les lignes du programme de maintenance sont créées en identifiant la ligne du plan de maintenance qui a la date de début et l’heure prévues initialement. | Ce type d’intervalle fonctionne fondamentalement comme « Associé depuis la date de début » décrit ci-dessus. Seule la différence est la date sur laquelle le type d’intervalle est basé. La date utilisée est la date et l’heure réelles auxquelles l’ordre de travail a été effectué sur l’actif *et* la combinaison type de tâche de maintenance/variante du type de tâche de maintenance/transaction. | Ce type d’intervalle fonctionne fondamentalement comme « Associé depuis la date de début » décrit ci-dessus. Seule la différence est la date sur laquelle le type d’intervalle est basé. La date utilisée est la date et l’heure réelles auxquelles l’ordre de travail a été effectué sur l’actif *et* la combinaison type de tâche de maintenance/variante du type de tâche de maintenance/transaction. |
| **Type d’intervalle : répété sur la valeur agrégée (compteur uniquement)** Lorsque le plan de maintenance est exécuté, une ligne de maintenance planifiée est créée chaque fois que la valeur accumulée d’un compteur d’actifs atteint la fréquence de la période ou un multiple pair de la fréquence de la période. (La fréquence de la période est définie sur la ligne du plan de maintenance.)<p>Pour plus d’informations sur l’activation et l’utilisation de cette fonctionnalité, voir la section [Améliorations de la maintenance basée sur un compteur](#counter-based-maintenance) plus loin dans cette rubrique. | Non applicable | **Exemple :** un compteur d’heures est configuré pour l’actif AK-101. Une ligne du plan d’actifs est également configurée pour l’actif. Le type d’intervalle de cette ligne est *Répété sur la valeur agrégée (compteur uniquement)* et la fréquence de la période est *1 000*. Lorsque le plan de maintenance est exécuté, une ligne de maintenance planifiée est générée lorsque la valeur agrégée du compteur dépasse 1 000 heures. Ensuite, lorsque la valeur agrégée du compteur dépasse 2 000 heures, une autre ligne de maintenance planifiée est générée, et ainsi de suite pour toutes les 1 000 heures supplémentaires. |
| **Type d’intervalle : une fois sur la valeur agrégée (compteur uniquement)** Lorsque le plan de maintenance est exécuté, une ligne de maintenance planifiée est créée chaque fois que la valeur accumulée d’un compteur d’actifs atteint la fréquence de la période qui est définie sur la ligne du plan de maintenance.<p>Pour plus d’informations sur l’activation et l’utilisation de cette fonctionnalité, voir la section [Améliorations de la maintenance basée sur un compteur](#counter-based-maintenance). | Non applicable | **Exemple :** un compteur d’heures est configuré pour l’actif AK-101. Une ligne du plan d’actifs est également configurée pour l’actif. Le type d’intervalle de cette ligne est *Une fois sur la valeur agrégée (compteur uniquement)* et la fréquence de la période est *1 000*. Lorsque le plan de maintenance est exécuté, une ligne de maintenance planifiée est générée lorsque la valeur agrégée du compteur dépasse 1 000 heures. |

>[!NOTE]
>Lorsque les lignes du programme de maintenance sont créées pour les lignes du plan de maintenance basées sur l’heure, l’heure prévue est toujours au début de la journée. Pour les lignes du plan de maintenance basées sur le compteur, l’heure prévue peut être n’importe quelle heure de la journée.

Ci-dessous, vous trouverez des exemples de la configuration des lignes du plan de maintenance basées sur l’heure et sur le compteur :

**Exemple 1 - Ligne du plan de maintenance basée sur l’heure :** Une tâche de lubrification peut être configurée dans un intervalle fixe, survenant une fois par semaine. À ce titre, sélectionnez « Répété à partir de la date du plan » dans le champ **Type d’intervalle**. Découvrez un exemple dans l’illustration suivante.

![Une tâche de service configurée sur un intervalle fixe, qui est effectuée une fois par semaine.](media/02-preventive-maintenance.png "Une tâche de service configurée sur un intervalle fixe, qui se produit une fois par semaine")

**Exemple 2 - Ligne du plan de maintenance basée sur l’heure :** une tâche d’inspection peut être configurée pour être exécutée environ une fois par semaine. À ce titre, sélectionnez « Répété à partir du dernier ordre de travail » dans le champ **Type d’intervalle**. Découvrez un exemple dans l’illustration suivante.

![Une tâche d’inspection configurée pour être effectuée environ une fois par semaine.](media/03-preventive-maintenance.png "Une tâche d’inspection configurée pour être effectuée environ une fois par semaine")

**Exemple 3 - Ligne du plan de maintenance basée sur le compteur :** L’illustration graphique suivante présente un compteur horaire pour lequel une nouvelle ligne de programme de maintenance est créée toutes les 250 heures. Le type d’intervalle pour cette ligne basée sur le compteur est « Répété depuis la date de début ». La date de début est la date de début des actifs associés dans la vue détaillée **Tous les actifs** \> raccourci **Plans de maintenance des actifs** \> champ **Date de début**, ou dans la vue détaillée **Poste technique** \> raccourci **Plans de maintenance** \> champ **Date de début**. C’est un exemple d’un plan de maintenance *préventive*, car la ligne du programme de maintenance est automatiquement créée chaque fois que le seuil (+ 250) est atteint.

![Un compteur d’heures qui crée périodiquement des lignes de programme de maintenance.](media/04-preventive-maintenance.png "Un compteur d’heures qui crée périodiquement des lignes du programme de maintenance")

**Exemple 4 - Ligne du plan de maintenance basée sur le compteur :** L’illustration graphique suivante présente une baisse de la contre-valeur, mesurant l’usure des plaquettes de frein. Une ligne du programme de maintenance est créée lorsqu’un enregistrement de compteur inférieur à 20 mm est créé sur les plaquettes de frein. Le type d’intervalle pour cette ligne basée sur le compteur est « Une fois atteint en dessous » ou « Une fois depuis la dernière date de début ». C’est un exemple d’un plan de maintenance *réactive*, car la ligne du programme de maintenance n’est pas créée tant qu’une mesure inférieure à 20 mm n’est pas enregistrée.

![Une baisse de la valeur du compteur, mesurant l’usure des plaquettes de frein.](media/05-preventive-maintenance.png "Une baisse de la valeur du compteur, mesurant l’usure des plaquettes de frein")

**Exemple 5 - Ligne du plan de maintenance basée sur le compteur :** l’illustration graphique suivante présente un compteur avec un seuil de -18° Celsius. Une ligne du programme de maintenance est créée lors d’un enregistrement de compteur au-dessus de -18° Celsius. Le type d’intervalle pour cette ligne basée sur le compteur est « Une fois atteint au-dessus ». C’est un exemple d’un plan de maintenance *réactive*, car la ligne du programme de maintenance n’est pas créée tant qu’une mesure supérieure à -18° Celsius n’est pas enregistrée.

![Un compteur avec un seuil de -18° Celsius.](media/06-preventive-maintenance.png "Un compteur avec un seuil de -18° Celsius")

- Lorsque vous créez un actif et que cet actif utilise un type d’actif associé à un plan de maintenance, le plan de maintenance est automatiquement inséré dans le raccourci **Tous les objets \> Plans de maintenance des actifs**. De plus, dans **Valeurs par défaut du type d’actif**, sous l’organisateur **Plans de maintenance**, les plans de maintenance associés sont automatiquement insérés.
- Si vous ajoutez ou supprimez des types d’actif ou de poste technique dans **Plans de maintenance**, cette modification réfléchira uniquement aux nouveaux actifs créés après avoir apporté la modification.
- Si vous ajoutez ou supprimez des actifs ou des postes techniques dans **Plans de maintenance**, cette modification est automatiquement mise à jour dans le raccourci **Tous les actifs \> Plans de maintenance des actifs**, ou dans le raccourci **Tous les postes techniques \> Plans de maintenance**.

L’illustration suivante présente un exemple d’un plan de maintenance « Service du camion » sur la page **Plans de maintenance**.

![Un exemple de plan de maintenance de service de camion.](media/07-preventive-maintenance.png "Un exemple de plan de maintenance de service de camion")

## <a name="add-a-maintenance-plan-to-an-asset"></a>Ajouter un plan de maintenance à un actif

1. Accédez à **Gestion des actifs \> Commun \> Actifs \> Tous les Actifs** ou **Actifs actifs**.

1. Sélectionnez l’actif pour lequel vous souhaitez paramétrer un plan de maintenance et sélectionnez **Modifier**.

1. Dans le raccourci **Plans de maintenance des actifs**, sélectionnez **Ajouter une ligne** pour ajouter un plan de maintenance à l’actif.

1. Dans le champ **Plan de maintenance**, sélectionnez le plan de maintenance approprié.

1. Dans le champ **Date de début**, sélectionnez la date à partir de laquelle la planification des tâches de maintenance peut être exécutée. 

1. Sélectionnez **Enregistrer**. Le champ **Actif** est mis à jour automatiquement.

L’illustration suivante présente un exemple d’un plan de maintenance configuré sur un actif sur la page **Tous les actifs**.

![Un exemple de plans de maintenance configurés sur un actif.](media/08-preventive-maintenance.png "Un exemple de plans de maintenance configurés sur un actif")

<a id="counter-based-maintenance"></a>

## <a name="counter-based-maintenance-enhancements"></a>Améliorations apportées à la maintenance par compteur

La fonctionnalité *Améliorations de la maintenance basée sur un compteur* introduit les fonctionnalités suivantes :

- Option pour insérer automatiquement un compteur qui a une valeur de *0* (zéro) lors de la création d’un actif. Cette option peut être utile lorsque vous utilisez la maintenance prédictive basée sur des compteurs. Lorsque la fonctionnalité *Améliorations de la maintenance basée sur un compteur* n’est pas utilisée, les compteurs qui ont une valeur de *0* (zéro) doivent être insérés manuellement.
- Possibilité de configurer un compteur afin qu’il soit automatiquement réinitialisé lors de la finalisation d’un ordre de travail. Cette fonctionnalité est utile lorsque vous souhaitez programmer la maintenance en fonction de la valeur agrégée depuis la fin du dernier ordre de travail.
- Un nouveau type d’intervalle du plan de maintenance nommé *Répété sur la valeur agrégée (compteur uniquement)*. Ce type déclenche la maintenance chaque fois qu’un compteur agrégé atteint un multiple d’une valeur spécifique. Par exemple, la maintenance peut être déclenchée toutes les 10 000 heures. Pour plus d’informations, voir la section [Vue d’ensemble des types d’intervalle](#interval-types) plus haut dans cette rubrique.
- Un autre nouveau type d’intervalle du plan de maintenance nommé *Une fois sur la valeur agrégée (compteur uniquement)*. Ce type déclenche la maintenance lorsqu’un compteur agrégé atteint un multiple d’une valeur spécifique, par exemple 8 000 heures. Pour plus d’informations, voir la section [Vue d’ensemble des types d’intervalle](#interval-types).

### <a name="turn-on-the-counter-based-maintenance-enhancements-feature"></a>Activer la fonctionnalité Améliorations de la maintenance basée sur un compteur

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des actifs*
- **Nom de la fonctionnalité :** *Améliorations de la maintenance basée sur un compteur*

### <a name="create-and-initialize-counters-when-an-asset-is-created"></a>Créer et initialiser des compteurs lors de la création d’un actif

Chaque fois que vous créez un actif, les compteurs d’actifs associés qui sont initialisés sur une valeur de *0* (zéro) peuvent être créés automatiquement, à condition de configurer votre système et de créer correctement l’actif.

1. Accédez à **Gestion des actifs \> Paramétrage \> Types d’actifs**.
1. Assurez-vous de disposer d’un type d’actif applicable à votre nouvel actif planifié. Créez un type d’actif selon vos besoins. Assurez-vous que tous les compteurs pertinents sont sélectionnés dans le raccourci **Compteurs**.
1. Accédez à **Gestion des actifs \> Paramétrage \> Types d’actifs \> Compteurs**.
1. Pour chaque compteur pertinent, assurez-vous que le champ **Agrégat total** est défini sur *Somme*.
1. Sur la page **Tous les actifs**, créez l’actif.
1. Définissez le champ **Type d’actif** sur le type d’actif que vous avez identifié ou créé à l’étape 2.
1. Terminez la configuration du nouvel actif selon vos besoins.
1. Accédez à **Gestion des actifs \> Recherches \> Actifs \> Compteurs**. Vous devriez pouvoir trouver les compteurs initialisés configurés pour votre nouvel actif.

> [!NOTE]
> Lorsque les compteurs d’actifs initialisés sont créés, on suppose que l’actif n’avait jamais été utilisé avant son ajout au système. Lorsque le programme de maintenance est exécuté pour la première fois, le calcul utilise la date et la valeur de compteur *0* (zéro) comme référence pour le calcul de la maintenance future. Si l’actif n’était pas nouveau lors de son ajout au système, vous pouvez ajuster manuellement la valeur du compteur afin qu’elle corresponde à la valeur réelle du compteur. Pour ajuster une valeur de compteur, ouvrez l’actif pertinent sur la page **Tous les actifs**, puis, dans le volet Actions, sous l’onglet **Actif**, dans le groupe **Préventif**, sélectionnez **Compteurs**. Sur la page **Compteurs d’actifs** de l’actif sélectionné, ajustez la valeur de la colonne **Valeur** pour l’enregistrement de compteur initial, selon vos besoins.

### <a name="automatically-reset-a-counter-value"></a>Réinitialiser automatiquement une valeur de compteur

Vous pouvez configurer le système pour réinitialiser automatiquement un compteur chaque fois qu’un ordre de travail pertinent atteint une valeur de statut sélectionnée.

1. Accédez à **Gestion des actifs \> Paramétrage \> Maintenance préventive \> Plans de maintenance**.
1. Dans le volet de liste, sélectionnez un plan de maintenance. La réinitialisation du compteur s’appliquera à tous les actifs qui utilisent ce plan.
1. Dans la section **Lignes**, recherchez une ligne du compteur d’actifs pour laquelle vous souhaitez réinitialiser un compteur et cochez la case **Réinitialiser le compteur** pour cette ligne. (Les lignes du compteur d’actifs ont une valeur dans la colonne **Compteur**. Le compteur spécifié dans cette colonne est le compteur qui sera réinitialisé pour l’actif pertinent.)
1. Accédez à **Gestion des actifs \> Paramétrage \> Ordres de travail \> États du cycle de vie**.
1. Dans le volet de liste, sélectionnez l’état du cycle de vie de l’ordre de travail sur lequel le compteur pertinent doit être réinitialisé.
1. Dans le raccourci **Général**, définissez l’option **Réinitialiser le compteur** sur *Oui*.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]