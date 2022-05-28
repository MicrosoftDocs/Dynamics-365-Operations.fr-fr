---
title: Traiter la rémunération
description: Le traitement de la rémunération vous permet de calculer les nouveaux montants de rémunération de vos employés en fonction des augmentations pour mérite, des cibles d’augmentation au mérite et des performances.
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: e4aa910d92c2905d54d96f656e1d3d1c36388636
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693862"
---
# <a name="process-compensation"></a>Traiter la rémunération


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Le traitement de la rémunération vous permet de calculer les nouveaux montants de rémunération de vos employés en fonction des augmentations pour mérite, des cibles d’augmentation au mérite et des performances. Cette rubrique couvre le flux de base du traitement de la rémunération pour les régimes de rémunération fixe sans tenir compte des performances d’un employé.

## <a name="plan-the-new-compensation-amounts-and-budgets"></a>Organiser les nouveaux montants et budgets de rémunération
Pour attribuer à vos employés une augmentation pour mérite, vous devez paramétrer un budget d’augmentation fixe pour chacun de vos services : **Gestion des rémunérations** > **Liens** > **Cibles d’augmentation au mérite**. (Sinon, vous pouvez ouvrir cette page via le département : **Organisation** > **Départements**.) Vous pouvez mieux spécifier si les employés d’un certain syndicat ou site doivent obtenir un pourcentage d’augmentation différent. Les champs **Budget** et **Devise** sont donnés à titre indicatif et peuvent servir à noter un montant en devise pour le budget.

## <a name="set-up-the-compensation-process"></a>Configurer le processus de rémunération
Sur la page **Processus de rémunération**, vous pouvez spécifier les paramètres pour le traitement de la rémunération. Cela inclut la période de date à évaluer pour déterminer les montants de rémunération, et la date à laquelle les nouveaux montants de rémunération doivent entrer en vigueur.

Éventuellement, vous pouvez inclure une **Date d’embauche au prorata du salaire fixe** si l’un de vos régimes de rémunération fixe utilisent une règle d’embauche en pourcentage. Pour ces régimes, toute personne qui a été engagée après la date de **Début de cycle** et avant la **Date d’embauche au prorata du salaire fixe** recevra 100 % du mérite calculé ou de la hausse générale. Toute personne ayant été embauchée après la **Date d’embauche au prorata du salaire fixe** et avant la **Date de fin du cycle** recevra une partie de son augmentation calculée en fonction de la durée des jours du cycle total pendant lesquels elle a été employée. Par exemple, si votre cycle court du 1er janvier au 31 décembre et que la date d’embauche au prorata du salaire fixe est le 1er avril, un employé qui est engagé en mars recevra l’augmentation calculée complète alors qu’un employé embauché le 1er juillet recevra environ la moitié de l’augmentation calculée.

L’événement de processus **Moment donné** est uniquement utilisée pour traiter certains régimes de rémunération variable et n’est pas couverte ici. La **Date limite de révision** est la date limite pour émettre toutes les recommandations afin que les nouveaux montants de rémunération puissent être chargés dans l’enregistrement de l’employé. La date de révision n’est fournie qu’à titre d’information.

Une fois que les paramètres de l’événement des traitements de données ont été enregistrés, vous pouvez cliquer sur le bouton **Paramétrage** pour indiquer les régimes à inclure lorsque ce processus est exécuté et les actions de rémunération fixe à effectuer pour chaque régime.

Cliquez sur le bouton **Ajouter** sous l’onglet **Régimes** pour ajouter un régime de rémunération à l’événement de processus. Les colonnes **Utiliser un autre chiffre**, **Facteur de chiffre** et **Description du chiffre** sont utilisées uniquement pour les régimes de rémunération variable et ne doivent pas être inclus dans cette rubrique.

Sauvegardez l’enregistrement, puis cliquez sur le bouton **Ajouter** sous l’onglet **Actions** pour ajouter des actions de rémunération fixe du régime sélectionné. Utilisez l’option **Activer les recommandations** pour entrer un montant différent de l’augmentation indicative calculée pour l’action. Pour calculer une action basée sur le résultat de l’action précédente pour lier plusieurs actions de compensation, cochez la case **Utiliser le résultat précédent**. Les actions de rémunération fixe sont des types de logique de rémunération auxquels vous pouvez donner des noms descriptifs. Pour les régimes **Niveau** et **Structure**, vous ne pouvez ajouter que les actions de rémunération fixe qui sont des types suivants :

| Type Action de rémunération fixe | Fonctionnalité                  |
|-------------------------------|-------------------------------------------------------------------------|
| Capitaux propres                        | Les actions de capitaux propres compareront le taux de salaire de l’employé à partir de la date de fin de cycle avec le plus faible point de référence pour le niveau défini dans la tâche de l’employé. Si le taux du salaire de l’employé est inférieur au point de référence minimale, l’augmentation nécessaire pour que l’employé soit au point minimum de la plage est calculée.                                                                                |
| Mérite                         | Les actions au mérite calculeront l’augmentation en fonction du taux de salaire de l’employé à partir de la date de fin de cycle et le pourcentage d’augmentation dans le budget d’augmentation fixe pour le département, le syndicat et le site de travail de l’employé.                                                                                                                                                                                         |
| Général                       | Les actions générales calculeront une augmentation basée sur un pourcentage ou l’octroi aux employés d’un montant fixe. Cela est déterminé sur les paramètres de la **rémunération fixe** sous l’onglet **Général**.                                                                                                                                                                                                                        |
| Promotion                     | Les actions de promotion vous fournissent un endroit nommé où vous pouvez attribuer des augmentations. Cochez l’option **Activer la recommandation** pour saisir une recommandation pour les employés qui recevront des promotions.  Les employés sans augmentation recommandée n’ont pas l’action **Promotion** ajoutée à leurs enregistrements de rémunération fixe.                                                                       |
| Autre changement de niveau            | Dans l’exemple précédent, **Rétrogradation** est le nom de l’action de **rémunération fixe** avec un type **Autre changement de niveau**. Cela génère une augmentation indicative 0 (modification zéro) afin que vous puissiez entrer un montant de recommandation pour ajuster le taux de rémunération de l’employé. (Sélectionnez l’option **Activer les recommandations**.) Les employés sans recommandation n’ont pas cette action ajoutée à leurs enregistrements de rémunération fixe. |

Vous ne pouvez ajouter des actions de **rémunération fixe** avec un type de régime par étapes.

| Type Action de rémunération fixe | Fonctionnalité                |
|--------------------------------|------------------------------|
| Etape                           | Sous l’onglet **Général**, indiquez si cette action d’étape doit faire passer les employés à l’étape 0, à l’étape 1 ou aux deux étapes.                                                                                  |
|                                | **Étapes 0** – L’employé reçoit le taux de salaire pour l’étape actuelle à laquelle il se situe.                                                                                                                      |
|                                | **Étape 1** – Le système vérifie si l’employé est déjà au dernier point de référence pour son niveau.                                                                                             |
|                                | **2 étapes** – L’employé avancera de deux étapes par rapport à son niveau actuel. L’employé ne peut que se déplacer d’une ou de zéro étape s’il atteint le dernier point de référence pour son niveau. |

## <a name="run-the-compensation-process"></a>Exécuter le processus de rémunération
Une fois l’événement de processus paramétré avec les champs de date, de régimes et d’actions nécessaires, cliquez sur **Exécuter le processus** dans la page **Événement de processus** ; cela ouvre la boîte de dialogue **Exécuter les événements de processus de rémunération**. Cliquez sur l’option **Afficher les résultats du traitement** pour connaître le mode de calcul des montants de rémunération pour chaque employé. Cliquer sur **Ajouter** exécutera le processus de rémunération pour tous les employés affectés à des régimes de rémunération à la date de fin du cycle.

## <a name="view-the-process-results"></a>Afficher les résultats du processus
Pour afficher les résultats de processus, ouvrez la page **Résultats du processus**. Un nouvel événement de rémunération est créé chaque fois que l’événement de processus est exécuté. Cela permet d’effectuer des tests, effectuer des ajustements et exécuter l’événement de rémunération plusieurs fois pour voir comment les différentes modifications impactent la rémunération des employés.

La page **Résultats du processus** contient des informations sur le processus exécuté notamment lors de l’exécution, l’utilisateur ayant effectué le processus, et si des erreurs se sont produites lors du processus. Cochez l’option **Verrouillé** pour désactiver le bouton **Charger la rémunération** et empêcher toute personne de charger les événements de rémunération dans les enregistrements des employés. Cliquer sur le bouton **Résultats des employés** permet d’afficher la liste des employés inclus dans l’exécution.

L’option **Résultats des employés** fournit des informations sur le processus lui-même, ainsi que toutes actions de rémunération exécutées en cours du processus. La section **Rémunération fixe** contient un enregistrement pour chaque action incluse dans l’événement de processus du régime de rémunération. Les colonnes **Directives actuelles** et **Recommandations** affichent plus d’informations sur l’action sélectionnée dans la section **Rémunération fixe**. Si **Activer les recommandations** a été marqué pour l’action, les champs **Recommandation** sont modifiables. Cela vous permettra d’ajuster manuellement les montants pour l’employé. Notez que si vous avez coché **Utiliser le résultat précédent** pour l’action sous Événement de processus, vous devez mettre à jour manuellement les montants de toutes les actions dépendantes.

Lorsque les montants de rémunération ont été revus pour un employé et que les ajustements ont été effectués pour les valeurs recommandées, vous pouvez modifier le **Statut** de la ligne **Événement d’employé** pour indiquer si l’événement a été approuvé ou doit être ignoré. Le cas échéant, vous pouvez effacer toutes les modifications apportées à la recommandation de l’employé en cliquant sur le bouton **Recalculer**. Cela marquera l’événement employé existant avec un statut Ignorer et créera un nouvel événement d’employé avec des valeurs recalculées.

## <a name="loading-approved-compensation-changes"></a>Chargement des modifications de rémunération approuvées
Une fois qu’un ou que plusieurs événements d’employé ont reçu leur statut mis à jour et **Approuvé**, ils peuvent être chargés dans les enregistrements de rémunération fixe des employés. Cela peut se faire, soit en sélectionnant chaque événement d’employé et en cliquant sur le bouton **Charger la rémunération d’employé** dans la page **Résultats des employés**, soit en cliquant sur **Charger la rémunération** dans la page **Résultats du processus** pour charger tous les événements d’employé approuvés simultanément.

Cliquer sur **OK** dans la boîte de dialogue **Charger la rémunération** permet d’ajouter des lignes d’action de rémunération autre que zéro à la page **Rémunération fixe de l’employé**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
