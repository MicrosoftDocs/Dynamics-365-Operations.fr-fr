--- 
title: Valider un flux de production et une version
description: "Cette procédure montre comment créer un flux de production et une première version pour la lean manufacturing."
author: ChristianRytt
manager: AnnBe
ms.date: 02/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 0ccc4d009422b148e46bc6d4772435a18a6dc9e8
ms.contentlocale: fr-fr
ms.lasthandoff: 07/28/2017

---
# <a name="validate-a-production-flow-and-version"></a>Valider un flux de production et une version

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure montre comment créer un flux de production et une première version pour la lean manufacturing. Conditions préalables : les paramètres de production pour la lean manufacturing et les unités de mesure du temps des classes doivent être définis. Vous devez également définir une Chaîne de valeur et un Groupe de production. Consultez les livres blancs sur la lean manufacturing pour vous familiariser avec les concepts des flux de production et des activités. Cette procédure fait référence à l'entité juridique USMF dans les données de démonstration. Toutefois, en supposant que l'entité juridique est configurée pour la lean manufacturing, il est possible d'utiliser d'autres entités juridiques.


## <a name="create-a-production-flow"></a>Création d'un flux de production
1. Accédez à Contrôle de la production > Paramétrage > Flux de production lean > Flux de production.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom.
4. Dans le champ Description, entrez une valeur.
5. Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Une chaîne de valeur est une unité opérationnelle qui couvre tous les activités et flux de la chaîne de valeur.   À ce stade, les unités opérationnelles sont limitées à une entité juridique et n'ont aucune fonctionnalité supplémentaire.  
7. Dans le champ Groupe de production, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Les groupes de production permettent de définir les matières, le travail, et les comptes de travaux en cours pour un processus de production. Pour associer le contexte de comptabilité à un flux de production, il convient de créer un groupe de production.  
9. Cliquez sur Enregistrer.

## <a name="create-a-production-flow-version"></a>Créer une version de flux de production
1. Cliquez sur Ajouter.
2. Entrez une date et une heure dans le champ Date d'expiration.
    * Vous pouvez mettre à jour la date d'expiration de la version à tout moment, même pour les versions actives. Utilisez l'expiration de la version pour planifier une suppression progressive d'une version.  
3. Cliquez sur OK.
4. Dans la liste, marquez la ligne sélectionnée.
5. Dans le champ Unité, tapez une valeur.
6. Sélectionner l'unité de takt.
7. Dans le champ Takt time moyen, entrez un nombre.
    * Pour le contrôle takt de la version du flux de production, définissez un takt time moyen cible.   Le takt est défini comme une quantité par période.  Dans l'exemple, le takt time est de 0,2 heures par 10 pièces. Pour une durée de travail de 8 heures, cela correspond à une capacité de production journalière de 400 pièces.  
8. Entrez un numéro dans le champ Quantité par cycle.
9. Développez ou réduisez la section Détails de la version.
10. Dans le champ Takt time minimal, entrez un nombre.
    * Le takt time minimal doit être inférieur ou égal au takt time moyen.  
11. Dans le champ Takt time maximal, entrez un nombre.
    * Le takt time maximal doit être supérieur ou égal au takt time moyen.  
12. Entrez un nombre de jours dans la période pour la durée de cycle réelle.
    * La période pour la durée de cycle réelle est le nombre de jours pendant lesquels les tâches sont regroupées à rebours à partir de la minute actuelle pour calculer la durée de cycle réelle. Cette valeur peut être modifiée à tout moment et n'est utilisée que pour le calcul des durées de cycle réelles.  
13. Cliquez sur Enregistrer.


