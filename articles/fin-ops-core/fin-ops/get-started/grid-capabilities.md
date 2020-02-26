---
title: Capacités de grille
description: Cette rubrique décrit plusieurs fonctionnalités puissantes du contrôle de grille. La nouvelle fonction de grille doit être activée pour avoir accès à ces capacités.
author: jasongre
manager: AnnBe
ms.date: 01/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: b49d7823f48bcc9cdbb56b87d5fa72d46ddfa15c
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019771"
---
# <a name="grid-capabilites"></a>Capacités de grille

[!include [banner](../includes/banner.md)]

Le nouveau contrôle de grille fournit un certain nombre de fonctionnalités utiles et puissantes qui peuvent être utilisées pour améliorer la productivité des utilisateurs, créer des vues plus intéressantes de vos données et obtenir des informations significatives sur vos données. Cet article couvrira les capacités suivantes : 

-  Calcul des totaux
-  Regroupement des données
-  Saisie avant le système
-  Évaluation des expressions mathématiques 

## <a name="calculating-totals"></a>Calcul des totaux
Dans les applications Finance and Operations, les utilisateurs ont la possibilité de voir les totaux au bas des colonnes numériques dans les grilles. Ces totaux sont indiqués dans une section de pied de page au bas de la grille. 

### <a name="showing-the-grid-footer"></a>Affichage du pied de page de la grille
Chaque grille tabulaire des applications Finance and Operations ont une zone de pied de page au bas de la grille qui peut afficher des informations précieuses liées aux données affichées. Ces informations comprennent : 
-  Le nombre de lignes sélectionnées dans le tableau (lorsque plusieurs enregistrements sont sélectionnés)
-  Les totaux généraux au bas des colonnes numériques configurées
-  Le nombre de lignes dans le dataset 

Ce pied de page est masqué par défaut, mais peut être facilement activé. Pour afficher le pied de page d'une grille, cliquez avec le bouton droit sur un en-tête de colonne dans la grille et sélectionnez l'option **Afficher le pied de page**. Une fois le pied de page activé pour une grille particulière, ce paramètre sera conservé jusqu'à ce que l'utilisateur choisisse de masquer le pied de page, ce qui peut être fait en cliquant avec le bouton droit sur un en-tête de colonne et en sélectionnant **Masquer le pied de page**.  Notez que l'emplacement de l'action **Afficher le pied de page / Masquer le pied de page** sera déplacé dans une future mise à jour. 

### <a name="specifying-columns-with-totals"></a>Spécification de colonnes avec des totaux
Actuellement, aucune colonne ne sera configurée pour afficher les totaux par défaut. Cela est considéré comme une activité de configuration à part, similaire à l'ajustement de la largeur des colonnes dans les grilles. Une fois que vous avez spécifié que vous souhaitez voir les totaux d'une colonne, ce paramètre sera mémorisé lors de votre prochaine visite sur la page.  

Il existe deux façons de configurer une colonne pour afficher un total : 
1.  Faites un clic droit sur la colonne pour laquelle vous souhaitez voir un total et sélectionnez **Total de cette colonne**. Cette action aura trois effets. Tout d'abord, elle rendra le pied de page visible. Deuxièmement, elle enregistrera votre préférence d'affichage du total sur cette colonne. Troisièmement, cette action lancera un calcul des totaux pour cette colonne et toutes les autres que vous avez précédemment configurées pour afficher les totaux. Le temps nécessaire à l'affichage d'un total est directement lié à la taille de l'ensemble de données que vous totalisez.  

2.  Une fois le pied de page affiché, vous pouvez également cliquer sur **Afficher le total**dans la zone de pied de page en bas de la colonne pour laquelle vous souhaitez voir un total. S'il n'y a pas de colonnes configurées, le bouton **Afficher le total** sera visible pour toutes les colonnes numériques. Une fois qu'il y a au moins une colonne configurée pour les totaux, les boutons **Afficher le total** ne seront disponibles qu'en survol ou en focus. Cette action enregistre simplement votre préférence d'affichage du total dans cette colonne pour les visites futures sur cette page, et cet état est indiqué par le tiret qui apparaît dans cette colonne dans le pied de page (ou un total s'affichera immédiatement si l'ensemble de données est suffisamment petit).

Si vous faites une erreur et que vous ne voulez plus voir un total dans une colonne particulière, faites un clic droit sur la colonne et sélectionnez **Masquer le total** ou sélectionnez le bouton **Masquer le total** dans le pied de page de cette colonne. Cette préférence sera également enregistrée pour les futures visites de la page. 

### <a name="calculating-totals"></a>Calcul des totaux
Lorsque vous accédez à une page avec le pied de page visible et des colonnes déjà configurées pour les totaux, les totaux peuvent ou non être affichés dans le pied de page. Le comportement dépend de la taille de l'ensemble de données sur la page. Si l'ensemble de données est suffisamment petit, les totaux seront affichés automatiquement, ainsi que le nombre de lignes dans l'ensemble de données. S'il y a des tirets dans le pied de page sous les colonnes que vous avez configurées pour les totaux, le jeu de données est trop volumineux pour que le système affiche immédiatement les totaux et une action explicite est nécessaire pour calculer les totaux. Pour ce faire, cliquez sur le bouton **Calculer** dans le pied de page, ou faites un clic droit sur une colonne pour laquelle vous souhaitez afficher un total et sélectionnez **Total de cette colonne**.  

Si le calcul prend trop de temps, vous pouvez annuler l'opération en sélectionnant le bouton **Annuler**. Parfois, cependant, l'ensemble de données sera trop volumineux pour calculer les totaux (une limite imposée par votre organisation), et vous serez invité à filtrer davantage vos données.

Les totaux seront mis à jour automatiquement lorsque vous mettez à jour, supprimez ou créez des lignes dans l'ensemble de données.  

## <a name="grouping-data"></a>Regroupement des données
Les utilisateurs professionnels doivent souvent effectuer une analyse ad hoc des données. Bien que cela puisse être fait en exportant des données vers Microsoft Excel et en utilisant des tableaux croisés dynamiques, la capacité de **Regroupement** dans les grilles tabulaires permet aux utilisateurs d'organiser leurs données de manière intéressante dans les applications Finance and Operations. Comme cette fonctionnalité étend la fonctionnalité **Totaux**, le **Regroupement** vous permet également d'obtenir des informations significatives sur les données en fournissant des sous-totaux au niveau du groupe.

Pour utiliser cette fonction, cliquez avec le bouton droit sur la colonne que vous souhaitez regrouper et sélectionnez **Regrouper par cette colonne**. Cette action triera les données selon la colonne sélectionnée, ajoutera une nouvelle colonne Grouper par au début de la grille et insérera des « lignes d'en-tête » au début de chaque groupe. Ces lignes d'en-tête fournissent les informations suivantes sur chaque groupe : 
-  Valeur des données pour le groupe 
-  Étiquette de colonne. Cela sera particulièrement utile une fois que plusieurs niveaux de regroupement seront pris en charge.  
-  Nombre de lignes de données dans ce groupe
-  Sous-totaux pour toute colonne configurée pour afficher les totaux

Lorsque [Vues enregistrées ](saved-views.md)est activé, ce regroupement peut être enregistré comme personnalisation dans le cadre d'une vue pour un accès rapide la prochaine fois que vous visiterez la page.  

Si vous sélectionnez **Regrouper par cette colonne** sur une autre colonne, le regroupement d'origine sera remplacé, car seul le niveau de regroupement est pris en charge dans 10.0.9 / Mise à jour de plateforme 33.

Pour annuler le regroupement dans une grille, cliquez avec le bouton droit sur la colonne de regroupement et sélectionnez **Dissocier**.  


## <a name="evaluating-math-expressions"></a>Évaluation des expressions mathématiques
Pour booster la productivité, l'utilisateur peut entrer des formules mathématiques dans des cellules numériques dans une grille, au lieu d'avoir à effectuer le calcul dans une application en dehors du système. Par exemple, vous pouvez saisir **= 15 \*4** et la touche de tabulation hors du champ. Le système évaluera l'expression et enregistrera une valeur de « 60 » pour le champ.

Pour que le système reconnaisse une valeur comme une expression, démarrez la valeur avec un signe égal (**=**). Pour plus de détails sur les opérateurs et la syntaxe pris en charge, consultez [Symboles mathématiques pris en charge](http://redhivesoftware.github.io/math-expression-evaluator/#supported-maths-symbols).  
