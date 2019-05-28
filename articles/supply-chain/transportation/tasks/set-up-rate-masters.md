---
title: Paramétrer des tables maître des taux
description: Cette procédure décrit le processus de paramétrage des données principales de taux.
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 462bfce89fa77c8830a93a22b0dd6c8c8fb2cde6
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555304"
---
# <a name="set-up-rate-masters"></a>Paramétrer des tables maître des taux

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit le processus de paramétrage des données principales de taux. Le responsable logistique configure généralement les données principales de taux en fonction des contacts signés avec les transporteurs. Dans ce scénario vous paramètrerez des données principales de taux pour un transporteur aérien. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="set-up-rate-master"></a>Paramétrer des données principales de taux
1. Accédez à Gestion du transport > Configurer > Taux > Données principales de taux.
2. Cliquez sur Nouveau.
3. Dans le champ Données principales de taux, saisissez une valeur.
4. Tapez une valeur dans le champ Nom.
5. Dans le champ ID des métadonnées de taux, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * L'ID des métadonnées de taux détermine les données nécessaires pour les données principales du taux, car cela définit les métadonnées attendues par le moteur de TMS utilisant cette table maître des taux.  
6. Pour cette exemple, sélectionnez l'option P2P
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Cliquez sur Enregistrer.

## <a name="set-up-rate-base"></a>Paramétrer la base de taux
1. Cliquez sur Base de taux.
    * La base de taux détermine le taux du transporteur, et peut être utilisée pour paramétrer une structure tarifaire car elle structure les taux dans les points d'arrêt définis dans les données principales des ruptures.  
2. Cliquez sur Nouveau.
3. Dans le champ Base de taux, saisissez une valeur.
4. Tapez une valeur dans le champ Nom.
5. Dans le champ Données principales de la rupture, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Les données principales des ruptures permettent de définir la structure de tarification et les points d'arrêt. La structure de tarification utilise la tarification progressive basée sur les dimensions physiques.  
6. Pour cet exemple, utilisez le poids
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Activez ou désactivez l'extension de la section Détails.
9. Cliquez sur Nouveau.
10. Dans le champ Code postal du lieu de livraison de départ, saisissez « 30301 ».
11. Dans le champ Code postal de lieu de livraison d'arrivée, saisissez « 30318 ».
12. Dans le champ Région du pays de livraison, saisissez « USA ».
13. Dans le champ <1.00 Lbs, saisissez « 100 ».
    * Insérez le taux par livres si le poids total de la charge est inférieur à 1 livre.  
14. Dans le champ <5,00 Lbs, saisissez « 300 ».
    * Insérez le taux par livres si le poids total de la charge est inférieur à 5 livres.  
15. Dans le champ <20,00 Lbs, saisissez « 500 ».
    * Insérez le taux par livres si le poids total de la charge est inférieur à 20 livres.  
16. Dans le champ <100,00 Lbs, saisissez « 1000 ».
    * Insérez le taux par livres si le poids total de la charge est inférieur à 100 livres.  
17. Dans le champ <1 000,00 Lbs, saisissez « 3000 ».
    * Insérez le taux par livres si le poids total de la charge est inférieur à 1000 livres.  
18. Cliquez sur Enregistrer.
19. Fermez la page.

## <a name="assign-rate-base"></a>Affecter la base de taux
1. Activer l'extension de la section des attributions de la base de taux.
2. Cliquez sur Nouveau.
    * Vous pouvez avoir plusieurs affectations de base de taux pour chaque table maître des taux. Cela permet de créer différents niveaux de prix pour chaque transporteur selon les destinations, les services ou les bases de taux. Dans cette procédure, vous allez créer une seule affectation de base de taux.  
3. Tapez une valeur dans le champ Nom.
4. Dans le champ Base de taux, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Dans le champ Service, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Dans le champ Code postal d'enlèvement, saisissez « 98052 ».
    * Spécifiez le code postal à partir duquel cette affectation de base de taux doit être valide.    
10. Dans le champ Région du pays d'enlèvement, saisissez « USA ».
11. Cliquez sur Enregistrer.

