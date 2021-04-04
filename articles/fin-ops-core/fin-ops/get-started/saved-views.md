---
title: Vues enregistrées
description: Cette rubrique décrit l’utilisation des fonctionnalités de vues enregistrées.
author: jasongre
manager: AnnBe
ms.date: 01/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: Platform update 28
ms.openlocfilehash: eaf3c530553d2908f14829a31537927c3306400a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566397"
---
# <a name="saved-views"></a>Vues enregistrées

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="introduction"></a>Introduction

La personnalisation joue un rôle important en permettant aux utilisateurs et aux organisations afin d’optimiser l’expérience utilisateur en fonction de leurs besoins. Pour plus d’informations sur la personnalisation, voir [Personnaliser l’expérience de l’utilisateur](personalize-user-experience.md).

La personnalisation traditionnelle permet aux utilisateurs de disposer d’un seul ensemble simple de personnalisations par page. La fonctionnalité **Vues enregistrées** étend la personnalisation de plusieurs façons importantes :

- Les vues permettent aux utilisateurs de disposer de plusieurs ensembles de personnalisations nommés par écran, entre lesquels ils peuvent rapidement basculer le cas échéant. Cela permet à un utilisateur pour créer plusieurs vues optimisées d’une page, où chaque vue a été adaptée pour qu’ils correspondent aux besoins d’exécuter une tâche particulière d’entreprise. 
- Les vues créées pour les types spécifiques de page peuvent également inclure les filtres ou les tris ajoutés par l’utilisateur, ce qui permet aux utilisateurs de revenir rapidement aux jeux de données généralement filtrés. Voir la rubrique [Quelles pages prennent en charge les vue](saved-views.md#what-pages-support-views) pour plus de détails. 
- Les vues peuvent être publiées aux utilisateurs ayant des rôles de sécurité spécifiques et dans des entités juridiques spécifiques. Par conséquent, tout utilisateur disposant d’un rôle spécifié et d’un accès à une entité juridique donnée peut accéder et utiliser cette vue, même si cet utilisateur n’a pas l’autorisation de la personnaliser. Cette capacité de publication permet aux organisations de définir les vues standard entreprise qui sont optimisées pour leur entreprise. Pour plus d’informations, voir la section [Gérer les personnalisations au niveau organisationnel avec des vues](saved-views.md#managing-personalizations-at-an-organizational-level-with-views).
- Contrairement à une personnalisation traditionnelle, les vues ne sont pas enregistrées automatiquement lorsqu’un utilisateur effectue des personnalisations ou filtre une liste. Les enregistrements explicites sont nécessaires pour donner aux utilisateurs la flexibilité de créer une vue avant ou après que les modifications associées à cette vue aient été apportées. Cette exigence garantit également que les définitions de vue ne soient pas modifiées par inadvertance par des filtres ou des personnalisations qui ne sont pas destinés à une utilisation à long terme. Les éléments que le système stocke automatiquement dans le cadre de l’utilisation typique des pages (par exemple, la largeur des colonnes ou l’état développé ou réduit des sections) seront enregistrés par vue.
- Les vues peuvent être ajoutées aux espaces de travail en tant que vignettes, listes liens. Par conséquent, un jeu de données filtré peut être affiché sur un espace de travail, et les utilisateurs peuvent associer un ensemble de personnalisations pertinent pour ce jeu de données avec une vignette ou un lien.

## <a name="switching-between-views"></a>Basculer entre les vues

Une fois les vues rendues disponibles pour un environnement, le sommet de n’importe quelle page qui prend en charge les vues inclut un contrôle de sélecteur de vue réduit montrant le nom de la vue actuelle.

Il existe deux variantes de taille pour le sélecteur de vue : 

- **Grands sélecteurs de vue** – Les pages qui mettent en évidence une liste ont un plus grand sélecteur de vue pour certains motifs. Avant tout, le plus grand sélecteur de vue indique les pages où la vue peut inclure les filtres définis par l’utilisateur. Comme les filtres sont inclus dans les vues, la taille supérieure de sélecteur est également justifiée car les noms de vue sont souvent la meilleure description des données affichées dans l’écran et il est prévu que les utilisateurs basculent entre les vues plus souvent sur ces types de page.
- **Petits sélecteurs de vue** – Toutes les autres pages en pleine écran (sauf les espaces de travail et le tableau de bord) ont un plus petit sélecteur de vue qui apparaît en regard de la légende de page. Les vues dans ces pages incluent uniquement les personnalisations, et non les filtres définis par l’utilisateur. Dans ces pages, la légende ou le titre d’enregistrement est souvent l’informations principale en haut de la page. Une plus petite taille du sélecteur de vue reflète également la fréquence inférieure de basculement entre les vue prévue dans ces pages. 
 
Si vous sélectionnez le nom de la vue, le sélecteur de vue est ouvert et indique la liste des vues disponibles pour la page.

- **Vue standard** – La vue **Standard** est la vue prédéfinie de la page, où aucune personnalisation explicite n’est appliquée.
- **Vues personnelles** – Les vues sans verrou représentent vos vues personnelles. Ce sont des vues que vous avez créées ou qu’un administrateur vous a données.
- **Vues verrouillées** – Certaines vues (par exemple la vue **Standard** et toutes les vues publiées pour votre rôle) ont un symbole du verrou en regard d’elles dans le sélecteur de vue. Ce symbole indique que vous ne pouvez pas modifier ces vues. Toutefois, les modifications qui reflètent l’utilisation de la page sont automatiquement enregistrées. Ces modifications incluent des modifications de la largeur d’une colonne de grille et des modifications de l’état développé ou réduit d’un organisateur. Toutefois, si vous disposez de privilèges de personnalisation, vous pouvez utiliser l’action **Enregistrer une copie** pour créer une vue personnelle basée sur la vue verrouillée.
- **Nouvelles vues** – Les vues publiées qui n’ont pas encore été ouvertes sont marquées d’un symbole d’étincelle à gauche du nom de vue.

Pour basculer vers une autre vue, ouvrez d’abord le sélecteur d’affichage et activer l’affichage que vous souhaitez charger. 

## <a name="creating-and-modifying-views"></a>Création et modification des vues

Contrairement à la personnalisation traditionnelle, les vues ne sont pas automatiquement enregistrées lorsqu’un utilisateur personnalise la page, ou lorsqu’un utilisateur applique un filtre à une liste ou la trie. Une action explicite est nécessaire pour enregistrer ces modifications dans une vue. Cette exigence donne aux utilisateurs la flexibilité de créer une vue avant ou après que les modifications associées à cette vue aient été apportées. Cela garantit également que les définitions de vue ne soient pas modifiées par inadvertance par des filtres ou des personnalisations uniques. Notez que les éléments d’utilisation typique des pages (par exemple, la largeur des colonnes ou l’état développé ou réduit des sections) sont automatiquement enregistrés pour la vue activée, même dans les vues verrouillées.

Pour vous assurer que l’état actuel de la vue est connu, lorsque vous commencez à modifier une vue en la personnalisant ou en la filtrant, un astérisque (\*) apparaît à côté du nom de la vue actuelle. Ce symbole indique que vous regardez une version modifiée et non enregistrée de cette vue.

Si vous souhaitez enregistrer ces modifications, procédez comme suit.

1. Sélectionnez le nom de vue pour ouvrir le sélecteur de vue.
2. Pour modifier la vue existante, sélectionnez **Enregistrer**. Notez que cette action n’est pas disponible pour les vues verrouillées. 
3. Pour créer une nouvelle vue :

    1. Sélectionnez **Enregistrer sous**. 
    2. Entrez un nom de vue et (facultatif) une description.
    3. Sélectionnez **Enregistrer**.

## <a name="changing-the-default-view"></a>Modification de la vue par défaut

La vue par défaut est la vue que le système essaie d’ouvrir lorsque vous ouvrez pour la première fois la page. Vous devez définir la vue par défaut sur la vue que vous comptez utiliser le plus souvent. 

> [!NOTE]
> Il existe une vue globale par défaut unique pour toutes les entreprises. Si vous modifiez la vue par défaut, cette vue sera ouverte par défaut, quelle que soit l’entité juridique dans laquelle vous vous trouvez actuellement. 

Pour modifier la vue par défaut d’une page, procédez comme suit :

1. Passez à la vue utilisée comme valeur par défaut. 
2. Sélectionnez le nom de vue pour ouvrir le sélecteur de vue. 
3. Sélectionnez **Plus** puis sur **Épingler par défaut**.

Sinon, lorsque vous créez une vue (à l’aide l’action **Enregistrer sous**), vous pouvez faire de cette nouvelle vue la vue par défaut en définissant l’option **Épingler par défaut** avant d’enregistrer la vue.

Notez que dans certains cas, la requête associée à la vue par défaut n’est pas exécutée pas lorsque vous ouvrez pour la première fois une page. Par exemple, si vous ouvrez la page via une vignette, la requête de la vignette sera exécutée indépendamment de la requête associée à la vue par défaut. En outre, si vous ouvrez une page avec une vue **Standard** ayant déjà une requête définie, la requête initiale sera exécutée à la place de la requête par défaut de la vue. Dans ce cas, vous recevrez un message d’information lorsque la vue sera chargée. Si vous changez de vue après le chargement de la page, la requête de vue doit pouvoir être exécutée comme prévu. Dans la version 10.0.10 et les versions ultérieures, le message d’information que vous recevez aura une action intégrée vous permettant de charger directement la requête de la vue par défaut.

## <a name="managing-personal-views"></a>Gestion des vues personnelles

La boîte de dialogue **Gérer mes vues** vous donne des fonctionnalités de gestion de base sur vos vues personnelles et l’ordre des vues dans le sélecteur de vue. Pour ouvrir cette page, sélectionnez le nom de vue pour ouvrir le menu déroulant du sélecteur de vue, sélectionnez **Plus**, puis sélectionnez **Gérer mes vues**.

Pour obtenir une liste des vues disponibles pour cette page, l’ensemble d’actions suivant est disponibles.

- **Modifier la vue par défaut** – Utilisez l’action **Épingler par défaut** pour faire de la vue actuelle sélectionnée la vue par défaut de cette page.
- **Réorganiser vos vues** – Utilisez les actions **Déplacer vers le haut** et **Déplacer vers le bas** pour réorganiser les vues dans un ordre spécifique.
- **Renommer une vue** – Utilisez l’action **Renommer** pour modifier le nom de la vue personnelle actuelle sélectionnée. Cette action est désactivée pour les vues verrouillées. 
- **Supprimer une vue** – Utilisez l’action **Supprimer** pour supprimer définitivement la vue actuelle sélectionnée de la page. Il n’existe aucune façon de récupérer une vue après l’avoir supprimer.

Tous les modifications effectuées dans cette boîte de dialogue prennent effet après avoir sélectionné le bouton **Enregistrer**.

## <a name="managing-personalizations-at-an-organizational-level-with-views"></a>Gérer les personnalisations au niveau organisationnel avec des vues

Pour vous aider à comprendre comment les vues enregistrées permettent d’améliorer la gestion des personnalisations au niveau organisationnel, cette section décrit certaines différences dans la gestion des personnalisations avec et sans la fonctionnalité **Vues enregistrées**.

Sans les vues, les administrateurs appliqueraient un ensemble de personnalisations pour une page à un utilisateur ou un groupe d’utilisateurs via la page de personnalisation. Si ces utilisateurs avaient des droits de personnalisation, les personnalisations seraient appliquées à cette page. Toutefois, il n’y avait aucune possibilité d’empêcher les utilisateurs de personnaliser davantage la page, qui signifiait que l’organisation ne pouvait pas garantir que les utilisateurs aient une interface utilisateur cohérente. Si l’un de ces utilisateurs n’avait pas de droits de personnalisation, les personnalisations accordées par un administrateur n’étaient pas chargées. De plus, si de nouveaux utilisateurs étaient engagés dans une organisation, les administrateurs devaient charger manuellement un ensemble de personnalisations pour l’utilisateur. Il n’y avait aucun mécanisme automatique pour indiquer qu’un certain ensemble de personnalisations devait être disponible pour les utilisateurs dotés de ce rôle.

La fonctionnalité **Vues enregistrées** rend la gestion organisationnelle des personnalisations bien plus simple, principalement car les vues peuvent être publiées pour des groupes d’utilisateurs. Après la publication d’une vue, tout utilisateur ayant l’un des rôles de sécurité définis et ayant accès à l’une des entités juridiques spécifiques peut afficher et utiliser la vue, même si cet utilisateur n’a pas accès à la personnalisation. Bien que chaque utilisateur ait une copie de la vue publiée où les éléments d’utilisation de page sont automatiquement appliqués, aucun utilisateur ne peut enregistrer de personnalisations ou de mises à jour de requêtes dans la vue publiée. Autrement dit, les vues publiées sont verrouillées. En outre, si de nouveaux utilisateurs se voient attribuer des rôles dans les entités juridiques où les vues ont été publiées, ils ont accès automatiquement aux vues associées à leurs rôles et entités juridiques. Aucune action supplémentaire n’est requise par l’administrateur. De même, si les utilisateurs modifient les rôles d’une organisation ou sont autorisés à accéder à différentes entités juridiques, ils peuvent ne plus être en mesure d’accéder aux vues qui ont été précédemment publiées pour eux. Là aussi, aucune action supplémentaire n’est requise par l’administrateur.

Les mises à jour d’une vue publiée peuvent être facilement distribuées aux utilisateurs en publiant à nouveau la vue dans les rôles de sécurité et entités juridiques appropriés.

La capacité de publication permet aux organisations de définir les vues standard entreprise qui sont optimisées pour leur entreprise, ciblées selon les utilisateurs dans des rôles de sécurité spécifiques.

## <a name="publishing-views"></a>Publier des vues

Lors du processus de publication, les vues peuvent être affectées à un ou plusieurs rôles de sécurité pour une ou plusieurs entités juridiques. Par conséquent, tout utilisateur ayant accès à une entité juridique et affecté à un de ces rôles peut accéder à et utiliser les vues. Cependant, l’utilisateur ne peut pas modifier les vues. Par défaut, les administrateurs système ont accès à l’action **Publier** dans le menu déroulant du sélecteur de vue. Toutefois, d’autres utilisateurs approuvés de votre organisation peuvent également se voir octroyer un accès pour afficher les publications via le nouveau rôle **Administrateur des vues enregistrées**.

Pour publier une vue, procédez comme suit :

1. Créez et enregistrez une copie personnelle de la vue à publier. 
2. Avec cette vue actuellement chargée, sélectionnez le nom de vue pour ouvrir le menu déroulant du sélecteur de vue. 
3. Sélectionnez le bouton **Plus**, puis sélectionnez **Publier**. La boîte de dialogue Publier s’affiche.
4. Entrez un nom pour la vue. Le nom que vous entrez est celui que les utilisateurs qui reçoivent cette vue verront dans leurs sélecteurs de vue. Les noms des vues publiées pour une page doivent être uniques. Aucun doublon de nom n’est autorisé, même si la liste des rôles ou des entités juridiques auxquelles les vues sont appliquées diffèrent.
5. **Mise à jour 10.0.17 ou ultérieure :** si la fonctionnalité **(Version préliminaire) Prise en charge de la traduction pour les vues d’organisation** est activée, vous pouvez ajouter des traductions pour le nom de votre vue dans autant de langues requises par votre organisation en sélectionnant le bouton **Traductions** en regard du champ **Nom**. Le nom de la vue sera alors affiché aux utilisateurs dans leur langue actuelle. Vous pouvez également définir la langue par défaut pour spécifier la traduction qui sera affichée aux utilisateurs qui exécutent des langues pour lesquelles aucune traduction n’est définie.
5. Facultatif : entrez une description pour la vue afin que les utilisateurs qui la reçoivent puissent mieux comprendre son objectif. 
6. Déterminez si la vue doit être publiée comme vue par défaut pour les utilisateurs sélectionnés. Lorsqu’une vue est définie comme vue par défaut, les utilisateurs la voient la prochaine fois qu’ils ouvriront la page cible. La vue par défaut unique et globale de chaque utilisateur ciblé sera modifiée. Cependant, les utilisateurs peuvent toujours modifier leur vue par défaut après la publication.
7. Ajoutez les rôles de sécurité qui correspondent aux utilisateurs ciblés par cette vue. 
8. Déterminez si vous souhaitez publier la vue dans les rôles enfants de chaque rôle de sécurité sélectionné. Si vous le faites, cochez la case **Inclure les rôles enfants** de la ligne des rôles de sécurité appropriés. Notez que cette case à cocher n’est pas disponible pour les rôles qui n’ont pas de rôle enfant.
9. Ajoutez les entités juridiques pour lesquelles cette vue doit être disponible. 
10. Sélectionnez **Publier**.

Notez que dans certains environnements, il peut prendre un certain temps (jusqu’à une heure) avant que les utilisateurs voient la vue publiée.

> [!NOTE]
> Tenez compte des attentes suivantes lorsque vous publiez une vue dans une entité juridique ou lorsque vous publiez une vue comme vue par défaut.
> - Si vous publiez une vue comme vue par défaut pour toutes ou certaines entités juridiques, vous modifiez la vue par défaut unique et globale de chaque utilisateur ciblé. Si un utilisateur a des rôles dans lesquels plusieurs vues sont publiées comme vue par défaut, la dernière vue publiée sera utilisée comme vue par défaut de l’utilisateur. 
> - Si vous publiez une vue dans une entité juridique, mais que vous ne la publiez pas comme vue par défaut, les utilisateurs ne verront initialement la vue dans le sélecteur de vue que pour les entités juridiques spécifiées. Cependant, une fois la vue chargée pour la première fois, elle sera toujours dans le sélecteur de vue de l’utilisateur pour cette page, quelle que soit l’entité juridique. 

## <a name="modifying-a-published-view"></a>Modifier une vue émise

Après avoir publié une vue, vous constaterez peut-être que vous souhaitez la modifier. Bien que vous ne puissiez pas effectuer les modifications en direct dans une vue publiée, car ces vues sont verrouillées à la modification pour tous les utilisateurs (éditeurs inclus), vous pouvez republier une vue pour la mettre à jour.

Si les modifications que vous souhaitez appliquer à une vue publiée impliquent que les paramètres de publication (le nom et la description de la vue, ou les rôles de sécurité auxquels la vue est publiée), procédez comme suit :

1. Passez à la vue publiée pour les paramètres que vous souhaitez mettre à jour. 
2. Dans le menu déroulant du sélecteur de vue, sélectionnez **Republier** . Si vous utilisez la version 10.0.12 ou une version antérieure, vous devez sélectionner **Publier**, puis **Oui** pour mettre à jour la vue existante.
3. Mettez à jour le nom, la description, les rôles de sécurité et les entités légales pour la vue. 
4. Sélectionnez **Publier**. Si vous avez sélectionné à l’origine cette vue publiée comme vue par défaut, elle sera à nouveau la vue par défaut pour les utilisateurs une fois que vous l’aurez republiée. 

Si les modifications de la vue publiée impliquent des modifications des personnalisations ou des filtres associés à la vue, procédez comme suit.

1. Chargez la vue publiée que vous souhaitez modifier. 
2. Apportez les modifications requises au brouillon local.
3. Dans le menu déroulant du sélecteur de vue, sélectionnez **Republier** .
4. Sélectionnez **Oui** pour indiquer que vous souhaitez publier la vue avec ses modifications non enregistrées. 
5. Ajustez tous les paramètres de publication qui nécessitent un ajustement, puis sélectionnez **Publier**. 

## <a name="managing-published-views"></a>Gestion des vues publiées

Comme pour gérer des vues personnelles, la boîte de dialogue **Gérer mes vues** donne aux utilisateurs des capacités de gestion de base des privilèges de publication sur les vues publiées de cette page (en plus de leurs propres affichages personnels). Pour ouvrir cette page, sélectionnez le nom de vue pour ouvrir le menu déroulant du sélecteur de vue, sélectionnez **Plus**, puis sélectionnez **Gérer mes vues**.

Bien que tous les utilisateurs aient un onglet **Mes vues** affichant leurs vues personnelles, les utilisateurs disposant de privilèges de publication ont également un onglet **Vues de l’organisation** qui affiche toutes les vues publiées et non publiées pour cette page. Comme plusieurs utilisateurs peuvent publier des vues, il est important que vous puissiez gérer la liste complète des vues publiées, même si vous n’êtes pas l’utilisateur ayant publié une vue donnée.

Pour obtenir la liste de toutes les vues publiées pour la page, l’ensemble d’actions suivant est disponibles. 

- **Republier** – Utilisez l’action **Republier** pour republier une vue après que les paramètres de publication (nom, description, rôles de sécurité ou entités juridiques) ont été modifiés.
- **Publier** – Utilisez l’action **Publier** pour publier une vue actuellement non publiée. 
- **Annuler la publication** – Utilisez l’action **Annuler la publication** pour rendre une vue inactive. La vue sera toujours disponible dans le système, mais les utilisateurs ne la verront pas dans le sélecteur de vue tant que la vue ne sera pas publiée à nouveau.
- **Enregistrer comme personnel** – Utilisez l’action **Enregistrer comme personnel** pour créer un brouillon personnel de la vue publiée. Cette fonctionnalité peut vous aider à comprendre le contenu d’une vue qui n’a pas été publiée pour vous ou qui n’a pas encore été publiée. Vous pouvez également l’utiliser pour modifier puis republier une vue.
- **Supprimer** – Utilisez l’action **Supprimer** pour supprimer définitivement une vue publiée ou non publiée. Cette action permet également de supprimer la vue pour tous les utilisateurs du système. La suppression des vues publiées prend effet après la sélection du bouton **Enregistrer**. Une fois qu’une vue est supprimée, elle ne peut pas être récupérée. 

## <a name="managing-views-globally"></a>Gestion globale des vues

Bien que certaines fonctionnalités de gestion soient présentées sur chaque page, comme indiqué dans cette rubrique, les **administrateurs système** et les **administrateurs de vues enregistrées** peuvent gérer les vues de manière plus globale pour le système via la page **Personnalisation**. En particulier, cette page comporte les sections et fonctionnalités suivantes : 

- **Vues publiées** – Cette section répertorie toutes les vues qui ont été publiées pour votre organisation. À partir de là, vous pouvez republier une vue après avoir ajusté les rôles de sécurité ou les entités juridiques ciblées par la vue. Vous pouvez également publier, supprimer ou annuler la publication des vues. Vous pouvez utiliser l’action **Enregistrer comme personnel** pour créer une copie personnelle d’une vue, afin de pouvoir la mettre à jour ou mieux comprendre son contenu. 
- **Vues non publiées** – Cette section répertorie toutes les vues d’organisation de votre système qui ne sont pas actuellement publiées. Ces vues entrent le plus souvent dans le système via la fonction d’importation. Vous pouvez publier, exporter ou supprimer ces vues. L’action **Publication rapide** ajoutée dans la version 10.0.12 permet de publier plusieurs vues de cette section en une seule action, en utilisant le rôle de sécurité et les configurations d’entité juridique existants. Vous pouvez utiliser l’action **Enregistrer comme personnel** pour créer des copies personnelles de ces vues, afin de pouvoir mieux comprendre leur contenu.
- **Vues personnelles** :– Cette section répertorie toutes les vues créées par les utilisateurs dans le système. De là, vous pouvez publier une vue personnelle dans l’organisation, ou copier une ou plusieurs de ces vues pour d’autres utilisateurs. Vous pouvez également exporter ou supprimer ces vues au besoin.
- **Paramètres utilisateur** – Sélectionnez un utilisateur à afficher ou ajustez la capacité de l’utilisateur à utiliser la personnalisation pour l’ensemble du système ou pour des pages spécifiques que l’utilisateur a visitées. Vous pouvez afficher et interagir avec les personnalisations de l’utilisateur dans le système. Vous pouvez également supprimer toutes les personnalisations pour cet utilisateur ou réinitialiser les légendes de fonctionnalités pour l’utilisateur. Si les légendes des fonctionnalités sont réinitialisées, les fenêtres contextuelles qui introduisaient de nouvelles fonctionnalités et ignorées précédemment par l’utilisateur s’afficheront de nouveau la prochaine fois que l’utilisateur rencontre ces fonctionnalités.
- **Paramètres système** – Vous pouvez désactiver temporairement la personnalisation de l’ensemble des utilisateurs du système. Dans ce cas, aucune personnalisation n’est appliquée pour les utilisateurs, et toutes les pages sont rétablies à leur état par défaut. Si vous réactivez la personnalisation ultérieurement, toutes les personnalisations sont réappliquées. Vous pouvez également supprimer définitivement toutes les personnalisations pour l’ensemble des utilisateurs du système. Les personnalisations qui ont été supprimées ne peuvent être restaurées. Par conséquent, avant d’effectuer cette tâche, veillez à exporter les personnalisations que vous souhaitez utiliser ultérieurement.

Les utilisateurs qui ont accès à la page **Personnalisation** peuvent également importer des vues personnelles ou d’organisation à l’aide du bouton **Importer les vues** du volet Actions. Pour les vues d’organisation, vous pouvez sélectionner **Publier immédiatement** pour rendre les vues disponibles aux utilisateurs sans publication explicite supplémentaire.

## <a name="known-issues"></a>Problèmes connus
Pour obtenir une liste des problèmes connus liés aux vues enregistrées, voir [Créer des formulaires qui utilisent pleinement les vues enregistrées](../../dev-itpro/user-interface/understanding-saved-views.md).

## <a name="frequently-asked-questions"></a>Forum aux questions

### <a name="how-do-i-enable-saved-views-in-my-environment"></a>Comment activer des vues enregistrées dans mon environnement ?

> [!NOTE]
> La fonctionnalité **Vues enregistrées** nécessite l’activation du système de personnalisation dans Finance and Operations. Si la personnalisation est désactivée pour tout l’environnement, les vues sont désactivées même si vous suivez la procédure ci-dessous. 

Vous pouvez activer et désactiver la fonctionnalité **Vues enregistrées** par le biais de la gestion des fonctionnalités dans n’importe quel environnement. Une fois la fonctionnalité activée, les vues enregistrées seront activées dans toutes les sessions utilisateur suivantes.

### <a name="what-happens-to-existing-personalizations-when-views-are-enabled"></a>Qu’arrive-t-il aux personnalisations existantes lorsque les vues sont activées ? 

Lorsque les vues est activée, toutes les personnalisations existantes pour un utilisateur et un écran sont enregistrées dans une nouvelle vue appelée **Ma vue** qui est automatiquement définie comme la vue par défaut. Cela est conçu pour vérifier qu’il existe une expérience utilisateur cohérente avant et après que des vues aient été activées, à l’exception du contrôle du sélecteur de vue figurant sur les écrans.

### <a name="what-pages-support-views"></a>Quelles pages prennent en charge les vues ? 

Les vues sont disponibles sur la plupart des pages, mais pas toutes. Spécifiquement, les vues sont actuellement disponibles sur toutes les pages en plein écran à l’exception des tableaux de bord et des espaces de travail. Les pages qui ne sont pas en plein écran, ce qui inclut les boîtes de dialogue, les boîtes de dialogue déroulantes, les recherches, les aperçus optimisés, ne prennent actuellement pas en charge les vues. La prise en charge des vues pour d’autres types de pages, tels que des espaces de travail et boîtes de dialogue, peut être envisagée pour une prochaine mise à jour.

### <a name="who-is-allowed-to-publish-views"></a>Qui est autorisé à publier des vues ?

Seuls les administrateurs et les utilisateurs du système qui ont été affectés au rôle **Administrateur de vues enregistrées** ont les droits requis pour publier des vues. 

### <a name="why-am-i-not-able-to-save-filters-with-this-view"></a>Pourquoi ne puis-je pas enregistrer des filtres avec cette vue ? 

Il existe certaines raisons pour lesquelles un filtre peut ne pas apparaître à enregistrer avec une vue : 

- La page peut ne pas prendre en charge les filtres d’enregistrement dans le cadre de la définition de vue. Notez que seules les pages avec des grands sélecteurs de vue autorisent l’enregistrement des personnalisations et des modifications de requête comme vue. Pour plus d’informations, voir la section **Basculer entre les vues**. 
- La page en question peut ne pas prendre en charge correctement les vues, car elle peut ignorer complètement la requête de vue ou peut opérer sur une table temporaire dont les données ne sont pas persistantes. 

### <a name="what-data-will-i-see-when-i-visit-a-page"></a>Quelles données vais-je voir lorsque je visite une page ?

Pour les pages ayant de petits sélecteurs de vue (seules les personnalisations peuvent être enregistrées dans la vue), vous affichez les mêmes données que lorsque vous visitez la page. 

Pour les pages ayant de grands sélecteurs de vue (les personnalisations et les requêtes peuvent être enregistrées dans la vue), vous affichez généralement les données liées à la requête associée à votre vue par défaut. Il existe deux principales exceptions :

- Si vous accédez à une page depuis une vignette, la requête de la vignette sera exécutée indépendamment de la requête associée à la vue par défaut. Si vous avez créé cette vignette après avoir activé les vues, la sélection d’une vignette ouvre la page avec la vue associée à cette vignette.
- Si vous accédez à une page et que le point d’entrée inclut une requête, la requête initiale s’exécutera initialement à la place de la requête par défaut de la vue. Dans ce cas, vous êtes averti par un message d’information lorsque la vue se charge. Vous pouvez confirmer également en basculant vers cette vue après le chargement de la page, car cela devrait permettre à la requête de vue de s’exécuter quand même.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]