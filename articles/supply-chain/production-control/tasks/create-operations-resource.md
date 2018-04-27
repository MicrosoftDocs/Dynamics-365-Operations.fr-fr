--- 
title: "Création d'une ressource opérationnelle"
description: "Une ressource opérationnelle réalise les activités d'un projet ou d'un processus de production."
author: sorenva
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: aa80e4b22d116c8f580c9aefe7c114cfe1d19cc8
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-an-operations-resource"></a>Création d'une ressource opérationnelle

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Une ressource opérationnelle réalise les activités d'un projet ou d'un processus de production. Cette procédure vous indique comment définir une ressource opérationnelle. Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données.

1. Allez dans Ressources.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Ressource.
4. Dans le champ Description, entrez une valeur.

## <a name="define-capacity-and-consumption-parameters"></a>Définir des paramètres de consommation et de capacité
1. Développez la section Opération.
2. Entrez un nombre dans le champ Pourcentage de rebut.
3. Saisissez ou sélectionnez une valeur dans le champ Catégorie de paramétrage.
    * Spécifiez la catégorie de coûts qui définit comment prendre en compte le coût du paramétrage.  
4. Saisissez ou sélectionnez une valeur dans le champ Catégorie de temps d'exécution.
    * Spécifiez la catégorie de coûts qui définit comment prendre en compte le coût du temps d'exécution.  
5. Saisissez ou sélectionnez une valeur dans le champ Catégorie de quantité.
    * Spécifiez la catégorie de coûts qui définit comment prendre en compte le coût de la ressource selon la quantité produite.  
6. Sélectionnez une option dans le champ Capacité disponible.
    * Spécifiez l'unité dans laquelle exprimer la capacité de la ressource opérationnelle.  
7. Entrez un nombre dans le champ Capacité.
8. Entrez un nombre dans le champ Pourcentage de rendement.
    * Spécifiez le rendement attendu de la ressource opérationnelle. Le pourcentage d'efficacité règle le débit de la ressource opérationnelle et affecte le temps réservé pour celle-ci.  
9. Entrez un nombre dans le champ Pourcentage d'ordonnancement.
    * Spécifiez le pourcentage maximal de la capacité de la ressource opérationnelle à utiliser dans la planification d'opérations.  
10. Sélectionnez Oui dans le champ Capacité finie.
    * Définissez cette option sur Oui si la ressource opérationnelle est planifiée en fonction de la capacité réelle disponible, et si les réservations de capacité existantes sont prises en compte. Si cette option est définie sur Non, la ressource opérationnelle est supposée avoir une capacité infinie, et elle peut être surréservée.  
11. Sélectionnez Oui dans le champ Ressource critique.

## <a name="define-working-times"></a>Définir des temps de travail
1. Développez la section Calendriers.
2. Cliquez sur Ajouter.
3. Saisissez ou sélectionnez une valeur dans le champ Calendrier.
    * Spécifiez le calendrier de temps de travail qui définit la capacité (en heures) de la ressource.  
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.

## <a name="define-resource-capabilities"></a>Définir des capacités de ressources
1. Développez la section Capacités.
2. Cliquez sur Ajouter.
    * Une capacité est la capacité d'une ressource opérationnelle à exercer une activité spécifique. Le moteur de planification alloue les ressources en faisant correspondre les demandes de ressources de chaque activité aux capacités des ressources opérationnelles disponibles.  
3. Saisissez ou sélectionnez une valeur dans le champ Capacité.
4. Dans le champ Niveau, entrez un nombre.
    * Spécifiez le niveau de qualification utilisé par la ressource pour traiter la capacité.  
5. Dans le champ Priorité, entrer un numéro.
    * Spécifiez la priorité de la ressource opérationnelle par rapport à la capacité. En planifiant par priorité, la ressource opérationnelle ayant la priorité la plus élevée (la valeur numérique la plus faible) est sélectionnée en premier.  

## <a name="assign-resource-to-resource-group"></a>Affecter une ressource au groupe de ressources
1. Développez la section Groupes de ressources.
2. Cliquez sur Ajouter.
    * Le groupe de ressources définit le site, l'unité de production et le contexte d'entrepôt pour les ressources opérationnelles. Les ressources opérationnelles peuvent uniquement être attribuées à un groupe de ressources et uniquement sur le site où se trouve le groupe de ressources.  
3. Saisissez ou sélectionnez une valeur dans le champ Groupe de ressources.
4. Saisissez ou sélectionnez une valeur dans le champ Emplacement de l'entrée.
    * Spécifiez l'emplacement d'entrepôt d'où la ressource opérationnelle consomme des matières.  


