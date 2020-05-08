---
title: Capacités de grille
description: Cette rubrique décrit plusieurs fonctionnalités puissantes du contrôle de grille. La nouvelle fonction de grille doit être activée pour avoir accès à ces capacités.
author: jasongre
manager: AnnBe
ms.date: 04/23/2020
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
ms.openlocfilehash: fd45f71fc15e467c461433682310ab7b7cc0158a
ms.sourcegitcommit: 0d7b700950b1f95dc030ceab5bbdfd4fe1f79ace
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2020
ms.locfileid: "3284402"
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

## <a name="typing-ahead-of-the-system"></a>Saisie avant le système
Dans de nombreux scénarios professionnels, la capacité de saisir rapidement des données dans le système est très importante. Avant l'introduction du nouveau contrôle de grille, les utilisateurs ne pouvaient modifier les données que dans la ligne actuelle. Avant de pouvoir créer une nouvelle ligne ou basculer vers une autre ligne, ils étaient obligés d'attendre que le système réussisse à valider les modifications. Afin de réduire le temps que les utilisateurs attendent pour que ces validations soient terminées et d'améliorer la productivité des utilisateurs, la nouvelle grille ajuste ces validations afin qu'elles soient asynchrones. Par conséquent, l'utilisateur peut passer à d'autres lignes pour apporter des modifications pendant que les validations de lignes précédentes sont en attente. 

Pour prendre en charge ce nouveau comportement, une nouvelle colonne pour le statut de la ligne a été ajoutée en haut de la grille lorsque la grille est en mode édition. Cette colonne indique l'un des statuts suivants :

- **Vide** - L'image sans statut indique que la ligne a été correctement enregistrée par le système.
- **Traitement en attente** - Ce statut indique que les modifications de la ligne n'ont pas encore été enregistrées par le serveur mais se trouvent dans une file d'attente de modifications qui doivent être traitées. Avant de prendre des mesures en dehors de la grille, vous devez attendre que toutes les modifications en attente soient traitées. En outre, le texte de ces lignes est en italique pour indiquer le statut non enregistré des lignes. 
- **Avertissement de validation** - Ce statut indique que le système ne peut pas enregistrer les modifications dans la ligne en raison d'un problème de validation. Dans l'ancienne grille, vous étiez obligé de retourner dans la ligne pour résoudre le problème immédiatement. Cependant, dans la nouvelle grille, vous êtes averti qu'un problème de validation a été rencontré, mais vous pouvez décider quand vous souhaitez résoudre les problèmes de la ligne. Lorsque vous êtes prêt à résoudre le problème, vous pouvez déplacer manuellement le focus sur la ligne. Vous pouvez également sélectionner l'action **Résoudre ce problème**. Cette action ramène immédiatement le focus sur la ligne qui pose problème et vous permet d'effectuer des modifications à l'intérieur ou à l'extérieur de la grille. Notez que le traitement des lignes en attente suivantes est arrêté jusqu'à ce que cet avertissement de validation soit résolu. 
- **En pause** - Ce statut indique que le traitement par le serveur est interrompu, car la validation de la ligne a déclenché une boîte de dialogue contextuelle qui nécessite une entrée utilisateur. Étant donné que l'utilisateur peut entrer des données dans une autre ligne, la boîte de dialogue contextuelle n'est pas immédiatement présentée à cet utilisateur. Au lieu de cela, elle sera affichée lorsque l'utilisateur choisira de reprendre le traitement. Ce statut est accompagné d'une notification qui informe l'utilisateur de la situation. La notification comprend une action **Reprendre le traitement** qui déclenchera la boîte de dialogue contextuelle.  
    
Lorsque les utilisateurs saisissent des données avant l'emplacement où le serveur effectue son traitement, ils peuvent s'attendre à quelques dégradations dans l'expérience de saisie de données, comme un manque de recherches, de validation au niveau du contrôle et de saisie de valeurs par défaut. Les utilisateurs qui ont besoin d'une liste déroulante pour trouver une valeur sont encouragés à attendre que le serveur rattrape la ligne actuelle. La validation au niveau du contrôle et la saisie des valeurs par défaut se produisent également lorsque le serveur traite cette ligne.   

### <a name="pasting-from-excel"></a>Collage depuis Excel
Les utilisateurs ont toujours pu exporter des données à partir de grilles dans les applications Finance and Operations vers Excel à l'aide du mécanisme **Exporter vers Excel**. Cependant, la possibilité d'entrer des données avant le système permet à la nouvelle grille de prendre en charge la copie de tableaux à partir d'Excel et de les coller directement dans des grilles dans les applications Finance and Operations. La cellule de grille à partir de laquelle l'opération de collage est lancée détermine où le tableau copié commence à être collé. Le contenu de la grille est écrasé par le contenu de la table copiée, sauf dans deux cas :

- Si le nombre de colonnes dans la table copiée dépasse le nombre de colonnes qui restent dans la grille, à partir de l'emplacement de collage, l'utilisateur est informé que les colonnes supplémentaires ont été ignorées. 
- Si le nombre de lignes dans le tableau copié dépasse le nombre de lignes dans la grille, à partir de l'emplacement de collage, les cellules existantes sont remplacées par le contenu collé et toutes les lignes supplémentaires du tableau copié sont insérées en tant que nouvelles lignes en bas de la grille. 

## <a name="evaluating-math-expressions"></a>Évaluation des expressions mathématiques
Pour booster la productivité, les utilisateurs peuvent entrer des formules mathématiques dans des cellules numériques d'une grille. Ils n'ont pas besoin d'effectuer le calcul dans une application en dehors du système. Par exemple, si vous entrez **=15\*4**, puis appuyez sur la touche **Tab** pour quitter le champ, le système évaluera l'expression et enregistrera la valeur de **60** pour le champ.

Pour que le système reconnaisse une valeur comme une expression, démarrez la valeur avec un signe égal (**=**). Pour en savoir plus sur les opérateurs et la syntaxe pris en charge, consultez [Symboles mathématiques pris en charge](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

## <a name="frequently-asked-questions"></a>Forum aux questions
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Comment activer le nouveau contrôle de grille dans mon environnement ? 

**10.0.9/Mise à jour de la plateforme 33 et ultérieure** La fonctionnalité **Nouveau contrôle de grille** est disponible directement dans la gestion des fonctionnalités de tout environnement. Comme les autres fonctionnalités d'aperçu public, l'activation de cette fonctionnalité en production est soumise à l'[accord supplémentaire Conditions d'utilisation](https://go.microsoft.com/fwlink/?linkid=2105274).  

**10.0.8/Platform Update 32 et 10.0.7/Platform Update 31** La fonctionnalité **Nouveau contrôle de grille** peut être activée dans les environnements de niveau 1 (développement/test) et de niveau 2 (bac à sable) afin de fournir des tests et des modifications de conception supplémentaires en suivant les étapes ci-dessous.

1.  **Activer la version d'évaluation** : Exécutez l'instruction SQL suivante : 

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLIReactGridEnableFeature', 1, 0, 5637144576);`

2. **Réinitialiser IIS** pour vider le cache de la version d'évaluation statique. 

3.  **Rechercher la fonctionnalité** : accédez à l'espace de travail **Gestion des fonctions**. Si **Nouveau contrôle de grille** n'apparaît pas dans la liste de toutes les fonctionnalités, sélectionnez **Vérifier les mises à jour**.   

4.  **Activer la fonctionnalité** : Recherchez la fonctionnalité **Nouveau contrôle de grille** dans la liste des fonctionnalités, puis sélectionnez **Activer maintenant** dans le volet des détails. Notez qu'une actualisation du navigateur est requise. 

Toutes les sessions utilisateur suivantes démarreront avec le nouveau contrôle de grille activé.

## <a name="known-issues"></a>Problèmes connus
Cette section contient une liste des problèmes connus concernant le nouveau contrôle de grille lorsque la fonctionnalité est dans un état d'aperçu.  

### <a name="open-issues"></a>Questions ouvertes

- Les listes de fiches qui étaient restituées sous forme de plusieurs colonnes sont désormais affichées en une seule colonne.
- Les listes groupées ne sont pas affichées en tant que groupes ou dans des colonnes distinctes.
- Les info-bulles ne sont pas affichées pour les images.
- L'affichage du quadrillage ne fonctionne pas pour tous les types de champs.
- Par intermittence, vous ne pouvez pas cliquer en dehors de la grille après avoir sélectionné plusieurs lignes.
- Les options de l'enregistreur de tâches **Valider** et **Copier** ne sont pas disponibles pour les contrôles de date/numéro.

### <a name="fixed-as-part-of-10012"></a>Corrigé dans le cadre de la version 10.0.12

> [!Note]
> Les informations suivantes sont fournies afin que vous puissiez planifier en conséquence. Pour plus d'informations sur la planification du lancement de la version 10.0.12 ciblée, voir [Disponibilité des mises à jour de service](../../fin-ops/get-started/public-preview-releases.md).

- [Problème 429126] Les contrôles en dehors de la grille ne sont pas mis à jour après la suppression du dernier enregistrement.
- [Problème 430575] Les contrôles de table ne mettent pas à jour le contenu des éléments affichés.
- [KB 4558570] Les éléments sont toujours affichés sur la page après la suppression de l'enregistrement.
- [KB 4558584] Les nombres négatifs ne sont pas rendus correctement.
- [KB 4558575] Les champs ne sont pas mis à jour après un changement de ligne/le traitement de la grille se bloque après la suppression de la ligne.
- [Problème 436980] Le style associé au volet Liste **ExtendedStyle** n'est pas appliqué.
- [KB 4558573] Les erreurs de validation ne peuvent pas être corrigées lorsque la modification requise est en dehors de la grille.
    
### <a name="quality-update-for-10011"></a>Mise à jour de qualité pour la version 10.0.11

- [KB 4558381] Les nombres négatifs ne sont pas restitués correctement/les utilisateurs sont parfois bloqués après des problèmes de validation.

### <a name="fixed-as-part-of-10011"></a>Corrigé dans le cadre de la version 10.0.11

- [KB 4558374] Les enregistrements qui nécessitent une boîte de dialogue de sélection polymorphe ne peuvent pas être créés.
- [KB 4558382] Des erreurs client inattendues se produisent.
- [KB 4558375] Le texte d'aide ne s'affiche pas sur les colonnes de la nouvelle grille.
- [KB 4558376] Les grilles du volet Liste ne sont pas affichées à la bonne hauteur dans Internet Explorer.
- [KB 4558377] Les colonnes de zone de liste modifiable qui ont la largeur **SizeToAvailable** ne s'affichent pas sur certaines pages.
- [KB 4549711] Les lignes d'une proposition de paiement ne peuvent pas être supprimées correctement une fois le nouveau contrôle de grille activé.
- [KB 4558378] L'exploration ouvre parfois le mauvais enregistrement.
- [KB 4558379] Une erreur se produit lorsque des recherches sont ouvertes où **ReplaceOnLookup**=**Non**.
- [KB 4558380] L'espace disponible dans la grille n'est pas rempli immédiatement après la réduction d'une partie de la page.
- [Problème 432458] Des lignes vides ou dupliquées sont affichées au début de certaines collections enfants.
- [KB 4558587] Les groupes de référence qui ont des zones de liste modifiable pour les champs de remplacement n'ont pas de valeurs.

### <a name="fixed-as-part-of-10010"></a>Corrigé dans le cadre de la version 10.0.10

- [Problème 414301] Certaines données des lignes précédentes disparaissent lorsque des lignes sont créées.
- [KB 4550367] Les valeurs d'heure ne sont pas mises en forme correctement.
- [KB 4549734] Les lignes actives ne sont pas traitées comme marquées si la colonne de marquage est masquée.
- [Bogue 417044] Il n'y a pas de message de grille vide pour les grilles de style de liste.
- [KB 4558367] La sélection de texte est incohérente lorsque les lignes sont modifiées.
- [KB 4558372] La nouvelle grille est bloquée en mode de traitement si le nombre de colonnes dans le contenu qui est collé dépasse le nombre de colonnes restantes dans la grille.
- [KB 4558368] La sélection multiple via le clavier est autorisée dans les scénarios de sélection unique.
- [KB 4539058] Certaines grilles (généralement sur les organisateurs) ne sont parfois pas affichées (mais elles le seront si vous effectuez un zoom arrière).
- [KB 4558369] Les images de statut disparaissent dans la grille hiérarchique.
- [KB 4558370] Une nouvelle ligne ne défile pas dans la vue.
- [KB 4549796] Les valeurs ne peuvent pas être modifiées dans une grille lorsqu'elle est en mode affichage.

### <a name="quality-update-for-1009platform-update-33"></a>Mise à jour de la qualité pour la version 10.0.9/Platform Update 33

- [KB 4550367] Les valeurs d'heure ne sont pas mises en forme correctement.
