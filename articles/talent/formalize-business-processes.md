---
title: Formaliser les processus d'entreprise
description: "Cette rubrique explique comment utiliser la fonction Processus d'entreprise pour créer un modèle de processus d'entreprise pour les processus qui doivent être exécutés dans votre organisation."
author: ShielaSogge
manager: AnnBe
ms.date: 01/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: PersonnelBusinessProcessGenericWorkspace, BusinessProcessGenericTemplateListpage, BusinessProcessGenericMyTemplates, BusinessProcessGroupAssignment
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: ShielaS
ms.search.validFrom: 2018-01-09
ms.dyn365.ops.version: AX 7.1.0, Talent October 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ee4035f3156a91faecdecba45289dbb1ca6e947a
ms.openlocfilehash: fd538677d897c1e7d3103cd714c688373aab8d29
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---
# <a name="formalize-business-processes"></a>Formaliser les processus d'entreprise

[!include[banner](includes/banner.md)]

La fonction Processus d'entreprise permet de créer un modèle de processus d'entreprise pour les processus d'entreprise qui doivent être exécutés dans votre organisation. Par exemple, votre société effectue un audit des ressources humaines chaque année. Dans ce cas, vous pouvez créer un modèle qui suit toutes les tâches du processus d'audit. Ce modèle permet ensuite de s'assurer que toutes les tâches sont exécutées chaque fois que l'audit est effectué. En outre, si les tâches doivent être exécutées dans un ordre spécifique, le modèle permet de s'assurer qu'elles sont exécutées dans l'ordre correct.

Les modèles peuvent être réutilisés pour des processus récurrents. Ils peuvent également être copiés et utilisés comme point de départ pour créer des modèles.

Une fois qu'un modèle de processus d'entreprise est créé, un processus d'entreprise peut être démarré et suivi dans l'espace de travail **Processus d'entreprise**. Lorsqu'un processus d'entreprise est démarré, les tâches sont affectées aux personnes appropriées, avec une date d'échéance.

## <a name="business-process-templates"></a>Modèles de processus d'entreprise
Un modèle de processus d'entreprise répertorie un groupe de tâches qui constituent un processus d'entreprise. Par défaut, les assistants et les responsables des ressources humaines peuvent créer des processus d'entreprise. Toutefois, vous pouvez modifier les rôles pouvant créer des processus d'entreprise en modifiant la tâche **Tenir à jour les processus d'entreprise génériques** dans la configuration de la sécurité.

Pour chaque processus d'entreprise, vous pouvez définir un propriétaire de processus. Le propriétaire de processus a une visibilité sur toutes les tâches du processus, et peut réaffecter des tâches ou modifier les dates d'échéance. Par exemple, le directeur des ressources humaines crée un modèle de processus d'entreprise pour la révision des avantages et définit le gestionnaire des rémunérations et avantages comme propriétaire du processus. Le gestionnaire des rémunérations et avantages a alors une visibilité sur les tâches à exécuter dans le cadre de la révision.

Un propriétaire de processus ne peut pas créer des processus d'entreprise ou des modèles de processus d'entreprise, ou encore supprimer des processus d'entreprise ou des modèles de processus d'entreprise actifs.

## <a name="tasks"></a>Tâches
Un processus d'entreprise comporte souvent plusieurs tâches. Certaines tâches telles que la révision des offres de cours internes peuvent être effectuées dans Microsoft Dynamics 365 for Talent[?]. Dans ce cas, une option est sélectionnée dans le champ **Lien des tâches**. D'autres tâches peuvent impliquer la révision ou le remplissage de pages sur un site Web. Dans ce cas, l'option **URL** est sélectionnée dans le champ **Lien des tâches**, et l'adresse Web peut être entrée. Vous pouvez entrer des URL pour des sites externes et internes. Vous pouvez également créer des tâches pour les activités que vous effectuez manuellement, par exemple la révision de l'accessibilité de toutes les structures. Dans ce cas, un lien de tâche n'est pas nécessaire. Cette flexibilité vous permet de suivre plusieurs types de tâches dans un processus complet.

Les tâches peuvent être affectées à un collaborateur spécifique ou à un poste. Par exemple, le gestionnaire des rémunérations et avantages sera toujours chargée de la révision des primes d'assurance. Par conséquent, lorsque vous créez cette tâche, sélectionnez **Poste** dans le champ **Type d'affectation**, puis sélectionnez **Gestionnaire de rémunération et avantages** dans la liste **Poste**. Lorsque le processus d'entreprise est démarré, la tâche est affectée au collaborateur qui occupe le poste de **Gestionnaire de rémunération et avantages**. Pour affecter une tâche à un collaborateur spécifique, sélectionnez **Collaborateur** dans le champ **Type d'affectation**, puis sélectionnez la personne appropriée.

Les dates d'échéance des tâches dépendent de la date cible saisie au début du processus d'entreprise. Certaines tâches doivent être effectuées avant la date cible, et d'autres tâches peuvent être effectuées après la date cible. Lorsque vous définissez une tâche, vous spécifiez une date d'échéance par rapport à la date cible dans le champ **Décalage de la date d'échéance par rapport à la date cible**. Par exemple, le gestionnaire des rémunérations et avantages doit effectuer une révision des primes d'assurance 10 jours avant la fin de l'audit des ressources humaines. Dans ce cas, la tâche créée pour la révision a la valeur **Décalage de la date d'échéance par rapport à la date cible** définie sur **-10**. Ainsi, si le processus d'entreprise est démarré le 13 mai, la tâche est due le 3 mai.

> [!NOTE]
> Les dates d'échéance peuvent également être ajustées après le démarrage du processus d'entreprise.

Les tâches complexes peuvent nécessiter plusieurs étapes, ou les personnes qui effectuent les tâches doivent peut-être fournir des informations supplémentaires. Pour ces scénarios, vous pouvez ajouter des instructions à une tâche. Les instructions peuvent fournir des informations supplémentaires sur l'exécution de la tâche à la personne affectée à son exécution. Vous pouvez même inclure une mise en forme du texte dans les instructions.

## <a name="starting-a-business-process"></a>Démarrage d'un processus d'entreprise
Dans un modèle de processus d'entreprise, vous pouvez démarrer un processus d'entreprise en sélectionnant **Démarrer le processus**. Lorsqu'un processus est démarré, des tâches sont créées pour les collaborateurs sélectionnés ou les postes définis dans les tâches incluses dans le modèle. Une date d'échéance est également affectée à chaque tâche en ajoutant ou en soustrayant le nombre de jours de décalage par rapport à la date cible, comme expliqué dans la section Tâches. Vous pouvez afficher les processus d'entreprise actifs dans l'espace de travail **Processus d'entreprise**.

## <a name="employee-self-service"></a>Libre-service employé
Une fois qu'une tâche est affectée à un employé, ce dernier peut l'afficher, ainsi que toutes les autres tâches qui lui sont affectées, dans la page **Libre-service employé**. Pour chaque tâche de processus d'entreprise qui lui est affectée, l'employé peut afficher le nom et la description de la tâche, les instructions d'exécution et le nom de la personne à contacter. Dans la page **Libre-service employé**, l'employé peut également ouvrir la page associée dans Microsoft Dynamics 365 ou la page Web associée, et marquer les tâches comme en cours, annulées ou terminées.

## <a name="business-process-workspace"></a>Espace de travail Processus d'entreprise
Les professionnels des ressources humaines peuvent afficher les processus d'entreprise actifs dans l'espace de travail **Processus d'entreprise**. Cet espace de travail répertorie tous les processus actifs et les tâches associées à chacun d'eux. La liste complète des tâches peut être filtrée par date d'échéance. L'espace de travail répertorie également les tâches en retard et les tâches affectées spécifiquement au professionnel des ressources humaines. Le professionnel des ressources humaines peut également mettre à jour le statut de toutes les tâches et, si nécessaire, réaffecter des tâches pour faire avancer le processus d'entreprise global.

## <a name="my-business-processes-workspace"></a>Espace de travail Mes processus d'entreprise
Les propriétaires de processus peuvent afficher les processus d'entreprise actifs qui leur sont affectés dans l'espace de travail **Mes processus d'entreprise**. Cet espace de travail répertorie tous les processus actifs appartenant à l'utilisateur, ainsi que les tâches associées. La liste complète des tâches peut être filtrée par date d'échéance. L'espace de travail répertorie également les tâches affectées spécifiquement au propriétaire du processus. Le propriétaire du processus peut également mettre à jour le statut de toutes les tâches et réaffecter une tâche quelconque.

## <a name="navigating-business-processes"></a>Navigation dans les processus d'entreprise
Pour créer ou copier un modèle de processus d'entreprise, ou pour démarrer un processus d'entreprise, accédez à Processus d'entreprise - Liens – Administration des processus d'entreprise. Vous pouvez ensuite effectuer les actions suivantes :

- Sélectionnez **Nouveau** pour créer un modèle de processus d'entreprise.
- Sélectionnez **Copier à partir d'un modèle** pour copier le modèle sélectionné vers un nouveau modèle.
- Sélectionnez **Démarrer le processus** pour démarrer le processus d'entreprise sélectionné, affecter des tâches et calculer les dates d'échéance.

Pour afficher les processus actifs et les tâches associées, ouvrez l'espace de travail **Processus d'entreprise**.


