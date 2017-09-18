--- 
title: "Création des stratégies d'achat"
description: "Cette procédure vous montre comment créer des stratégies d'achat pour les aligner avec vos processus d'entreprise pour les achats."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 51486712d732bba064fd6c9b64dbccb730603877
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-purchasing-policies"></a>Création des stratégies d'achat

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous montre comment créer des stratégies d'achat pour les aligner avec vos processus d'entreprise pour les achats. Avant de pouvoir créer des stratégies d'achat, vous devez définir les paramètres de politique d'achat. Il est possible de créer, de modifier, et de retirer une politique d'achat, mais vous ne pouvez pas supprimer une politique d'achat. Cette procédure est généralement effectuée par un gestionnaire des achats. Vous pouvez utiliser cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données.


## <a name="set-up-policy-parameters"></a>Définition des paramètres de stratégie
1. Allez dans Politiques d'achat.
2. Cliquez sur Paramètres.
    * Les règles de priorité de la stratégie s'appliquent à différents niveaux de votre organisation. Les unités organisationnelles qui sont affichées dépendent de votre hiérarchie organisationnelle, et des niveaux de la hiérarchie auxquels le but du contrôle interne de fourniture a été affecté. Par exemple, votre organisation peut avoir des entités juridiques, des centres de coût, des régions et des départements mais il se peut que seulement certains d'entre eux aient un objectif hiérarchique de contrôle interne de l'approvisionnement. L'organisation du type Société est disponible par défaut.  
3. Cliquez sur l'onglet Paramètres de type de règle de stratégie.
4. Dans l'arborescence, sélectionnez « Politique d'achat\Règle de contrôle de demande d'achat ».
    * Vous définissez l'ordre de priorité de la résolution des stratégies au niveau de la stratégie. Toutefois, pour certains types de stratégies, vous pouvez remplacer l'ordre de priorité pour des types de règles de stratégie spécifiques. Par exemple, vous pouvez définir l'ordre de la priorité des politiques d'achat : centre de coût, département, société. Pour la règle de stratégie de catalogue, vous pouvez souhaiter modifier l'ordre de priorité comme suit : département, centre de coût, société. Vous pouvez modifier l'ordre de priorité que pour la règle de stratégie de catalogue. Lorsqu'un collaborateur crée une demande, le catalogue affiché est déterminé par les stratégies associées au département du collaborateur, puis au centre de coût et à la société de celui-ci.  
    * S'il y a plus d'un niveau organisationnel répertorié, vous pouvez utiliser les flèches haut/bas pour définir l'ordre de priorité pour la règle de contrôle de demande d'achat.  
5. Fermez la page.

## <a name="create-a-new-policy"></a>Créer une nouvelle stratégie
1. Cliquez sur Nouveau.
2. Tapez une valeur dans le champ Nom.
3. Dans le champ Description, entrez une valeur.
    * Une même politique d'achat ne peut s'appliquer qu'à une seule hiérarchie d'organisation. Par exemple, vous pourriez avoir une hiérarchie appelée « Géographique » et une autre appelée « Département », et avoir une politique d'achat différente pour chacune.  
    * Choisissez une organisation à laquelle la stratégie doit s'appliquer.  
4. Cliquez sur la flèche pour ajouter l'organisation sélectionnée.
    * Vous pouvez répéter ce processus pour ajouter plus d'organisations.  

## <a name="add-a-policy-rule"></a>Ajouter une règle de stratégie
1. Dans la liste Type de règle de stratégie, sélectionnez Règle d'objectif de demande.
    * Vous allez créer une règle qui définir l'objectif de demande par défaut sur le type de consommation mais qui permet au type de réapprovisionnement d'être choisi à la place.  
2. Cliquez sur Créer une règle de stratégie.
3. Sélectionnez Oui dans le champ Autoriser le remplacement manuel.
4. Cliquez sur Fermer.
    * Maintenant vous pouvez définir d'autres règles de stratégie pour la politique d'achat.   Notez qu'un type de règle de stratégie ne peut pas avoir de règles superposées actives en même temps dans une stratégie d'approvisionnement unique.  
5. Fermez la page.
6. Fermez la page.

