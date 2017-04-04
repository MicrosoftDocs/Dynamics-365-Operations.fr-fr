---
title: "Enregistrement dans Contrôle et suivi de la production"
description: "Cette rubrique décrit les concepts et les termes importants que vous devez comprendre pour configurer et utiliser le contrôle et suivi de la production."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: JmgRegistration
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 70103
ms.assetid: 52ba1cdd-767f-4edd-896f-61adce8479d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: aee0a4eda2a2ac2f272f590781b9e751a8797095
ms.lasthandoff: 03/31/2017


---

# <a name="registration-for-manufacturing-execution"></a>Enregistrement dans Contrôle et suivi de la production

Cette rubrique décrit les concepts et les termes importants que vous devez comprendre pour configurer et utiliser le contrôle et suivi de la production. 

Le contrôle et suivi de la production est principalement destiné aux sociétés de fabrication. Les collaborateurs peuvent enregistrer la consommation de temps et d'articles sur des tâches de production à l'aide de l'écran **Enregistrement de tâche**. Tous les enregistrements sont approuvés et ensuite sont transférés vers les modules appropriés. L'approbation et le transfert continus d'enregistrements permettent aux responsables de suivre les coûts réels des ordres de fabrication.

## <a name="manufacturing-execution-and-registration-terminology"></a>Terminologie du contrôle et suivi de production
Le tableau suivant contient des termes relatifs au contrôle et suivi de la production ainsi qu'aux tâches d'enregistrement associées.

| Terme                          | description ;                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Contrôle et suivi de la production       | Fonctionnalité qui permet d'enregistrer le temps, la consommation de matières, les coûts des tâches de production, les projets, les activités indirectes. L'enregistrement est effectué dans un client d'enregistrement du module Contrôle et suivi de la production.                                                                                                                                                                                                                                                                                                                                                                                                   |
| Liste de tâches                      | La page **Enregistrement de tâche** présente aux collaborateurs la liste des tâches qu'ils doivent effectuer sur une ressource spécifique, telle qu'une machine. Un travailleur peut enregistrer la consommation de temps et d'articles sur chaque tâche figurant dans la liste.                                                                                                                                                                                                                                                                                                                                                                           |
| Regroupement des tâches                  | Si un collaborateur commence plusieurs tâches en même temps sur la page **Enregistrement de tâche**, on parle de regroupement de tâches. Le temps passé sur les tâches regroupées peut être affecté à des tâches individuelles de différentes manières à l'aide de clés de répartition.                                                                                                                                                                                                                                                                                                                                                         |
| Enregistrements de pilote/assistant | Un collaborateur peut s'enregistrer comme assistant pour une ressource et créer une petite équipe au sein de laquelle plusieurs collaborateurs travaillent sur les mêmes tâches de production. Les ressources auxquelles les travailleurs sont connectés en temps qu'assistants sont appelées pilotes. Seule la ressource pilote doit effectuer des enregistrements. Tous les assistants obtiennent automatiquement les mêmes enregistrements. Par exemple, si une machine fonctionne comme pilote, un collaborateur qui s'est enregistré comme assistant pour cette machine peut effectuer des enregistrements sur la page **Enregistrement de tâche**. Tant la machine que les collaborateurs connectés en tant qu'assistants reçoivent alors les mêmes enregistrements. |
| Activité indirecte             | Activité ou tâche non directement liée à une tâche de production ou à un projet, par exemple, une réunion de service, ou une tâche de nettoyage ou de maintenance à l'atelier. Les collaborateurs peuvent effectuer des enregistrements sur des activités indirectes de la même manière que sur des tâches de production et des projets.                                                                                                                                                                                                                                                                                                |

## <a name="registrations-in-manufacturing-execution"></a>Enregistrements dans le module Contrôle et suivi de la production
Les collaborateurs peuvent entrer plusieurs types d'enregistrements dans le module Contrôle et suivi de la production pour le travail effectué sur des tâches de production. Selon le paramétrage du système, les collaborateurs peuvent parfois effectuer des enregistrements sur des activités de projet et des tâches non productives telles que des pauses, absences et activités indirectes. Les types d'enregistrements sont les suivants :

-   **Pointage à l'arrivée/pointageà la sortie** (disponible dans Pointage) – Les collaborateurs pointent lorsqu'ils arrivent au travail et lorsqu'ils quittent le travail.
-   **Enregistrer sur les tâches de production** - Les collaborateurs peuvent effectuer des enregistrements, tels que le démarrage d'une tâche ou l'émission d'une rétroaction concernant une tâche, sur les tâches de production figurant dans sa liste de tâches. Les collaborateurs peuvent démarrer plusieurs tâches à la fois. On parle alors de regroupement des tâches.
-   **Enregistrer sur le stock** - Les collaborateurs peuvent effectuer des enregistrements sur des matières utilisées en atelier, qui ne sont pas directement liées à des tâches de production. Il peut s'agir, par exemple, de graisses, de lubrifiants ou d'autres matières utilisées pour entretenir les machines. L'enregistrement est effectué dans un journal de stock.
-   **Enregistrer sur des projets** (disponible dans Pointage) – Les collaborateurs peuvent effectuer des enregistrements, tels que le démarrage et l'achèvement d'une tâche, sur les projets ou activités de projet figurant dans leur liste de tâches.
-   ** Les frais et les articles de projet du registre ** (disponible dans Pointage) – Les travailleurs peuvent enregistrer les frais (dépenses) associés à un projet dans un journal de frais de projet par exemple, kilométrage et péages). Les travailleurs peuvent également enregistrer la consommation d'articles sur des projets. Ces informations sont enregistrées dans un journal d'articles de projet.
-   **S'enregistrer en tant qu'assistant d'un autre travailleur** – Si deux collaborateurs ou plus doivent collaborer sur une tâche de production ou un projet, un collaborateur peut s'enregistrer comme assistant pour une machine ou un autre collaborateur, qui fera fonction de pilote. Si nécessaire, le pilote peut sélectionner un autre collaborateur comme pilote.
-   **Enregistrer une absence** (disponible dans Pointage) – Les collaborateurs peuvent enregistrer des heures via différents codes absence paramétrés. Il est possible d'indiquer une absence si un collaborateur arrive en retard, doit s'absenter au cours de la journée de travail ou quitter le travail plus tôt que l'heure définie dans le profil de temps de travail standard.
-   **Enregistrer des pauses** (disponible dans Pointage) – Durant la journée de travail, les collaborateurs peuvent enregistrer le fait qu'ils quittent leur station de travail pour prendre une pause. Plusieurs types de pauses peuvent être paramétrés. Lorsqu'un collaborateur revient et se reconnecte, le système enregistre le retour du collaborateur et l'enregistrement de la pause s'arrête.
-   **Enregistrer des activités indirectes** (disponible dans Pointage) –Les activités indirectes sont des activités non productives que les collaborateurs peuvent effectuer au cours d'une journée de travail (par exemple, réunion de service, réunion d'équipe ou tâche de maintenance à l'atelier). Les travailleurs peuvent effectuer des enregistrements sur les activités indirectes paramétrées.
-   **Enregistrer des heures supplémentaires** (temps disponible dans Pointage) – Les collaborateurs qui ont été invités à travailler plus longtemps peuvent sélectionner si les heures supplémentaires doivent être enregistrées comme horaire flexible ou heures supplémentaires.



