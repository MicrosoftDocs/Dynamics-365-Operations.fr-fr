---
title: Vues enregistrées
description: Cette rubrique décrit l'utilisation des fonctionnalités de vues enregistrées.
author: jasongre
manager: AnnBe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: Platform update 28
ms.openlocfilehash: c6a5880c6ae9470dbf7986f39798ec888d0c22ea
ms.sourcegitcommit: 1789a78de1cbeac19d96767812df653a191c67e9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2020
ms.locfileid: "3100306"
---
# <a name="saved-views"></a>Vues enregistrées

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="introduction"></a>Introduction
La personnalisation joue un rôle important en permettant aux utilisateurs et aux organisations afin d'optimiser l'expérience utilisateur en fonction de leurs besoins. Pour plus d'informations sur la personnalisation, voir [Personnaliser l'expérience de l'utilisateur](personalize-user-experience.md).

Avec la personnalisation traditionnelle, les utilisateurs peuvent contenir un ensemble simple de personnalisations par écran. Les vues enregistrées étendent la personnalisation de plusieurs façons importantes :

-    Les vues permettent aux utilisateurs de disposer de plusieurs ensembles de personnalisations nommés par écran, entre lesquels ils peuvent rapidement basculer le cas échéant. Cela permet à un utilisateur pour créer plusieurs vues optimisées d'une page, où chaque vue a été adaptée pour qu'ils correspondent aux besoins d'exécuter une tâche particulière d'entreprise. 

-    Les vues créées pour les types spécifiques de page peuvent également inclure les filtres ou les tris ajoutés par l'utilisateur, ce qui permet aux utilisateurs de revenir rapidement aux jeux de données généralement filtrés. Voir la rubrique [Quelles pages prennent en charge les vue](saved-views.md#what-pages-support-views) pour plus de détails. 

-    Les vues peuvent être publiées aux utilisateurs ayant des rôles de sécurité spécifiques et dans des entités juridiques spécifiques. Par conséquent, tout utilisateur disposant d'un rôle spécifié et d'un accès à une entité juridique donnée peut accéder et utiliser cette vue, même si cet utilisateur n'est pas forcément en mesure de la personnaliser. Cette capacité de publication permet aux organisations de définir les vues standard entreprise qui sont optimisées pour leur entreprise. Pour plus d'informations, voir la section [Gérer les personnalisations au niveau organisationnel avec des vues](saved-views.md#managing-personalizations-at-an-organizational-level-with-views).

-    Contrairement à une personnalisation traditionnelle, les vues ne sont pas enregistrées automatiquement lorsqu'un utilisateur effectue des personnalisations explicites ou filtre une liste. Des enregistrements explicites sont requis pour fournir la flexibilité en créant une vue avant ou après les modifications liées à cette vue soient effectuées et pour vous assurer que les définitions de vue ne sont pas involontairement modifiées par les filtres ou les personnalisations qui ne sont pas conçues pour l'utilisation à long terme.  

-    Les vues peuvent être ajoutées aux espaces de travail en tant que vignettes, listes liens. Par conséquent, un jeu de données filtré peut être affiché sur un espace de travail, et les utilisateurs peuvent associer un ensemble de personnalisations pertinentes pour ce jeu de données avec la vignette ou le lien.

## <a name="switching-between-views"></a>Basculer entre les vues
Une fois les vues activées pour un environnement, n'importe quelle page qui prend en charge les vues inclut un contrôle de sélecteur de vue réduit en haut de l'écran montrant le nom de la vue actuelle.  

Il existe deux variantes de taille pour le sélecteur de vue : 

-   **Grands sélecteurs de vue** : Les pages qui mettent en évidence une liste ont un plus grand sélecteur de vue pour certains motifs. Avant tout, le plus grand sélecteur de vue indique les pages où la vue peut inclure les filtres définis par l'utilisateur. Comme les filtres sont inclus dans les vues, la taille supérieure de sélecteur est également justifiée car les noms de vue sont souvent la meilleure description des données affichées dans l'écran et il est prévu que les utilisateurs basculent entre les vues plus souvent sur ces types de page.  
 
-   **Petits sélecteurs de vue** : Tous les autres écrans en pleine page (à l'exception des espaces de travail et du tableau de bord) ont un plus petit sélecteur de vue qui apparaît en regard de la légende de page. Les vues dans ces pages incluent uniquement les personnalisations (et des filtres non définis par l'utilisateur). Dans ces pages, la légende d'écran ou le titre d'enregistrement est souvent l'informations principale en haut de l'écran. Une plus petite taille reflète également une fréquence prévue inférieure de basculement entre les vue dans ces pages. 
 
Si vous cliquez sur le nom de vue, le sélecteur de vue s'ouvre et indique la liste des vues disponibles pour cette page

-    **Vue standard** : La vue **Standard** (précédemment appelée **Classique** ) est la vue prête à l'emploi de la page, où aucune personnalisation explicite n'est appliquée.
-    **Vues personnelles** : Les vues sans verrou représentent vos vues personnelles. Ce sont des vues que vous avez créées ou qu'un administrateur vous a données.  
-    **Vues verrouillées** : Certaines vues (par exemple la vue **Standard** et toutes les vues publiées pour votre rôle) ont un symbole du verrou en regard d'elles dans le sélecteur de vue. Ce symbole indique que vous ne pouvez pas modifier ces vues. Toutefois, les personnalisations implicites qui reflètent l'utilisation de la page sont automatiquement enregistrées. Ces personnalisations implicites incluent une modification de la largeur d'une colonne de la grille, ou un développement ou une réduction d'un organisateur. Toutefois, si vous disposez de privilèges de personnalisation, vous pouvez utiliser l'action **Enregistrer une copie** pour créer une vue personnelle basée sur la vue verrouillée.
-    **Nouvelles vues** : Les vues publiées qui n'ont pas encore été ouvertes sont démarquées avec une étincelle à gauche du nom de vue.  

Pour basculer vers une autre vue, ouvrez d'abord le sélecteur d'affichage et activer l'affichage que vous souhaitez charger. 

## <a name="creating-and-modifying-views"></a>Création et modification des vues
Contrairement à une personnalisation traditionnelle, les vues ne sont pas enregistrées automatiquement lorsqu'un utilisateur effectue des personnalisations explicites (ou filtre une liste). Une action explicite est nécessaire pour enregistrer ces modifications dans une vue. Cela fournit la flexibilité en créant une vue avant ou après les modifications liées à cette vue soient effectuées et garantit également que les définitions de vue ne sont pas involontairement modifiées par les filtres ou les personnalisations uniques. Notez que les personnalisations implicites (par exemple développer ou réduire un organisateur ou modifier la largeur d'une colonne de grille) sont automatiquement enregistrées dans la vue actuelle, même pour les vues verrouillées. 

Pour vous assurer que l'état actuel de la vue est connu, lorsque vous démarrez apporter des modifications à une vue en effectuant une personnalisation explicite ou en filtrant, un astérisque s'affiche en regard du nom de vue actuel indiquant que vous consultez une version non enregistrées et modifiée de cette vue.

Si vous souhaitez enregistrer ces modifications, procédez comme suit.
1.  Sélectionnez le nom de vue pour ouvrir le sélecteur de vue.
2.  Pour modifier la vue existante :
     1. Sélectionnez **Enregistrer**. Notez que cette action n'est pas activée pour les vues verrouillées. 
3.  Pour créer une nouvelle vue :
     1.    Sélectionnez **Enregistrer sous**. 
     2.    Entrez un nom de vue et (facultatif) une description.
     3.    Sélectionnez **Enregistrer**.

## <a name="changing-the-default-view"></a>Modification de la vue par défaut
La vue par défaut est la vue que le système essaiera d'ouvrir lorsque vous accéderez pour la première fois à la page. Vous devez définir cela sur la vue que vous comptez utiliser le plus souvent.  

Pour modifier la vue par défaut d'une page, procédez comme suit : 
1.  Passez à la vue utilisée comme valeur par défaut. 
2.  Sélectionnez le nom de vue pour ouvrir le sélecteur de vue. 
3.  Sélectionnez **Plus** puis sur **Épingler par défaut**.  

Sinon, lorsque vous créez une vue (à l'aide l'action **Enregistrer sous**), vous pouvez faire de cette nouvelle vue la vue par défaut en définissant l'option **Épingler par défaut** avant d'enregistrer la vue.

Notez que dans certains cas, la requête associée à la vue par défaut ne s'exécute pas lorsque vous accédez d'abord à une page. Par exemple, si vous accédez à une page via une vignette, la requête de la vignette sera exécutée indépendamment de la requête associée à la vue par défaut. En outre, si vous accédez à une page dont la vue Standard a déjà une requête définie, la requête initiale s'exécutera à la place de la requête par défaut de la vue. Dans ce cas, vous serez averti par un message d'information lorsque la vue se chargera. Basculer entre les vues après la page ait chargé doit permettre à la requête de vue de s'exécuter comme prévue. À partir de la version 10.0.10 Platform update 34, le message d'information aura une action intégrée vous permettant de charger directement la requête de la vue par défaut.

## <a name="managing-personal-views"></a>Gestion des vues personnelles 
La boîte de dialogue **Gérer mes vues** vous donne des fonctionnalités de gestion de base sur vos vues personnelles et l'ordre des vues dans le sélecteur de vue. Pour ouvrir cette page, cliquez sur le nom de vue pour ouvrir le menu déroulant du sélecteur de vue, sélectionnez **Plus**, puis sélectionnez **Gérer mes vues**.  

Pour obtenir une liste des vues disponibles pour cette page, l'ensemble d'actions suivant est disponibles.  
-    **Modifier la vue par défaut** : Utilisez l'action **Épingler par défaut** pour faire de la vue actuelle en surbrillance la vue par défaut de cette page.  
-    **Réorganiser vos vues** : Utilisez les actions **Déplacer vers le haut** et **Déplacer vers le bas** pour réorganiser les vues dans un ordre spécifique.  
-    **Renommer une vue** : Utilisez l'action **Renommer** pour modifier le nom de la vue personnelle actuelle en surbrillance. Cette action est désactivée pour les vues verrouillées. 
-    **Supprimer une vue** : Utilisez l'action **Supprimer** pour supprimer définitivement la vue actuelle en surbrillance de la page. Il n'existe aucune façon de récupérer une vue après l'avoir supprimer.  

Tous les modifications effectuées dans cette boîte de dialogue prennent effet après avoir sélectionné le bouton **Enregistrer**.

## <a name="managing-personalizations-at-an-organizational-level-with-views"></a>Gérer les personnalisations au niveau organisationnel avec des vues
Pour vous aider à comprendre comment les vues enregistrées permettent d'améliorer la gestion des personnalisations au niveau organisationnel, cette section décrit certaines différences dans la gestion des personnalisations avec et sans la fonctionnalité des vues enregistrées.

Sans les vues, les administrateurs appliqueraient un ensemble de personnalisations pour une page à un utilisateur ou un groupe d'utilisateurs via la page de personnalisation. Si ces utilisateurs avaient des droits de personnalisation, les personnalisations seraient appliquées à cette page. Toutefois, il n'y avait aucune possibilité d'empêcher les utilisateurs de personnaliser davantage la page, qui signifiait que l'organisation ne pouvait pas garantir que les utilisateurs aient une interface utilisateur cohérente. Si l'un de ces utilisateurs n'avait pas de droits de personnalisation, les personnalisations accordées par un administrateur n'étaient pas chargées. De plus, si de nouveaux utilisateurs étaient engagés dans une organisation, les administrateurs devaient charger manuellement un ensemble de personnalisations pour l'utilisateur. Il n'y avait aucun mécanisme automatique pour indiquer qu'un certain ensemble de personnalisations devait être disponible pour les utilisateurs dotés de ce rôle.

La fonctionnalité des vues enregistrées rend la gestion organisationnelle des personnalisations sensiblement plus simple, principalement car les vues peuvent être publiées pour des groupes d'utilisateurs. Après la publication d'une vue, tout utilisateur ayant l'un des rôles de sécurité définis et ayant accès à l'une des entités juridiques spécifiques peut afficher et utiliser la vue, même s'il n'est pas forcément autorisé à la personnaliser. Bien que chaque utilisateur ait une copie de la vue publiée où l'utilisation de page (personnalisations implicites) est automatiquement appliquée, aucun utilisateur ne peut enregistrer de personnalisations ou de mises à jour de requêtes explicites dans la vue publiée. Autrement dit, les vues publiées sont verrouillées. En outre, si de nouveaux utilisateurs reçoivent des rôles dans les entités juridiques où les vues ont été publiées, ils ont accès automatiquement aux vues associées à leurs rôles et entités juridiques. Aucune action supplémentaire n'est requise par l'administrateur. De même, si les utilisateurs changent de rôle dans une organisation ou sont autorisés à accéder à différentes entités juridiques, ils peuvent ne plus être en mesure d'accéder aux vues précédemment publiées pour eux. Là aussi, aucune action supplémentaire n'est requise par l'administrateur.

Les mises à jour d'une vue publiée peuvent être facilement distribuées aux utilisateurs en publiant à nouveau la vue dans les rôles de sécurité et entités juridiques appropriés.

La capacité de publication permet aux organisations de définir les vues standard entreprise qui sont optimisées pour leur entreprise, ciblées selon les utilisateurs dans des rôles de sécurité spécifiques.  

## <a name="publishing-views"></a>Publier des vues
Lors du processus de publication, les vues peuvent être affectées à un ou plusieurs rôles de sécurité pour une ou plusieurs entités juridiques. Par conséquent, tout utilisateur ayant accès à une entité juridique et affecté à un de ces rôles peut accéder à et utiliser les vues, bien qu'ils ne puissent pas les modifier. Les administrateurs système ont accès à l'action **Publier** dans le menu déroulant du sélecteur de vue. Toutefois, d'autres utilisateurs approuvés de votre organisation peuvent également se voir octroyer un accès pour afficher les publications via le nouveau rôle **Administrateur des vues enregistrées**.

Pour publier une vue, procédez comme suit : 
1.  Créez et enregistrez une copie personnelle de la vue à publier. 
2.  Avec cette vue actuellement chargée, sélectionnez le nom de vue pour ouvrir le menu déroulant du sélecteur de vue. 
3.  Sélectionnez le bouton **Plus**, puis sélectionnez **Publier**. La boîte de dialogue Publier s'affiche.  
4.  Entrez un nom et (facultatif) une description pour la vue. Le nom que vous entrez est celui que les utilisateurs qui reçoivent cette vue verront dans leurs sélecteurs de vue. Les noms des vues publiées pour une page doivent être uniques. Aucun doublon de nom n'est autorisé, même si la liste des rôles ou des entités juridiques auxquelles les vues sont appliquées diffèrent.
5.  Ajoutez les rôles de sécurité qui correspondent aux utilisateurs ciblés par cette vue.
6. Ajoutez les entités juridiques pour lesquelles cette vue doit être disponible. 
7. [10.0.9/Mise à jour de la plateforme 33 ou ultérieure] Déterminez si la vue doit être publiée comme vue par défaut pour les utilisateurs sélectionnés. La vue par défaut est celle que les utilisateurs verront la prochaine fois qu'ils ouvriront la page cible. Cela modifie la vue par défaut pour ces utilisateurs. Cependant, les utilisateurs peuvent toujours modifier leur vue par défaut après la publication.    
8.  Sélectionnez **Publier**.

Notez que dans certains environnements, il peut prendre un certain temps (jusqu'à une heure) avant que les utilisateurs voient la vue publiée.

## <a name="modifying-a-published-view"></a>Modifier une vue émise
Après avoir publié une vue, vous pouvez découvrir que vous souhaitez modifier une vue publiée. Bien que vous ne puissiez pas effectuer les modifications en direct dans une vue publiée, car ces vues sont verrouillées à la modification pour tous les utilisateurs (éditeurs inclus), vous pouvez republier une vue pour effectuer des mises à jour.  

Si les modifications que vous souhaitez appliquer à une vue publiée impliquent que les paramètres de publication (le nom et la description de la vue, ou les rôles de sécurité auxquels la vue est publiée), procédez comme suit : 
1.  Passez à la vue publiée pour les paramètres que vous souhaitez mettre à jour. 
2.  Sélectionnez **Publier** dans le menu déroulant du sélecteur de vue. 
3.  Sélectionnez **Oui** si vous souhaitez mettre à jour la vue existante (ou **Non** si vous souhaitez publier cela sous un autre nom).
4.  Mettez à jour le nom, la description, et/ou les rôles de sécurité pour la vue. 
5.  Sélectionnez **Publier**. 
6.  [10.0.8/Mise à jour de la plateforme 32 ou antérieure] Si vous avez mis à jour le nom de la vue publiée, vous devez également supprimer la vue publiée avec l'ancien nom (voir la section **Gestion des vues publiées** pour plus de détails). 
7. [10.0.9/Mise à jour de la plateforme 33 ou ultérieure] Si vous aviez initialement choisi cette vue publiée comme vue par défaut, elle sera de nouveau la vue par défaut pour ces utilisateurs après la republication.  

Si les modifications de la vue publiée impliquent de modifier les personnalisations ou les filtres associés à la vue, procédez comme suit : 
1.  Passez à la vue publiée que vous souhaitez modifier. 
2.  Enregistrez une copie de la vue publiée pour créer un brouillon local de la vue publiée. 
3.  Modifiez le brouillon local avec les modifications nécessaires.
4.  Publiez la vue avec le nom d'origine. 

## <a name="managing-published-views"></a>Gestion des vues publiées
Comme pour gérer des vues personnelles, la boîte de dialogue **Gérer mes vues** donne aux utilisateurs des capacités de gestion de base des privilèges de publication sur les vues publiées de cette page (en plus de leurs propres affichages personnels). Pour ouvrir cette page, sélectionnez le nom de vue pour ouvrir le menu déroulant du sélecteur de vue, sélectionnez **Plus**, puis sélectionnez **Gérer mes vues**.

Bien que tous les utilisateurs voient un onglet **Mes vues** affichant leurs vues personnelles, les utilisateurs disposant de privilèges de publication voient également un onglet **Publié** qui affiche toutes les vues publiées pour cette page. Comme il peut y avoir plusieurs utilisateurs publiant des vues, il est important de pouvoir gérer la liste complète des vues publiées, que vous soyez l'utilisateur qui a publiée réellement la vue ou non.

Pour obtenir la liste de toutes les vues publiées pour la page, l'ensemble d'actions suivant est disponibles. 

-    **Publier** : Utilisez l'action **Publier** pour republier une vue après que les paramètres de publication (nom, description, rôles de sécurité ou entités juridiques) ont été modifiés.
-    **Supprimer** : Utilisez l'action **Supprimer** pour supprimer définitivement une vue publiée. Cette action permet de supprimer la vue pour tous les utilisateurs du système. La suppression des vues publiées prend effet après la sélection du bouton **Enregistrer**.

## <a name="frequently-asked-questions"></a>Forum aux questions
### <a name="how-do-i-enable-saved-views-in-my-environment"></a>Comment activer des vues enregistrées dans mon environnement ? 
Remarque : la fonctionnalité **Vues enregistrées** nécessite l'activation du système de personnalisation dans Finance and Operations. Si la personnalisation est désactivée pour tout l'environnement, les vues sont désactivées même si vous suivez la procédure ci-dessous. 

**10.0.9/Mise à jour de la plateforme 33 et ultérieure** La fonctionnalité **Vues enregistrées** est disponible directement dans la gestion des fonctionnalités de tout environnement. Comme les autres fonctionnalités d'aperçu public, l'activation de cette fonctionnalité en production est soumise à l'[accord supplémentaire Conditions d'utilisation](https://go.microsoft.com/fwlink/?linkid=2105274).  

**10.0.8/Mise à jour de la plateforme 32 et antérieure** La fonctionnalité **Vues enregistrées** peut être activée dans les environnements de niveau 1 (développement/test) et de niveau 2 (bac à sable) afin de fournir des tests et des modifications de conception supplémentaires en suivant les étapes ci-dessous.

1.  **Activer la version d'évaluation** : Exécutez l'instruction SQL suivante : 

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLISavedViewsEnableFeature', 1, 0, 5637144576);`

2. **Réinitialiser IIS** pour vider le cache de la version d'évaluation statique. 

3.  **Rechercher la fonctionnalité** : accédez à l'espace de travail **Gestion des fonctions**. Si l'option **Vues enregistrées** n'apparaît pas dans la liste, sélectionnez **Rechercher des mises à jour**.   

4.  **Activer la fonctionnalité** : Recherchez la fonctionnalité **Vues enregistrées** dans la liste des fonctionnalités, puis sélectionnez **Activer maintenant** dans le volet des détails.

Toutes les sessions utilisateur suivantes démarreront avec les vues enregistrées activées.


### <a name="what-happens-to-existing-personalizations-when-views-are-enabled"></a>Qu'arrive-t-il aux personnalisations existantes lorsque les vues sont activées ? 
Lorsque les vues est activée, toutes les personnalisations existantes pour un utilisateur et un écran sont enregistrées dans une nouvelle vue appelée **Ma vue** qui est automatiquement définie comme la vue par défaut. Cela est conçu pour vérifier qu'il existe une expérience utilisateur cohérente avant et après que des vues aient été activées, à l'exception du contrôle du sélecteur de vue figurant sur les écrans.  

### <a name="what-pages-support-views"></a>Quelles pages prennent en charge les vues ? 
Les vues sont disponibles sur la plupart des pages, mais pas toutes. Spécifiquement, les vues sont actuellement disponibles sur toutes les pages en plein écran à l'exception des tableaux de bord et des espaces de travail. Les pages qui ne sont pas en plein écran, ce qui inclut les boîtes de dialogue, les boîtes de dialogue déroulantes, les recherches, les aperçus optimisés, ne prennent actuellement pas en charge les vues. La prise en charge des vues pour d'autres types de pages, tels que des espaces de travail et boîtes de dialogue, peut être envisagée pour une prochaine mise à jour.   

### <a name="who-is-allowed-to-publish-views"></a>Qui est autorisé à publier des vues ?
Seuls les administrateurs et les utilisateurs du système qui ont été affectés au rôle **Administrateur de vues enregistrées** ont les droits requis pour publier des vues. 

### <a name="why-am-i-not-able-to-save-filters-with-this-view"></a>Pourquoi ne puis-je pas enregistrer des filtres avec cette vue ? 
Il existe certaines raisons pour lesquelles un filtre peut ne pas apparaître à enregistrer avec une vue : 

- La page peut ne pas prendre en charge les filtres d'enregistrement dans le cadre de la définition de vue. Notez que seules les pages avec des grands sélecteurs de vue autorisent l'enregistrement des personnalisations et des modifications de requête comme vue. Pour plus d'informations, voir la section **Basculer entre les vues**. 

- La page en question peut ne pas prendre en charge correctement les vues, car elle peut ignorer complètement la requête de vue ou peut opérer sur une table temporaire dont les données ne sont pas persistantes. 

### <a name="what-data-will-i-see-when-i-visit-a-page"></a>Quelles données vais-je voir lorsque je visite une page ? 
Pour les pages avec de petits sélecteurs de vue (seules les personnalisations peuvent être enregistrées dans la vue), vous affichez les mêmes données que lorsque vous visitez la page. 

Pour les pages avec de grands sélecteurs de vue (les personnalisations et les requêtes peuvent être enregistrées dans la vue), vous affichez principalement les données liées à la requête associée avec votre vue par défaut. 2 exceptions à cette règle : - Si vous accédez à une page depuis une vignette, la requête de vignette est exécutée indépendamment de la requête associée à la vue par défaut. Si vous avez créé cette vignette après avoir activé les vues, la sélection d'une vignette ouvre la page avec la vue associée à cette vignette.   
     - Si vous accédez à une page et que le point d'entrée inclut une requête, la requête initiale s'exécute initialement à la place de la requête de la vue par défaut. Dans ce cas, vous êtes averti par un message d'information lorsque la vue se charge. Vous pouvez confirmer également en basculant vers cette vue après le chargement de la page, car cela devrait permettre à la requête de vue de s'exécuter quand même.  


