---
title: "Créer une structure d'entrepôt"
description: "Cette procédure vous montre comment définir des informations sur les emplacements d'un entrepôt."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 15610bc797cf7e7abdec433d0a5cead60da7a555
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-new-warehouse-layout"></a>Créer une structure d'entrepôt

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous montre comment définir des informations sur les emplacements d'un entrepôt. Cela s'applique uniquement aux entrepôts créés à l'aide de « l'entreposage de base » dans le module Gestion des stocks, pas aux entrepôts créés dans le module Gestion des entrepôts. Vous pouvez utiliser cette procédure dans la société USMF fictive ou utiliser vos propres données.


## <a name="set-the-default-location-capacity"></a>Définir la capacité d'emplacement par défaut
1. Accédez à Gestion des stocks > Paramétrage > Paramètres de gestion des stocks et des entrepôts.
2. Cliquez sur l'onglet Emplacements.
3. Entrez un numéro dans le champ Largeur standard.
4. Entrez un numéro dans le champ Profondeur standard.
5. Entrez un numéro dans le champ Hauteur standard.
6. Cliquez sur Enregistrer.
7. Fermez la page.

## <a name="define-the-location-name-format"></a>Définir le format du nom d'emplacement
1. Accédez à Gestion des stocks > Paramétrage > Décomposition du stock > Entrepôts.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Entrepôts.
4. Tapez une valeur dans le champ Nom.
5. Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
7. Activez ou désactivez l'extension de la section Noms d'emplacement.
    * Les options de cette section définissent le format par défaut pour les noms d'emplacement. Dans notre exemple, le numéro d'allée, le nombre de rayon et le nombre d'étagère sont inclus.  
8. Définissez l'option Inclure allée sur Oui.
9. Définissez l'option Inclure rayon sur Oui.
10. Tapez une valeur pour le rayon dans le champ Format.
    * Par exemple : -##  
11. Définissez l'option Inclure étagère sur Oui.
12. Tapez une valeur pour l'étagère dans le champ Format.
    * Par exemple : -##  

## <a name="define-warehouse-locations"></a>Définir les emplacements des entrepôts
1. Cliquez sur Entrepôt dans le volet Actions.
2. Cliquez sur Assistant Emplacement.
3. Cliquez sur Suivant.
4. Annuler la sélection de l'option Quais d’expédition
5. Annuler la sélection de l'option Emplacements de stockage en gros
6. Cliquez sur Suivant.
7. Cliquez sur Suivant.
8. Cliquez sur Suivant.
9. Cliquez sur Suivant.
10. Cliquez sur Suivant.
11. Cliquez sur Suivant.
12. Cliquez sur Suivant.
    * Notez que les dimensions physiques affichées dans cette page sont celles que vous définissez au début de cette procédure.  
13. Cliquez sur Suivant.
14. Cliquez sur Terminer.
15. Fermez la page.
16. Actualisez la page.

