---
title: Afficher le besoin prévisionnel intersociétés en sortie
description: Cette rubrique fournit une procédure qui montre comment afficher la demande intersociétés planifiée sortante.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqOutboundIntercompanyDemand
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8cf2350d754c5da9d3d428e2b75950d027ccfd63
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7569743"
---
# <a name="view-outbound-planned-intercompany-demand"></a>Afficher le besoin prévisionnel intersociétés en sortie

[!include [banner](../../includes/banner.md)]

Cette procédure indique comment afficher tous les ordres prévisionnels qui seront honorés par un fournisseur intersociétés. La société fictive de démonstration utilisée pour créer cette procédure est DEMF.

1. Sélectionnez **Planification**.
2. Dans le champ **Plan**, saisissez ou sélectionnez une valeur.
    * Dans le champ **Plan**, sélectionnez le plan *10*.  
3. Sélectionnez *Exécuter*.
4. Entrez un nombre dans le champ **Nombre de threads**.
    * Représente le nombre de threads parallèles à utiliser pour la planification.  
5. Cliquez sur **OK**.
    * Cette opération peut prendre du temps.  
6. Sélectionnez **Besoin prévisionnel intersociétés**.
7. Sélectionnez **Besoin prévisionnel intersociétés en sortie**.
    * Cette page fournit une vue d’ensemble de la demande planifiée qui sera honorée par un fournisseur de la chaîne d’approvisionnement interne.  
8. Développez la section **Détails du besoin en amont**.
    * Dans cette section, vous pouvez afficher les détails sur la façon dont la demande sera honorée. Vous devrez attendre l’exécution de la planification dans la société d’approvisionnement avant de pouvoir consulter les informations supplémentaires ici.  

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
