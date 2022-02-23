---
title: Générer un plan avec contrainte
description: Cette rubrique indique comment créer un plan qui prend en compte des contraintes en termes de matière et de capacité.
author: ShylaThompson
manager: tfehr
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d8b9d5712dd1b4f9958de775e1a2224b64485d05
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427909"
---
# <a name="generate-a-constrained-plan"></a>Générer un plan avec contrainte

[!include [banner](../../includes/banner.md)]

Cette rubrique indique comment créer un plan qui prend en compte des contraintes en termes de matière et de capacité. Le plan vérifie que la fabrication ne démarre pas avant que les matières soient disponibles et que des ressources ne soient pas surréservées. 

Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette procédure est destinée au gestionnaire de production.


## <a name="set-up-a-constrained-plan"></a>Paramétrer un plan avec contrainte
1. Dans la page d'accueil, sélectionnez l'espace de travail **Planification**.
2. Sélectionnez **Plans généraux** dans la liste des liens dans la partie droite de l'espace de travail.
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité. Exemple : **StaticPlan**  
4. Sélectionnez **Oui** dans le champ **Capacité finie**.
5. Entrez `30` dans le champ **Plage de gestion de la capacité finie**.
6. Développez la section **Plages de gestion en jours**.
7. Sélectionnez **Oui** dans le champ **Capacité**.
8. Entrez un nombre dans le champ **Plage de gestion de planification de capacité (jours)**. Exemple : `60`  
9. Sélectionnez **Oui** dans le champ **Retards calculés**.
10. Entrez un nombre dans le champ **Calculer la plage de gestion des retards (jours)**. Exemple : `60` 
11. Développez la section **Retards calculés**.
12. Sélectionnez **Oui** dans tous les champs **Ajouter le retard calculé à la date de besoin**.
13. Fermez la page.

## <a name="create-a-constrained-plan"></a>Créer un plan avec contrainte
1. Sélectionnez **Exécuter**.
2. Dans le champ **Plan général**, entrez ou sélectionnez le plan pour lequel vous avez paramétré les contraintes.  
3. Cliquez sur **OK**.
4. Sélectionnez **Ordres prévisionnels**.

