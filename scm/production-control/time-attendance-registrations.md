---
title: Enregistrement de Pointage
description: "Les collaborateurs qualifiés pour l&quot;enregistrement des heures peuvent entrer plusieurs types d&quot;enregistrements d&quot;heures : par exemple, le pointage à l&quot;arrivée, le pointage à la sortie, l&quot;enregistrement des activités indirectes et l&quot;enregistrement des absences. Cet article décrit les enregistrements, leur calcul, leur approbation, et l&quot;utilisation du workflow pour ajouter la structure et l&quot;approbation automatisée au processus d&quot;approbation des feuilles de temps."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmWorker, JmgCalcApprovePickDialog, JmgGroupApprove, JmgGroupCalc, JmgGroupSigningTable, JmgRegistration, JmgTimeCalcParmeters, WorkflowTableListPageRnr
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 53351
ms.assetid: 885b0cdf-53d7-4cb4-92fe-da1b9e32b39f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: f82033798dbe603c0f2e2c92f91d28985c12b3b4
ms.lasthandoff: 03/31/2017


---

# <a name="time-and-attendance-registration"></a>Enregistrement de Pointage

[!include[banner](../includes/banner.md)]


Les collaborateurs qualifiés pour l'enregistrement des heures peuvent entrer plusieurs types d'enregistrements d'heures : par exemple, le pointage à l'arrivée, le pointage à la sortie, l'enregistrement des activités indirectes et l'enregistrement des absences. Cet article décrit les enregistrements, leur calcul, leur approbation, et l'utilisation du workflow pour ajouter la structure et l'approbation automatisée au processus d'approbation des feuilles de temps. 

<a name="registrations"></a>Enregistrements
-------------

Dans les sociétés qui utilisent le pointage, les travailleurs doivent enregistrer le temps passé au travail, ainsi que leur présence. Dans certaines sociétés, il se peut que les travailleurs soient tenus d'enregistrer les pointages à l'arrivée et à la sortie uniquement. Dans d'autres sociétés, les travailleurs peuvent également être tenus d'enregistrer la consommation de temps liée aux activités réelles effectuées et aux pauses prises. Le module Pointage est destiné aux utilisateurs suivants :
-   Travailleurs tenus d'enregistrer leurs heures et leur présence à des intervalles réguliers (par exemple, à une fréquence quotidienne, hebdomadaire ou bihebdomadaire).
-   Superviseurs, responsables et responsables des salaires chargés de calculer, approuver et transférer les enregistrements des travailleurs pour traitement.

| **Remarque **                                                                                                                                                                                                                                                    |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Si vous exécutez le module Pointage avec le module Contrôle et suivi de la production, tous les enregistrements relatifs aux projets, activités de projet, activités indirectes, codes absence, heures supplémentaires et heures flexibles sont enregistrés et utilisés pour calculer la paie dans les deux modules. |

## <a name="time-registrations-workers"></a> Collaborateurs qualifiés pour l'enregistrement des heures
Pour pouvoir enregistrer les heures et absences, les travailleurs doivent être configurés en tant que travailleurs qualifiés pour l'enregistrement des heures dans la société où ils sont employés.

Après le paramétrage, les travailleurs peuvent entrer plusieurs types d'enregistrements.

-   Pointage à l'arrivée au travail et pointage à la sortie du travail.
-   Consommation de temps et d'articles liée aux tâches de production.
-   Temps d'utilisation d'une machine de l'atelier, si la machine a été définie comme ressource.

| **Remarque **                                                                                                                                                                                                                      |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Il est possible d'affecter automatiquement à un travailleur les enregistrements horaires effectués sur une machine spécifique de l'atelier, si le travailleur choisit de travailler comme assistant sur la machine lorsqu'il démarre la tâche de production. |

-   Enregistrements d'heures sur des projets et des activités de projet.
-   Enregistrement des frais de projet et de la consommation d'articles via les journaux de frais de projet et les journaux d'articles de projet respectifs.
-   Absence prévue.
-   Absence en cas d'arrivée en retard au travail ou de sortie du travail plus tôt que prévu.
-   Pauses de travail enregistrées manuellement ou calculées automatiquement par le système.
-   Activités indirectes, qui sont des activités non productives qu'un travailleur peut effectuer au cours d'une journée de travail. Il peut s'agir par exemple de réunions ou du nettoyage de leur espace de travail.
-   Heures supplémentaires qui peuvent être enregistrées comme heures supplémentaires ou heures flexibles.

## <a name="adding-clockout-registrations"></a>Ajout d'enregistrements de pointage à la sortie
Si un travailleur oublie de pointer à la fin de sa journée de travail, l'enregistrement manquant peut être ajouté en exécutant un traitement par lots. Le système compare l'heure de pointage à l'arrivée et l'heure de pointage à la sortie en fonction du profil associé du travailleur, et insère automatiquement l'enregistrement de pointage à la sortie manquant pour correspondre à l'heure de fin du profil. Les enregistrements de pointage à l'arrivée et à la sortie sont essentiels pour le calcul et l'approbation ultérieurs des enregistrements d'heures avant leur transfert vers la paie.

## <a name="calculating-registrations"></a>Calcul des enregistrements
Un groupe de calcul qui se rapporte généralement à une équipe ou un groupe de travail spécifique est affecté à un travailleur qualifié pour l'enregistrement. Le responsable d'équipe ou le superviseur valide généralement les enregistrements effectués par les travailleurs, et est donc la personne chargée d'exécuter le calcul pour les groupes de calcul respectifs au quotidien. Dans le cadre du processus de calcul, le responsable d'équipe ou le superviseur peut :
-   Corriger les enregistrements erronés. Par exemple, modifier les codes de report et ajuster les commentaires sur les tâches de production.
-   Ajouter des enregistrements manquants. Par exemple, créer des enregistrements de pointage à la sortie et créer des transactions d'absence.
-   Supprimer les enregistrements incorrects.

Comme le temps enregistré doit correspondre au profil de temps du travailleur avant le calcul des enregistrements, vous devez remplacer le profil de temps de travail d'un travailleur ayant une exception à son profil de temps de travail standard. Dans le cas où le profil du travailleur est Équipe de jour et que le travailleur a accepté de travailler en équipe de nuit sans rémunération pour les heures supplémentaires, le responsable d'équipe ou le superviseur doit remplacer le profil par défaut du travailleur afin de calculer le temps de travail au taux de nuit standard et non comme heures supplémentaires. Le calcul affiche également une erreur si un enregistrement d'absence est manquant. Il doit être ajouté pour pouvoir effectuer le calcul.

## <a name="approving-registrations"></a>Approbation des enregistrements
Tout comme vous affectez un groupe de calcul à un travailleur qualifié pour l'enregistrement des heures, vous devez également affecter un groupe d'approbation. Le groupe est généralement spécifique à une équipe ou un groupe de travail. Vous devez approuver les enregistrements d'heures qui ont été calculés correctement. Cela implique d'effectuer un calcul sans erreurs pour pouvoir générer les articles de salaire et les transférer vers un système de paie. L'administrateur de paie approuve généralement les enregistrements, et avant leur approbation, il peut :
-   Remplacer les accords salariaux pour des travailleurs individuels.
-   Ajouter des primes manuelles.
-   Entrer des informations supplémentaires sur les enregistrements d'absence.

| **Remarque **                                                                                                                                                                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Si les heures supplémentaires ont été calculées pour des travailleurs spécifiques, elles peuvent être affectées à des tâches spécifiques au cours de la journée. Une telle opération est appropriée si le coût de la tâche est calculé sur la base du salaire du travailleur. |

## <a name="approving-registrations-using-workflow"></a> Approbation d'enregistrements à l'aide d'un workflow
Vous pouvez paramétrer un processus d'approbation de workflow qui approuve automatiquement les enregistrements conformes aux règles de workflow, en conservant uniquement les écarts à traiter manuellement. Si l'approbation du workflow est activée, le responsable d'équipe ou le superviseur envoie les enregistrements calculés pour approbation. Le processus du workflow génère les approbations et les tâches appropriées, et les affecte aux utilisateurs et rôles appropriés identifiés dans le workflow. Il existe deux approbations de workflow pour le pointage.

| Workflow                                  | Objectif                                                                                                   | Type d'enregistrement                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Total des jours de pointage            | Le workflow contrôle les enregistrements, par exemple, par rapport au nombre attendu d'heures de travail pour la journée. |                                                                                                                                                                                                                                                       |
| Enregistrement du journal de pointage. | Le workflow contrôle chaque type d'enregistrement par rapport à la date de l'enregistrement.                           | Pointage • Pointage à l'arrivée • Pointage à la sortie • Absence • Pause• Code de report • Projet • Activité de projet • Activité indirecte • Tâches de production • Temps d'attente avant • Paramétrage • Processus • Chevauchement • Transport • Temps d'attente après • Début d'assistance • Fin d'assistance |

 

## <a name="transferring-approved-registrations"></a>Transfert des enregistrements approuvés
Après approbation des enregistrements, vous pouvez les transférer vers une tâche de paie périodique. Un enregistrement transféré est validé pour une activité ou une tâche à laquelle il a trait, par exemple, un ordre de fabrication ou un projet. Les transactions de paie sont générées pour chaque travailleur sur la base des enregistrements.  

## <a name="reversing-transferred-registrations"></a>Contrepassation des enregistrements transférés
La tâche de contrepassation ou d'annulation des transactions peut être effectuée jusqu'à l'exécution du transfert de paie de la période de salaire. Cela signifie que les données de paie ont été transférées vers un fichier externe. Une fois contrepassés, tous les enregistrements sont retirés et les transactions validées sur des ordres de fabrication ou des projets spécifiques sont compensées et neutralisées.

| **Remarque **                                                 |
|----------------------------------------------------------|
| Le fichier externe peut être importé dans un système de paie. |

## <a name="registrations-in-electronic-timecards"></a>Enregistrements dans les cartes de pointage électroniques
Les travailleurs dont les tâches ne nécessitent pas de commentaires immédiats, comme c'est le cas pour les tâches de production, mais qui travaillent sur des activités de projet, peuvent utiliser la carte de pointage électronique. Les cartes de pointage électroniques vous offrent la flexibilité d'entrer des enregistrements à tout moment et de la façon qui convient le mieux au programme de votre entreprise, par exemple, journalier, hebdomadaire ou lorsqu'un travailleur retourne au bureau après une absence. Pour utiliser les cartes de pointage électronique ou ces travailleurs, vous devez spécifier l'option Utiliser la carte de pointage dans les détails du travailleur. Les cartes de pointage électronique permettent au travailleur d'enregistrer :

-   Date
-   Type d'enregistrement
-   Référence de la tâche, par exemple projet, activité indirecte ou ordre de fabrication
-   Identification de tâche
-   consommation de temps.
-   Frais du projet
-   Articles du projet





