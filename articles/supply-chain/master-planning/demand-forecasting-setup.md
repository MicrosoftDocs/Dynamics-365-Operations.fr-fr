---
title: Paramétrage de la prévision de la demande
description: Cette rubrique décrit les tâches de paramétrage que vous devez effectuer pour préparer la prévision de la demande.
author: t-benebo
ms.date: 11/23/2021
ms.topic: article
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3b52b970a8040dcba5a1fc59d297dc9ce1a3c53
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "8470007"
---
# <a name="demand-forecasting-setup"></a>Paramétrage de la prévision de la demande

[!include [banner](../includes/banner.md)]

Cette rubrique décrit le paramétrage de prévision de la demande.  

## <a name="item-allocation-keys"></a>Clés de répartition par article

Les clés de répartition des articles établissent des groupes d’articles. Une prévision de la demande est calculée pour un article et ses dimensions uniquement si l’article fait partie d’une clé de répartition par article. Cette règle s’applique pour regrouper un grand nombre d’articles, de sorte que les prévisions de la demande puissent être créées plus rapidement. Les prévisions sont créées en fonction des données historiques uniquement.

Un article et ses dimensions doivent faire partie d’une seule clé de répartition par article si la clé de répartition par article est utilisée lors de la création de la prévision.

Pour créer des clés de répartition des articles et leur ajouter une unité de gestion des stocks (SKU), procédez comme suit.

1. Accédez à **Planification \> Installer \> Prévision de la demande \> Clés de répartition par article**.
1. Sélectionnez une clé de répartition par article dans le volet de liste ou sélectionnez **Nouveau** dans le volet Actions pour en créer une. Dans l’en-tête de la nouvelle clé ou de celle sélectionnée, définissez les champs suivants :

    - **Clé de répartition des articles** – Saisissez un nom unique pour la clé.
    - **Nom** – Entrez un nom descriptif pour la clé.

1. Suivez l’une de ces étapes pour ajouter des articles à la clé de répartition d’articles sélectionnée ou supprimer des articles :

    - Sur le raccourci **Répartition des articles**, utilisez les boutons **Nouveau** et **Supprimer** de la barre d’outils pour ajouter ou supprimer des éléments selon vos besoins. Pour chaque ligne, sélectionnez le numéro d’article, puis attribuez des valeurs de dimension dans les autres colonnes selon vos besoins. Sélectionnez **Dimensions d’affichage** dans la barre d’outils pour modifier l’ensemble de colonnes de dimension affiché dans la grille. (La valeur de la colonne **Pourcentage** est ignorée lorsque des prévisions de la demande sont générées.)
    - Si vous souhaitez ajouter un grand nombre d’éléments à la clé, sélectionnez **Attribuer des éléments** dans le volet Actions pour ouvrir une page où vous pouvez rechercher et affecter plusieurs éléments à la clé sélectionnée.

> [!IMPORTANT]
> Veillez à n’inclure que les éléments pertinents dans chaque clé de répartition d’élément. Les articles inutiles peuvent entraîner des coûts augmentés lorsque vous utilisez Microsoft Azure Machine Learning.

## <a name="intercompany-planning-groups"></a>Groupes de planification intersociétés

La prévision de la demande peut générer des prévisions de société croisée. Dans Dynamics 365 Supply Chain Management, les sociétés qui sont planifiées ensemble sont regroupées dans le même groupe de planification intersociétés. Pour spécifier, par société, les clés de répartition d’articles à prendre en compte pour la prévision de la demande, associez une clé de répartition d’articles au membre du groupe de planification intersociétés.

> [!IMPORTANT]
> Le service Optimisation de la planification ne prend actuellement pas en charge les groupes de planification intersociétés. Pour effectuer une planification intersociétés qui utilise le service Optimisation de la planification, configurez des travaux par lots de planification principale qui incluent des plans directeurs pour toutes les sociétés concernées.

Pour paramétrer des groupes de planification intersociétés, procédez comme suit :

1. Accédez à **Planification générale \> Paramétrage \> Groupes de planification intersociétés**.
1. Sélectionnez un groupe de planification dans le volet de liste ou sélectionnez **Nouveau** dans le volet Actions pour en créer un. Dans l’en-tête du nouveau groupe ou du groupe sélectionné, définissez les champs suivants :

    - **Nom** : entrez un nom unique pour le groupe de planification.
    - **Description** : entrez une brève description du groupe de planification.

1. Sur le raccourci **Membres du groupe de planification interentreprises**, utilisez les boutons de la barre d’outils pour ajouter une ligne pour chaque société (entité légale) qui devrait faire partie du groupe. Pour chaque ligne, définissez les champs suivants :

    - **Entité légale** : sélectionnez le nom d’une société (personne morale) membre du groupe sélectionné.
    - **Séquence de planification** : attribuez l’ordre dans lequel la société doit être traitée par rapport aux autres sociétés. Les valeurs faibles sont traitées en premier. Cette commande peut être importante lorsque la demande pour une entreprise affecte d’autres entreprises. Dans ces cas, l’entreprise qui fournit la demande doit être traitée en dernier.
    - **Plan général** : sélectionnez le plan général à déclencher pour la société actuelle.
    - **Copie automatique vers le plan statique** : cochez cette case pour copier le résultat du plan dans le plan statique.
    - **Copie automatique vers le plan dynamique** : cochez cette case pour copier le résultat du plan dans le plan dynamique.

1. Par défaut, si aucune clé de répartition par article n’est affectée aux membres du groupe de planification intersociétés, une prévision de la demande est calculée pour tous les articles affectés à toutes les clés de répartition par article de toutes les sociétés. Des options de filtrage supplémentaires pour les sociétés et des clés de répartition des articles sont disponibles dans la boite de dialogue **Générer des prévisions de base statistiques** (**Planification générale \> Prévision\> Prévision de la demande \> Générer des prévisions de base statistiques**). Pour affecter des clés de répartition d’articles à une société du groupe de planification intersociétés sélectionné, sélectionnez la société, puis, dans le raccourci **Membres du groupe de planification interentreprises**, sélectionnez **Clés de répartition par article** sur la barre d’outils.

> [!IMPORTANT]
> Veillez à n’inclure que les clés de répartition par article pertinentes dans chaque groupe de planification intersociétés. Les articles inutiles peuvent entraîner des coûts augmentés lorsque vous utilisez Azure Machine Learning.

## <a name="set-up-demand-forecasting-parameters"></a><a name="parameters"></a>Configurer des paramètres de prévision de la demande

Utilisez la page **Paramètres de prévision de la demande** pour configurer plusieurs options qui contrôlent le fonctionnement de la prévision de la demande dans votre système.

### <a name="open-the-demand-forecasting-parameters-page"></a>Ouvrir la page Paramètres de prévision de la demande

Pour configurer des paramètres de prévision de la demande, accédez à **Planification générale \> Paramétrage \> Prévision de la demande \> Paramètres de prévision de la demande**. Comme la prévision de demande fonctionne sur toutes les sociétés, le paramétrage est global. Autrement dit, le paramétrage s’applique à toutes les entités juridiques (sociétés).

### <a name="general-settings"></a>Paramètres généraux

Utilisez l’onglet **Général** de la page **Paramètres de prévision de la demande** pour définir les paramètres généraux de prévision de la demande.

#### <a name="demand-forecast-unit"></a>Unité de prévision de la demande

La prévision de la demande génère la prévision en quantités. Par conséquent, l’unité de mesure dans laquelle la quantité doit être exprimée doit être spécifiée dans le champ **Unité de prévision de la demande**. Ce champ définit l’unité qui sera utilisée pour toutes les prévisions de demande, quelles que soient les unités de stock habituelles pour chaque produit. Le fait d’utiliser une unité de prévision cohérente, permet de garantir une agrégation et une distribution de pourcentage logiques. Pour plus d’informations sur l’agrégation et la distribution de pourcentage, voir [Effectuer des ajustements manuels de la prévision de base](manual-adjustments-baseline-forecast.md).

Pour chaque unité de mesure utilisée pour les SKU inclus dans une prévision de la demande, assurez-vous qu’il existe une règle de conversion pour l’unité de mesure et l’unité de mesure de la prévision générale que vous sélectionnez ici. Lorsque vous générez une prévision, la liste des articles qui n’ont pas de conversion d’unités de mesure est enregistrée. Par conséquent, vous pouvez facilement corriger la configuration. Pour plus d’informations sur les unités de mesure et sur leur conversion, voir [Gérer les unités de mesure](../pim/tasks/manage-unit-measure.md).

#### <a name="transaction-types"></a>Types de transactions

Utilisez les champs du raccourci **Types de transactions** pour sélectionner les types de transaction utilisés lorsque les prévisions de base statistiques sont générées.

La prévision de la demande peut être utilisée pour prévoir à la fois la demande dépendante et indépendante. Par exemple, si seule l’option **Commande client** est définie sur *Oui*, et si tous les articles qui sont considérés pour la prévision de la demande sont des articles vendus, le système calcule une demande indépendante. Toutefois, des sous-composants critiques peuvent être ajoutés aux clés de répartition par article et être inclus dans une prévision de la demande. Dans ce cas, si l’option **Ligne de production** est définie sur *Oui*, une prévision dépendante est calculée.

Vous pouvez remplacer les types de transaction pour une ou plusieurs clés de répartition d’articles spécifiques à l’aide de l’onglet **Clés de répartition par article**. Cet onglet fournit des champs similaires.

#### <a name="choose-how-to-create-the-baseline-forecast"></a>Choisissez comment créer la prévision de base

Le champ **Stratégie de génération de la prévision** vous permet de sélectionner la méthode utilisée pour créer une prévision de base. Trois méthodes sont disponibles :

- *Copier sur la demande historique* : permet de créer des prévisions en copiant simplement les données historiques.
- *Azure Machine Learning Service* : permet d’utiliser un modèle de prévision qui utilise Azure Machine Learning Service. Azure Machine Learning Service est la solution de Machine Learning actuelle pour Azure. Par conséquent, nous vous recommandons de l’utiliser si vous souhaitez utiliser un modèle de prévision.
- *Azure Machine Learning* : permet d’utiliser un modèle de prévision qui utilise Azure Machine Learning Studio (classique). Azure Machine Learning Studio (classique) est obsolète et sera bientôt supprimé d’Azure. Par conséquent, nous vous recommandons de sélectionner *Azure Machine Learning Service* si vous configurez la prévision de la demande pour la première fois. Si vous utilisez actuellement Azure Machine Learning Studio (classique), vous devez prévoir de basculer vers Azure Machine Learning Service dès que possible.

Vous pouvez remplacer la méthode de génération de prévision pour une ou plusieurs clés de répartition d’articles spécifiques à l’aide de l’onglet **Clés de répartition par article**. Cet onglet fournit des champs similaires.

#### <a name="override-default-forecast-algorithm-parameters-globally"></a>Remplacer globalement les paramètres de l’algorithme de prévision par défaut

Les paramètres et les valeurs de l’algorithme de prévision par défaut sont attribués sur la page **Paramètres de prévision de la demande** (**Planification \> Paramétrage \> Prévision de la demande \> Paramètres de prévision de la demande**). Cependant, vous pouvez les remplacer globalement en utilisant le raccourci **Paramètres de l’algorithme de prévision** de l’onglet **Général** de la page **Paramètres de prévision de la demande**. (Vous pouvez également les remplacer pour des clés de répartition spécifiques en utilisant l’onglet **Clés de répartition par article** de la page **Paramètres de prévision de la demande**.)

Utilisez les boutons **Ajouter** et **Supprimer** de la barre d’outils pour établir la collection des remplacements de paramètre requise. Pour chaque paramètre de la liste, sélectionnez une valeur dans le champ **Nom**, puis saisissez une valeur appropriée dans le champ **Valeur**. Tous les paramètres qui ne sont pas répertoriés ici prendront leurs valeurs à partir des paramètres de la page **Paramètres de prévision de la demande**. Pour plus d’informations sur l’utilisation de l’ensemble standard de paramètres et leur sélection de valeurs, consultez la section [Paramètres et valeurs par défaut des modèles de prévision de la demande](#model-parameters).

### <a name="set-forecast-dimensions"></a>Définir des dimensions de prévision

Une dimension de prévision indique le niveau de détail pour lequel la prévision est définie. La société, le site et la clé de répartition par article sont des dimensions de prévision obligatoires. Vous pouvez également générer des prévisions aux niveaux de l’entrepôt, du statut du stock, du groupe de clients, du compte client, du pays/de la région, de l’état, et/ou de l’article, ainsi qu’à tous les niveaux de dimension d’article. Utilisez l’onglet **Dimensions de prévision** de la page **Paramètres de prévision de la demande** pour sélectionner l’ensemble de dimensions de prévision utilisé lorsque la prévision de la demande est générée.

À tout moment, vous pouvez ajouter des dimensions de prévision à la liste des dimensions utilisées pour les prévisions de la demande. Vous pouvez également supprimer des dimensions de prévision de la liste. Toutefois, les ajustements manuels sont perdus si vous ajoutez ou supprimez une dimension de prévision.

### <a name="set-up-overrides-for-specific-item-allocation-keys"></a>Configurer des remplacements pour des clés de répartition d’articles spécifiques

Tous les articles ne se comportent de la même manière du point de vue de la prévision de la demande. Par conséquent, vous pouvez établir des remplacements pour des clés de répartition d’articles spécifiques pour la plupart des paramètres définis sur l’onglet **Général**. À l’exception de l’unité de prévision de la demande. Pour configurer des remplacements pour une clé de répartition d’article spécifique, procédez comme suit.

1. Sur la page **Paramètres de prévision de la demande**, sur l’onglet **Clés de répartition par article**, utilisez les boutons de la barre d’outils pour ajouter des clés de répartition par article à la grille de gauche, ou supprimez-les, selon vos besoins. Sélectionnez ensuite la clé de répartition pour laquelle vous souhaitez configurer des remplacements.
1. Sur le raccourci **Types de transactions**, activez les types de transactions que vous souhaitez utiliser pour générer des prévisions de base statistiques pour les produits qui appartiennent à la clé de répartition sélectionnée. Les paramètres fonctionnent de la même façon sur l’onglet **Général**, mais ils ne s’appliquent qu’à la clé de répartition de l’article sélectionnée. Tous les paramètres ici (les deux valeurs *Oui* et les valeurs *Non*) remplacent tous les paramètres **Types de transactions** sur l’onglet **Général**.
1. Sur le raccourci **Paramètres de l’algorithme de prévision**, sélectionnez la stratégie de génération de prévision et les remplacements de paramètre d’algorithme de prévision pour les produits qui appartiennent à la clé de répartition sélectionnée. Ces paramètres fonctionnent de la même façon que sur l’onglet **Général**, mais ils ne s’appliquent qu’à la clé de répartition de l’article sélectionnée. Utilisez les boutons **Ajouter** et **Supprimer** de la barre d’outils pour définir la collection des remplacements de paramètre requise. Pour chaque paramètre de la liste, sélectionnez une valeur dans le champ **Nom**, puis saisissez une valeur appropriée dans le champ **Valeur**. Pour plus d’informations sur l’utilisation de l’ensemble standard de paramètres et leur sélection de valeurs, consultez la section [Paramètres et valeurs par défaut des modèles de prévision de la demande](#model-parameters).

### <a name="set-up-the-connection-to-the-azure-machine-learning-service"></a>Configurer la connexion à Azure Machine Learning Service

Utilisez l’onglet **Azure Machine Learning Service** pour configurer la connexion à Azure Machine Learning Service. Cette solution est l’une des options pour créer la prévision de base. Les paramètres de cet onglet n’ont d’effet que lorsque le champ **Stratégie de génération de la prévision** est défini sur *Azure Machine Learning Service*.

Pour plus d’informations sur la configuration d’Azure Machine Learning Service et de l’utilisation des paramètres mentionnés ici pour vous y connecter, consultez la section [Configurer le service Azure Machine Learning](#setup-amls).

### <a name="set-up-the-connection-to-azure-machine-learning-studio-classic"></a>Configurer la connexion à Azure Machine Learning Studio (classique)

> [!IMPORTANT]
> Azure Machine Learning Studio (classique) est obsolète. Par conséquent, vous ne pouvez plus créer de nouveaux espaces de travail pour celui-ci dans Azure. Il a été remplacé par Azure Machine Learning Service, qui fournit des fonctionnalités similaires et plus encore. Si vous n’utilisez pas encore Azure Machine Learning, vous devez commencer à utiliser Azure Machine Learning Service. Si vous disposez déjà d’un espace de travail créé pour Azure Machine Learning Studio (classique), vous pouvez continuer à l’utiliser jusqu’à ce que la fonctionnalité soit complètement supprimée d’Azure. Cependant, nous vous recommandons de mettre à jour le service Azure Machine Learning dès que possible. Bien que l’application continue de vous avertir qu’Azure Machine Learning Studio (classique) est obsolète, le résultat de la prévision ne sera pas affecté. Pour plus d’informations sur le nouveau service Azure Machine Learning Service et sur la façon de la configurer, consultez la section [Configurer le service Azure Machine Learning](#setup-amls).
>
> Vous pouvez librement basculer entre les nouvelles et les anciennes solutions de machine learning avec Supply Chain Management tant que votre ancien espace de travail Azure Machine Learning Studio (classique) reste disponible.

Si vous disposez déjà d’un espace de travail Azure Machine Learning Studio (classique), vous pouvez l’utiliser pour générer des prévisions en le connectant à Supply Chain Management. Vous pouvez établir cette connexion en utilisant l’onglet **Azure Machine Learning** de la page **Paramètres de prévision de la demande**. (Les paramètres de cet onglet n’ont d’effet que lorsque le champ **Stratégie de génération de la prévision** est défini sur *Azure Machine Learning*.) Saisissez les détails suivants pour votre espace de travail Azure Machine Learning Studio (classique) :

- Clé de l’interface de programmation d’applications (API) du service Web
- URL du point de terminaison du service Web
- Nom du compte de stockage Azure
- Clé du compte de stockage Azure

> [!NOTE]
> Le nom et la clé du compte de stockage Azure sont obligatoires uniquement si vous utilisez un compte personnalisé de stockage. Si vous déployez la version sur site, vous devez posséder un compte personnalisé de stockage dans Azure, afin que Machine Learning puisse accéder aux données historiques.

## <a name="default-parameters-and-values-for-demand-forecasting-models"></a><a name="model-parameters"></a>Paramètres et valeurs par défaut des modèles de prévision de la demande

Lorsque vous utilisez le Machine Learning pour générer vos modèles de planification des prévisions, vous contrôlez les options de Machine Learning en définissant des valeurs pour *paramètres de l’algorithme de prévision*. Ces valeurs sont envoyées de Supply Chain Management à Azure Machine Learning. Utilisez la page **Paramètres de l’algorithme de prévision** pour contrôler les types de valeurs à fournir et les valeurs de chacun.

Pour configurer les paramètres par défaut et les valeurs utilisées pour les modèles de prévision de la demande, accédez à **Planification générale\> Paramétrage \> Prévision de la demande \> Paramètres de l’algorithme de prévision**. Un ensemble standard de paramètres est fourni. Les champs suivants sont disponibles pour chaque paramètre :

- **Nom** : nom du paramètre, tel qu’utilisé par Azure. En règle générale, vous ne devez pas modifier ce nom, sauf si vous avez personnalisé l’expérience dans Azure Machine Learning.
- **Description** : nom courant pour le paramètre. Ce nom est utilisé pour identifier le paramètre à d’autres endroits du système (par exemple, sur la page **Paramètres de prévision de la demande**).
- **Valeur** : valeur par défaut du paramètre. La valeur à entrer dépend du paramètre que vous modifiez. 
- **Explication** : brève description du paramètre et de son utilisation. Cette description comprend généralement des conseils sur les valeurs valides pour le champ **Valeur**.

Les paramètres suivants sont fournis par défaut. (Si vous devez revenir à cette liste standard, sélectionnez **Restaurer** dans le volet Actions.)

- **Pourcentage du niveau de confiance** : un intervalle de confiance comporte une plage de valeurs qui constitue une bonne estimation des prévisions de la demande. Un pourcentage de niveau de confiance à 95 % indique qu’il existe un risque de 5 % que la demande future se trouve en dehors de l’intervalle de confiance.
- **Forcer le caractère saisonnier** : indique s’il convient de forcer le modèle pour utiliser un type spécifique de caractère saisonnier. Ce paramètre s’applique à ARIMA et ETS uniquement. Options : *AUTOMATIQUE (par défaut)*, *AUCUN*, *ADDITIF*, *MULTIPLICATIF*.
- **Modèle de prévision** : spécifie le modèle de prévision à utiliser. Options : *ARIMA*, *ETS*, *STL*, *ETS+ARIMA*, *ETS+STL*, *TOUT*. Pour sélectionner le modèle le plus adapté, utilisez *TOUT*.
- **Valeur maximale prévue** : indique la valeur maximale à utiliser pour les prévisions. Format : +1E [n] ou constante numérique.
- **Valeur minimale prévue** : indique la valeur minimale à utiliser pour les prévisions. Format : -1E[n] ou constante numérique.
- **Substitution de valeur manquante** : indique comment les trous dans les données historiques sont comblés. Options : *(valeur numérique)*, *MOYENNE*, *PRÉCÉDENTE*, *INTERPOLATION LINÉAIRE*, *INTERPOLATION POLYNOMIALE*.
- **Étendue de substitution de valeur manquante** : indique si la valeur de substitution s’applique uniquement à la plage de dates de chaque attribut individuel granulaire, ou à l’intégralité de l’ensemble de données. Les options suivantes sont disponibles pour établir la plage de dates que le système utilise pour combler les lacunes dans les données historiques :

    - *GLOBAL* : le système utilise toute la plage de dates de tous les attributs granulaires.
    - *HISTORY_DATE_RANGE* : le système utilise une plage de dates spécifique qui est définie par les champs **Date de début** et **Date de fin** de la section **Horizon historique** dans la boîte de dialogue  **Générer des prévisions de base statistiques**.
    - *GRANULARITY_ATTRIBUTE* : le système utilise la plage de dates de l’attribut de granularité actuellement traité.

    > [!NOTE]
    > Un attribut de granularité est une combinaison de dimensions de prévision par rapport auxquelles la prévision est effectuée. Vous pouvez définir les dimensions de prévision dans la page **Paramètres de prévision de la demande**.

- **Conseil sur la saisonnalité** : pour les données saisonnières, fournissez un conseil au modèle de prévisions pour améliorer la précision des prévisions. Format : le nombre entier qui représente le nombre de plages selon lequel le modèle de demande se répète. Par exemple, entrez *6* pour les données qui se répètent tous les six mois.
- **Tester le pourcentage de taille défini** : pourcentage des données historiques à utiliser dans le cadre d’un test défini pour le calcul de la précision des prévisions.

Vous pouvez remplacer les valeurs de ces paramètres en allant dans **Planification générale \> Paramétrage \> Prévision de la demande \> Paramètres de prévision de la demande**. Sur la page **Paramètres de prévision de la demande**, vous pouvez remplacer ces paramètres de la manière suivante :

- Utilisez l’onglet **Général** pour remplacer les paramètres globalement.
- Utilisez l’onglet **Clés de répartition par article** pour remplacer les paramètres pour des clés de répartition par article spécifiques. Les paramètres qui sont remplacés pour une clé de répartition par article spécifique n’affectent que la prévision des articles associés à cette clé de répartition par article.

> [!NOTE]
> Sur la page **Paramètres de l’algorithme de prévision**, vous pouvez utiliser les boutons du volet Actions pour ajouter des paramètres à la liste ou supprimer des paramètres de la liste. Toutefois, en règle générale, vous ne devez pas adopter cette approche, sauf si vous avez personnalisé l’expérience dans Azure Machine Learning.

## <a name="set-up-the-azure-machine-learning-service"></a><a name="setup-amls"></a>Configurer Azure Machine Learning Service

Supply Chain Management calcule les prévisions de la demande à l’aide d’Azure Machine Learning Service, que vous devez configurer et exécuter sur votre propre abonnement Azure. Cette section décrit comment configurer Azure Machine Learning Service dans Azure, puis le connecter à votre environnement Supply Chain Management.

### <a name="enable-the-azure-machine-learning-service-in-feature-management"></a>Activer Azure Machine Learning Service dans la gestion des fonctionnalités

Avant de pouvoir utiliser Azure Machine Learning Service pour la prévision de la demande, vous devez activer une fonctionnalité dans Supply Chain Management pour activer l’intégration. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Planification*
- **Nom de la fonctionnalité :** *Azure Machine Learning Service pour la prévision de la demande*

### <a name="set-up-machine-learning-in-azure"></a><a name="ml-workspace"></a>Configurer le Machine Learning dans Azure

Pour permettre à Azure d’utiliser le Machine Learning pour traiter vos prévisions, vous devez configurer un espace de travail Azure Machine Learning. Vous avez deux possibilités pour cela :

- Pour configurer l’espace de travail en exécutant un script fourni par Microsoft, suivez les instructions de la section [Option 1 : Exécuter un script pour configurer automatiquement votre espace de travail Machine Learning](#ml-workspace-script), puis passez directement à la section [Configurer les paramètres de connexion Azure Machine Learning Service dans Supply Chain Management](#demand-forecast-parameters).
- Pour configurer manuellement votre espace de travail, suivez les instructions de la section [Option 2 : Configurer manuellement votre espace de travail Machine Learning](#ml-workspace-manual), puis passez à la section [Configurer les paramètres de connexion Azure Machine Learning Service dans Supply Chain Management](#demand-forecast-parameters). Cette option prend plus de temps, mais elle vous donne plus de contrôle.

#### <a name="option-1-run-a-script-to-automatically-set-up-your-machine-learning-workspace"></a><a name="ml-workspace-script"></a>Option 1 : Exécuter un script pour configurer automatiquement votre espace de travail Machine Learning

Cette section décrit comment configurer votre espace de travail Machine Learning à l’aide d’un script automatisé fourni par Microsoft. Si vous préférez, vous pouvez configurer manuellement toutes les ressources en suivant les instructions de la section [Option 2 : Configurer manuellement votre espace de travail Machine Learning](#ml-workspace-manual). Vous n’êtes pas obligé d’effectuer les deux options.

1. Sur GitHub, ouvrez le référentiel [Modèles pour la prévision de la demande Dynamics 365 Supply Chain Management avec Azure Machine Learning](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) et téléchargez les fichiers suivants :

    - quick_setup.ps1
    - sampleInput.csv
    - src/parameters.py
    - src/api_trigger.py
    - src/run.py
    - src/REntryScript/forecast.r

1. Ouvrez une fenêtre PowerShell et exécutez le script **quick_setup.ps1** que vous avez téléchargé à l’étape précédente. Suivez les instructions à l’écran. Le script configurera l’espace de travail, le stockage, la banque de données par défaut et les ressources de calcul requis. Cependant, vous devez toujours créer les pipelines requis en suivant les étapes restantes de cette procédure. (Les pipelines permettent de démarrer des scripts de prévision à partir de Supply Chain Management.)
1. Dans Azure Machine Learning Studio, chargez le fichier **sampleInput.csv** que vous avez téléchargé à l’étape 1 dans le conteneur nommé *demplan-azureml*. (Le script quick_setup.ps1 a créé ce conteneur.) Ce fichier est requis pour publier le pipeline et générer une prévision de test. Pour obtenir des instructions, voir [Charger un objet blob de blocs](/azure/storage/blobs/storage-quickstart-blobs-portal#upload-a-block-blob).
1. Dans Azure Machine Learning Studio, sélectionnez **Notebooks** dans le navigateur.
1. Recherchez l’emplacement suivant dans la structure **Fichiers** : **Users/\[current user\]/src**.
1. Téléchargez les quatre fichiers restants que vous avez téléchargés à l’étape 1 à l’emplacement de l’étape précédente.
1. Sélectionnez le fichier **api_trigger.py** que vous venez de télécharger et exécutez-le. Il créera un pipeline qui peut être déclenché via l’API.
1. Votre espace de travail est maintenant configuré. Passez à la section [Configurer les paramètres de connexion Azure Machine Learning Service dans Supply Chain Management](#demand-forecast-parameters).

#### <a name="option-2-manually-set-up-your-machine-learning-workspace"></a><a name="ml-workspace-manual"></a>Option 2 : Configurer manuellement votre espace de travail Machine Learning

Cette section décrit comment configurer manuellement votre espace de travail Machine Learning. Vous devez effectuer les procédures de cette section uniquement si vous avez décidé de ne pas exécuter le script d’installation automatique, comme décrit dans la section [Option 1 : Exécuter un script pour configurer votre espace de travail Machine Learning](#ml-workspace-script).

##### <a name="step-1-create-a-new-workspace"></a><a name="create-workspace"></a>Étape 1 : Créer un nouvel espace de travail

Utilisez la procédure suivante pour créer un espace de travail Machine Learning.

1. Connectez-vous à votre portail Azure.
1. Ouvrez le service **Machine learning**.
1. Sélectionnez **Créer** dans la barre d’outils pour ouvrir l’Assistant **Créer**.
1. Renseignez l’Assistant en suivant les instructions à l’écran. Gardez les points suivants à l’esprit lorsque vous travaillez :

    - Utilisez les paramètres par défaut à moins que d’autres points de cette liste ne recommandent des paramètres différents.
    - Assurez-vous de sélectionner la région géographique qui correspond à la région où votre instance de Supply Chain Management est déployée. Sinon, certaines de vos données pourraient se trouver hors des limites de la région. Pour plus d’informations, voir la section [Avis de confidentialité](#privacy) plus loin dans cette rubrique.
    - Utilisez des ressources dédiées, telles que des groupes de ressources, des comptes de stockage, des registres de conteneurs, des coffres de clés Azure et des ressources réseau.
    - Sur la page **Configurer les paramètres de connexion Azure Machine Learning Service** de l’Assistant, vous devez fournir un nom de compte de stockage. Utilisez un compte dédié à la prévision de la demande. Les données d’entrée et de sortie de prévision de la demande seront stockées dans ce compte de stockage.

Pour plus d’informations, voir [Créer l’espace de travail](/azure/machine-learning/quickstart-create-resources#create-the-workspace).

##### <a name="step-2-configure-storage"></a><a name="config-storage"></a>Étape 2 : Configurer le stockage

La procédure suivante permet de configurer le stockage.

1. Sur GitHub, ouvrez le référentiel [Modèles pour la prévision de la demande Dynamics 365 Supply Chain Management avec Azure Machine Learning](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) et téléchargez le fichier **sampleInput.csv**.
1. Ouvrez le compte de stockage que vous avez créé dans la section [Étape 1 : Créer un nouvel espace de travail](#create-workspace).
1. Suivez les instructions de la section [Créer un conteneur](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) pour créer un conteneur nommé *demplan-azureml*.
1. Chargez le fichier **sampleInput.csv** que vous avez téléchargé à l’étape 1 dans le conteneur que vous venez de créer. Ce fichier est requis pour publier le pipeline et générer une prévision de test. Pour obtenir des instructions, voir [Charger un objet blob de blocs](/azure/storage/blobs/storage-quickstart-blobs-portal#upload-a-block-blob).

##### <a name="step-3-configure-a-default-datastore"></a>Étape 3 : Configurer une banque de données par défaut

La procédure suivante permet de configurer une banque de données par défaut.

1. Dans Azure Machine Learning Studio, sélectionnez **Magasins de données** dans le navigateur.
1. Créez une nouvelle banque de données de type *Azure Blob Storage* qui pointe vers le conteneur de stockage Blob *demplan-azureml* que vous avez créé dans la section [Étape 2 : Configurer le stockage](#config-storage). (Si le type d’authentification de la nouvelle banque de données est *Clé de compte*, fournissez une clé de compte pour le compte de stockage créé. Pour obtenir des instructions, voir [Gérer les clés d’accès au compte de stockage](/azure/storage/common/storage-account-keys-manage?tabs=azure-portal).)
1. Définissez votre nouvelle banque de données comme celle par défaut en ouvrant ses détails et en sélectionnant **Définir comme banque de données par défaut**.

##### <a name="step-4-configure-compute-resources"></a><a name="config-compute-resources"></a>Étape 4 : Configurer les ressources de calcul

Utilisez la procédure suivante pour configurer une ressource de calcul dans Azure Machine Learning Studio afin d’exécuter vos scripts de génération de prévisions.

1. Ouvrez la page de détails de l’espace de travail Machine Learning que vous avez créé dans la section [Étape 1 : Créer un nouvel espace de travail](#create-workspace). Recherchez la valeur **URL Web Studio** et sélectionnez le lien pour l’ouvrir.
1. Sélectionnez **Calculer** sur le volet de navigation.
1. Sur l’onglet **Instances de calcul**, sélectionnez **Nouveau** pour ouvrir un assistant qui vous aidera à créer une nouvelle instance de calcul. Suivez les instructions à l’écran. L’instance de calcul sera utilisée pour créer le pipeline de prévision de la demande (elle peut être supprimée une fois le pipeline publié.) Utilisez les paramètres par défaut.
1. Sur l’onglet **Clusters de calcul**, sélectionnez **Nouveau** pour ouvrir un assistant qui vous aidera à créer un nouveau cluster de calcul. Suivez les instructions à l’écran. Le cluster de calcul sera utilisé pour générer des prévisions de demande. Ses paramètres affectent les performances et le niveau maximal de parallélisation de l’exécution. Définissez les champs suivants, mais utilisez les paramètres par défaut pour tous les autres champs :

    - **Nom** : entrez *e2ecpucluster*.
    - **Taille de la machine virtuelle** : ajustez ce paramètre en fonction du volume de données que vous prévoyez d’utiliser comme entrée pour la prévision de la demande. Le nombre de nœuds ne doit pas dépasser 11, car un nœud est requis pour déclencher la génération de prévisions de la demande et le nombre maximal de nœuds pouvant ensuite être utilisés pour générer une prévision est de 10. (Vous devez également définir le nombre de nœuds dans le fichier parameters.py dans la section [Étape 5 : créer des pipelines](#create-pipelines).) Sur chaque nœud, il y aura plusieurs processus de travail qui exécuteront des scripts de prévision en parallèle. Le nombre total de processus de travail dans votre tâche sera : *Nombre de cœurs d’un nœud* × *Nombre de nœuds*. Par exemple, si votre cluster de calcul est de type *Standard\_D4* (huit cœurs) et a un maximum de 11 nœuds, et si la valeur de `nodes_count` est définie sur *10* dans le fichier parameters.py, le niveau de parallélisme effectif est de 80.

##### <a name="step-5-create-pipelines"></a><a name="create-pipelines"></a>Étape 5 : créer des pipelines

Les pipelines permettent de démarrer des scripts de prévision à partir de Supply Chain Management. Suivez la procédure suivante pour créer les pipelines requis.

1. Sur GitHub, ouvrez le référentiel [Modèles pour la prévision de la demande Dynamics 365 Supply Chain Management avec Azure Machine Learning](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) et téléchargez les fichiers suivants :

    - src/parameters.py
    - src/api_trigger.py
    - src/run.py
    - src/REntryScript/forecast.r

1. Dans Azure Machine Learning Studio, sélectionnez **Notebooks** dans le navigateur.
1. Recherchez l’emplacement suivant dans la structure **Fichiers** : **Users/\[current user\]/src**.
1. Téléchargez les quatre fichiers que vous avez téléchargés à l’étape 1 à l’emplacement de l’étape précédente.
1. Dans Azure, ouvrez et examinez le fichier **parameters.py** que vous venez de télécharger. Assurez-vous que la valeur de `nodes_count` est une inférieure de 1 à la valeur que vous avez configurée pour le cluster de calcul dans la section [Étape 4 : Configurer les ressources de calcul](#config-compute-resources). Si la valeur `nodes_count` est supérieure ou égale au nombre de nœuds dans le cluster de calcul, l’exécution du pipeline pourra peut-être démarrer. Cependant, il cessera alors de répondre pendant qu’il attend les ressources requises. Pour plus d’informations sur le nombre de nœuds, consultez la section [ Étape 4 : Configurer les ressources de calcul](#config-compute-resources).
1. Sélectionnez le fichier **api_trigger.py** que vous venez de télécharger et exécutez-le. Il créera un pipeline qui peut être déclenché via l’API.

### <a name="set-up-a-new-active-directory-application"></a><a name="aad-app"></a>Configurer une nouvelle application Active Directory

Une application Active Directory est requise pour s’authentifier auprès des ressources dédiées à la prévision de la demande à l’aide du principal de service. Par conséquent, l’application doit avoir le niveau de privilège le plus bas requis pour générer la prévision.

1. Connectez-vous à votre portail Azure.
1. Enregistrez une nouvelle application dans le service Azure Active Directory (Azure AD) du locataire. Pour obtenir des instructions, voir [Utiliser le portail pour créer une application Azure AD et un principal de service qui peut accéder aux ressources](/azure/active-directory/develop/howto-create-service-principal-portal).
1. Renseignez l’Assistant en suivant les instructions à l’écran. Utilisez les paramètres par défaut.
1. Donnez à votre nouvelle application Active Directory l’accès aux ressources que vous avez créées dans la section [Configurer le Machine Learning dans Azure](#ml-workspace). Pour obtenir des instructions, voir [Attribuer des rôles Azure à l’aide du portail Azure](/azure/role-based-access-control/role-assignments-portal?tabs=current). Cette étape permettra au système d’importer et d’exporter des données de prévision et de déclencher des exécutions de pipeline de machine learning à partir de Supply Chain Management.

    - Rôle du contributeur à l’espace de travail Machine Learning
    - Rôle du contributeur au compte de stockage dédié
    - Rôle du contributeur de données de l’objet blob de stockage au compte de stockage dédié

1. Dans la section **Certificats et secrets** de l’application que vous avez créée, créez un secret pour l’application. Pour obtenir des instructions, voir [Ajouter un secret client](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret).
1. Notez l’ID de l’application et son secret. Vous aurez besoin des détails de cette application plus tard, lorsque vous configurerez la page **Paramètres de prévision de la demande** dans Supply Chain Management.

### <a name="set-up-azure-machine-learning-service-connection-parameters-in-supply-chain-management"></a><a name="demand-forecast-parameters"></a>Configurer les paramètres de connexion Azure Machine Learning Service dans Supply Chain Management

Suivez la procédure suivante pour connecter votre environnement Supply Chain Management au service Machine Learning que vous venez de configurer dans Azure.

1. Connectez-vous à Supply Chain Management.
1. Accédez à **Planification \> Paramétrage \> Prévision de la demande \> Paramètres de prévision de la demande**.
1. Sur l’onglet **Général**, assurez-vous que le champ **Stratégie de génération de la prévision** est défini sur *Azure Machine Learning Service*.
1. Sur l’onglet **Clés de répartition par article**, assurez-vous que le champ **Stratégie de génération de la prévision** est défini sur *Azure Machine Learning Service* pour chaque clé d’allocation qui doit utiliser Azure Machine Learning Service pour la prévision de la demande.
1. Définissez les champs suivants sur l’onglet **Azure Machine Learning Service** :

    - **ID de locataire** : entre l’ID de votre locataire Azure. Supply Chain Management utilisera cet ID pour s’authentifier auprès d’Azure Machine Learning Service. Vous pouvez trouver votre identifiant de locataire sur la page **Présentation** pour Azure AD dans le portail Azure.
    - **ID de l’application principale du service** : saisissez l’ID de l’application que vous avez créée dans la section [Application Active Directory](#aad-app). Cette valeur est utilisée pour autoriser les demandes d’API dans Azure Machine Learning Service.
    - **Secret du principal du service** : saisissez le secret de l’application du principal de service que vous avez créée dans la section [Application Active Directory](#aad-app). Cette valeur est utilisée pour acquérir le jeton d’accès pour le principal de sécurité que vous avez créé pour effectuer des opérations autorisées sur le stockage Azure et l’espace de travail Azure Machine Language.
    - **Nom du compte de stockage** : entrez le nom du compte de stockage Azure que vous avez spécifié lorsque vous avez exécuté l’assistant de configuration dans votre espace de travail Azure. (Pour plus d’informations, voir la section [Configurer le Machine Learning dans Azure](#ml-workspace).)
    - **Adresse du point de terminaison du pipeline** : saisissez l’URL du point de terminaison REST du pipeline pour votre Azure Machine Learning Service. Ce pipeline été créé comme dernière étape dans la section [Configurer le Machine Learning dans Azure](#ml-workspace). Pour obtenir l’URL du pipeline, connectez-vous à votre portail Azure, sélectionnez **Pipelines** sur la navigation. Sur l’onglet **Pipeline**, sélectionnez le point de terminaison du pipeline nommé **TriggerDemandForecastGeneration**. Copiez ensuite le point de terminaison REST affiché.

    ![Paramètres sur l’onglet Azure Machine Learning Service de la page Paramètres de prévision de la demande.](media/azure-ml-service-parameters.png "Paramètres sur l’onglet Azure Machine Learning Service de la page Paramètres de prévision de la demande")

## <a name="privacy-notice"></a><a name="privacy"></a>Avis de confidentialité

Lorsque vous sélectionnez *Azure Machine Learning Service* en tant que stratégie de génération de prévisions, Supply Chain Management envoie automatiquement vos données client pour la demande historique, telles que les quantités agrégées, les noms de produits et leurs dimensions, les emplacements d’expédition et de réception, les identifiants client, ainsi que les paramètres de prévision, à la région géographique où votre espace de travail Machine Learning et son compte de stockage lié sont localisés, dans le but de prévoir les demandes futures. Il est possible que le service Azure Machine Learning Service se trouve dans une région géographique différente de celle où Supply Chain Management est déployé. Certains utilisateurs peuvent contrôler si cette fonctionnalité est activée en sélectionnant la stratégie de génération de la prévision sur la page **Paramètres de prévision de la demande**.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble de la prévision de la demande](introduction-demand-forecasting.md)
- [Générer des prévisions de base statistiques](generate-statistical-baseline-forecast.md)
- [Effectuer des ajustements manuels sur la prévision de base](manual-adjustments-baseline-forecast.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
