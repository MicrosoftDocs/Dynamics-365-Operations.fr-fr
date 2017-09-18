--- 
title: "Créer une règle de kanban à l'aide d'un événement de stock minimal"
description: "Cette procédure consiste à réaliser le paramétrage nécessaire pour créer une règle de kanban à l'aide d'un événement de stock minimal pour s'assurer qu'un produit spécifique est toujours disponible à un emplacement spécifique."
author: ChristianRytt
manager: AnnBe
ms.date: 08/24/2016
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: c655f9e2cb3967a44c357f16d18884ec0bc55357
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# Créer une règle de kanban à l'aide d'un événement de stock minimal

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure consiste à réaliser le paramétrage nécessaire pour créer une règle de kanban à l'aide d'un événement de stock minimal pour s'assurer qu'un produit spécifique est toujours disponible à un emplacement spécifique. Une règle de kanban est créée pour transférer le matériel vers l'emplacement quand le niveau d'inventaire chute en-dessous de 200 pièces. L'exécution du traitement de l'événement de l'origine des besoins permet de créer les kanbans nécessaires. Les données fictives utilisées pour créer cette tâche correspondent à la société USMF. Cette tâche est destinée à l'ingénieur processus ou au responsable de la chaîne de valeur, car ils préparent la production d'un produit nouveau ou modifié dans un environnement lean.


## Créer une règle de kanban
1. Accédez à Gestion des informations sur les produits > Lean manufacturing > Règles de kanban.
2. Cliquez sur Nouveau.
3. Sélectionnez Prélèvement dans le champ Type.
    * Ce type permet de créer des kanbans de transfert.  
4. Dans le champ Stratégie de réapprovisionnement, sélectionnez « Événement ».
    * La stratégie d'événement est utilisée pour créer le transfert des kanbans selon un événement. Plus tard dans la procédure, vous déclencherez des kanbans de transfert à l'aide du réapprovisionnement de stock.  
5. Entrez ou sélectionnez une valeur dans le champ Première activité de plan.
    * Entrez ou sélectionnez ReplenishSpeakerComponents. Cette activité de transfert a l'entrepôt de sortie et l'emplacement 12, ce qui signifie que les matériaux sont déplacés vers l'emplacement 12 dans l'entrepôt 12.  
6. Développez la section Détails.
7. Dans le champ Produit, saisissez ou sélectionnez une valeur.
    * Sélectionnez M0007.  
8. Développez la section Événements.
9. Sélectionnez « Traitement par lots » dans le champ Événement de réapprovisionnement de stock.
    * Ceci crée des kanbans pour répondre aux besoins en matériaux à l'emplacement associé pendant le traitement d'événement de l'origine des besoins.  

## Définissez la quantité minimale pour l'article.
1. Cliquez pour suivre le lien dans le champ Produit.
2. Cliquez pour suivre le lien dans le champ Numéro d'article.
3. Augmentez le récapitulatif de l'image du produit.
4. Cliquez sur Planifier dans le volet Actions.
5. Cliquez sur Couverture de l'article.
6. Cliquez sur Nouveau.
7. Dans la liste, marquez la ligne sélectionnée.
8. Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.
    * Définissez Entrepôt sur 12.  
9. Définissez Minimum sur 200.

## Exécuter le job de création d'événement de traitement par lots
1. Allez dans Contrôle de la production > Tâches périodiques > Traitement par lots de tâche de Kanban > Traitement d'événements d'origine des besoins.
2. Cliquez sur OK.
3. Accédez à Gestion des informations sur les produits > Lean manufacturing > Règles de kanban.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez la règle de kanban créée précédemment.  
5. Développer la section Kanbans.
    * Notez qu'un kanban a été créé pour transférer le matériel nécessaire vers l'entrepôt 12.  

