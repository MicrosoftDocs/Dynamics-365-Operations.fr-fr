---
title: Traiter la rémunération
description: Le traitement de la rémunération vous permet de calculer les nouveaux montants de rémunération de vos employés en fonction des augmentations pour mérite, des cibles d'augmentation au mérite et des performances.
author: andreabichsel
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 05f7be778857380d40a73d068e2b0b4fc7d1d1f6
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009017"
---
# <a name="process-compensation"></a>Traiter la rémunération

Le traitement de la rémunération vous permet de calculer les nouveaux montants de rémunération de vos employés en fonction des augmentations pour mérite, des cibles d'augmentation au mérite et des performances. Cet article couvre le flux de base du traitement de la rémunération pour les régimes de rémunération fixe sans tenir compte des performances d'un employé.

## <a name="plan-the-new-compensation-amounts-and-budgets"></a>Organiser les nouveaux montants et budgets de rémunération
Pour attribuer à vos employés une augmentation pour mérite, vous devez paramétrer un budget d'augmentation fixe pour chacun de vos services : Gestion des rémunérations > Liens > Cibles d'augmentation au mérite. (Sinon, vous pouvez ouvrir cet écran via le département : Organisation > Départements.) Vous pouvez mieux spécifier si les employés d'un certain syndicat ou site doivent obtenir un pourcentage d'augmentation différent. Les champs **Budget** et **Devise** sont donnés à titre indicatif et peuvent servir à noter un montant en devise pour le budget.

## <a name="set-up-the-compensation-process"></a>Configurer le processus de rémunération
Un événement de processus vous permet de spécifier les paramètres de traitement de rémunération. Cela inclut la période de date à évaluer pour déterminer les montants de rémunération, et la date à laquelle les nouveaux montants de rémunération doivent entrer en vigueur.

Éventuellement, vous pouvez inclure une date d'embauche au prorata du salaire fixe si l'un de vos régimes de rémunération fixe utilisent une règle d'embauche en pourcentage. Pour ces régimes, toute personne qui a été engagée après la date de début de cycle et avant la date d'embauche au prorata du salaire fixe recevra 100 % du mérite calculé ou de la hausse générale. Toute personne ayant été embauchée après la date d'embauche au prorata du salaire fixe et avant la date de fin du cycle recevra une partie de son augmentation calculée en fonction de la durée des jours du cycle total pendant lesquels elle a été employée. Par exemple, si notre cycle court du 1er janvier au 31 décembre et que la date d'embauche au prorata du salaire fixe est le 1er avril, un employé qui est engagé en mars recevra l'augmentation calculée complète alors qu'un employé embauché le 1er juillet recevra environ la moitié de l'augmentation calculée.

L'événement de processus **Moment donné** est uniquement utilisée pour traiter certains régimes de rémunération variable et n'est pas couverte ici. La **Date limite de révision** est la date limite pour émettre toutes les recommandations afin que les nouveaux montants de rémunération puissent être chargés dans l'enregistrement de l'employé. La date de révision n'est fournie qu'à titre d'information.

Une fois que les paramètres de l'événement des traitements de données ont été enregistrés, vous pouvez cliquer sur le bouton **Paramétrage** pour indiquer les régimes à inclure lorsque ce processus est exécuté et les actions de rémunération fixe à effectuer pour chaque régime.

Cliquez sur le bouton **Ajouter** sous l'onglet **Régimes** pour ajouter un régime de rémunération à l'événement de processus. Les colonnes **Utiliser un autre chiffre**, **Facteur de chiffre** et **Description du chiffre** sont utilisées uniquement pour les régimes de rémunération variable et ne doivent pas être inclus dans cet article.

Sauvegardez l'enregistrement, puis cliquez sur le bouton **Ajouter** sous l'onglet **Actions** pour ajouter des actions de rémunération fixe du régime sélectionné. Utilisez l'option **Activer les recommandations** pour entrer un montant différent de l'augmentation indicative calculée pour l'action. Pour calculer une action selon le résultat de l'action précédente permettant de lier plusieurs actions de rémunération, activez l'option **Utiliser le résultat précédent**. Les actions de rémunération fixe sont des types de logique de rémunération auxquels vous pouvez attribuer des noms descriptifs. Pour les régimes Niveau et Structure, vous ne pouvez ajouter que les actions de rémunération fixe qui sont des types suivants :

| Type d'action de rémunération fixe | Fonctionnalité                                                                                                                                                                                                                                                                                                                                                                                                    |
|-------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Capitaux propres                        | Les actions de capitaux propres compareront le taux de salaire de l'employé à partir de la date de fin de cycle avec le plus faible point de référence pour le niveau défini dans la tâche de l'employé. Si le taux du salaire de l'employé est inférieur au point de référence minimale, l'augmentation nécessaire pour que l'employé soit au point minimum de la plage est calculée.                                                                                |
| Mérite                         | Les actions au mérite calculeront l'augmentation en fonction du taux de salaire de l'employé à partir de la date de fin de cycle et le pourcentage d'augmentation dans le budget d'augmentation fixe pour le département, le syndicat et le site de travail de l'employé.                                                                                                                                                                                         |
| Général                       | Les actions générales calculeront une augmentation basée sur un pourcentage ou l'octroi aux employés d'un montant fixe. Cela est déterminé sur les paramètres de la **rémunération fixe** sous l'onglet **Général**.                                                                                                                                                                                                                        |
| Promotion                     | Les actions de promotion vous offrent un point nommé où vous pouvez accorder une augmentation, donc veillez à activer l'option **Activer les recommandations** afin que vous puissiez entrer une recommandation pour les employés qui recevront des promotions.  Les employés sans augmentation recommandée n'ont pas l'action **Promotion** ajoutée à leurs enregistrements de rémunération fixe.                                                                       |
| Autre changement de niveau            | Dans l'exemple précédent, **Rétrogradation** est le nom de notre action de **rémunération fixe** avec un type **Autre changement de niveau**. Cela génère une augmentation indicative 0 (modification zéro) afin que vous puissiez entrer un montant de recommandation pour ajuster le taux de rémunération de l'employé. (Veillez à cocher l'option **Activer les recommandations**.) Les employés sans recommandation n'ont pas cette action ajoutée à leurs enregistrements de rémunération fixe. |

Vous ne pouvez ajouter des actions de **rémunération fixe** avec un type de régime par étapes.

| Type Action de rémunération fixe | Fonctionnalité                                                                                                                                                                                           |
|--------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Etape                           | Sous l'onglet Général, indiquez si cette action d'étape doit faire passer les employés à l'étape 0, à l'étape 1 ou aux deux étapes.                                                                                  |
|                                | **Étapes 0** - L'employé reçoit le taux de salaire pour l'étape actuelle à laquelle il se situe.                                                                                                                      |
|                                | **Étape 1** - Le système vérifie si l'employé est déjà au dernier point de référence pour son niveau.                                                                                             |
|                                | **2 étapes** - Le système fera avancer l'employé de deux étapes par rapport à son niveau actuel. Le système ne peut que déplacer l'employé d'une ou de zéro étape s'il atteint le dernier point de référence pour son niveau. |

## <a name="run-the-compensation-process"></a>Exécuter le processus de rémunération
Une fois l'événement de processus paramétré avec les champs de date, de régimes et d'actions nécessaires, vous pouvez cliquer sur **Exécuter le processus** dans la page **Événement de processus**. Cela permet d'ouvrir la boîte de dialogue **Exécuter les événements de processus de rémunération**. Dans cette boîte de dialogue, vous pouvez cliquer sur l'option **Afficher les résultats du traitement** pour connaître le mode de calcul des montants de rémunération pour chaque employé. Cliquer sur **Ajouter** exécutera le processus de rémunération pour tous les employés affectés à des régimes de rémunération à la date de fin du cycle.

## <a name="view-the-process-results"></a>Afficher les résultats du processus
Pour afficher les résultats de processus, ouvrez la page **Résultats du processus**. Un nouvel événement de rémunération est créé chaque fois que l'événement de processus est exécuté. De cette manière, vous pouvez effectuer des tests, effectuer des ajustements et exécuter l'événement de rémunération plusieurs fois pour voir comment les différentes modifications impactent la rémunération des employés.

La page **Résultats du processus** contient des informations sur le processus exécuté notamment lors de l'exécution, l'utilisateur ayant effectué le processus, et si des erreurs se sont produites lors du processus. Vous pouvez également cocher l'option **Verrouillé** pour désactiver le bouton **Charger la rémunération** et empêcher toute personne de charger les événements de rémunération dans les enregistrements des employés. Cliquer sur le bouton **Résultats des employés** permet d'afficher la liste des employés inclus dans l'exécution.

L'option **Résultats des employés** fournit des informations sur le processus lui-même, ainsi que toutes actions de rémunération exécutées en cours du processus. La section **Rémunération fixe** contient un enregistrement pour chaque action incluse dans l'événement de processus du régime de rémunération. Les colonnes **Directives actuelles** et **Recommandations** affichent plus d'informations sur l'action sélectionnée dans la section **Rémunération fixe**. Si **Activer les recommandations** a été marqué pour l'action, les champs Recommandation sont modifiables. Cela vous permettra d'ajuster manuellement les montants pour l'employé. Notez que si vous avez coché **Utiliser le résultat précédent** pour l'action sous Événement de processus, vous devez mettre à jour manuellement les montants de toutes les actions dépendantes.

Lorsque les montants de rémunération ont été revus pour un employé et que les ajustements ont été effectués pour les valeurs recommandées, vous pouvez modifier le **Statut** de la ligne **Événement d'employé** pour indiquer si l'événement a été approuvé ou doit être ignoré. Le cas échéant, vous pouvez effacer toutes les modifications apportées à la recommandation de l'employé en cliquant sur le bouton **Recalculer**. Cela marquera l'événement employé existant avec un statut Ignorer et créera un nouvel événement d'employé avec des valeurs recalculées.

## <a name="loading-approved-compensation-changes"></a>Chargement des modifications de rémunération approuvées
Une fois qu'un ou que plusieurs événements d'employé ont reçu leur statut mis à jour et approuvé, ils peuvent être chargés dans les enregistrements de rémunération fixe des employés. Cela peut se faire, soit en sélectionnant chaque événement d'employé et en cliquant sur le bouton **Charger la rémunération d'employé** dans la page **Résultats des employés**, soit en cliquant sur **Charger la rémunération** dans la page **Résultats du processus** pour charger tous les événements d'employé approuvés simultanément.

Cliquer sur **OK** dans la boîte de dialogue **Charger la rémunération** permet d'ajouter des lignes d'action de rémunération autre que zéro à la page **Rémunération fixe de l'employé**.
