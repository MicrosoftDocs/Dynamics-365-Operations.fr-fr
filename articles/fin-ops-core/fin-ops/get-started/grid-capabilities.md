---
title: Capacités de grille
description: Cette rubrique décrit plusieurs fonctionnalités puissantes du contrôle de grille. Vous devez activer la nouvelle fonction de grille pour avoir accès à ces capacités.
author: jasongre
ms.date: 03/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 81577f54bd7fdc7d683c760dd4410f27da8ee1f0
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462790"
---
# <a name="grid-capabilities"></a>Capacités de grille

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Le nouveau contrôle de grille fournit un certain nombre de fonctionnalités utiles et puissantes qui peuvent être utilisées pour améliorer la productivité des utilisateurs, créer des vues plus intéressantes de vos données et obtenir des informations significatives sur vos données. Cet article couvrira les capacités suivantes : 

- Calcul des totaux
- Saisie avant le système
- Évaluation des expressions mathématiques 
- Regroupement des données tabulaires (activé séparément à l’aide de la fonctionnalité **Regroupement en grilles**)
- Figeage des colonnes (activé séparément en utilisant la fonctionnalité **Figeage des colonnes dans les grilles**)
- Ajuster automatiquement la largeur de la colonne
- Colonnes extensibles

## <a name="calculating-totals"></a>Calcul des totaux
Dans les applications Finances et Opérations, les utilisateurs ont la possibilité de voir les totaux au bas des colonnes numériques dans les grilles. Une section de pied de page au bas de la grille affiche ces totaux. 

### <a name="showing-the-grid-footer"></a>Affichage du pied de page de la grille
Une zone de pied de page se trouve au bas de chaque grille tabulaire dans les applications Finances et Opérations. Le pied de page peut afficher des informations utiles relatives aux données qui s’affichent dans la grille. Voici quelques exemples de ces informations :

- Le nombre de lignes sélectionnées dans le tableau (lorsque plusieurs enregistrements sont sélectionnés)
- Les totaux généraux au bas des colonnes numériques configurées
- Le nombre de lignes dans le dataset 

Ce pied de page est masqué par défaut, mais peut être facilement activé. Pour afficher le pied de page d’une grille, sélectionnez le bouton **Options de grille** dans l’en-tête de la grille, puis sélectionnez l’option **Afficher le pied de page**. Une fois que vous avez activé le pied de page pour une grille particulière, ce paramètre sera mémorisé jusqu’à ce que l’utilisateur choisisse de masquer le pied de page. Pour masquer le pied de page, sélectionnez **Masquer le pied de page** dans le menu **Options de grille**.

### <a name="specifying-columns-with-totals"></a>Spécification de colonnes avec des totaux
Actuellement, aucune colonne n’affiche les totaux par défaut. Cela est considéré comme une activité de configuration à part, similaire à l’ajustement de la largeur des colonnes dans les grilles. Une fois que vous avez spécifié que vous souhaitez voir les totaux d’une colonne, ce paramètre sera mémorisé lors de votre prochaine visite sur la page.

Il existe deux façons de configurer une colonne pour afficher un total : 

- Faites un clic droit dans la colonne pour laquelle vous souhaitez voir un total, puis sélectionnez **Total de cette colonne**. Cette action provoque trois événements :

    1. Le pied de page devient visible. 
    2. Votre préférence d’affichage du total pour cette colonne est enregistrée. 
    3. Un calcul des totaux est lancé pour cette colonne et toutes les autres colonnes que vous avez précédemment configurées pour afficher les totaux. Le temps nécessaire pour afficher un total dépend de la taille de l’ensemble de données que vous totalisez.

- Une fois le pied de page visible, sélectionnez **Afficher le total** dans la zone de pied de page en bas de la colonne pour laquelle vous souhaitez voir un total. S’il n’y a pas de colonnes configurées, le bouton **Afficher le total** sera disponible pour toutes les colonnes numériques. 

    Une fois qu’au moins une colonne est configurée pour les totaux, les boutons **Afficher le total** ne seront disponibles qu’en survol ou en focus. L’action de sélection de l’option **Afficher le total** enregistre simplement votre préférence d’affichage du total dans cette colonne, afin que la préférence soit appliquée lors des visites futures sur cette page. Dans le pied de page, cet état est indiqué par un tiret qui s’affiche dans la colonne. (Sinon, si l’ensemble de données est suffisamment petit, un total s’affiche immédiatement.)

Si vous faites une erreur et que vous ne voulez plus voir un total dans une colonne particulière, faites un clic droit sur la colonne et sélectionnez **Masquer le total** ou sélectionnez le bouton **Masquer le total** dans le pied de page de cette colonne. Cette préférence sera également enregistrée pour les futures visites de la page. 

### <a name="calculating-totals"></a>Calcul des totaux
Lorsque vous accédez à une page avec le pied de page visible et des colonnes déjà configurées pour les totaux, les totaux peuvent ou non être affichés dans le pied de page. Le comportement dépend de la taille de l’ensemble de données sur la page. Si l’ensemble de données est suffisamment petit, les totaux seront affichés automatiquement, ainsi que le nombre de lignes dans l’ensemble de données. S’il y a des tirets dans le pied de page sous les colonnes que vous avez configurées pour les totaux, le jeu de données est trop volumineux pour que le système affiche immédiatement les totaux et une action explicite est nécessaire pour calculer les totaux. Pour ce faire, cliquez sur le bouton **Calculer** dans le pied de page, ou faites un clic droit sur une colonne pour laquelle vous souhaitez afficher un total et sélectionnez **Total de cette colonne**.

Si le calcul prend trop de temps, vous pouvez annuler l’opération en sélectionnant le bouton **Annuler**. Parfois, cependant, l’ensemble de données sera trop volumineux pour calculer les totaux (une limite imposée par votre organisation), et vous serez invité à filtrer davantage vos données. 

> [!NOTE]
> Les administrations système peuvent modifier la limite du nombre d’enregistrements disponibles pour le calcul des totaux en ajustant le paramètre **Nombre maximal d’enregistrements locaux pour chaque grille** sur la page **Options de performances des clients**. La valeur par défaut est 25 000 enregistrements. Les administrateurs doivent être prudents lors du réglage de cette valeur, car une valeur trop élevée peut épuiser la mémoire disponible sur la machine de l’utilisateur. La recommandation est de ne pas dépasser 50 000 enregistrements.   

Les totaux seront mis à jour automatiquement lorsque vous mettez à jour, supprimez ou créez des lignes dans l’ensemble de données.

## <a name="typing-ahead-of-the-system"></a>Saisie avant le système
Dans de nombreux scénarios professionnels, la capacité de saisir rapidement des données dans le système est très importante. Avant l’introduction du nouveau contrôle de grille, les utilisateurs ne pouvaient modifier les données que dans la ligne actuelle. Avant de pouvoir créer une nouvelle ligne ou basculer vers une autre ligne, ils étaient obligés d’attendre que le système réussisse à valider les modifications. Afin de réduire le temps que les utilisateurs attendent pour que ces validations soient terminées et d’améliorer la productivité des utilisateurs, la nouvelle grille ajuste ces validations afin qu’elles soient asynchrones. Par conséquent, l’utilisateur peut passer à d’autres lignes pour apporter des modifications pendant que les validations de lignes précédentes sont en attente. 

Pour prendre en charge ce nouveau comportement, une nouvelle colonne pour le statut de la ligne a été ajoutée à droite de la colonne de sélection de ligne lorsque la grille est en mode édition. Cette colonne indique l’un des statuts suivants :

- **Vide** – L’image sans statut indique que la ligne a été correctement enregistrée par le système.
- **Traitement en attente** – Ce statut indique que les modifications de la ligne n’ont pas encore été enregistrées par le serveur mais se trouvent dans une file d’attente de modifications qui doivent être traitées. Avant de prendre des mesures en dehors de la grille, vous devez attendre que toutes les modifications en attente soient traitées. En outre, le texte de ces lignes est en italique pour indiquer le statut non enregistré des lignes. 
- **Etat non valide** – Ce statut indique qu’un avertissement ou un message a été déclenché pendant le traitement de la ligne et qu’il a pu empêcher le système d’enregistrer les modifications dans cette ligne. Dans l’ancienne grille, si l’enregistrement avait échoué, vous étiez obligé de retourner dans la ligne pour résoudre le problème immédiatement. Cependant, dans la nouvelle grille, vous êtes averti qu’un problème de validation a été rencontré, mais vous pouvez décider quand vous souhaitez résoudre les problèmes de la ligne. Lorsque vous êtes prêt à résoudre un problème, vous pouvez placer manuellement le focus sur la ligne. Vous pouvez également sélectionner l’action **Résoudre ce problème**. Cette action ramène immédiatement le focus sur la ligne qui pose problème et vous permet d’effectuer des modifications à l’intérieur ou à l’extérieur de la grille. Notez que le traitement des lignes en attente suivantes est arrêté jusqu’à ce que cet avertissement de validation soit résolu. 
- **En pause** – Ce statut indique que le traitement par le serveur est interrompu, car la validation de la ligne a déclenché une boîte de dialogue contextuelle qui nécessite une entrée utilisateur. Étant donné que l’utilisateur peut entrer des données dans une autre ligne, la boîte de dialogue contextuelle n’est pas immédiatement présentée à cet utilisateur. Au lieu de cela, elle sera affichée lorsque l’utilisateur choisira de reprendre le traitement. Ce statut est accompagné d’une notification qui informe l’utilisateur de la situation. La notification comprend une action **Reprendre le traitement** qui déclenchera la boîte de dialogue contextuelle.

Lorsque les utilisateurs saisissent des données avant l’emplacement où le serveur effectue son traitement, ils peuvent s’attendre à quelques dégradations dans l’expérience de saisie de données, comme un manque de recherches, de validation au niveau du contrôle et de saisie de valeurs par défaut. Les utilisateurs qui ont besoin d’une liste déroulante pour trouver une valeur sont encouragés à attendre que le serveur rattrape la ligne actuelle. La validation au niveau du contrôle et la saisie des valeurs par défaut se produisent également lorsque le serveur traite cette ligne.

### <a name="pasting-from-excel"></a>Collage depuis Excel
Les utilisateurs ont toujours pu exporter des données à partir de grilles dans les applications Finances et Opérations vers Microsoft Excel à l’aide du mécanisme **Exporter vers Excel**. Cependant, la possibilité d’entrer des données avant le système permet à la nouvelle grille de prendre en charge la copie de tableaux à partir d’Excel et de les coller directement dans des grilles dans les applications Finances et Opérations. La cellule de grille à partir de laquelle l’opération de collage est lancée détermine où le tableau copié commence à être collé. Le contenu de la grille est écrasé par le contenu de la table copiée, sauf dans deux cas :

- Si le nombre de colonnes dans la table copiée dépasse le nombre de colonnes qui restent dans la grille, à partir de l’emplacement de collage, l’utilisateur est informé que les colonnes supplémentaires ont été ignorées. 
- Si le nombre de lignes dans le tableau copié dépasse le nombre de lignes dans la grille, à partir de l’emplacement de collage, les cellules existantes sont remplacées par le contenu collé et toutes les lignes supplémentaires du tableau copié sont insérées en tant que nouvelles lignes en bas de la grille. 

## <a name="evaluating-math-expressions"></a>Évaluation des expressions mathématiques
Pour booster la productivité, les utilisateurs peuvent entrer des formules mathématiques dans des cellules numériques d’une grille. Ils n’ont pas besoin d’effectuer le calcul dans une application en dehors du système. Par exemple, si vous entrez **=15\*4**, puis appuyez sur la touche **Tab** pour quitter le champ, le système évaluera l’expression et enregistrera la valeur de **60** pour le champ.

Pour que le système reconnaisse une valeur comme une expression, démarrez la valeur avec un signe égal (**=**). Pour en savoir plus sur les opérateurs et la syntaxe pris en charge, consultez [Symboles mathématiques pris en charge](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

## <a name="grouping-tabular-data"></a>Regroupement des données tabulaires
Les utilisateurs professionnels doivent souvent effectuer une analyse ad hoc des données. Bien que cela puisse être fait en exportant des données vers Microsoft Excel et en utilisant des tableaux croisés dynamiques, la fonctionnalité **Regroupement en grilles**, dépendante de la nouvelle fonctionnalité de contrôle de grille, permet aux utilisateurs d’organiser leurs données tabulaires de manière intéressante dans les applications Finances et Opérations. Du fait que cette fonctionnalité étend la fonctionnalité **Totaux**, le **Regroupement** vous permet également d’obtenir des informations significatives sur les données en fournissant des sous-totaux au niveau du groupe.

Pour utiliser cette fonction, cliquez avec le bouton droit sur la colonne selon laquelle vous souhaitez regrouper et sélectionnez **Regrouper par cette colonne**. Cette action triera les données selon la colonne sélectionnée, ajoutera une nouvelle colonne **Grouper par** au début de la grille et insérera des « lignes d’en-tête » au début de chaque groupe. Ces lignes d’en-tête fournissent les informations suivantes sur chaque groupe :

- Valeur des données pour le groupe 
- Nom de colonne (ces informations sont particulièrement utiles lorsque vous avez plusieurs niveaux de regroupement)
- Nombre de lignes de données dans ce groupe
- Sous-totaux pour toute colonne configurée pour afficher les totaux

Lorsque [Vues enregistrées ](saved-views.md) est activé, ce regroupement peut être enregistré comme personnalisation dans le cadre d’une vue pour un accès rapide la prochaine fois que vous visiterez la page.

### <a name="multiple-levels-of-grouping"></a>Plusieurs niveaux de regroupement
Après avoir regroupé les données dans une seule colonne, vous pouvez regrouper les données dans une colonne différente en sélectionnant **Regrouper selon cette colonne** sur la colonne souhaitée. Ce processus peut être répété jusqu’à ce que vous disposiez de 5 niveaux de regroupement imbriqués, ce qui correspond à la profondeur maximale prise en charge. À ce stade, vous ne pourrez plus regrouper par colonnes supplémentaires.

À tout moment, vous pouvez supprimer le regroupement sur n’importe quelle colonne en cliquant avec le bouton droit sur cette colonne et en sélectionnant **Dissocier**. Vous pouvez également supprimer le regroupement de toutes les colonnes en sélectionnant **Options de grille** puis **Dissocier tout**.

### <a name="sorting-grouped-data"></a>Tri des données groupées
Après avoir regroupé les données sur une ou plusieurs colonnes, vous pouvez modifier le sens du tri pour n’importe quelle colonne de regroupement via l’en-tête de colonne correspondant. 

Le comportement lorsque vous triez sur des colonnes non groupées dépend de la version de votre produit :

- Dans la version 10.0.24 et les versions antérieures, si vous triez sur une colonne non groupée, le regroupement est supprimé de toutes les colonnes et les données sont triées sur la colonne sélectionnée. 
- Dans la version 10.0.25 et les versions ultérieures, si vous triez sur une colonne non groupée, le regroupement reste intact et les données sont triées dans chaque groupe, selon la colonne sélectionnée.

### <a name="expanding-and-collapsing-groups"></a>Développer et réduire les groupes
Le regroupement initial de données aura tous les groupes développés. Vous pouvez créer des vues résumées des données en réduisant des groupes individuels, ou vous pouvez utiliser le développement et la réduction de groupe pour faciliter la navigation dans les données. Pour développer ou réduire un groupe, sélectionnez le bouton de chevron (>) dans la ligne d’en-tête de groupe correspondante. Notez que l’état de développement/réduction des groupes individuels **n’est pas** enregistré dans la personnalisation.

### <a name="selecting-and-unselecting-rows-at-the-group-level"></a>Sélection et désélection de lignes au niveau du groupe
De la même manière que vous pouvez sélectionner (ou désélectionner) toutes les lignes de la grille en cochant la case en haut de la première colonne de la grille, vous pouvez également sélectionner (ou désélectionner) rapidement toutes les lignes d’un groupe en cochant la case dans la ligne d’en-tête de groupe correspondante. La case à cocher dans la ligne d’en-tête de groupe reflète toujours l’état de sélection actuel des lignes de ce groupe, que toutes les lignes soient sélectionnées, qu’aucune ligne ne soit sélectionnée ou que seules certaines lignes soient sélectionnées.

### <a name="hiding-column-names"></a>Masquer les noms de colonnes
Lors du regroupement de données, le comportement par défaut consiste à afficher le nom de la colonne dans la ligne d’en-tête de groupe. Vous pouvez choisir de supprimer le nom de colonne dans les lignes d’en-tête de groupe en sélectionnant **Options de grille** > **Masquer le nom de la colonne du groupe**.

### <a name="grouping-on-date-and-time-columns"></a>Regroupement sur des colonnes de date et d’heure
À partir de la version 10.0.24, pour les champs Date ou DateHeure, l’option a été ajoutée pour regrouper par Année, Mois ou Jour. Le groupe « valeur » dans la ligne d’en-tête correspondante correspondra au format de ce champ. De plus, pour les champs DateHeure et Heure, vous pouvez regrouper par Heure, Minute ou Seconde. 

## <a name="freezing-columns"></a>Figer les colonnes
Certaines colonnes d’une grille peuvent être suffisamment importantes en termes de contexte que vous ne souhaitez pas qu’elles défilent hors de la vue. Au lieu de cela, vous voulez que les valeurs de ces colonnes soient toujours visibles. La fonctionnalité **Figeage des colonnes dans la grille** offre cette flexibilité aux utilisateurs. 

Pour figer une colonne, cliquez avec le bouton droit sur l’en-tête de la colonne, puis sélectionnez **Figer la colonne**. La première fois que vous effectuez cette étape, la colonne sélectionnée devient la première colonne et ne défilera plus hors du champ visuel. Toute colonne suivante que vous figez sera ajoutée à droite de la dernière colonne figée. Vous pouvez utiliser la fonctionnalité Déplacer standard pour réorganiser les colonnes figées selon vos besoins. Cependant, les colonnes figées ne peuvent pas être déplacées de sorte qu’elles apparaissent dans l’ensemble des colonnes non figées. De même, les colonnes non figées ne peuvent pas être déplacées de sorte qu’elles apparaissent dans l’ensemble des colonnes figées.

Pour libérer une colonne, cliquez avec le bouton droit sur l’en-tête de la colonne figée, puis sélectionnez **Libérer la colonne**. 

Notez que les colonnes de sélection de ligne et d’état de ligne dans la nouvelle grille sont toujours figées comme les deux premières colonnes. Par conséquent, lorsque ces colonnes sont incluses dans une grille, elles seront toujours visibles pour les utilisateurs, quelle que soit la position de défilement horizontal dans la grille. Ces deux colonnes ne peuvent pas être réorganisées.

## <a name="autofit-column-width"></a>Ajuster automatiquement la largeur de la colonne
Comme dans Excel, les utilisateurs peuvent forcer automatiquement le redimensionnement d’une colonne en fonction du contenu actuellement affiché dans cette colonne. Pour ce faire, double-cliquez sur les poignées de redimensionnement dans la colonne, ou mettez en évidence l’en-tête de colonne et appuyez sur **A** (pour l’ajustement automatique). Cette fonctionnalité est disponible à partir de la version 10.0.23.

## <a name="frequently-asked-questions"></a>Forum aux questions
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Comment activer le nouveau contrôle de grille dans mon environnement ? 

La fonctionnalité **Nouveau contrôle de grille** est disponible directement dans la gestion des fonctionnalités de tout environnement. Après avoir activé la fonctionnalité dans la gestion des fonctionnalités, toutes les sessions utilisateur suivantes utiliseront le nouveau contrôle de grille. 

Cette fonctionnalité est activée par défaut à partir de la version 10.0.21 et devrait devenir obligatoire en octobre 2022.  

## <a name="developer-opting-out-individual-pages-from-using-the-new-grid"></a>[Développeur] Empêcher des pages individuelles d’utiliser la nouvelle grille 
Si votre organisation découvre une page qui n’arrive pas à utiliser la nouvelle grille, une API est disponible pour autoriser un formulaire individuel à utiliser le contrôle de grille hérité tout en autorisant le reste du système à utiliser le nouveau contrôle de grille. Pour désactiver une page individuelle dans la nouvelle grille, ajoutez le message d’appel suivant `super()` dans la méthode `run()` du formulaire.

```this.forceLegacyGrid();```

Cette API sera disponible jusqu’à ce que le nouveau contrôle de grille devienne obligatoire. Ce changement est actuellement prévu pour octobre 2022. Si des problèmes nécessitent l’utilisation de cette API, signalez-les à Microsoft.

### <a name="forcing-a-page-to-use-the-new-grid-after-previously-opting-out-the-grid"></a>Forcer une page à utiliser la nouvelle grille après avoir précédemment refusé la grille
Si vous avez refusé l’utilisation de la nouvelle grille pour une page individuelle, vous souhaiterez peut-être réactiver ultérieurement la nouvelle grille une fois les problèmes sous-jacents résolus. Pour ce faire, il vous suffit de supprimer l’appel à `forceLegacyGrid()`. La modification ne prendra effet que lorsque l’un des événements suivants se produira :

- **Redéploiement de l’environnement** : lorsqu’un environnement est mis à jour et redéployé, la table qui stocke les pages pour lesquelles a été refusée la nouvelle grille (FormControlReactGridState) est automatiquement effacée.
- **Effacement manuel de la table** : pour les scénarios de développement, vous devrez utiliser SQL pour effacer la table FormControlReactGridState, puis redémarrer l’AOS. Cette combinaison d’actions réinitialisera la mise en cache des pages pour lesquelles la nouvelle grille a été refusée.

## <a name="developer-opting-individual-grids-out-of-the-typing-ahead-of-the-system-capability"></a>[Développeur] Désactiver les grilles individuelles de la saisie avant la capacité du système
Certains scénarios se sont présentés qui ne se prêtent pas à une bonne collaboration avec la capacité *Saisie avant le système* de la grille. (Par exemple, un code qui est déclenché lorsqu’une ligne est validée provoque le déclenchement d’une recherche de source de données, et la recherche peut alors corrompre des modifications non validées sur des lignes existantes.) Si votre organisation fait face à un tel scénario, une API est disponible afin que le développeur désactive une grille individuelle de la validation de ligne asynchrone et rétablisse le comportement hérité.

Lorsque la validation de ligne asynchrone est désactivée dans une grille, les utilisateurs ne peuvent pas créer de ligne ou passer à une autre ligne existante dans la grille tant qu’il existe des problèmes de validation sur la ligne actuelle. Comme effet secondaire de cette action, les tableaux ne peuvent pas être collés depuis Excel dans les grilles Finances et Opérations.

Pour désactiver une grille individuelle de la validation de ligne asynchrone, ajoutez l’appel suivant après `super()` dans la méthode `run()` du formulaire.

```<gridControl>.allowPreemptiveClient(false);```

> [!NOTE]
> - Cet appel ne doit être invoqué que dans des cas exceptionnels et ne doit pas être la norme pour toutes les grilles.
> - Nous vous déconseillons de basculer cette API au moment de l’exécution après le chargement du formulaire.

## <a name="developer-size-to-available-width-columns"></a>[Développeur] Ajuster à disponible la largeur des colonnes
Si un développeur définit la propriété **WidthMode** sur **Ajuster à disponible** pour les colonnes à l’intérieur de la nouvelle grille, ces colonnes ont initialement la même largeur qu’elles auraient si la propriété était définie sur **Ajuster à disponible**. Cependant, elles s’étirent pour utiliser toute largeur supplémentaire disponible à l’intérieur de la grille. Si la propriété est définie sur **Ajuster à disponible** pour plusieurs colonnes, toutes ces colonnes partagent la largeur supplémentaire disponible à l’intérieur de la grille. Cependant, si un utilisateur redimensionne manuellement l’une de ces colonnes, la colonne devient statique. Elle restera à cette largeur et ne s’étirera plus pour prendre la largeur de grille supplémentaire disponible.

## <a name="known-issues"></a>Problèmes connus
Cette section maintient une liste des problèmes connus pour le nouveau contrôle de grille.

### <a name="open-issues"></a>Questions ouvertes
- Après avoir activé la fonctionnalité **Nouveau contrôle de grille**, certaines pages vont continuer à utiliser le contrôle de grille existant. Cela se produit dans les scénarios suivants :
 
    - Il existe une liste de cartes sur la page qui est affichée dans plusieurs colonnes.
    - Il existe une liste de cartes groupée sur la page.
    - Une colonne de grille avec un contrôle extensible non réactif.

    Lorsqu’un utilisateur rencontre pour la première fois l’un de ces scénarios, un message concernant l’actualisation de la page s’affiche. Une fois ce message affiché, la page va continuer à utiliser la grille existante pour tous les utilisateurs jusqu’à la prochaine mise à jour de la version du produit. Une meilleure gestion de ces scénarios, afin de pouvoir utiliser la nouvelle grille, est envisagée pour une future mise à jour.

- [KB 4582758] Les enregistrements sont flous lorsque vous changez le zoom de 100 à tout autre pourcentage
- [KB 4592012] Erreur client inattendue dans IE11 lors du collage de plusieurs lignes à partir d’Excel

    Microsoft ne cherche pas à résoudre ce problème


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
