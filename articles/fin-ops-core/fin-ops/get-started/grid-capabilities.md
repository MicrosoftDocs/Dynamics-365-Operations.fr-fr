---
title: Capacités de grille
description: Cet article décrit plusieurs fonctionnalités puissantes du contrôle de grille. Vous devez activer la nouvelle fonction de grille pour avoir accès à ces capacités.
author: jasongre
ms.date: 08/29/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 6d14bba13dbf701a8c27c10ac2d318b071092bc1
ms.sourcegitcommit: 77ffeccffff28fbb6ff576864d7abddd412cdab6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2022
ms.locfileid: "9852371"
---
# <a name="grid-capabilities"></a>Capacités de grille

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Le nouveau contrôle de grille fournit un certain nombre de fonctionnalités utiles et puissantes qui peuvent être utilisées pour améliorer la productivité des utilisateurs, créer des vues plus intéressantes de vos données et obtenir des informations significatives sur vos données. Cet article couvrira les capacités suivantes : 

- Affichage des valeurs calculées 
- Saisie avant le système
- Évaluation des expressions mathématiques 
- Regroupement des données tabulaires (activé séparément à l’aide de la fonctionnalité **Regroupement en grilles**)
- Figeage des colonnes (activé séparément en utilisant la fonctionnalité **Figeage des colonnes dans les grilles**)
- Ajuster automatiquement la largeur de la colonne
- Colonnes extensibles

## <a name="showing-calculated-values"></a>Affichage des valeurs calculées
Dans les applications financières et opérationnelles, les utilisateurs peuvent afficher une valeur calculée pour chaque colonne numérique d’une grille. Une section de pied de page au bas de la grille affiche ces valeurs calculées.

[![Affichage des valeurs calculées dans des grilles.](./media/grids-aggregation.png)](./media/grids-aggregation.png)

Dans les versions antérieures à 10.0.29, le total est la seule valeur calculée prise en charge. Cependant, à partir de la version 10.0.29, après avoir activé la fonctionnalité **Capacités d’agrégation de grille étendues** , les utilisateurs peuvent sélectionner parmi les quatre valeurs calculées suivantes :

- Minimale
- Maximale
- Total
- Moyenne

Une seule colonne ne peut afficher qu’un seul type de valeur calculée. Cependant, chaque colonne de la grille peut être configurée pour afficher un type différent de valeur calculée.

### <a name="showing-the-grid-footer"></a>Affichage du pied de page de la grille
Une zone de pied de page se trouve au bas de chaque grille tabulaire dans les applications de finances et d’opérations. Le pied de page peut afficher des informations utiles relatives aux données qui s’affichent dans la grille. Voici quelques exemples de ces informations :

- Le nombre de lignes sélectionnées dans le tableau (quand plusieurs enregistrements sont sélectionnés)
- Les valeurs calculées au bas des colonnes numériques configurées (par exemple, grands totaux)
- Le nombre de lignes dans le dataset 

Ce pied de page est masqué par défaut, mais peut être facilement activé. Pour afficher le pied de page d’une grille, sélectionnez le bouton **Options de grille** dans l’en-tête de la grille, puis sélectionnez l’option **Afficher le pied de page**. Une fois que vous avez activé le pied de page pour une grille particulière, ce paramètre sera mémorisé jusqu’à ce que l’utilisateur choisisse de masquer le pied de page. Pour masquer le pied de page, sélectionnez **Masquer le pied de page** dans le menu **Options de grille**.

### <a name="specifying-columns-with-calculated-values"></a>Spécification de colonnes avec des valeurs calculées
Actuellement, aucune colonne n’affiche les valeurs calculées par défaut. Au lieu de cela, la configuration est considérée comme une activité ponctuelle, comme l’ajustement de la largeur des colonnes dans les grilles. Après avoir spécifié que vous souhaitez voir une valeur calculée pour une colonne, ce paramètre sera mémorisé la prochaine fois que vous visiterez la page.

Il existe deux façons de configurer une colonne pour afficher une valeur calculée :

- Sélectionnez et maintenez (ou cliquez avec le bouton droit) dans la colonne pour laquelle vous souhaitez afficher une valeur calculée. Si la fonction **Capacités d’agrégation de grille étendues** est activée, sélectionnez **Afficher les totaux des colonnes**, et ensuite sélectionnez la valeur calculée souhaitée. Si cette fonctionnalité n’est pas activée, sélectionnez **Additionnez cette colonne**. Cette action provoque trois événements :

    1. Le pied de page de la grille devient visible. 
    2. Votre préférence pour l’affichage d’une valeur calculée pour la colonne est enregistrée. 
    3. Le calcul souhaité est lancé pour la colonne et toutes les autres colonnes que vous avez précédemment configurées pour afficher une valeur calculée. Le temps nécessaire pour afficher les valeurs calculées dépend de la taille du jeu de données.

- Une fois le pied de page visible, sélectionnez **Afficher le total** (ou **Sélectionnez la valeur calculée** si la **Capacités d’agrégation de grille étendues** est activée) dans la zone de pied de page au bas de la colonne pour laquelle vous souhaitez afficher une valeur calculée. S’il n’y a pas de colonnes configurées, ce bouton sera disponible dans le pied de page dans toutes les colonnes numériques.

    Une fois qu’au moins une colonne est configurée pour afficher une valeur calculée, la **Afficher le total** (ou **Sélectionnez la valeur calculée**) ne sera disponible que lors du survol ou de la mise au point. L’action de sélection du bouton enregistre simplement votre préférence d’affichage d’une valeur calculée dans la colonne, afin que la préférence soit appliquée au moment des visites futures sur cette page. Dans le pied de page, cet état est indiqué par un tiret qui s’affiche dans la colonne. (Notez que la valeur calculée apparaîtra immédiatement si l’ensemble de données est suffisamment petit.)

Si vous faites une erreur et que vous ne souhaitez plus afficher une valeur calculée dans une colonne spécifique, sélectionnez et maintenez (ou cliquez avec le bouton droit) dans la colonne, puis sélectionnez **Masquer le total** (ou **Afficher les totaux des colonnes \> Aucun** si la **Capacités d’agrégation de grille étendues** fonction est activée). Sinon, sélectionnez **Masquer le total** (ou **Masquer la valeur calculée**) dans le pied de page de cette colonne. Cette préférence sera également enregistrée pour les futures visites de la page. 

### <a name="calculating-aggregate-values"></a>Calcul des valeurs agrégées
Lorsque vous accédez à une page où le pied de page est visible et que les colonnes sont déjà configurées pour afficher les valeurs calculées, ces valeurs peuvent ne pas s’afficher dans le pied de page. Le comportement dépend de la taille du jeu de données sur la page. Si le jeu de données est suffisamment petit, les valeurs calculées seront affichées automatiquement, ainsi que le nombre de lignes dans le jeu de données. S’il y a des tirets dans le pied de page sous les colonnes que vous avez configurées, le jeu de données est trop volumineux pour que le système affiche immédiatement les valeurs calculées. Dans ce cas, une action explicite est requise pour calculer les valeurs. Pour calculer les valeurs, sélectionnez le **Calculer** bouton dans le pied de page. Sinon, sélectionnez et maintenez (ou cliquez avec le bouton droit) dans une colonne dont vous souhaitez afficher le total, et ensuite sélectionnez **Totaliser cette colonne** (ou **Afficher les totaux des colonnes** et puis la valeur calculée souhaitée si la fonction **Capacités d’agrégation de grille étendues** est activée).

Si le calcul prend trop de temps, vous pouvez annuler l’opération à tout moment en sélectionnant le bouton **Annuler**. Parfois, le jeu de données sera trop volumineux pour calculer des valeurs agrégées (une limite imposée par votre organisation). Dans ce cas, vous serez plutôt averti de filtrer davantage vos données.

> [!NOTE]
> Les administrateurs de système peuvent modifier la limite du nombre d’enregistrements qui sont disponibles pour le calcul des agrégats en ajustant le paramètre **Nombre maximal d’enregistrements locaux pour chaque grille** sur la page **Options de performances des clients** . La valeur par défaut est 25 000 enregistrements. Les administrateurs doivent être prudents lorsqu’ils ajustent cette valeur, car une valeur trop élevée peut épuiser la mémoire disponible sur la machine de l’utilisateur. Nous recommandons que la valeur ne doit pas dépasser 50 000 enregistrements.

Les valeurs calculées seront mises à jour automatiquement quand vous mettez à jour, supprimez ou créez des lignes dans le jeu de données.

## <a name="typing-ahead-of-the-system"></a>Saisie avant le système
Dans de nombreux scénarios professionnels, la capacité de saisir rapidement des données dans le système est très importante. Avant l’introduction du nouveau contrôle de grille, les utilisateurs ne pouvaient modifier les données que dans la ligne actuelle. Par conséquent, après avoir effectué des modifications dans une ligne, les utilisateurs ne pouvaient pas passer à une autre ligne ou créer une nouvelle ligne tant que le système n’avait pas validé avec succès les modifications dans la ligne actuelle et (dans le cas de la création de lignes) exécuté toute la logique associée avec la création d’une nouvelle ligne. Pour aider à réduire le temps que les utilisateurs passent à attendre que ces opérations soient terminées, et aider à améliorer la productivité des utilisateurs, la nouvelle grille ajuste ces actions afin qu’elles soient asynchrones. Les utilisateurs peuvent créer de nouvelles lignes ou passer à d’autres lignes pour apporter des modifications pendant que les validations de lignes précédentes et la logique de création de lignes sont en attente. 

[![Saisie en amont du système.](./media/gridFastEntry-07-25-2022.gif)](./media/gridFastEntry-07-25-2022.gif)

Pour prendre en charge ce nouveau comportement, une nouvelle colonne pour le statut de la ligne a été ajoutée à droite de la colonne de sélection de ligne quand la grille est en mode édition. Cette colonne indique l’un des statuts suivants :

- **Vide** – L’image sans statut indique que la ligne a été correctement enregistrée par le système.
- **Traitement en attente** – Ce statut indique que les modifications de la ligne n’ont pas encore été enregistrées par le serveur mais se trouvent dans une file d’attente de modifications qui doivent être traitées. Avant de prendre des mesures en dehors de la grille, vous devez attendre que toutes les modifications en attente soient traitées. En outre, le texte de ces lignes est en italique pour indiquer le statut non enregistré des lignes. 
- **Etat non valide** – Ce statut indique qu’un avertissement ou un message a été déclenché pendant le traitement de la ligne et qu’il a pu empêcher le système d’enregistrer les modifications dans cette ligne. Dans l’ancienne grille, si l’enregistrement avait échoué, vous étiez obligé de retourner dans la ligne pour résoudre le problème immédiatement. Cependant, dans la nouvelle grille, vous êtes averti qu’un problème de validation a été rencontré, mais vous pouvez décider quand vous souhaitez résoudre les problèmes de la ligne. Quand vous êtes prêt à résoudre un problème, vous pouvez placer manuellement le focus sur la ligne. Vous pouvez également sélectionner l’action **Résoudre ce problème**. Cette action ramène immédiatement le focus sur la ligne qui pose problème et vous permet d’effectuer des modifications à l’intérieur ou à l’extérieur de la grille. Notez que le traitement des lignes en attente suivantes est arrêté jusqu’à ce que cet avertissement de validation soit résolu. 
- **En pause** – Ce statut indique que le traitement par le serveur est interrompu, car la validation de la ligne a déclenché une boîte de dialogue contextuelle qui nécessite une entrée utilisateur. Étant donné que l’utilisateur peut entrer des données dans une autre ligne, la boîte de dialogue contextuelle n’est pas immédiatement présentée à cet utilisateur. Au lieu de cela, elle sera affichée quand l’utilisateur choisira de reprendre le traitement. Ce statut est accompagné d’une notification qui informe l’utilisateur de la situation. La notification comprend une action **Reprendre le traitement** qui déclenchera la boîte de dialogue contextuelle.

### <a name="differences-when-entering-data-ahead-of-the-system"></a>Différences lors de la saisie de données en amont du système
Lorsque vous saisissez des données avant l’endroit où le système traite, vous pouvez vous attendre à quelques changements dans l’expérience de saisie des données :

- Vous remarquerez qu’il n’y a pas de listes déroulantes de recherche, que les valeurs de champ ne sont pas validées après le passage à une autre colonne de la même ligne et que les colonnes n’affichent pas initialement les valeurs par défaut. Ce problème se produit lorsque vous créez ou mettez à jour avant le système. Cependant, une fois que le système aura rattrapé l’endroit où vous êtes en train d’éditer, l’expérience standard reprendra. Si vous avez apporté des modifications à un champ qui reçoit généralement une valeur par défaut, vos modifications remplacent la valeur du champ par défaut lorsque le serveur commence à traiter la ligne.
- Si vous créez une nouvelle ligne à l’aide de la clé **Flèche vers le bas** , toutes les colonnes de la grille apparaîtront comme modifiables. Par défaut, le focus sera placé dans la première colonne de la nouvelle ligne. Cette colonne peut ne pas être la même colonne qui a reçu le focus initial dans la grille héritée, ou la même colonne qui reçoit le focus après avoir sélectionné un **Nouveau** bouton. Votre organisation peut personnaliser le système et modifier la colonne qui reçoit le focus initial lorsque le **Flèche vers le bas** clé est sélectionnée. Pour plus d’informations, consultez la section [Spécification de la colonne qui reçoit le focus initial lorsque de nouvelles lignes sont créées à l’aide de la touche fléchée vers le bas](#developer-specifying-the-column-that-receives-the-initial-focus-when-new-rows-are-created-by-using-the-down-arrow-key) . Quoi qu’il en soit, vous pouvez utiliser la personnalisation pour optimiser chaque grille pour la saisie de données. Plus précisément, vous pouvez réorganiser les champs afin que la première colonne soit la colonne dans laquelle vous souhaitez commencer à saisir des données. Vous souhaiterez peut-être également réorganiser les champs en général pour la saisie de données, afin de réduire les taquets de tabulation et de masquer les champs qui ne sont pas requis pour la saisie de données dans cette vue particulière.

### <a name="pasting-from-excel"></a>Collage depuis Excel
Les utilisateurs ont toujours pu exporter des données à partir de grilles dans les applications de finances et d’opérations vers Microsoft Excel à l’aide du mécanisme **Exporter vers Excel**. Cependant, la possibilité d’entrer des données avant le système permet à la nouvelle grille de prendre en charge la copie de tableaux à partir d’Excel et de les coller directement dans des grilles dans les applications de finances et d’opérations. La cellule de grille à partir de laquelle l’opération de collage est lancée détermine où le tableau copié commence à être collé. Le contenu de la grille est écrasé par le contenu de la table copiée, sauf dans deux cas :

- Si le nombre de colonnes dans la table copiée dépasse le nombre de colonnes qui restent dans la grille, à partir de l’emplacement de collage, l’utilisateur est informé que les colonnes supplémentaires ont été ignorées. 
- Si le nombre de lignes dans le tableau copié dépasse le nombre de lignes dans la grille, à partir de l’emplacement de collage, les cellules existantes sont remplacées par le contenu collé et toutes les lignes supplémentaires du tableau copié sont insérées en tant que nouvelles lignes en bas de la grille. 

## <a name="evaluating-math-expressions"></a>Évaluation des expressions mathématiques
Pour booster la productivité, les utilisateurs peuvent entrer des formules mathématiques dans des cellules numériques d’une grille. Ils n’ont pas besoin d’effectuer le calcul dans une application en dehors du système. Par exemple, si vous entrez **=15\*4**, puis appuyez sur la touche **Tab** pour quitter le champ, le système évaluera l’expression et enregistrera la valeur de **60** pour le champ.

[![Évaluation des expressions mathématiques.](./media/gridMathExpression-07-25-2022.gif)](./media/gridMathExpression-07-25-2022.gif)

Pour que le système reconnaisse une valeur comme une expression, démarrez la valeur avec un signe égal (**=**). Pour en savoir plus sur les opérateurs et la syntaxe pris en charge, consultez [Symboles mathématiques pris en charge](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

Depuis la version 10.0.29, la possibilité d’évaluer les expressions mathématiques dans les commandes numériques a été étendue et est désormais également disponible en dehors de la grille.

## <a name="grouping-tabular-data"></a>Regroupement des données tabulaires
Les utilisateurs métier doivent souvent effectuer une analyse ad hoc des données. Bien que cette analyse puisse être faite en exportant des données vers Microsoft Excel et en utilisant des tableaux croisés dynamiques, la fonctionnalité **Regroupement en grilles**, dépendante de la nouvelle fonctionnalité de contrôle de grille, permet aux utilisateurs d’organiser leurs données tabulaires de manière intéressante dans les applications de finances et d’opérations. Du fait que cette fonctionnalité étend la fonctionnalité de **Valeurs calculées**, le **Regroupement** vous permet également d’obtenir des informations significatives sur les données en fournissant des valeurs calculées (par exemple, des sous-totaux) au niveau du groupe.

[![Regroupement des données dans une grille.](./media/grids-groupingWithTotals.png)](./media/grids-groupingWithTotals.png)

Pour utiliser cette fonction, cliquez avec le bouton droit sur la colonne selon laquelle vous souhaitez regrouper et sélectionnez **Regrouper par cette colonne**. Cette action triera les données selon la colonne sélectionnée, ajoutera une nouvelle colonne **Grouper par** au début de la grille et insérera des « lignes d’en-tête » au début de chaque groupe. Ces lignes d’en-tête fournissent les informations suivantes sur chaque groupe :

- Valeur des données pour le groupe 
- Nom de colonne (ces informations sont particulièrement utiles quand vous avez plusieurs niveaux de regroupement)
- Nombre de lignes de données dans ce groupe
- Valeurs calculées pour toute colonne configurée (par exemple, sous-totaux si la colonne est configurée pour afficher un total)

Avec [Vues enregistrées](saved-views.md) activées, vous pouvez enregistrer le regroupement dans le cadre d’une vue sur des pages qui permettent d’enregistrer des requêtes dans des vues. Par exemple, celles avec de grands sélecteurs de vue. Pour obtenir des informations détaillées, voir la section [Basculer entre les vues](saved-views.md#switching-between-views). 

### <a name="multiple-levels-of-grouping"></a>Plusieurs niveaux de regroupement
Après avoir regroupé les données dans une seule colonne, vous pouvez regrouper les données dans une colonne différente en sélectionnant **Regrouper selon cette colonne** sur la colonne souhaitée. Ce processus peut être répété jusqu’à ce que vous disposiez de 5 niveaux de regroupement imbriqués, ce qui correspond à la profondeur maximale prise en charge. À ce stade, vous ne pourrez plus regrouper par colonnes supplémentaires.

À tout moment, vous pouvez supprimer le regroupement sur n’importe quelle colonne en cliquant avec le bouton droit sur cette colonne et en sélectionnant **Dissocier**. Vous pouvez également supprimer le regroupement de toutes les colonnes en sélectionnant **Options de grille** puis **Dissocier tout**.

### <a name="sorting-grouped-data"></a>Tri des données groupées
Après avoir regroupé les données sur une ou plusieurs colonnes, vous pouvez modifier le sens du tri pour n’importe quelle colonne de regroupement via l’en-tête de colonne correspondant. 

Si vous triez sur une colonne non groupée, le regroupement reste intact. Les données sont triées à l’intérieur de chaque groupe, en fonction de la colonne sélectionnée.

### <a name="expanding-and-collapsing-groups"></a>Développer et réduire les groupes
Le regroupement initial de données aura tous les groupes développés. Vous pouvez créer des vues résumées des données en réduisant des groupes individuels, ou vous pouvez utiliser le développement et la réduction de groupe pour faciliter la navigation dans les données. Pour développer ou réduire un groupe, sélectionnez le bouton de chevron (>) dans la ligne d’en-tête de groupe correspondante. Notez que l’état de développement/réduction des groupes individuels **n’est pas** enregistré dans la personnalisation.

### <a name="selecting-and-unselecting-rows-at-the-group-level"></a>Sélection et désélection de lignes au niveau du groupe
De la même manière que vous pouvez sélectionner (ou désélectionner) toutes les lignes de la grille en cochant la case en haut de la première colonne de la grille, vous pouvez également sélectionner (ou désélectionner) rapidement toutes les lignes d’un groupe en cochant la case dans la ligne d’en-tête de groupe correspondante. La case à cocher dans la ligne d’en-tête de groupe reflète toujours l’état de sélection actuel des lignes de ce groupe, que toutes les lignes soient sélectionnées, qu’aucune ligne ne soit sélectionnée ou que seules certaines lignes soient sélectionnées.

### <a name="hiding-column-names"></a>Masquer les noms de colonnes
Au moment du regroupement de données, le comportement par défaut consiste à afficher le nom de la colonne dans la ligne d’en-tête de groupe. Vous pouvez choisir de supprimer le nom de colonne dans les lignes d’en-tête de groupe en sélectionnant **Options de grille** > **Masquer le nom de la colonne du groupe**.

### <a name="grouping-on-date-and-time-columns"></a>Regroupement sur des colonnes de date et d’heure
Lorsque vous regroupez sur les champs Date ou DateHeure, vous avez l’option pour regrouper par Année, Mois ou Jour. Le groupe « valeur » dans la ligne d’en-tête correspondante correspondra au format de ce champ. De plus, pour les champs DateHeure et Heure, vous pouvez regrouper par Heure, Minute ou Seconde.

> [!IMPORTANT]
> Les utilisateurs ne peuvent actuellement pas ajouter de colonne de regroupement après s’être regroupés sur un segment d’une colonne de date ou d’heure.

## <a name="freezing-columns"></a>Figer les colonnes
Certaines colonnes d’une grille peuvent être suffisamment importantes en termes de contexte que vous ne souhaitez pas qu’elles défilent hors de la vue. Au lieu de cela, vous voulez que les valeurs de ces colonnes soient toujours visibles. La fonctionnalité **Figeage des colonnes dans la grille** offre cette flexibilité aux utilisateurs. 

[![Figeage des colonnes dans une grille.](./media/gridFreezingColumns-07-25-2022.gif)](./media/gridFreezingColumns-07-25-2022.gif)

Pour figer une colonne, cliquez avec le bouton droit sur l’en-tête de la colonne, puis sélectionnez **Figer la colonne**. La première fois que vous effectuez cette étape, la colonne sélectionnée devient la première colonne et ne défilera plus hors du champ visuel. Toute colonne suivante que vous figez sera ajoutée à droite de la dernière colonne figée. Vous pouvez utiliser la fonctionnalité Déplacer standard pour réorganiser les colonnes figées selon vos besoins. Cependant, les colonnes figées ne peuvent pas être déplacées de sorte qu’elles apparaissent dans l’ensemble des colonnes non figées. De même, les colonnes non figées ne peuvent pas être déplacées de sorte qu’elles apparaissent dans l’ensemble des colonnes figées.

Pour libérer une colonne, cliquez avec le bouton droit sur l’en-tête de la colonne figée, puis sélectionnez **Libérer la colonne**. 

Notez que les colonnes de sélection de ligne et d’état de ligne dans la nouvelle grille sont toujours figées comme les deux premières colonnes. Par conséquent, quand ces colonnes sont incluses dans une grille, elles seront toujours visibles pour les utilisateurs, quelle que soit la position de défilement horizontal dans la grille. Ces deux colonnes ne peuvent pas être réorganisées.

## <a name="autofit-column-width"></a>Ajuster automatiquement la largeur de la colonne
Comme dans Excel, les utilisateurs peuvent forcer le redimensionnement automatique d’une colonne en fonction du contenu qui y est actuellement affiché. Appuyez simplement deux fois (ou double-cliquez) sur les poignées de dimensionnement dans la colonne. Vous pouvez également placer le focus dans l’en-tête de colonne, puis sélectionner la clé **UNE** (pour l’ajustement automatique).

## <a name="frequently-asked-questions"></a>Forum aux questions
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Comment activer le nouveau contrôle de grille dans mon environnement ? 

La fonctionnalité **Nouveau contrôle de grille** est disponible directement dans la gestion des fonctionnalités de tout environnement. Après avoir activé la fonctionnalité dans la gestion des fonctionnalités, toutes les sessions utilisateur suivantes utiliseront le nouveau contrôle de grille. 

Cette fonctionnalité a commencé à être activée par défaut dans la version 10.0.21. Il devrait devenir obligatoire en octobre 2022.

## <a name="developer-topics"></a>Rubriques de développeur

### <a name="developer-opting-out-individual-pages-from-using-the-new-grid"></a>[Développeur] Empêcher des pages individuelles d’utiliser la nouvelle grille 
Si votre organisation découvre une page qui n’arrive pas à utiliser la nouvelle grille, une API est disponible pour autoriser un formulaire individuel à utiliser le contrôle de grille hérité tout en autorisant le reste du système à utiliser le nouveau contrôle de grille. Pour désactiver une page individuelle dans la nouvelle grille, ajoutez le message d’appel suivant `super()` dans la méthode `run()` du formulaire.

```this.forceLegacyGrid();```

Cette API sera éventuellement obsolète pour permettre la suppression du contrôle de grille hérité. Cependant, il restera disponible pendant au moins 12 mois après l’annonce de sa dépréciation. Si des problèmes nécessitent l’utilisation de cette API, signalez-les à Microsoft.

#### <a name="forcing-a-page-to-use-the-new-grid-after-previously-opting-out-the-grid"></a>Forcer une page à utiliser la nouvelle grille après avoir précédemment refusé la grille
Si vous avez refusé l’utilisation de la nouvelle grille pour une page individuelle, vous souhaiterez peut-être réactiver ultérieurement la nouvelle grille une fois les problèmes sous-jacents résolus. Pour ce faire, il vous suffit de supprimer l’appel à `forceLegacyGrid()`. La modification ne prendra effet que quand l’un des événements suivants se produira :

- **Redéploiement de l’environnement** : quand un environnement est mis à jour et redéployé, la table qui stocke les pages pour lesquelles a été refusée la nouvelle grille (FormControlReactGridState) est automatiquement effacée.
- **Effacement manuel de la table** : pour les scénarios de développement, vous devrez utiliser SQL pour effacer la table FormControlReactGridState, puis redémarrer l’AOS. Cette combinaison d’actions réinitialisera la mise en cache des pages pour lesquelles la nouvelle grille a été refusée.

### <a name="developer-opting-individual-grids-out-of-the-typing-ahead-of-the-system-capability"></a>[Développeur] Désactiver les grilles individuelles de la saisie avant la capacité du système
Certains scénarios se sont présentés qui ne se prêtent pas à une bonne collaboration avec la capacité *Saisie avant le système* de la grille. (Par exemple, un code qui est déclenché quand une ligne est validée provoque le déclenchement d’une recherche de source de données, et la recherche peut alors corrompre des modifications non validées sur des lignes existantes.) Si votre organisation fait face à un tel scénario, une API est disponible afin que le développeur désactive une grille individuelle de la validation de ligne asynchrone et rétablisse le comportement hérité.

Quand la validation de ligne asynchrone est désactivée dans une grille, les utilisateurs ne peuvent pas créer de ligne ou passer à une autre ligne existante dans la grille tant qu’il existe des problèmes de validation sur la ligne actuelle. Comme effet secondaire de cette action, les tableaux ne peuvent pas être collés depuis Excel dans les grilles de finances et d’opérations.

Pour désactiver une grille individuelle de la validation de ligne asynchrone, ajoutez l’appel suivant après `super()` dans la méthode `run()` du formulaire.

```<gridControl>.allowPreemptiveClient(false);```

> [!NOTE]
> - Cet appel ne doit être invoqué que dans des cas exceptionnels et ne doit pas être la norme pour toutes les grilles.
> - Nous vous déconseillons de basculer cette API au moment de l’exécution après le chargement du formulaire.

### <a name="developer-size-to-available-width-columns"></a>[Développeur] Ajuster à disponible la largeur des colonnes
Si un développeur définit la propriété **WidthMode** sur **Ajuster à disponible** pour les colonnes à l’intérieur de la nouvelle grille, ces colonnes ont initialement la même largeur qu’elles auraient si la propriété était définie sur **Ajuster à disponible**. Cependant, elles s’étirent pour utiliser toute largeur supplémentaire disponible à l’intérieur de la grille. Si la propriété est définie sur **Ajuster à disponible** pour plusieurs colonnes, toutes ces colonnes partagent la largeur supplémentaire disponible à l’intérieur de la grille. Cependant, si un utilisateur redimensionne manuellement l’une de ces colonnes, la colonne devient statique. Elle restera à cette largeur et ne s’étirera plus pour prendre la largeur de grille supplémentaire disponible.

### <a name="developer-specifying-the-column-that-receives-the-initial-focus-when-new-rows-are-created-by-using-the-down-arrow-key"></a>[Développeur] Consultez la colonne qui reçoit le focus initial lorsque de nouvelles lignes sont créées à l’aide de la touche fléchée vers le bas
Comme cela a été discuté dans la section [Différences lors de la saisie de données en amont du système](#differences-when-entering-data-ahead-of-the-system) , si la fonctionnalité « Saisir en amont du système » est activée et qu’un utilisateur crée une nouvelle ligne à l’aide de la touche **Flèche vers le bas**, le comportement par défaut consiste à mettre l’accent sur la première colonne de la nouvelle ligne. Cette expérience peut différer de l’expérience de la grille héritée ou lorsqu’un **Nouveau** bouton est sélectionné.

Les utilisateurs et les organisations peuvent créer des vues enregistrées optimisées pour la saisie de données. (Par exemple, vous pouvez réorganiser les colonnes afin que la première colonne soit celle dans laquelle vous souhaitez commencer à saisir des données.) De plus, à partir de la version 10.0.29, les organisations peuvent ajuster ce comportement en utilisant le **selectedControlOnCreate()** méthode. Cette méthode permet à un développeur de spécifier la colonne qui doit recevoir le focus initial lorsqu’une nouvelle ligne est créée à l’aide de la touche **Fléchée vers le bas** . En entrée, cette API prend l’ID de contrôle qui correspond à la colonne qui doit recevoir le focus initial.

### <a name="developer-handling-grids-with-non-react-extensible-controls"></a>[Développeur] Gestion des grilles avec des contrôles extensibles non React
Lors du chargement d’une grille, si le système rencontre un contrôle extensible qui n’est pas basé sur React, le système forcera le rendu de la grille héritée à la place. Quand un utilisateur rencontre pour la première fois cette situation, un message concernant l’actualisation de la page s’affiche. Ensuite, cette page chargera automatiquement l’ancienne grille sans aucune autre notification aux utilisateurs jusqu’à la prochaine mise à jour du système. 

Pour surmonter cette situation de manière permanente, les auteurs de contrôles extensibles peuvent créer une version React du contrôle à utiliser dans la grille.  Une fois développée, la classe X++ pour le contrôle peut être décorée avec l’attribut **FormReactControlAttribute** pour spécifier l’emplacement du bundle React à charger pour ce contrôle. Consultez la catégorie `SegmentedEntryControl` à titre d’exemple.  

## <a name="known-issues"></a>Problèmes connus
Cette section maintient une liste des problèmes connus pour le nouveau contrôle de grille.

### <a name="open-issues"></a>Questions ouvertes
- Après avoir activé la fonctionnalité **Nouveau contrôle de grille**, certaines pages vont continuer à utiliser le contrôle de grille existant. Cela se produit dans les scénarios suivants :
 
    - [Résolu] Problème 762533 : erreur client inattendue lors de la sélection d’une ligne dans une liste de cartes.
    - [Résolu] Il existe une liste de cartes sur la page qui est affichée dans plusieurs colonnes.
        - Ce type de liste de cartes est pris en charge par le **Nouveau contrôle de grille** à partir de la version 10.0.30. Toute utilisation de forceLegacyGrid() à cette fin peut être supprimée. 
    - [Résolu] Il existe une liste de cartes groupée sur la page.
        - Les listes de cartes regroupées sont prises en charge par le **Nouveau contrôle de grille** à partir de la version 10.0.30. Toute utilisation de forceLegacyGrid() à cette fin peut être supprimée. 
    - [Résolu] Une colonne de grille avec un contrôle extensible non React.
        - Les contrôles extensibles peuvent fournir une version React de leur contrôle qui sera chargée lorsqu’ils sont placés dans la grille et ajuster leur définition de contrôle pour charger ce contrôle lorsqu’il est utilisé dans la grille. Voir la section développeur correspondante pour plus de détails. 

    Quand un utilisateur rencontre pour la première fois l’un de ces scénarios, un message concernant l’actualisation de la page s’affiche. Une fois ce message affiché, la page va continuer à utiliser la grille existante pour tous les utilisateurs jusqu’à la prochaine mise à jour de la version du produit. Une meilleure gestion de ces scénarios, afin de pouvoir utiliser la nouvelle grille, est envisagée pour une future mise à jour.

- [KB 4582758] Les enregistrements sont flous quand vous changez le zoom de 100 à tout autre pourcentage

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

