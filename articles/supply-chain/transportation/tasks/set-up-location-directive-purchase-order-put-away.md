---
title: Paramétrer une instruction d'emplacement pour le rangement des commandes fournisseur
description: Cette rubrique décrit comment paramétrer une simple instruction d'emplacement.
author: ShylaThompson
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventFixedLocation
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0fd6814163afba0c5b4c99e45a703b00948b73d6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004900"
---
# <a name="set-up-a-location-directive-for-purchase-order-put-away"></a>Paramétrer une instruction d'emplacement pour le rangement des commandes fournisseur

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit comment paramétrer une simple instruction d'emplacement. L'exemple qui est indiqué crée une instruction d'emplacement à utiliser pour déterminer où mettre les articles reçus pour une commande fournisseur. Vous pouvez lire ce guide des tâches avec les données mentionnées en utilisant la société USMF de données de démonstration. Conditions préalables : vous devez créer un code disposition. Dans cette procédure nous utilisons un code disposition appelé Relabel. Si vous créez une instruction d'emplacement dans vos propres données, vous devez avoir configuré la gestion des entrepôts avancée pour votre entrepôt et vos articles. Cette procédure est destinée au gestionnaire d'entrepôts.

1. Dans le volet de navigation, accédez à **Modules > Gestion des entrepôts > Paramétrage > Entrepôt > Instructions d'emplacement**.
2. Dans le champ **Type d'ordre de travail**, sélectionnez **Commandes fournisseurs**.

## <a name="create-a-location-directive-header"></a>Créer un en-tête d'instruction d'emplacement
1. Sélectionnez **Nouveau**.
2. Entrez un nombre dans le champ **Numéro de souche**. Il s'agit de la séquence selon laquelle l'instruction d'emplacement est traitée pour le type de travail sélectionné. Vous pouvez également modifier la séquence, au besoin.  
3. Tapez une valeur dans le champ **Nom**. Il s'agit de l'identificateur unique pour cette instruction.  
4. Dans le champ **Type de travail**, sélectionnez **Put**. Sélectionnez le type de travail à effectuer. Pour l'instruction à la commande fournisseur de type commande de travail, **Put** est la seule valeur prise en charge.  
5. Tapez une valeur dans le champ **Site**.
6. Dans le champ **Entrepôts**, saisissez une valeur. Laissez le code directif vide.  Les codes directifs sont utilisés pour lier une ligne d'ordre de travail de type Mettre à l'instruction spécifique. Pour les commandes fournisseur, l'emplacement de la dernière ligne d'ordre de travail de type Put est résolu avant que le modèle de travail soit déterminé. Par conséquent il est impossible de connecter la dernière ligne d'un modèle de travail à une instruction spécifique.   
7. Dans le champ **Disposition**, tapez une valeur. Code disposition limite l'utilisation de l'instruction de l'emplacement, de sorte que l'instruction d'emplacement n'est utilisée que si le travailleur de l'entrepôt entre cette valeur spécifique lors de l'enregistrement de l'article à l'aide d'un périphérique portable.  
8. Sélectionnez **Enregistrer**.

## <a name="edit-the-query-for-directive"></a>Modifier la requête pour l'instruction
1. Sélectionnez **Modifier une requête**. L'utilisation de cette instruction est déjà limitée pour être utilisée pour les articles stockés dans l'entrepôt spécifié et avec code instruction que vous avez spécifié. Vous pouvez ajouter d'autres contraintes à l'aide de la requête.  
2. Cliquez sur **OK**.

## <a name="add-directive-lines"></a>Ajouter des lignes d'instruction
1. Sélectionnez **Nouveau**. Il s'agit de la séquence selon laquelle les lignes d'instruction d'emplacement sont traitées pour le type de travail sélectionné. Vous pouvez également modifier la séquence, au besoin.  
2. Dans le champ **Quantité de départ**, entrez un nombre. Il s'agit de la plus petite quantité pour laquelle cette ligne directive est valide.  
3. Dans le champ **Quantité d'arrivée**, entrez un nombre.
4. Dans le champ **Unité**, tapez une valeur. Il s'agit de l'unité dans laquelle Quantité de départ et Quantité d'arrivée sont exprimées. Si vous ne renseignez pas ce champ, l'unité de stock de l'article est utilisée.  
5. Dans le champ **Localiser la quantité**, sélectionnez une option.
    - Aucune ou Quantité du contenant : la quantité enregistrée de chaque contenant.  
    - Quantité unitisée : la totalité de la quantité enregistrée.  
    - Quantité restante : la quantité à enregistrer à partir de la ligne de commande fournisseur.  
    - Quantité attendue : la quantité totale spécifiée sur la ligne de commande fournisseur.  
6. Activez ou désactivez la case à cocher **Restreindre par unité**. Si vous sélectionnez cette option et spécifiez l'unité de la page **Restreindre par unité**, seuls les articles avec cette unité de mesure peuvent être mis dans l'emplacement. Par exemple, si l'unité de mesure correspond à des palettes, seuls les articles en palettes peuvent être rangés dans l'emplacement spécifié.  
7. Activez ou désactivez la case à cocher **Autoriser le fractionnement**. Ceci permet à l'instruction de répartir la quantité entre plusieurs emplacements.  
8. Sélectionnez **Enregistrer**.

## <a name="restrict-the-directive-line-to-a-specific-unit"></a>Limiter la ligne directive à une unité spécifique
1. Sélectionnez **Restreindre par unité**. Ce bouton n'est disponible que lorsque vous appuyez sur **Enregistrer** après avoir activé la case à cocher **Restreindre par unité**.  
2. Dans le champ **Unité**, tapez une valeur.
3. Fermez la page.

## <a name="add-a-location-directive-action-line"></a>Ajouter une ligne d'action d'instruction d'emplacement
1. Sélectionnez **Nouveau**. Il s'agit de la séquence selon laquelle les lignes d'action d'instruction d'emplacement sont traitées pour le type de travail sélectionné. Vous pouvez également modifier la séquence, au besoin.  
2. Tapez une valeur dans le champ **Nom**. Il s'agit de l'identificateur unique pour cette action d'instruction.  
3. Dans le champ **Utilisation d'un emplacement fixe**, sélectionnez une option.
    - Emplacements fixes et non fixes : tous les emplacements non fixes sont valides ainsi que le propre emplacement fixe du produit, dans la marge spécifiée dans la requête.  
    - N'utiliser que des emplacements fixes pour le produit : les emplacements fixes pour le produit sont valides, et toutes les variantes de produit partagent le même ensemble d'emplacements fixes.  
    - N'utiliser des emplacements fixes que pour les variantes du produit : seuls les emplacements fixes spécifiés pour chaque variante de produit sont valides.  
4. Dans le champ **Stratégie**, sélectionnez une option. Les ordres de travail de type Commande fournisseur sont compatibles avec les stratégies suivantes : 
    - Aucun : l'article est placé au premier emplacement trouvé.  
    - Consolider : l'article est situé dans un emplacement où des articles similaires sont déjà disponibles.  
    - Emplacement vide sans travail entrant : l'article est situé dans le premier emplacement vide qui est trouvé. Un emplacement est considéré comme vide s'il ne contient pas de stock physique, ni aucun travail entrant prévu.  
5. Sélectionnez **Enregistrer**.

## <a name="edit-the-query-for-directive-action-line"></a>Modifier la requête pour la ligne d'action d'instruction
1. Sélectionnez **Modifier une requête**.
2. Sélectionnez **Ajouter**.
3. Dans le champ **Champ**, saisissez `location profile ID`. Dans cet exemple, nous limiterons les emplacements possibles à l'aide d'un ID de profil d'emplacement.  
4. Tapez une valeur dans le champ **Critères**.
5. Cliquez sur **OK**. Vous pouvez continuer à ajouter des lignes directives et des actions d'instruction jusqu'à ce que vous ayez couvert tous les scénarios possibles de votre entrepôt.  

