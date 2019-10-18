---
title: Vue d'ensemble des structures de répartition du travail
description: Une structure de répartition du travail (WBS) est une description du travail qui sera effectué pour un projet. Il s'agit d'une hiérarchie des tâches qui représente la compréhension par l'équipe projet de la composition du travail, de son étendue, du coût et de la durée de chaque composant ou tâche.
author: KimANelson
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjWorkBreakdownStructure
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 23861
ms.assetid: 241a0464-0056-4a69-b468-0afbe2d5f3ae
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 954965ee947cbce9d1ae686d281a5fed25a78245
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174395"
---
# <a name="work-breakdown-structures-overview"></a>Vue d'ensemble des structures de répartition du travail

[!include [banner](../includes/banner.md)]

Une structure de répartition du travail (WBS) est une description du travail qui sera effectué pour un projet. Il s'agit d'une hiérarchie des tâches qui représente la compréhension par l'équipe projet de la composition du travail, de son étendue, du coût et de la durée de chaque composant ou tâche. Une WBS a trois objectifs principaux :

-   Décrire la décomposition du travail en tâches.
-   Planifier le travail du projet.
-   Estimer le coût de chaque tâche.

Le degré de détail dans une WBS dépend du niveau de précision souhaité pour les estimations et le niveau de suivi requis par rapport à ces estimations. Les projets qui ont une tolérance très basse aux écarts de durée ou de coût nécessitent généralement une WBS plus détaillée, et un suivi diligent de la progression et du coût des travaux par rapport à la WBS. Ce type de projet est courant dans les secteurs de la construction et de l'ingénierie. 

En revanche, les projets dans les secteurs tels que les médias et la publicité, le logiciel et l'infrastructure informatique ont tendance à être tous uniques en leur genre et la productivité dépend de l'expérience et de la qualification de la personne qui exécute la tâche. C'est pourquoi ces industries utilisent une WBS pour obtenir une approximation de la taille d'un projet, et non pour suivre la progression de ce projet en détail. 

L'élaboration d'une WBS est un processus intensif qui est généralement effectué sur une longue période, et qui nécessite la collaboration et les informations d'un large éventail de personnes. Cette rubrique décrit la manière dont vous pouvez utiliser les améliorations de la WBS pour répondre à vos besoins pour les estimations et le suivi.

## <a name="prerequisites-for-creating-a-wbs"></a>Conditions préalables à la création d'une WBS
Pour créer une WBS, vous devez pouvoir créer un planning de travail et estimer le coût du travail.

### <a name="prerequisites-for-creating-a-work-schedule"></a>Conditions préalables à la création d'un planning de travail

Pour utiliser les capacités complètes de planification des fonctionnalités de la WBS, réalisez le paramétrage suivant :

1.  Paramétrer un calendrier par défaut et un calendrier de projet :
    1.  Cliquez sur **Gestion et comptabilité des projets** &gt; **Paramétrage** &gt; **Paramètres de gestion et comptabilité des projets** &gt; **Planification**. Dans le champ **Calendrier de travail par défaut**, spécifiez un calendrier par défaut. Cela sera le calendrier de travail par défaut pour tous les nouveaux projets créés.
    2.  Vous pouvez modifier le calendrier par défaut pour un projet spécifique. Dans la page des détails du projet, puis ensuite dans l'organisateur **Équipe de projet et planification**, mettez à jour le champ **Calendrier de planification** en sélectionnant un autre calendrier.

2.  Paramétrez les jours de travail et les heures travaillées standard. Le calendrier que vous définissez comme calendrier de travail pour votre projet serez utilisé dans la WBS pour déterminer les informations suivantes :

-   Jours ouvrables et congés
-   Nombre d'heures travaillées dans une journée

Pour paramétrer les jours ouvrables et les heures travaillées pour un calendrier, ou pour créer un calendrier, cliquez sur **Administration d'organisation** &gt; **Commun** &gt; **Calendriers**.

### <a name="prerequisites-for-estimating-the-cost-of-work"></a>Conditions préalables à l'estimation du coût du travail

Pour utiliser les capacités complètes d'estimation de coût de la WBS, vous devez paramétrer les coûts et les prix de vente pour les collaborateurs, les catégories de travail, les dépenses, les frais et les articles.

-   Pour paramétrer le coût et le prix de vente du travail, les dépenses et les catégories de frais, cliquez sur **Gestion de projets et comptabilité** &gt; **Paramétrage** &gt; **Prix**.
-   Pour paramétrer le coût et le prix de vente des articles, utilisez la page **Accords commerciaux** pour chaque article dans la page de liste **Produits lancés** dans le module Gestion des informations sur le produit.

## <a name="creating-a-wbs"></a>Création d'une WBS
La création d'une WBS implique trois activités :

1.  **Décomposition du travail** – Permet de créer une décomposition du travail en segments faciles à gérer ou en tâches.
2.  **Planning de travail** – Estimez le temps nécessaire pour exécuter une tâche, définissez les interdépendances entre les tâches et sélectionnez les dates de début et de fin pour les tâches.
3.  **Estimation de coût** – Estimez les coûts pour chaque tâche.

Les sections suivantes présentent la manière dont les fonctionnalités de WBS peuvent vous aider dans chacune de ces activités.

### <a name="work-decomposition"></a>Décomposition du travail

La création d'une décomposition du travail est généralement la première étape du processus de création d'une WBS. La fonctionnalité de WBS prend en charge les éléments de base suivants pour la décomposition du travail. 

**Tâche racine de projet** La tâche racine du projet est la tâche récapitulative de niveau supérieur du projet. Toutes les autres tâches de projet sont créées en dessous d'elle. Nom de la tâche racine est toujours défini comme le nom du projet. L'effort, les dates et la durée du nœud racine résument les valeurs correspondant aux tâches en dessous de la tâche racine. Vous ne pouvez pas modifier les propriétés du nœud racine ni les supprimer.

**Tâches de synthèse ou de conteneur** Une tâche de synthèse est une tâche qui a des sous-tâches ou des tâches constitutives en dessous d'elle. Une tâche de synthèse n'a aucun effort de travail ou coût propre. Au lieu de cela, l'effort de travail et le coût d'une tâche de synthèse sont la somme de l'effort de travail et du coût de ses tâches constitutives. La première date de début des tâches constitutives est utilisée comme date de début de la tâche de synthèse, et la dernière date de fin des tâches constitutives est utilisée comme date de fin. Vous pouvez modifier le nom d'une tâche de synthèse, mais vous ne pouvez pas modifier les propriétés de planification pour l'effort, les dates et la durée. Si vous supprimez une tâche de synthèse, vous supprimez également toutes ses tâches constitutives. 

**Tâches de nœud terminal** Une tâche de nœud terminal représente le plus petit élément de travail du projet. Un nœud terminal a un effort estimé, un nombre prévu de ressources, une date de début et de fin prévue, et une durée. 

Vous pouvez effectuer les opérations suivantes de hiérarchie pour activer la création d'une hiérarchie ou d'une décomposition de travail pour un projet. 

**Nouvelle tâche** Toute nouvelle tâche que vous créez est automatiquement ajoutée sous le nœud racine, et un numéro WBS lui est automatiquement affecté. Le numéro WBS représente le niveau de la tâche dans la hiérarchie. Pour les tâches du premier niveau sous la tâche racine du projet, on utilise un modèle de numérotation 1, 2, 3, etc. Pour les tâches en dessous du premier niveau, on utilise un modèle de numérotation 1.1, 1.2, 1.3, etc. Pour chaque niveau qui est ajouté sous un niveau précédent, on ajoute une série de numéros à points. 

Actuellement, vous ne pouvez pas personnaliser la numérotation WBS. 

**Retrait d'une tâche** Lorsque vous appliquez un retrait à une tâche, elle devient enfant de la tâche qui la précède. Le numéro WBS de la nouvelle tâche enfant est recalculé automatiquement en fonction du numéro WBS de son nouveau parent. La tâche parent est désormais une tâche de synthèse ou de conteneur, et devient donc un regroupement de ses tâches constitutives. 

> [!NOTE] 
> Lorsque vous appliquez un retrait à des tâches sous une tâche qui était un nœud terminal avant le retrait, la tâche se synthèse nouvellement créée perd ses propres valeurs de dates, effort et nombre de ressources. Elle utilise désormais une synthèse des valeurs de ses tâches constitutives. 

**Retrait négatif d'une tâche** Lorsque vous appliquez un retrait négatif à une tâche, elle n'est plus une tâche constitutive de son parent. Le numéro WBS de cette tâche est recalculé automatiquement pour refléter le nouveau niveau de la tâche dans la hiérarchie. Les valeurs d'effort, de coût, et de dates de la tâche parent précédente sont recalculés pour exclure cette tâche. 

**Déplacement vers le haut et vers le bas** Lorsque vous cliquez sur **Déplacer vers le haut** et **Déplacer vers le bas**, vous modifiez la position d'une tâche dans la hiérarchie de son parent. La position d'une tâche n'a aucune incidence sur l'effort, le coût, les dates ou la durée de la tâche. Toutefois, le numéro WBS de cette tâche est recalculé automatiquement pour refléter la nouvelle position de la tâche.

### <a name="schedule-estimation"></a>Estimation de planification

L'estimation de planification est généralement la deuxième étape de la création d'une WBS. Il est bon de réaliser l'estimation de planification après avoir créé les tâches. La page **Structure de répartition du travail** dans Finance comporte deux sections. Le volet supérieur est destiné à l'estimation de planification, et le volet inférieur inclut un onglet **Coûts estimés et produits** que vous pouvez utiliser pour l'estimation de coût. 
**Dépendances entre les tâches** Dans une WBS, vous pouvez créer une relation de prédécesseur entre les tâches. Lorsque vous affectez des tâches de prédécesseur à une tâche, cette tâche ne peut commencer qu'une fois que toutes ses tâches de prédécesseur ont été terminées. La date de début prévue de la tâche est automatiquement définie à la dernière date de tous ses prédécesseurs. 

**Planification des tâches** Les facteurs suivants déterminent la planification des tâches de nœud terminal :

-   Prédécesseurs
-   Effort
-   Nombre de ressources
-   Dates de début et de fin

La date de début d'une tâche de nœud terminal qui n'a pas de prédécesseur est automatiquement définie sur la date de début de la planification de projet. La durée d'une tâche de nœud terminal est toujours calculée comme le nombre de jours ouvrables entre sa date de début et sa date de fin. 

*<strong><em>Règles de planification</em></strong>* Lorsque l'aide de planification automatique est activée, les règles suivantes s'appliquent à la planification des tâches pour les tâches de nœud terminal :

-   Les dates de début et de fin d'une tâche donnée doivent être des jours ouvrables, en fonction du calendrier de planification du projet.
-   La date de début d'une tâche qui a des prédécesseurs est automatiquement définie à la dernière date de fin de tous ses prédécesseurs.
-   L'effort d'une tâche est automatiquement calculé comme suit :

Nombre de personnes × Durée × Nombre d'heures dans un jour de travail standard dans le calendrier du projet. 

Dans certains cas, vous pouvez souhaiter dévier de ces règles. Vous pouvez désactiver la planification automatique pour empêcher Finance de définir ou de corriger automatiquement les propriétés des tâches de nœud terminal. Lorsque vous entrez des informations pour une tâche qui entraîne une violation d'une règle de planification, une icône d'erreur de planification s'affiche pour la tâche. Si vous ne souhaitez pas que les erreurs de planification s'affichent, cliquez sur **Les erreurs de planification sont affichées** pour désactiver la fonctionnalité. 

> [!NOTE] 
> Les valeurs pour une tâche de synthèse ou de conteneur continuent d'être calculées comme la somme des valeurs des tâches constitutives, indépendamment du fait que l'aide à la planification automatique est activée ou non. 

**Corriger les erreurs de planification** Lorsque l'aide à la planification automatique est activée, peu d'erreurs de planification sont susceptibles de se produire. Toutefois, si vous désactivez l'aide à la planification automatique et l'activez ensuite à nouveau, des icônes d'erreur de planification peuvent apparaître dans la WBS. 

**Corriger les erreurs de planification par tâche** Lorsque vous double-cliquez sur l'icône d'erreur de planification pour une tâche spécifique, une boîte de dialogue affiche toutes les erreurs de planification pour cette tâche. Vous pouvez choisir les erreurs de planification à corriger pour la tâche. 

**Résolution de toutes les erreurs de planification** Si vous souhaitez que Finance corrige toutes les erreurs de planification dans la WBS, dans le volet Actions, cliquez sur **Corriger tous les écarts de planification**. 

> [!NOTE] 
> Cette fonction peut entraîner des modifications significatives de la WBS. Les erreurs sont corrigées dans l'ordre suivant :

1.  L'effort estimé pour toutes les tâches est modifié pour qu'il soit égal à la capacité définie dans le calendrier de projet.
2.  La date de début de chaque tâche est modifiée afin que la tâche commence après toutes ses tâches de prédécesseur sont terminées.
3.  La date de début de chaque tâche est modifiée pour supprimer les écarts dans les dates de début des tâches de prédécesseur.

### <a name="cost-estimation"></a>Estimation de coût

Comme il a été indiqué précédemment dans ce document, vous entrez l'estimation de coût pour chaque tâche de nœud terminal à l'aide de l'onglet **Coûts estimés et produits** dans le volet inférieur de la page **Structure de répartition du travail**. 

> [!NOTE] 
> Vous ne pouvez pas modifier l'estimation de coût pour une tâche de synthèse ou de conteneur. L'estimation de coût pour une tâche de synthèse est égale à la somme de l'estimation de coût de ses tâches de nœud terminal. Le coût total estimé pour chaque tâche est calculé comme la somme des montants de coût estimé pour les types de transactions suivants :

-   Main-d'œuvre
-   Article ou matières
-   Dépenses

On utilise un type de transaction **Frais** pour estimer le produit basé sur les frais. Ce type de transaction n'a pas de composant de coût et n'est donc pas pris en considération lorsque les coûts sont estimés. 

On utilise un type de transaction **En compte** pour enregistrer le prix de vente contractuel dans un type de projet à valeur fixe. Ce type de transaction n'est pas non plus pris en considération lorsque les coûts sont estimés. 

Lorsque vous estimez des coûts relatifs aux salaires, aux matières et aux dépenses pour chaque tâche, vous devez affecter une catégorie de projet au coût estimé. 

**Estimation des coûts de travail** Pour chaque tâche de nœud terminal, vous affectez un effort de travail en heures et une catégorie par défaut. Donc, lorsque vous paramétrez un programme pour une tâche, l'estimation de coût de travail pour cette tâche est automatiquement ajoutée dans la catégorie par défaut pour le travail. Cette estimation des coûts s'affiche sous l'onglet **Produit et coûts estimés** dans la grille **Détails de ligne** pour cette tâche. Si vous avez besoin de plus d'estimations du coût de travail, vous pouvez les ajouter sous cet onglet. Si vous augmentez ou diminuez des heures dans l'estimation du coût de travail, le programme pour la tâche est recalculé automatiquement. 

**Estimation des dépenses et coûts matériels** L'onglet **Produit et coûts estimés** permet également d'estimer les dépenses et les coûts matériels d'une tâche, si vous avez besoin d'estimations. 

Le coût et le prix de vente pour chaque ligne d'estimation de travail ou de dépenses sont basées sur le paramétrage défini pour chaque catégorie dans les tables de tarification dans **Gestion de projets et comptabilité** &gt; **Paramétrage** &gt; **Tarification**. Pour les articles, le coût et le prix de vente des articles sont ajoutés par défaut à partir des articles ou des accords commerciaux dans la page **Produits lancés** dans le module Gestion des informations sur le produit.

## <a name="tracking-progress-on-the-wbs"></a>Suivi de l'avancement de la WBS
Dans certains secteurs on suit la progression d'un projet avec une WBS à un niveau très granulaire, tandis que dans d'autres on suit la progression à un niveau plus élevé de la WBS. Cette section décrit la manière dont vous pouvez utiliser le suivi de WBS selon les besoins de votre projet. 

Finance comporte trois vues pour la WBS d'un projet : l'affichage Planification, l'affichage Suivi d'effort, et l'affichage Suivi des coûts.

### <a name="planning-view"></a>Affichage Planification

La vue Planification affiche l'estimation prévue ou de référence du programme et les informations de coût. Bien qu'il n'y ait aucune fonctionnalité pour suivre la version et la référence pour une WBS de projet, les valeurs de cette vue sont destinées à représenter la version de référence. Les sections Estimation de planification et Estimation de coût de cette rubrique décrivent cette vue et la manière de l'utiliser pour créer une WBS.

### <a name="effort-tracking-view"></a>Vue de suivi des efforts

La vue Suivi d'effort affiche le suivi de la progression des tâches de la WBS. Elle compare les heures d'effort réellement cumulées pour une tâche aux heures d'effort prévues. Les formules suivantes donnent les valeurs dans la vue Suivi d'effort :

-   Pourcentage de progression = Effort réel à ce jour ÷ Effort prévu de la tâche
-   L'effort restant (également appelé Estimation à terminer \[ETC\], Estimate-to-complete) = Effort prévu – Effort réel à ce jour
-   Estimation à terminer (EAC, Estimate at complete) = Effort restant + Effort réel à ce jour
-   Écart prévu pour l'effort = Effort prévu– EAC

La vue Suivi d'effort affiche une projection de l'écart d'effort pour la tâche, basé sur le fait que l'EAC est supérieur ou inférieur à l'effort prévu :

-   Si l'EAC est supérieur à l'effort prévu, la projection est que la tâche va prendre plus de temps qu'initialement prévu et est en retard sur le programme.
-   Si l'EAC est inférieur à l'effort prévu, la projection est que la tâche va prendre moins de temps qu'initialement prévu et est en avance sur le programme.

**Nouvelle projection d'effort par le chef de projet** Parfois, un chef de projet ou une personne qui suit la progression d'un projet doit modifier les estimations d'origine d'une tâche. La tâche peut avancer plus vite ou plus lentement qu'initialement anticipé pour différentes raisons. Par exemple, son étendue a été réduite, ou les collaborateurs ont moins d'expérience qu'initialement prévu. Les projections sont la perception des estimations par le chef de projet, selon le statut actuel d'un projet. En général vous ne devez pas modifier les chiffres de référence, car une référence de projet représente un document publié pour le programme du projet et l'estimation des coûts qui a été accepté par toutes les parties prenantes du projet. 

Il existe deux méthodes par lesquelles les chefs de projet peuvent modifier l'effort sur les tâches :

-   Modifier l'effort restant qui est automatiquement défini pour mettre à jour l'effort restant réel de la tâche.
-   Modifier le pourcentage de progression qui est automatiquement défini pour mettre à jour la progression réelle de la tâche.

Les deux approches provoquent un nouveau calcul de l'ETC et de l'EAC, du pourcentage de progression et de l'écart d'effort prévu de la tâche. L'EAC, l'ETC et le pourcentage de progression des tâches de synthèse sont également recalculés, et leur écart d'effort prévu est mis à jour. 

**Effort modifié pour des tâches de synthèse** Vous pouvez modifier l'effort pour des tâches de synthèse ou de conteneur. Indépendamment du fait que vous modifiez ces valeurs à l'aide de l'effort restant ou du pourcentage de progression des tâches de synthèse, les calculs se produisent automatiquement dans l'ordre suivant :

1.  L'EAC, l'ETC et le pourcentage de progression de la tâche sont calculés.
2.  Le nouvel EAC est distribué aux tâches enfant dans la même proportion que le montant de l'EAC original.
3.  Le nouvel EAC de chaque tâche de nœud terminal est calculé.
4.  L'effort restant et le pourcentage de progression sont recalculés pour toutes les tâches enfant affectées, selon la nouvelle valeur de l'EAC. L'écart d'effort des tâches est également recalculé.
5.  L'EAC des tâches de synthèse est également recalculé à partir des nœuds terminaux.

Cliquez sur **Développer jusqu'au niveau** dans la vue Suivi d'effort pour définir le niveau auquel suivre et tenir à jour la WBS. La WBS est automatiquement développée à ce niveau dans la vue Suivi d'effort à chaque fois que vous l'ouvrez.

### <a name="cost-tracking-view"></a>Vue de suivi des coûts

La vue Suivi des coûts affiche le suivi de la consommation des coûts pour une tâche. Dans cette vue, le coût réel qui a été dépensé pour une tâche à ce jour est comparé au coût planifié pour la tâche. Les formules suivantes donnent les valeurs dans la vue Suivi des coûts :

-   Pourcentage du coût consommé = Coût réel à ce jour ÷ Coût planifié pour la tâche
-   Coût à terminer (CTC, Cost to complete) = Coût planifié - Coût réel à ce jour
-   Estimation à terminer (EAC, Estimate at complete) = CTC + Coût réel à ce jour
-   Écart de coût prévu = Coût planifié – EAC

La vue Suivi des coûts affiche une projection de l'écart de coût pour la tâche, basé sur le fait que l'EAC est supérieur ou inférieur au coût prévu :

-   Si l'EAC est supérieur au coût prévu, la projection est que la tâche va coûter plus cher qu'initialement prévu et est en dépassement de budget.
-   Si l'EAC est inférieur au coût prévu, la projection est que la tâche va coûter moins cher qu'initialement prévu et est en dessous du budget.

**Nouvelle projection du coût par le chef de projet** Les chefs de projet doivent utiliser le CTC pour réviser l'estimation initiale du coût d'une tâche. Le chef de projet peut modifier la valeur du CTC au coût nécessaire pour terminer la tâche. Si vous modifiez la valeur du CTC, le CTC, l'EAC, le pourcentage du coût consommé et l'écart de coût prévu sur une tâche sont recalculés. L'EAC, l'ETC et le pourcentage de coût consommé des tâches de synthèse sont également recalculés, et leur écart de coût prévu est mis à jour. 

> [!NOTE] 
> Lorsque vous modifiez l'effort pour une tâche de WBS dans la vue Suivi d'effort, le CTC, l'EAC, le pourcentage de coût consommé et l'écart de coût prévu tous sont recalculés dans la vue Suivi des coûts. Toutefois, les révisions de coût n'affectent pas les valeurs de la vue Suivi d'effort, car le coût par type de transaction (salaires, matières ou dépense) ou catégorie de projet n'est pas modifié. 

**Révision de la projection pour les coûts des tâches de synthèse** Vous pouvez réviser les coûts des tâches de synthèse, et les calculs se produisent automatiquement dans l'ordre suivant :

1.  L'EAC, le CTC et le pourcentage de coût consommé de la tâche sont recalculés.
2.  Le nouvel EAC est distribué aux tâches enfant dans la même proportion que le montant de l'EAC des tâches.
3.  Le nouvel EAC est calculé pour chaque tâche.
4.  Le CTC et le pourcentage du coût consommé sont recalculés pour les tâches enfant affectées, selon la valeur de l'EAC. L'écart de coût des tâches est également recalculé.
5.  L'EAC de toutes les tâches de synthèse est recalculé selon cette modification.

Cliquez sur **Développer jusqu'au niveau** dans la vue Suivi des coûts pour définir le niveau auquel suivre et tenir à jour la WBS. La WBS est automatiquement développée à ce niveau dans la vue Suivi des coûts à chaque fois que vous l'ouvrez.

### <a name="earned-value-management"></a>Gestion de la valeur gagnée

Vous pouvez utiliser la méthode EVM (Earned Value Method, méthode de la valeur gagnée) pour suivre la progression d'un projet. Vous pouvez afficher les mesures de la valeur gagnée dans l'aperçu interactif du chef de projet. Le composant graphique de la valeur gagnée indique les valeurs organisées dans le temps de la valeur planifiée et du coût réel. La valeur gagnée à la date du jour est indiquée par un point. Les données organisées dans le temps de la valeur gagnée ne sont actuellement pas disponibles. 

La phase de temps sur le graphique de valeur gagnée est affichée en semaines ou en mois. Cette section décrit les trois piliers de l'EVM : valeur planifiée, valeur gagnée et coût réel. 

**Valeur planifiée** La théorie EVM indique que le graphique de la valeur planifiée représente le taux auquel l'équipe du projet a prévu de gagner de la valeur sur le projet. 

Finance utilise la règle de gain 0:100 pour tracer la valeur planifiée. Avec cette règle, la valeur de la tâche est validée à la tâche à partir de sa date de fin. Aucune valeur n'est validée tant que la tâche n'est pas terminée à 100 %. 

Dans le module gestion de projets et comptabilité, vous entrez la date de fin des nœuds terminaux et leur coût prévu. Lorsque le graphique de la valeur planifiée est affiché par semaine, la valeur planifiée est synthétisée par semaine pour toutes les tâches de nœud terminal pour toute la durée du projet. 

**Valeur gagnée** La théorie EVM indique que le graphique de la valeur gagnée représente le taux auquel l'équipe du projet gagne réellement de la valeur sur le projet. 

Finance utilise la règle de gain 0:100 pour tracer la valeur gagnée. Avec cette règle, la valeur de la tâche est validée à la tâche à partir de sa date de fin. Aucune valeur n'est validée tant que la tâche n'est pas terminée à 100 %. 

Quand la valeur gagnée est calculée, le pourcentage de progression de chaque tâche est pris en compte. Avec la règle de gain 0:100 , seules les tâches terminées dans une période donnée sont prises en compte dans le calcul de la valeur gagnée à la fin de cette période. La valeur gagnée sur le projet est calculée pour toutes les tâches terminées au moment où le graphique est créé. 

> [!NOTE] 
> Actuellement, le système de suivi de la WBS n'a pas de structure de données pour enregistrer l'historique des pourcentages de progression sur chaque tâche. Par conséquent, la valeur gagnée peut être déclarée uniquement à partir du moment où le cube est exécuté. Exécutez le cube régulièrement pour mettre à jour la valeur gagnée qui figure sur l'aperçu interactif. 

**Coût réel** La théorie EVM indique que le tracé du coût réel représente le taux auquel de l'argent est dépensé est en projet. 

Les transactions validées dans un projet sont utilisées pour tracer le coût réel. Les coûts sont synthétisés par date. Ces données sont alors utilisées pour représenter graphiquement les coûts réels par semaine ou par mois dans le graphique de la valeur gagnée.

### <a name="how-to-use-the-concepts-of-planned-value-earned-value-and-actual-cost"></a>Utilisation des concepts de valeur planifiée, valeur gagnée et coût réel

**Écart du programme** Lors de la planification, vous créez une prévision du travail sur une chronologie. Par conséquent, la valeur planifiée est le taux auquel les organisateurs ont imaginé que le travail serait réalisé sur le projet. Une fois qu'un projet a avancé, du travail est terminé et le projet gagne la valeur. En comparant la valeur planifiée à la valeur gagnée, vous pouvez voir comment avance le travail sur un projet. Le résultat de cette comparaison est appelé un écart de programme. 

Si la valeur planifiée pour une période est supérieure à la valeur gagnée, la quantité de travail qui a été effectuée sur un projet est inférieure à ce qui a été planifié. Par conséquent, le projet est en retard. Dans la mesure où la valeur prévue et la valeur gagnée sont exprimées en valeur monétaire, l'écart de temps sur le projet est également donné comme une valeur monétaire. 

Si la valeur planifiée pour une période est inférieure à la valeur gagnée, la quantité de travail qui a été effectuée sur un projet est supérieure à ce qui a été planifié. Par conséquent, le projet est en avance. Cette avance est également donnée comme une valeur monétaire.

**Écart de coût** Dans la mesure où la valeur gagnée utilise le prix de revient comme multiplicateur, la valeur gagnée indique le coût du travail qui est effectué sur un projet. À mesure que le projet progresse, le journal des transactions fournit un enregistrement de l'argent réellement dépensé pour ce projet. En comparant la valeur gagnée au coût réel, vous pouvez afficher la somme d'argent dépensée par rapport à la valeur gagnée. Le résultat de cette comparaison est appelé un écart de coût. 

Si le coût réel dépensé pour une période est supérieur à la valeur gagnée, il a été dépensé plus d'argent qu'il n'en a été gagné. Par conséquent, le projet est en dépassement de budget. 

Si le coût réel dépensé pour une période est inférieur à la valeur gagnée, il a été gagné plus d'argent qu'il n'en a été dépensé. Par conséquent, le projet est en dessous du budget.

## <a name="wbs-templates"></a>Modèles WBS
Utilisez la fonctionnalité des modèles de WBS pour créer des modèles standard pour les projets. Si les projets qu'offre votre société comporte beaucoup de travail reproductible, vous devez envisager de créer un modèle de WBS. 

Vous pouvez créer un modèle de WBS pour la WBS d'un projet existant, de sorte que les connaissances et les bonnes pratiques que vous avez recueillies durant la planification de ce projet puissent être réutilisées à l'avenir sur les projets similaires. Toutefois, il n'est parfois pas judicieux d'enregistrer la WBS entière comme modèle. Par conséquent, vous pouvez également créer des modèles à partir de parties de la WBS d'un projet.

### <a name="saving-a-projects-wbs-as-a-template"></a>Enregistrement de la WBS d'un projet comme modèle

Après avoir créé un modèle, vous pouvez l'importer dans la WBS d'un nouveau projet sous le nœud racine, ou sous n'importe quelle tâche de la WBS du projet.

### <a name="importing-a-wbs-template-into-a-projects-wbs"></a>Importation d'un modèle de WBS dans la WBS d'un projet

Lorsque vous importez des tâches, les tâches du modèle sont organisées en fonction de la date de début de la tâche sous laquelle elles sont importées. Pendant l'importation, les relations de prédécesseur des tâches du modèle sont utilisées pour calculer les dates de début des tâches importées. Le calendrier de travail standard du projet de destination est appliqué pour calculer les dates de fin des tâches importées, de sorte que les jours ouvrables et les heures de travail standard définis dans le calendrier de travail du projet actuel sont conservés. 

Les coûts et les prix de vente sur les lignes d'estimation sont appliqués pour garantir que les prix spécifiques au projet ou au contrat de projet ont des dates valides.

### <a name="differences-between-a-projects-wbs-and-a-wbs-template"></a>Différences entre la WBS d'un projet et un modèle de WBS

-   Les tâches dans les modèles de WBS n'ont pas de dates de début et de fin.

Les jours ouvrables et non-ouvrables ne sont pas définis pour les modèles de WBS.

-   Les modèles de WBS utilisent toujours calendrier de planification paramétré comme calendrier par défaut pour tous les projets.

Le calendrier de planification par défaut est utilisé uniquement pour connaître les heures d'une journée de travail standard.

-   Les relations de prédécesseur ne sont pas copiées dans un modèle de WBS.

Comme les modèles de WBS ne comportent aucune date, la logique de date de début qui est basée sur la date de fin d'un prédécesseur n'est pas nécessaire.

-   Une ligne d'estimation de coût de main-d'œuvre est automatiquement créée lorsqu'une tâche est créée dans un modèle de WBS. Le prix de vente et le coût sont copiés à partir du collaborateur sélectionné.

Les coûts de dépense et d'articles peuvent être créés manuellement, tout comme dans la WBS d'un projet.

-   Des erreurs de planification s'affichent lorsqu'il existe des écarts à partir de la formule suivante :

Effort = Nombre de ressources × Durée × Nombre d'heures dans un jour de travail standard 

Vous pouvez corriger toutes les erreurs de planification en même temps en cliquant sur **Corriger toutes les erreurs de planification**. 

Sinon, vous pouvez corriger les erreurs de planification individuellement en cliquant sur l'icône d'avertissement pour chaque tâche.



