---
title: Capacités de grille
description: Cette rubrique décrit plusieurs fonctionnalités puissantes du contrôle de grille. La nouvelle fonction de grille doit être activée pour avoir accès à ces capacités.
author: jasongre
manager: AnnBe
ms.date: 02/10/2020
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
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 7136edba828bf97b6e0c8d2a698b884640d680e5
ms.sourcegitcommit: 880f617d1d6e95eccbed762c7ea04398553c2ec0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "3036263"
---
# <a name="grid-capabilities"></a>Capacités de grille

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Le nouveau contrôle de grille fournit un certain nombre de fonctionnalités utiles et puissantes qui peuvent être utilisées pour améliorer la productivité des utilisateurs, créer des vues plus intéressantes de vos données et obtenir des informations significatives sur vos données. Cet article couvrira les capacités suivantes : 

-  Calcul des totaux
-  Regroupement des données
-  Saisie avant le système
-  Évaluation des expressions mathématiques 

## <a name="calculating-totals"></a>Calcul des totaux
Dans les applications Finance and Operations, les utilisateurs ont la possibilité de voir les totaux au bas des colonnes numériques dans les grilles. Ces totaux sont indiqués dans une section de pied de page au bas de la grille. 

### <a name="showing-the-grid-footer"></a>Affichage du pied de page de la grille
Une zone de pied de page se trouve au bas de chaque grille tabulaire dans les applications Finance and Operations. Le pied de page peut afficher des informations utiles relatives aux données qui s'affichent dans la grille. Voici quelques exemples de ces informations :

- Le nombre de lignes sélectionnées dans le tableau (lorsque plusieurs enregistrements sont sélectionnés)
- Les totaux généraux au bas des colonnes numériques configurées
- Le nombre de lignes dans le dataset 

Ce pied de page est masqué par défaut, mais peut être facilement activé. Pour afficher le pied de page d'une grille, cliquez avec le bouton droit sur un en-tête de colonne dans la grille et sélectionnez l'option **Afficher le pied de page**. Une fois le pied de page activé pour une grille particulière, ce paramètre sera conservé jusqu'à ce que l'utilisateur choisisse de masquer le pied de page, ce qui peut être fait en cliquant avec le bouton droit sur un en-tête de colonne et en sélectionnant **Masquer le pied de page**.  Notez que l'emplacement de l'action **Afficher le pied de page / Masquer le pied de page** sera déplacé dans une future mise à jour. 

### <a name="specifying-columns-with-totals"></a>Spécification de colonnes avec des totaux
Actuellement, aucune colonne ne sera configurée pour afficher les totaux par défaut. Cela est considéré comme une activité de configuration à part, similaire à l'ajustement de la largeur des colonnes dans les grilles. Une fois que vous avez spécifié que vous souhaitez voir les totaux d'une colonne, ce paramètre sera mémorisé lors de votre prochaine visite sur la page.  

Il existe deux façons de configurer une colonne pour afficher un total : 

- Faites un clic droit dans la colonne pour laquelle vous souhaitez voir un total, puis sélectionnez **Total de cette colonne**. Cette action provoque trois événements :

    1. Le pied de page devient visible. 
    2. Votre préférence d'affichage du total pour cette colonne est enregistrée. 
    3. Un calcul des totaux est lancé pour cette colonne et toutes les autres colonnes que vous avez précédemment configurées pour afficher les totaux. Le temps nécessaire pour afficher un total dépend de la taille de l'ensemble de données que vous totalisez.

- Une fois le pied de page visible, sélectionnez **Afficher le total** dans la zone de pied de page en bas de la colonne pour laquelle vous souhaitez voir un total. S'il n'y a pas de colonnes configurées, le bouton **Afficher le total** sera disponible pour toutes les colonnes numériques. 

    Une fois qu'au moins une colonne est configurée pour les totaux, les boutons **Afficher le total** ne seront disponibles qu'en survol ou en focus. L'action de sélection de l'option **Afficher le total** enregistre simplement votre préférence d'affichage du total dans cette colonne, afin que la préférence soit appliquée lors des visites futures sur cette page. Dans le pied de page, cet état est indiqué par un tiret qui s'affiche dans la colonne. (Sinon, si l'ensemble de données est suffisamment petit, un total s'affiche immédiatement.)

Si vous faites une erreur et que vous ne voulez plus voir un total dans une colonne particulière, faites un clic droit sur la colonne et sélectionnez **Masquer le total** ou sélectionnez le bouton **Masquer le total** dans le pied de page de cette colonne. Cette préférence sera également enregistrée pour les futures visites de la page. 

### <a name="calculating-totals"></a>Calcul des totaux
Lorsque vous accédez à une page avec le pied de page visible et des colonnes déjà configurées pour les totaux, les totaux peuvent ou non être affichés dans le pied de page. Le comportement dépend de la taille de l'ensemble de données sur la page. Si l'ensemble de données est suffisamment petit, les totaux seront affichés automatiquement, ainsi que le nombre de lignes dans l'ensemble de données. S'il y a des tirets dans le pied de page sous les colonnes que vous avez configurées pour les totaux, le jeu de données est trop volumineux pour que le système affiche immédiatement les totaux et une action explicite est nécessaire pour calculer les totaux. Pour ce faire, cliquez sur le bouton **Calculer** dans le pied de page, ou faites un clic droit sur une colonne pour laquelle vous souhaitez afficher un total et sélectionnez **Total de cette colonne**.  

Si le calcul prend trop de temps, vous pouvez annuler l'opération en sélectionnant le bouton **Annuler**. Parfois, cependant, l'ensemble de données sera trop volumineux pour calculer les totaux (une limite imposée par votre organisation), et vous serez invité à filtrer davantage vos données.

Les totaux seront mis à jour automatiquement lorsque vous mettez à jour, supprimez ou créez des lignes dans l'ensemble de données.  

## <a name="grouping-data"></a>Regroupement des données
Les utilisateurs professionnels doivent souvent effectuer une analyse ad hoc des données. Bien que cela puisse être fait en exportant des données vers Microsoft Excel et en utilisant des tableaux croisés dynamiques, la capacité de **Regroupement** dans les grilles tabulaires permet aux utilisateurs d'organiser leurs données de manière intéressante dans les applications Finance and Operations. Comme cette fonctionnalité étend la fonctionnalité **Totaux**, le **Regroupement** vous permet également d'obtenir des informations significatives sur les données en fournissant des sous-totaux au niveau du groupe.

Pour utiliser cette fonction, cliquez avec le bouton droit sur la colonne que vous souhaitez regrouper et sélectionnez **Regrouper par cette colonne**. Cette action triera les données selon la colonne sélectionnée, ajoutera une nouvelle colonne Grouper par au début de la grille et insérera des « lignes d'en-tête » au début de chaque groupe. Ces lignes d'en-tête fournissent les informations suivantes sur chaque groupe : 
-  Valeur des données pour le groupe 
-  Libellé de colonne (Ces informations seront particulièrement utiles une fois que plusieurs niveaux de regroupement seront pris en charge.)
-  Nombre de lignes de données dans ce groupe
-  Sous-totaux pour toute colonne configurée pour afficher les totaux

Lorsque [Vues enregistrées ](saved-views.md)est activé, ce regroupement peut être enregistré comme personnalisation dans le cadre d'une vue pour un accès rapide la prochaine fois que vous visiterez la page.  

Si vous sélectionnez **Regrouper par cette colonne** pour une autre colonne, le regroupement d'origine est remplacé, car un seul niveau de regroupement est pris en charge dans la version 10.0.9 avec Plateform update 33.

Pour annuler le regroupement dans une grille, cliquez avec le bouton droit sur la colonne de regroupement et sélectionnez **Dissocier**.  


## <a name="evaluating-math-expressions"></a>Évaluation des expressions mathématiques
Pour booster la productivité, les utilisateurs peuvent entrer des formules mathématiques dans des cellules numériques d'une grille. Ils n'ont pas besoin d'effectuer le calcul dans une application en dehors du système. Par exemple, si vous entrez **=15\*4**, puis appuyez sur la touche **Tab** pour quitter le champ, le système évaluera l'expression et enregistrera la valeur de **60** pour le champ.

Pour que le système reconnaisse une valeur comme une expression, démarrez la valeur avec un signe égal (**=**). Pour plus de détails sur les opérateurs et la syntaxe pris en charge, consultez [Symboles mathématiques pris en charge](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).  
