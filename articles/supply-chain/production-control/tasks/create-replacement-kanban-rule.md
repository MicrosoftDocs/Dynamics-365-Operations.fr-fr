---
title: Créer une règle de kanban de remplacement
description: Cette procédure se concentre sur le remplacement d’une règle de kanban existante par une nouvelle règle de kanban à une date spécifique.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3d42c98efe33bb9904a384aed6e7cbf97ac5f39cc860cd3d220336ad0d26d53d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751863"
---
# <a name="create-a-replacement-kanban-rule"></a>Créer une règle de kanban de remplacement

[!include [banner](../../includes/banner.md)]

Cette procédure se concentre sur le remplacement d’une règle de kanban existante par une nouvelle règle de kanban à une date spécifique. Cela est utile lorsque des modifications du flux de production ou des règles de réapprovisionnement doivent être coordonnés et planifiées. La société fictive de démonstration utilisée pour créer cette procédure est USMF. Cette procédure est destinée à l’ingénieur processus ou au responsable de la chaîne de valeur quand ils préparent la production pour un flux de production modifié ou une nouvelle règle d’approvisionnement. Cette tâche remplace la règle de kanban 000022 par une nouvelle règle et augmente la quantité maximale de 48 à 100 pour cette nouvelle règle.


## <a name="select-a-kanban-rule-to-replace"></a>Sélectionner la règle de kanban à remplacer
1. Accédez aux règles de kanban.
2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    * Sélectionnez la règle de kanban 000022.  

## <a name="create-a-replacement-kanban-rule"></a>Créer une règle de kanban de remplacement
1. Cliquez sur Remplacer la règle de kanban.
2. Entrez une date et une heure dans le champ Date d’effet.
    * Sélectionnez une date dans le futur, dans une semaine par exemple. Il s’agit de la date et de l’heure auxquelles la règle de kanban devient active et remplace la règle de kanban ancienne.  
    * Si la règle de kanban fait passer le chemin d’accès par le flux de production, une autre activité peut être sélectionnée.  Dans cette procédure, nous maintiendrons l’activité intacte.  
3. Cliquez sur OK.
    * Notez qu’une règle de kanban est créée pour remplacer la règle de kanban 000022.  
    * La date d’effet est définie selon la date choisie lorsque vous remplacez la règle de kanban.  
4. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    * Sélectionnez la règle de kanban de remplacement 000022.  
    * Notez que la règle de kanban de remplacement a la même date que la date d’expiration car il s’agit de la date à laquelle elle expirera.  
5. Sélectionnez la ligne 1 dans la liste.
    * Sélectionnez la nouvelle règle de kanban en haut de la liste. Il s’agit de la règle de kanban avec le numéro de règle de kanban le plus élevé.  
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Cliquez sur le numéro de la règle de kanban pour ouvrir la règle de kanban.  

## <a name="modify-maximum-quantity-for-the-replacement-kanban-rule"></a>Modifier la quantité maximale pour la règle de kanban de remplacement
1. Définissez la quantité maximale sur 100.
    * Développez l’organisateur Quantités pour voir le champ Quantité maximale. Le fait de définir la quantité maximale sur 100 permet de traiter jusqu’à 100 kanbans.    Il s’agit de la dernière étape de cette tâche.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]