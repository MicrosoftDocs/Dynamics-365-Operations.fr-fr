---
title: Ajouter une activité existante à une version de flux de production
description: Lors de la création de nouvelles versions des flux de production, vous pouvez choisir d'ajouter des activités créées pour les versions antérieures, à la nouvelle version.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityAddExisting, PlanActivityAddExistingLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f95958e57b1b1a93e43eb2cf02d2651ccb9587b6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427622"
---
# <a name="add-an-existing-activity-to-a-production-flow-version"></a>Ajouter une activité existante à une version de flux de production

[!include [banner](../../includes/banner.md)]

Lors de la création de nouvelles versions des flux de production, vous pouvez choisir d'ajouter des activités créées pour les versions antérieures, à la nouvelle version. Cette procédure décrit la manière dont une version est créée pour un flux de production existant, sans copier les activités. Dans l'étape suivante, une activité existante est ajoutée à la nouvelle version. 

Cette tâche nécessite un flux de production avec une version et des activités déjà créées.


## <a name="create-a-new-production-flow-version"></a>Créer une nouvelle version de flux de production
1. Accédez à Contrôle de la production > Paramétrage > Flux de production lean > Flux de production.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Cliquez sur Modifier.
5. Dans la liste, marquez la ligne sélectionnée.
6. Entrez une date et une heure dans le champ Date d'expiration.
    * Notez qu'avant de créer une version du flux de production, veillez à vérifier la date et l'heure d'expiration de la version active. La nouvelle version est créée avec une date de début effective, qui se connecte à la date d'expiration de la version sélectionnée.  
7. Cliquez sur Ajouter.
8. Sélectionnez Non dans le champ Copier à partir de la version.
    * Sélectionnez Non pour démarrer avec une version vide si la plupart des activités de la version copiée sont remplacées par de nouvelles activités. Ajoutez manuellement les activités inchangées à la fonction Ajouter existant de l'écran d'activité.  
9. Sélectionnez Non dans le champ Dupliquer les règles de kanban.
    * Lorsque les activités ne sont pas copiées vers la nouvelle version, il n'est pas possible de copier les règles de kanban au moment de la création de la nouvelle version.   Vous pouvez utiliser la fonction de création de règles de kanban de remplacement dans l'écran de règle de kanban pour remplacer les règles de kanban de l'ancienne version du flux de production par des règles de kanban utilisant les activités de la nouvelle version.  
10. Cliquez sur OK.
11. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.

## <a name="add-an-existing-activity"></a>Ajouter une activité existante
1. Cliquez sur Activités.
2. Cliquez sur Ajouter existant pour ouvrir la boîte de dialogue.
    * Recherchez et sélectionnez une activité existante à ajouter à la nouvelle version du flux de production.  Notez que la liste répertorie toutes les activités créées pour ce flux de production pour toutes les versions précédentes du flux.  
3. Dans le champ Activité, entrez ou sélectionnez une valeur.
4. Cliquez sur OK.

