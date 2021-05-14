---
title: Capacités de grille
description: Cette rubrique décrit plusieurs fonctionnalités puissantes du contrôle de grille. Vous devez activer la nouvelle fonction de grille pour avoir accès à ces capacités.
author: jasongre
ms.date: 01/22/2021
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
ms.openlocfilehash: b7a1809a3012af86ad9ba39da8721c63b3c4b885
ms.sourcegitcommit: 2f766e5bb8574d250f19180ff2e101e895097713
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5923596"
---
# <a name="grid-capabilities"></a>Capacités de grille

[!include [banner](../includes/banner.md)]


Le nouveau contrôle de grille fournit un certain nombre de fonctionnalités utiles et puissantes qui peuvent être utilisées pour améliorer la productivité des utilisateurs, créer des vues plus intéressantes de vos données et obtenir des informations significatives sur vos données. Cet article couvrira les capacités suivantes : 

-  Calcul des totaux
-  Saisie avant le système
-  Évaluation des expressions mathématiques 
-  Regroupement des données tabulaires (activé séparément à l’aide de la fonctionnalité **(Version préliminaire) Regroupement en grilles**)
-  Figer les colonnes

## <a name="calculating-totals"></a>Calcul des totaux
Dans les applications Finance and Operations, les utilisateurs ont la possibilité de voir les totaux au bas des colonnes numériques dans les grilles. Une section de pied de page au bas de la grille affiche ces totaux. 

### <a name="showing-the-grid-footer"></a>Affichage du pied de page de la grille
Une zone de pied de page se trouve au bas de chaque grille tabulaire dans les applications Finance and Operations. Le pied de page peut afficher des informations utiles relatives aux données qui s’affichent dans la grille. Voici quelques exemples de ces informations :

- Le nombre de lignes sélectionnées dans le tableau (lorsque plusieurs enregistrements sont sélectionnés)
- Les totaux généraux au bas des colonnes numériques configurées
- Le nombre de lignes dans le dataset 

Ce pied de page est masqué par défaut, mais peut être facilement activé. Pour afficher le pied de page d’une grille, cliquez avec le bouton droit sur un en-tête de colonne dans la grille et sélectionnez l’option **Afficher le pied de page**. Une fois que vous avez activé le pied de page pour une grille particulière, ce paramètre sera mémorisé jusqu’à ce que l’utilisateur choisisse de masquer le pied de page. Pour masquer le pied de page, cliquez avec le bouton droit sur un en-tête de colonne et sélectionnez **Masquer le pied de page**.  (L’emplacement de l’action **Afficher le pied de page/Masquer le pied de page** sera déplacé dans une future mise à jour. 

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

Les totaux seront mis à jour automatiquement lorsque vous mettez à jour, supprimez ou créez des lignes dans l’ensemble de données.  

## <a name="typing-ahead-of-the-system"></a>Saisie avant le système
Dans de nombreux scénarios professionnels, la capacité de saisir rapidement des données dans le système est très importante. Avant l’introduction du nouveau contrôle de grille, les utilisateurs ne pouvaient modifier les données que dans la ligne actuelle. Avant de pouvoir créer une nouvelle ligne ou basculer vers une autre ligne, ils étaient obligés d’attendre que le système réussisse à valider les modifications. Afin de réduire le temps que les utilisateurs attendent pour que ces validations soient terminées et d’améliorer la productivité des utilisateurs, la nouvelle grille ajuste ces validations afin qu’elles soient asynchrones. Par conséquent, l’utilisateur peut passer à d’autres lignes pour apporter des modifications pendant que les validations de lignes précédentes sont en attente. 

Pour prendre en charge ce nouveau comportement, une nouvelle colonne pour le statut de la ligne a été ajoutée à droite de la colonne de sélection de ligne lorsque la grille est en mode édition. Cette colonne indique l’un des statuts suivants :

- **Vide** – L’image sans statut indique que la ligne a été correctement enregistrée par le système.
- **Traitement en attente** – Ce statut indique que les modifications de la ligne n’ont pas encore été enregistrées par le serveur mais se trouvent dans une file d’attente de modifications qui doivent être traitées. Avant de prendre des mesures en dehors de la grille, vous devez attendre que toutes les modifications en attente soient traitées. En outre, le texte de ces lignes est en italique pour indiquer le statut non enregistré des lignes. 
- **Etat non valide** – Ce statut indique qu’un avertissement ou un message a été déclenché pendant le traitement de la ligne et qu’il a pu empêcher le système d’enregistrer les modifications dans cette ligne. Dans l’ancienne grille, si l’enregistrement avait échoué,vous étiez obligé de retourner dans la ligne pour résoudre le problème immédiatement. Cependant, dans la nouvelle grille, vous êtes averti qu’un problème de validation a été rencontré, mais vous pouvez décider quand vous souhaitez résoudre les problèmes de la ligne. Lorsque vous êtes prêt à résoudre un problème, vous pouvez placer manuellement le focus sur la ligne. Vous pouvez également sélectionner l’action **Résoudre ce problème**. Cette action ramène immédiatement le focus sur la ligne qui pose problème et vous permet d’effectuer des modifications à l’intérieur ou à l’extérieur de la grille. Notez que le traitement des lignes en attente suivantes est arrêté jusqu’à ce que cet avertissement de validation soit résolu. 
- **En pause** – Ce statut indique que le traitement par le serveur est interrompu, car la validation de la ligne a déclenché une boîte de dialogue contextuelle qui nécessite une entrée utilisateur. Étant donné que l’utilisateur peut entrer des données dans une autre ligne, la boîte de dialogue contextuelle n’est pas immédiatement présentée à cet utilisateur. Au lieu de cela, elle sera affichée lorsque l’utilisateur choisira de reprendre le traitement. Ce statut est accompagné d’une notification qui informe l’utilisateur de la situation. La notification comprend une action **Reprendre le traitement** qui déclenchera la boîte de dialogue contextuelle.  
    
Lorsque les utilisateurs saisissent des données avant l’emplacement où le serveur effectue son traitement, ils peuvent s’attendre à quelques dégradations dans l’expérience de saisie de données, comme un manque de recherches, de validation au niveau du contrôle et de saisie de valeurs par défaut. Les utilisateurs qui ont besoin d’une liste déroulante pour trouver une valeur sont encouragés à attendre que le serveur rattrape la ligne actuelle. La validation au niveau du contrôle et la saisie des valeurs par défaut se produisent également lorsque le serveur traite cette ligne.   

### <a name="pasting-from-excel"></a>Collage depuis Excel
Les utilisateurs ont toujours pu exporter des données à partir de grilles dans les applications Finance and Operations vers Excel à l’aide du mécanisme **Exporter vers Excel**. Cependant, la possibilité d’entrer des données avant le système permet à la nouvelle grille de prendre en charge la copie de tableaux à partir d’Excel et de les coller directement dans des grilles dans les applications Finance and Operations. La cellule de grille à partir de laquelle l’opération de collage est lancée détermine où le tableau copié commence à être collé. Le contenu de la grille est écrasé par le contenu de la table copiée, sauf dans deux cas :

- Si le nombre de colonnes dans la table copiée dépasse le nombre de colonnes qui restent dans la grille, à partir de l’emplacement de collage, l’utilisateur est informé que les colonnes supplémentaires ont été ignorées. 
- Si le nombre de lignes dans le tableau copié dépasse le nombre de lignes dans la grille, à partir de l’emplacement de collage, les cellules existantes sont remplacées par le contenu collé et toutes les lignes supplémentaires du tableau copié sont insérées en tant que nouvelles lignes en bas de la grille. 

## <a name="evaluating-math-expressions"></a>Évaluation des expressions mathématiques
Pour booster la productivité, les utilisateurs peuvent entrer des formules mathématiques dans des cellules numériques d’une grille. Ils n’ont pas besoin d’effectuer le calcul dans une application en dehors du système. Par exemple, si vous entrez **=15\*4**, puis appuyez sur la touche **Tab** pour quitter le champ, le système évaluera l’expression et enregistrera la valeur de **60** pour le champ.

Pour que le système reconnaisse une valeur comme une expression, démarrez la valeur avec un signe égal (**=**). Pour en savoir plus sur les opérateurs et la syntaxe pris en charge, consultez [Symboles mathématiques pris en charge](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

## <a name="grouping-tabular-data"></a>Regroupement des données tabulaires
Les utilisateurs professionnels doivent souvent effectuer une analyse ad hoc des données. Bien que cela puisse être fait en exportant des données vers Microsoft Excel et en utilisant des tableaux croisés dynamiques, la fonctionnalité **Regroupement en grilles**, disponible généralement dans la version 10.0.16/Platform update 40 et dépendante de la nouvelle fonctionnalité de contrôle de grille, permet aux utilisateurs d’organiser leurs données tabulaires de manière intéressante dans les applications Finance and Operations. Du fait que cette fonctionnalité étend la fonctionnalité **Totaux**, le **Regroupement** vous permet également d’obtenir des informations significatives sur les données en fournissant des sous-totaux au niveau du groupe.

Pour utiliser cette fonction, cliquez avec le bouton droit sur la colonne selon laquelle vous souhaitez regrouper et sélectionnez **Regrouper par cette colonne**. Cette action triera les données selon la colonne sélectionnée, ajoutera une nouvelle colonne **Grouper par** au début de la grille et insérera des « lignes d’en-tête » au début de chaque groupe. Ces lignes d’en-tête fournissent les informations suivantes sur chaque groupe : 
-  Valeur des données pour le groupe 
-  Nom de colonne (ces informations sont particulièrement utiles lorsque vous avez plusieurs niveaux de regroupement)  
-  Nombre de lignes de données dans ce groupe
-  Sous-totaux pour toute colonne configurée pour afficher les totaux

Lorsque [Vues enregistrées ](saved-views.md)est activé, ce regroupement peut être enregistré comme personnalisation dans le cadre d’une vue pour un accès rapide la prochaine fois que vous visiterez la page.  

### <a name="multiple-levels-of-grouping"></a>Plusieurs niveaux de regroupement
Après avoir regroupé les données dans une seule colonne, vous pouvez regrouper les données dans une colonne différente en sélectionnant **Regrouper selon cette colonne** sur la colonne souhaitée. Ce processus peut être répété jusqu’à ce que vous disposiez de 5 niveaux de regroupement imbriqués, ce qui correspond à la profondeur maximale prise en charge. À ce stade, vous ne pourrez plus regrouper par colonnes supplémentaires.  

À tout moment, vous pouvez supprimer le regroupement sur n’importe quelle colonne en cliquant avec le bouton droit sur cette colonne et en sélectionnant **Dissocier**. Vous pouvez également supprimer le regroupement de toutes les colonnes en sélectionnant **Options de grille** puis **Dissocier tout**.   

Notez qu’avant la version 10.0.16 / Platform update 40, un seul niveau de regroupement est pris en charge. Dans ces versions, si les données sont groupées et que vous sélectionnez **Regrouper par cette colonne** pour une colonne différente, le groupement d’origine est remplacé.  


### <a name="expanding-and-collapsing-groups"></a>Développer et réduire les groupes
Le regroupement initial de données aura tous les groupes développés. Vous pouvez créer des vues résumées des données en réduisant des groupes individuels, ou vous pouvez utiliser le développement et la réduction de groupe pour faciliter la navigation dans les données. Pour développer ou réduire un groupe, sélectionnez le bouton de chevron (>) dans la ligne d’en-tête de groupe correspondante. Notez que l’état de développement/réduction des groupes individuels **n’est pas** enregistré dans la personnalisation.

### <a name="selecting-and-unselecting-rows-at-the-group-level"></a>Sélection et désélection de lignes au niveau du groupe
De la même manière que vous pouvez sélectionner (ou désélectionner) toutes les lignes de la grille en cochant la case en haut de la première colonne de la grille, vous pouvez également sélectionner (ou désélectionner) rapidement toutes les lignes d’un groupe en cochant la case dans la ligne d’en-tête de groupe correspondante. La case à cocher dans la ligne d’en-tête de groupe reflète toujours l’état de sélection actuel des lignes de ce groupe, que toutes les lignes soient sélectionnées, qu’aucune ligne ne soit sélectionnée ou que seules certaines lignes soient sélectionnées.

### <a name="hiding-column-names"></a>Masquer les noms de colonnes
Lors du regroupement de données, le comportement par défaut consiste à afficher le nom de la colonne dans la ligne d’en-tête de groupe. À compter de la version 10.0.14/Platform update 38, vous pouvez choisir de supprimer le nom de colonne dans les lignes d’en-tête de groupe en sélectionnant **Options de grille** > **Masquer le nom de la colonne du groupe**.

## <a name="freezing-columns"></a>Figer les colonnes
Certaines colonnes d’une grille peuvent être suffisamment importantes en termes de contexte que vous ne souhaitez pas qu’elles défilent hors de la vue. Au lieu de cela, vous voulez que les valeurs de ces colonnes soient toujours visibles. Dans la version 10.0.17, la fonctionnalité **Figer les colonnes dans la grille** offre cette flexibilité aux utilisateurs. 

Pour figer une colonne, cliquez avec le bouton droit sur l’en-tête de la colonne, puis sélectionnez **Figer la colonne**. La première fois que vous effectuez cette étape, la colonne sélectionnée devient la première colonne et ne défilera plus hors du champ visuel. Toute colonne suivante que vous figez sera ajoutée à droite de la dernière colonne figée. Vous pouvez utiliser la fonctionnalité Déplacer standard pour réorganiser les colonnes figées selon vos besoins. Cependant, les colonnes figées ne peuvent pas être déplacées de sorte qu’elles apparaissent dans l’ensemble des colonnes non figées. De même, les colonnes non figées ne peuvent pas être déplacées de sorte qu’elles apparaissent dans l’ensemble des colonnes figées.

Pour libérer une colonne, cliquez avec le bouton droit sur l’en-tête de la colonne figée, puis sélectionnez **Libérer la colonne**. 

Notez que les colonnes de sélection de ligne et d’état de ligne dans la nouvelle grille sont toujours figées comme les deux premières colonnes. Par conséquent, lorsque ces colonnes sont incluses dans une grille, elles seront toujours visibles pour les utilisateurs, quelle que soit la position de défilement horizontal dans la grille. Ces deux colonnes ne peuvent pas être réorganisées.

## <a name="frequently-asked-questions"></a>Forum aux questions
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Comment activer le nouveau contrôle de grille dans mon environnement ? 

**10.0.9 / Platform update 33 et versions ultérieures**

La fonctionnalité **Nouveau contrôle de grille** est disponible directement dans la gestion des fonctionnalités de tout environnement. Comme les autres fonctionnalités d’aperçu public, l’activation de cette fonctionnalité en production est soumise à l’[accord supplémentaire Conditions d’utilisation](public-preview-terms.md).  

**10.0.8 / Platform update 32 et 10.0.7 / Platform update 31**

La fonctionnalité **Nouveau contrôle de grille** peut être activée dans les environnements de niveau 1 (développement/test) et de niveau 2 (bac à sable) afin de fournir des tests et des modifications de conception supplémentaires en suivant les étapes ci-dessous.

1.  **Activer la version d’évaluation** : Exécutez l’instruction SQL suivante : 

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLIReactGridEnableFeature', 1, 0, 5637144576);`

2. **Réinitialiser IIS** pour vider le cache de la version d’évaluation statique. 

3.  **Rechercher la fonctionnalité** : accédez à l’espace de travail **Gestion des fonctions**. Si **Nouveau contrôle de grille** n’apparaît pas dans la liste de toutes les fonctionnalités, sélectionnez **Vérifier les mises à jour**.   

4.  **Activer la fonctionnalité** : Recherchez la fonctionnalité **Nouveau contrôle de grille** dans la liste des fonctionnalités, puis sélectionnez **Activer maintenant** dans le volet des détails. Notez qu’une actualisation du navigateur est requise. 

Toutes les sessions utilisateur suivantes démarreront avec le nouveau contrôle de grille activé.

## <a name="developer-opting-out-individual-pages-from-using-the-new-grid"></a>[Développeur] Empêcher des pages individuelles d’utiliser la nouvelle grille 
Si votre organisation découvre une page qui n’arrive pas à utiliser la nouvelle grille, une API est disponible à partir de la version 10.0.13/Platform update 37 pour autoriser un formulaire individuel à utiliser le contrôle de grille hérité tout en autorisant le reste du système à utiliser le nouveau contrôle de grille. Pour désactiver une page individuelle dans la nouvelle grille, ajoutez le message d’appel suivant `super()` dans la méthode `run()` du formulaire.

 ```this.forceLegacyGrid();```

Cette API sera disponible jusqu’à la version d’octobre 2021, lorsque le nouveau contrôle de grille deviendra obligatoire. Si des problèmes nécessitent l’utilisation de cette API, signalez-les à Microsoft.

## <a name="developer-size-to-available-width-columns"></a>[Développeur] Ajuster à disponible la largeur des colonnes
Si un développeur définit la propriété **WidthMode** sur **Ajuster à disponible** pour les colonnes à l’intérieur de la nouvelle grille, ces colonnes ont initialement la même largeur qu’elles auraient si la propriété était définie sur **Ajuster à disponible**. Cependant, elles s’étirent pour utiliser toute largeur supplémentaire disponible à l’intérieur de la grille. Si la propriété est définie sur **Ajuster à disponible** pour plusieurs colonnes, toutes ces colonnes partagent la largeur supplémentaire disponible à l’intérieur de la grille. Cependant, si un utilisateur redimensionne manuellement l’une de ces colonnes, la colonne devient statique. Elle restera à cette largeur et ne s’étirera plus pour prendre la largeur de grille supplémentaire disponible.  

## <a name="known-issues"></a>Problèmes connus
Cette section maintient une liste des problèmes connus pour le nouveau contrôle de grille.  

### <a name="open-issues"></a>Questions ouvertes
-  Après avoir activé la fonctionnalité **Nouveau contrôle de grille**, certaines pages vont continuer à utiliser le contrôle de grille existant. Cela se produit dans les scénarios suivants :  
    -  Il existe une liste de cartes sur la page qui est affichée dans plusieurs colonnes.
    -  Il existe une liste de cartes groupée sur la page.
    -  Une colonne de grille avec un contrôle extensible non réactif.

    Lorsqu’un utilisateur rencontre pour la première fois l’un de ces scénarios, un message concernant l’actualisation de la page s’affiche. Une fois ce message affiché, la page va continuer à utiliser la grille existante pour tous les utilisateurs jusqu’à la prochaine mise à jour de la version du produit. Une meilleure gestion de ces scénarios, afin de pouvoir utiliser la nouvelle grille, est envisagée pour une future mise à jour.    
    
-  [KB 4582758] Les enregistrements sont flous lorsque vous changez le zoom de 100 à tout autre pourcentage
-  [KB 4592012] Erreur client inattendue dans IE11 lors du collage de plusieurs lignes à partir d’Excel
    -  Microsoft ne cherche pas à résoudre ce problème

### <a name="fixed-as-part-of-10016"></a>Corrigé dans le cadre de la version 10.0.16

-  [KB 4598335] Les contrôles de chaîne multiligne ne respectent pas leurs DisplayHeights dans les listes/cartes 
-  [KB 4591891] Les lignes de proposition de facture disparaissent lors de la suppression des lignes
-  [KB 4592104] Impossible de modifier les enregistrements après avoir cliqué sur « Résoudre le problème » et être passé à une autre ligne sans résoudre le problème de validation
-  [KB 4594449] Boutons « Jamais » et « Effacer » manquants dans le sélecteur de date 
-  [KB 4594448] La saisie de l’heure est traitée différemment avec la nouvelle grille
-  [KB 4600059] Erreur client inattendue avec limitation de requêtes par e-mail
-  [KB 4574584] L’aperçu des pièces jointes des dépenses n’est pas disponible lorsque vous passez la souris sur l’icône du reçu

### <a name="fixed-as-part-of-10015"></a>Corrigé dans le cadre de la version 10.0.15    

-  (Mise à jour de la qualité) [KB 4594444] Erreur client inattendue avec aperçu pour le contrôle des entrées segmentées
-  [KB 4582723] Les options d’affichage ne s’affichent pas lorsqu’elles sont effectuées plus tard dans le cycle de vie du formulaire
-  [KB 4591988] Problèmes d’utilisation du clavier pour sélectionner une valeur dans une recherche ReferenceGroup
-  [KB 4588958] Regression Suite Automation Tool Le test (RSAT) échoue avec l’erreur : TypeError : Impossible de lire la propriété ’text’ non définie
-  [KB 4591970] Erreur client inattendue lors du collage depuis Excel immédiatement après avoir cliqué dans la grille
-  [KB 4591904] Les modifications de données ne sont pas enregistrées si, après la modification d’un contrôle, l’utilisateur a immédiatement cliqué et ouvert la recherche d’un contrôle différent
-  [KB 4584752] Erreur client inattendue avec la page de propositions de facture de projet
-  [KB 4584540] Impossible de quitter la grille après avoir collé une seule ligne dans une ligne de journal
-  [KB 4591908] Lors de la création d’une nouvelle ligne, la mise au point reste dans la colonne dans laquelle vous étiez

### <a name="fixed-as-part-of-10014"></a>Corrigé dans le cadre de la version 10.0.14

-  (Mise à jour de la qualité) [KB 4584752] Erreur client inattendue avec la page de propositions de facture de projet
-  [KB 4583880] Regression Suite Automation Tool (RSAT) échoue sur l’action OpenLookup avec « Impossible de lire la propriété RowIndex non définie »
-  [KB 4583847] Erreur client inattendue lors de la navigation dans les recherches

### <a name="fixed-as-part-of-10013"></a>Corrigé dans le cadre de la version 10.0.13

-  (Mise à jour de la qualité) [KB 4584752] Erreur client inattendue avec la page de propositions de facture de projet
-  (Mise à jour de qualité) [KB 4583880] Regression Suite Automation Tool (RSAT) échoue sur l’action OpenLookup avec "Impossible de lire la propriété RowIndex non définie"
-  (Mise à jour de qualité) [KB 4583847] Erreur client inattendue lors de la navigation dans les recherches 
-  (Mise à jour de qualité) [Bogue 471777] Impossible de sélectionner des champs dans une grille pour modifier ou créer une application mobile
-  [KB 4582727] La grille se fige une fois que l’utilisateur obtient une boîte de dialogue pour les éléments avec plusieurs quantités
-  [Bogue 474851] Les liens hypertexte dans les contrôles du groupe de référence ne fonctionnent pas 
-  [Bogue 474848] Les aperçus améliorés avec des grilles ne s’affichent pas
-  [KB 4582726] La propriété RotateSign n’est pas respectée  
-  [Bogue 470173] Les cases à cocher des lignes inactives basculent lorsque l’utilisateur clique sur l’espace blanc de la cellule
-  [Bogue 474848] Les aperçus améliorés avec des grilles ne s’affichent pas
-  [Bogue 474851] Les liens hypertexte dans les contrôles du groupe de référence ne fonctionnent pas 
-  [Bogue 471777] Impossible de sélectionner des champs dans une grille pour modifier ou créer une application mobile
-  [KB 4569441] Problèmes d’affichage des listes de cartes à plusieurs colonnes, des info-bulles sur les images et des options d’affichage sur certains champs
-  [KB 4575279] Toutes les lignes marquées ne sont pas supprimées dans le journal des opérations diverses
-  [KB 4575233] Les options d’affichage ne sont pas restaurées après le déplacement vers une autre ligne
-  [Bug 477884] Les recherches renvoient une valeur/un enregistrement incorrect si un nouveau contrôle de grille est activé
-  [KB 4571095] La validation de l’accusé de réception de marchandises se produit lorsque vous appuyez accidentellement sur Entrée (gestion correcte de l’action par défaut d’une page)
-  [KB 4575437] Les recherches avec des contrôles modifiables se ferment de manière inattendue
-  [KB 4569418] Ligne en double créée dans le formulaire du plan de livraison
-  [KB 4575435] L’aperçu amélioré persiste parfois même lorsque le pointeur de la souris n’est pas près du champ
-  [KB 4575434] La recherche ne filtre pas lorsque le champ a été modifié
-  [KB 4575430] Les valeurs des champs de mot de passe ne sont pas masquées dans la grille
-  [KB 4569438] Le message « Le traitement s’est arrêté en raison d’un problème de validation » s’affiche après le marquage des lignes lors du règlement des transactions fournisseur
-  [KB 4569434] L’actualisation du formulaire Entités juridiques génère moins d’enregistrements
-  [KB 4575297] Le focus continue à se déplacer vers le volet Enregistreur de tâches lors de la modification et de la navigation par tabulation dans une grille
-  [KB 4566773] Les transactions de correction ne s’affichent pas sous forme de valeurs négatives lors de la recherche de transactions de N° document 
-  [KB 4575288] Le focus est réinitialisé sur la ligne active lors de la sélection de la bordure entre les lignes dans une liste simple
-  [KB 4575287] Le focus n’est pas rétabli sur la première colonne lors de l’utilisation de la flèche Bas pour créer une ligne dans les journaux
-  [KB 4564819] Impossible de supprimer des lignes dans une facture financière (car la source de données ChangeGroupMode=ImplicitInnerOuter)
-  [KB 4563317] Les infos-bulles/aperçus améliorés ne s’affichent pas pour les images

### <a name="fixed-as-part-of-10012"></a>Corrigé dans le cadre de la version 10.0.12

- [KB 4558545] Les contrôles de table ne mettent pas à jour le contenu des éléments affichés.
- [KB 4558570] Les éléments sont toujours affichés sur la page après la suppression de l’enregistrement.
- [KB 4558572] Le style associé au volet Liste **ExtendedStyle** n’est pas appliqué.
- [KB 4558573] Les erreurs de validation ne peuvent pas être corrigées lorsque la modification requise est en dehors de la grille.
- [KB 4558584] Les nombres négatifs ne sont pas rendus correctement.
- [KB 4560726] Une « erreur client inattendue » se produit après un échange entre listes à l’aide d’un contrôle Affichage de liste.
- [KB 4562141] Les indices de grille sont désactivés après l’ajout d’un nouvel enregistrement.
- [KB 4562151] Les options de l’enregistreur de tâches **Valider** et **Copier** ne sont pas disponibles pour les contrôles de date/numéro. 
- [KB 4562153] Les cases à cocher à sélection multiple ne sont pas visibles sur les grilles de liste/carte.
- [KB 4562646] Vous ne pouvez parfois pas cliquer en dehors de la grille après avoir sélectionné plusieurs lignes.
- [KB 4562647] Le focus est réinitialisé sur le premier contrôle de la boîte de dialogue **Publier** après l’ajout d’une nouvelle ligne dans la grille des rôles de sécurité.
- [KB 4563310] L’aperçu amélioré n’est pas fermé après la modification d’une ligne.
- [KB 4563313] Une « erreur client inattendue » se produit dans Internet Explorer lorsqu’une valeur est sélectionnée dans une recherche.
- [KB 4564557] Les recherches et les menus déroulants ne s’ouvrent pas dans Internet Explorer
- [KB 4563324] La navigation ne fonctionne pas après l’ouverture de l’espace de travail **Gestion du personnel**.

### <a name="fixed-as-part-of-10011"></a>Corrigé dans le cadre de la version 10.0.11

- [Problème 432458] Des lignes vides ou dupliquées sont affichées au début de certaines collections enfants.
- [KB 4549711] Les lignes d’une proposition de paiement ne peuvent pas être supprimées correctement une fois le nouveau contrôle de grille activé.
- [KB 4558374] Les enregistrements qui nécessitent une boîte de dialogue de sélection polymorphe ne peuvent pas être créés.
- [KB 4558375] Le texte d’aide ne s’affiche pas sur les colonnes de la nouvelle grille.
- [KB 4558376] Les grilles du volet Liste ne sont pas affichées à la bonne hauteur dans Internet Explorer.
- [KB 4558377] Les colonnes de zone de liste modifiable qui ont la largeur **SizeToAvailable** ne s’affichent pas sur certaines pages.
- [KB 4558378] L’exploration ouvre parfois le mauvais enregistrement.
- [KB 4558379] Une erreur se produit lorsque des recherches sont ouvertes où **ReplaceOnLookup**=**Non**.
- [KB 4558380] L’espace disponible dans la grille n’est pas rempli immédiatement après la réduction d’une partie de la page.
- [KB 4558381] Les nombres négatifs ne sont pas restitués correctement/les utilisateurs sont parfois bloqués après des problèmes de validation.
- [KB 4558382] Des erreurs client inattendues se produisent.
- [KB 4558383] Les contrôles en dehors de la grille ne sont pas mis à jour après la suppression du dernier enregistrement.
- [KB 4558587] Les groupes de référence qui ont des zones de liste modifiable pour les champs de remplacement n’ont pas de valeurs.
- [KB 4562143] Les champs ne sont pas mis à jour après un changement de ligne/le traitement de la grille se bloque après la suppression de la ligne.
- [KB 4562645] Une exception se produit lorsqu’une recherche est ouverte pendant l’exécution des tests RSAT (Regression Suite Automation Tool).

### <a name="fixed-as-part-of-10010"></a>Corrigé dans le cadre de la version 10.0.10

- [Problème 414301] Certaines données des lignes précédentes disparaissent lorsque des lignes sont créées.
- [Bogue 417044] Il n’y a pas de message de grille vide pour les grilles de style de liste.
- [KB 4539058] Certaines grilles (généralement sur les organisateurs) ne sont parfois pas affichées (mais elles le seront si vous effectuez un zoom arrière).
- [KB 4549734] Les lignes actives ne sont pas traitées comme marquées si la colonne de marquage est masquée.
- [KB 4549796] Les valeurs ne peuvent pas être modifiées dans une grille lorsqu’elle est en mode affichage.
- [KB 4558367] La sélection de texte est incohérente lorsque les lignes sont modifiées.
- [KB 4558368] La sélection multiple via le clavier est autorisée dans les scénarios de sélection unique.
- [KB 4558369] Les images de statut disparaissent dans la grille hiérarchique.
- [KB 4558370] Une nouvelle ligne ne défile pas dans la vue.
- [KB 4558372] La nouvelle grille est bloquée en mode de traitement si le nombre de colonnes dans le contenu qui est collé dépasse le nombre de colonnes restantes dans la grille.
- [KB 4562631] Les valeurs d’heure ne sont pas mises en forme correctement.

### <a name="quality-update-for-1009platform-update-33"></a>Mise à jour de la qualité pour la version 10.0.9/Platform Update 33

- [KB 4550367] Les valeurs d’heure ne sont pas mises en forme correctement.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
