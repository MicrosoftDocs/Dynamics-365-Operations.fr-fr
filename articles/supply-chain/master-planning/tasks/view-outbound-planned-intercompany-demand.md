---
title: Afficher le besoin prévisionnel intersociétés en sortie
description: Cette rubrique fournit une procédure qui montre comment afficher la demande intersociétés planifiée sortante.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqOutboundIntercompanyDemand
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 39f2c1ad6fa6f282d9e281e4d1ed9483d45f096a
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469389"
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
