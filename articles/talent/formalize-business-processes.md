---
title: Formaliser les processus d'entreprise
description: "La fonction Processus entreprise permet de créer un modèle de processus d'entreprise pour les processus qui doivent être exécutés dans votre organisation."
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
ms.sourcegitcommit: 812db9f1d319e4d16f83700a7153a0a3b318963e
ms.openlocfilehash: 48f80eac5009e1a241d501b0c4a3a70b78f5d709
ms.contentlocale: fr-fr
ms.lasthandoff: 03/23/2018

---
# <a name="formalize-business-processes"></a>Formaliser les processus d'entreprise
La fonction Processus entreprise permet de créer un modèle de processus d'entreprise pour les processus qui doivent être exécutés dans votre organisation. Par exemple, votre société peut réaliser un audit annuel des ressources humaines. Un modèle peut être créé pour suivre toutes les tâches de l'audit pour s'assurer qu'elles sont effectuées à chaque exécution du processus et, si nécessaire, pour s'assurer qu'elles sont effectuées dans l'ordre correct. Les modèles peuvent être réutilisés pour les processus récurrents ou être copiés pour servir de point de départ à la création de nouveaux modèles.

Une fois qu'un modèle est créé, un processus peut être démarré et suivi dans l'espace de travail Processus d'entreprise.  Lorsqu'un processus d'entreprise est démarré, les tâches sont affectées aux personnes appropriées, avec une date d'échéance. Nous détaillerons ces composants ci-dessous.

## <a name="business-process-template"></a>Modèle de processus d'entreprise
Un modèle de processus d'entreprise répertorie un groupe de tâches qui constituent un processus d'entreprise. Les assistants et les responsables des ressources humaines peuvent créer des processus d'entreprise par défaut.  Toutefois, cela peut être modifié dans la configuration de la sécurité en modifiant le droit Tenir à jour les processus d'entreprise génériques.

Un propriétaire de processus peut être défini pour chaque processus.  Il a une visibilité sur toutes les tâches du processus, et peut réaffecter des tâches ou modifier leurs dates d'échéance.  Par exemple, le directeur des ressources humaines peut créer un modèle de processus d'entreprise pour la révision des avantages.  Le responsable des rémunérations et avantages peut être défini comme propriétaire du processus, afin qu'il puisse avoir un aperçu des tâches à effectuer dans le cadre de la révision.  Un propriétaire de processus ne peut pas créer ou supprimer des processus d'entreprise ou des modèles de processus d'entreprise actifs.

## <a name="task"></a>Tâche
Un processus d'entreprise comporte souvent plusieurs tâches. Certaines tâches peuvent être effectuées dans Dynamics 365 for Talent[?], par exemple la révision des offres de cours internes. Dans ce cas, une option de menu est sélectionnée dans le champ Lien des tâches. D'autres tâches peuvent impliquer la révision ou le remplissage d'écrans sur un site Web. La sélection de l'URL dans le champ Lien des tâches active l'adresse Web à saisir. Vous pouvez entrer des URL pour des sites externes et internes dans ce champ. Vous pouvez également créer des tâches pour les activités que vous effectuez manuellement, par exemple la révision de l'accessibilité de toutes les structures. Dans ce cas, un lien de tâche n'est pas nécessaire. Cette flexibilité vous permet de suivre plusieurs types de tâches dans un processus complet.

Les tâches peuvent être affectées à un collaborateur spécifique ou à un poste. Par exemple, le responsable des rémunérations et avantages sera toujours chargée de la révision des primes d'assurance.   Lors de la création de cette tâche, sélectionnez Poste pour le type d'affectation, puis sélectionnez Responsable des rémunérations et avantages dans la liste Poste. Lorsque le processus démarre, la tâche est affectée au collaborateur qui occupe le poste de responsable des rémunérations et avantages. Vous pouvez également affecter une tâche à un collaborateur spécifique en sélectionnant Collaborateur dans le champ Type d'affectation, puis en sélectionnant la personne appropriée.

Les dates d'échéance des tâches dépendent de la date cible saisie au début du processus. Certaines tâches doivent être effectuées avant la date cible, et d'autres peuvent être effectuées après la date cible.  Lors de la définition d'une tâche, vous saisissez une date d'échéance par rapport à la date cible dans le champ Décalage de la date d'échéance par rapport à la date cible. Par exemple, supposons que le responsable des rémunérations et avantages doit effectuer une révision des primes d'assurance 10 jours avant la fin de l'audit des ressources humaines. La tâche créée aura une date d'échéance par rapport à la date cible de -10. Ainsi, si le processus est démarré le 13 mai, la tâche sera due le 3 mai. Remarque : les dates d'échéance peuvent également être ajustées après le démarrage du processus.

Les tâches complexes peuvent nécessiter plusieurs étapes, ou la personne qui effectue les tâches doit fournir des informations supplémentaires. Vous pouvez ajouter des instructions à la tâche, et inclure une mise en forme du texte pour les instructions. Les instructions peuvent fournir des informations supplémentaires sur l'exécution de la tâche à la personne chargée de son exécution.

Démarrage d'un processus Un processus peut être démarré dans un modèle de processus d'entreprise en sélectionnant Démarrer le processus.  Lorsqu'un processus est démarré, des tâches sont créées pour les collaborateurs et/ou les postes sélectionnés définis dans les tâches incluses dans le modèle de processus d'entreprise. Une date d'échéance est également affectée à chaque tâche en ajoutant ou en soustrayant les jours de décalage de la date cible (consultez les informations concernant les jours de décalage dans la section Tâche). Les processus d'entreprise actifs peuvent être affichés dans l'espace de travail Processus d'entreprise. 

## <a name="employee-self-service"></a>Libre-service employé
Les tâches affectées à un employé peuvent être affichées sur la page Libre service employé. Les employés à qui une tâche de processus d'entreprise est affectée peuvent afficher la tâche, sa description, les instructions d'exécution et le nom d'un contact. Ils peuvent ouvrir la page Dynamics 365 ou la page Web associée à partir de leur page Libre service employé. Les tâches peuvent être marquées comme En cours, annulées ou terminées.

## <a name="business-process-workspace"></a>Espace de travail Processus d'entreprise
Les professionnels des ressources humaines peuvent afficher les processus d'entreprise actifs à partir de l'espace de travail Processus d'entreprise. L'espace de travail répertorie tous les processus actifs et les tâches associées à chacun d'eux. La liste complète des tâches peut être filtrée par date d'échéance. La page répertorie également les tâches en retard et les tâches spécifiquement affectées au responsable des ressources humaines. Ils peuvent également mettre à jour le statut de toutes les tâches et, si nécessaire, réaffecter des tâches pour assurer la progression du processus d'entreprise global.

## <a name="my-business-processes-workspace"></a>Espace de travail Mes processus d'entreprise
Les propriétaires de processus peuvent afficher les processus d'entreprise actifs qui leur sont affectés dans l'espace de travail Mes processus d'entreprise. L'espace de travail répertorie tous les processus actifs et les tâches associées appartenant à l'utilisateur.  La liste complète des tâches peut être filtrée par date d'échéance. La page répertorie également les tâches spécifiquement affectées au propriétaire du processus. Le propriétaire du processus peut également mettre à jour le statut de toutes les tâches, et réaffecter des tâches.

## <a name="navigating-business-processes"></a>Navigation dans les processus d'entreprise
1.   Pour ajouter un modèle de processus d'entreprise, accédez à Processus d'entreprise – Liens – Administration des processus d'entreprise.
 - a.   Nouveau : permet de créer un modèle.
 - b.   Copier à partir d'un modèle : permet de copier le modèle sélectionné vers un nouveau modèle.
 - c.   Démarrer le processus : permet de démarrer le processus d'entreprise sélectionné, d'affecter des tâches et de calculer les dates d'échéance.  
2.  Pour afficher les processus actifs et les tâches associées, accédez à l'espace de travail Processus d'entreprise.

