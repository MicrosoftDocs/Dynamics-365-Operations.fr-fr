---
title: Vue d'ensemble de la Gestion du personnel
description: "Cette rubrique décrit l'utilisation du service Gestion du personnel (WFM) pour bénéficier des clients de point de vente (PDV) familiers, du PDV moderne et du PDV cloud, afin que les responsables de magasins puissent gérer facilement leur personnel."
author: shalabhjainmsft
manager: AnnBe
ms.date: 7/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Core
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-07-30
ms.dyn365.ops.version: Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: d67ad79c068651f32ce7dc776bc460698557bc29
ms.openlocfilehash: f747dce6b9595de50297cb5af7db523d5f26a844
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="workforce-management-overview"></a>Vue d'ensemble de la Gestion du personnel

[!include[banner](includes/banner.md)]
    
Le service Gestion du personnel (WFM) bénéficie des clients de point de vente (PDV) familiers, du PDV moderne et du PDV cloud, pour permettre aux responsables de magasins de gérer facilement leur personnel. Le service WFM utilise la structure d'extension pour télécharger les modules appropriés dans le PDV. Ces modules sont téléchargés lorsque le PDV est clôturé puis rouvert. Donc, lorsque Microsoft publie de nouvelles fonctions pour le service WFM, l'application du PDV doit être fermée et rouverte.

En utilisant ce service, les directeurs de magasin peuvent facilement créer et publier le planning de travail hebdomadaire pour les magasins. Les employés de magasin peuvent ensuite rapidement afficher leurs propres programmes et les programmes de leurs collègues. De cette façon, ils peuvent apprendre qui travaillera avec eux dans les équipes de travail assignées. Les employés de magasin peuvent également créer des demandes d'absence, de permutation d'équipe et d'offre de service dans une équipe. Toutes les demandes déclenchent un workflow défini.

Pendant un quart de travail, les employés du magasin peuvent profiter de la fonctionnalité de pointage à l'arrivée et de pointage à la sortie intégrée aux clients PDV. Les données sont ensuite envoyées au siège pour l'établissement des salaires. La fonction de pointage à l'arrivée et de pointage à la sortie est une fonctionnalité existante du PDV. Pour plus d'informations sur le paramétrage et les scénarios pris en charge, voir [Pointage à l'arrivée et pointage à la sortie](retail-time-attendance.md).

## <a name="supported-scenarios"></a>Scénarios pris en charge
Cette section fournit plus d'informations sur les scénarios pris en charge.

- **Créer et publier des plannings** – Le service WFM utilise les autorisations du PDV configurées au siège pour déterminer si un collaborateur dispose des privilèges de directeur de magasin. Seuls les directeurs de magasin peuvent créer et publier des plannings à l'aide de l'opération de gestion des plannings. Ils peuvent rapidement créer un emploi du temps en copiant et en collant un poste de travail existant d'un travailleur à un autre. Ils peuvent également créer un planning en important le planning de toute la semaine précédente à la semaine en cours.

    Si un planning n'est pas publié, il demeure à l'état de brouillon et apparaît différemment d'un planning publié. Les directeurs de magasin peuvent publier un planning en cliquant sur le bouton **Publier** de n'importe quelle semaine. Une fois que le planning est publié pour une semaine, les modifications sont automatiquement publiées. Des exemples de modifications incluent l'ajout ou la suppression d'équipes/d'absences de travail, ou encore les permutations d'équipes ou absences de travail. Les employés de magasin ne peuvent visualiser que les plannings publiés pour différentes semaines.
    
- **Créer et approuver des demandes** – Les employés de magasin peuvent créer trois types de demandes :

    - Demande d'absence
    - Demande de permutation d'équipe
    - Offre de service dans une équipe

    Ces demandes peuvent être créées à l'aide de l'opération de demande de planning. Chaque demande suit un workflow défini, et les collaborateurs peuvent aisément voir le statut actuel de leurs demandes.
    
    Les demandes d'absence sont automatiquement soumises au directeur de magasin pour approbation. S'il y a plusieurs directeurs de magasin, tous les responsables peuvent afficher une demande donnée, mais un seul responsable peut l'approuver ou la rejeter. Les types d'absences sont configurés au siège de vente au détail à l'aide de la page **Types de congé et d'absence** dans le module **Vente au détail**. Une fois que le directeur de magasin approuve ou rejette une demande, elle est déplacée vers l'onglet **Historique** pour l'opération de demandes de planning.
    
    Une demande de permutation d'équipe ou d'offre de service dans une équipe arrive d'abord chez le collaborateur auquel la demande a été envoyée. Le directeur de magasin ne peut afficher la demande qu'une fois que ce travailleur l'a approuvée. Par conséquent, si le travailleur rejette la demande de permutation d'équipe ou une offre de service dans une équipe, le responsable ne peut pas l'afficher. Le collaborateur ayant créé la demande peut également l'annuler avant que le responsable l'approuve ou la refuse.

- **Afficher les employés de magasin actifs dans la vue planning** – Lorsqu'un collaborateur est ajouté à un magasin, par exemple en l'associant au carnet d'adresses de l'employé du magasin, le collaborateur devient disponible pour la planification dans le service WFM. Un traitement par lots récurrent nommé **Traiter les données des collaborateurs pour la gestion de la main-d'œuvre** est exécuté au siège social. Cette tâche prépare les associations magasin/collaborateur qui seront envoyées à Common Data Service (CDS).

    Le même processus est utilisé lorsqu'un collaborateur est supprimé d'un magasin. Toutefois, le collaborateur qui est supprimé est toujours affiché pour les semaines passées, actuelles et futures si une équipe de travail ou une absence active est attribuée à ce collaborateur. Par conséquent, à moins que ces équipes de travail et ces absences ne soient supprimées, le travailleur supprimé continuera d'être affiché pour ces semaines.

