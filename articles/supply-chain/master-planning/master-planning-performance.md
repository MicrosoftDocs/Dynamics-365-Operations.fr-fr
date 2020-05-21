---
title: Améliorer les performances de planification
description: Cette rubrique explique les diverses options vous permettant d'améliorer les performances de la planification ou de résoudre les problèmes.
author: t-benebo
manager: tfehr
ms.date: 12/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-05-31
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: fa8426c3a1f19f8607f45e9ac4d57300abddb161
ms.sourcegitcommit: 68092ed283bfbb7b6f611cce1b62c791f9b6a208
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2020
ms.locfileid: "3323644"
---
# <a name="improve-master-planning-performance"></a>Améliorer les performances de planification

[!include [banner](../includes/banner.md)]

Cette rubrique explique les diverses options vous permettant d'améliorer les performances de la planification ou de résoudre les problèmes. Elle inclut des informations sur les paramètres et sur les configurations et les actions recommandées. Elle contient également un récapitulatif de tous les paramètres importants à prendre en compte lors de la mise en œuvre de planifications à long terme.

Cette rubrique est destinée aux administrateurs système ou aux utilisateurs informaticiens ayant des capacités de résolution de problèmes. Elle est également destinées aux planificateurs de production ou d'approvisionnement, car elle comprend des informations sur les paramètres liés aux exigences de la planification d'entreprise. 

## <a name="parameters-related-to-master-planning-performance"></a>Paramètres associés aux performances de la planification

Différents paramètres influencent le temps d'exécution de la planification et doivent être pris en compte.

### <a name="number-of-threads"></a>Nombre de threads

Le paramètre **Nombre de threads** vous permet d'adapter le processus de calcul PDP/MRP pour qu'il améliore ses performances sur une jeu de données spécifique. Ce paramètre spécifie le nombre total de threads qui seront utilisés pour exécuter la planification. Il entraîne la parallélisation de l'exécution de la planification qui permet de réduire le temps d'exécution. 

Vous pouvez définir le paramètre **Nombre de threads** dans la boîte de dialogue **Exécution de la planification**. Pour ouvrir cette boîte de dialogue, accédez à **Planification \> Planification \> Exécution \> Planification**, ou sélectionnez **Exécuter** dans l'espace de travail **Planification**. Pour déterminer la meilleure valeur pour ce paramètre, vous devez procéder par essai-erreur. Toutefois, vous pouvez utiliser les formules suivantes pour calculer une valeur initiale :

- **Si votre secteur est la fabrication :** (Nombre de threads) = (Nombre d'ordres prévsionnels ÷ 1 000)
- **Sinon :** (Nombre de threads) = (Nombre d'articles ÷ 1 000)

Le nombre d'applications d'assistance utilisées lors de la planification doit être inférieur ou égal au nombre maximal de threads autorisés sur le serveur de traitement par lots. Si le nombre d'applications d'assistance dépasse le nombre de threads sur le serveur de traitement par lots, les threads supplémentaires ne fonctionneront pas.

> [!NOTE]
> La définition du paramètre **Nombre de threads** sur **0** (zéro) augmente le temps d'exécution de la planification. Par conséquent, nous vous recommandons de toujours définir une valeur supérieure à 0.

### <a name="number-of-tasks-in-helper-task-bundle"></a>Nombre de tâches dans l'offre groupée des tâches de l'application d'assistance

En modifiant le paramètre **Nombre de tâches par paquet de tâches** (c'est-à-dire, la taille de paquet), vous pouvez réduire le temps d'exécution. Ce paramètre contrôle le nombre d'articles qui sont planifiés ensemble par une seule application d'assistance.

Vous pouvez définir le paramètre **Nombre de tâches par paquet de tâches** dans la section **Performances** de l'onglet **Général** de la page **Paramètres de planification** (**Planification \> Paramétrage \> Paramètres de Planification**). La meilleure valeur pour ce paramètre dépend de vos données. Par conséquent, il est recommandé de commencer par une valeur **1**, puis de procéder par essai-erreur pour déterminer la meilleure valeur pour votre configuration.

En général, nous recommandons d'augmenter le nombre de tâches lorsque le nombre d'articles est très importante (de l'ordre de la centaine de milliers). Sinon, vous devez réduire le nombre de tâches. Pour les secteurs spécifiques suivants, tenez compte des recommandations suivantes :

- Dans les secteurs de la vente au détail et de la distribution, où il existe de nombreux articles indépendants, utilisez de nombreuses d'applications d'assistance, car il n'existe pas de dépendance entre les articles. 
- Dans le secteur de la fabrication, où il existe de nombreuses nomenclatures (BOM) et des sous-composants partagés, utilisez moins d'applications d'assistance, car les dépendances entre les articles peuvent entraîner des délais d'attente.

> [!TIP]
> Si vous constatez des problèmes de performances, nous vous recommandons de ramener le paramètre **Nombre d'applications d'assistance par paquet de tâches** à **1**. Vous pouvez alors commencer le processus d'essai-erreur pour identifier le meilleur valeur pour votre configuration. En général, les problèmes de performances surviennent lorsqu'un article demande un temps de traitement plus long que les autres. Dans ce cas, vous voyez que deux tâches consécutives ayant le statut **Couverture** dans la planification demandent des durées sensiblement différentes pour s'exécuter. Dans les cas extrêmes, cette différence peut atteindre 30 minutes. Vous pouvez donc déduire la durée d'exécution des tâches en observant la durée de chacune.

### <a name="use-of-cache"></a>Utilisation du cache

Le paramètre **Utilisation du cache** vous permet d'adapter le processus de calcul PDP/MRP pour qu'il ait de meilleurs performances sur une jeu de données spécifique. Par exemple, vous pouvez l'ajuster pour atteindre les résultats suivants :

- Plus la mise en cache est conséquente, plus il y a de données en mémoire. L'attente est que ces données seront utilisées à nouveau ultérieurement. S'il y a des données en mémoire, vous pouvez enregistrer certaines requêtes de base de données. Toutefois, plus la mise en cache est conséquente, plus les besoins de mémoire augmentent.
- Si la mise en cache est moindre, il faut extraire les mêmes données dans la base de données plus fréquemment. En outre, le serveur d'objets d'application (AOS) enregistre peu de données dans la mémoire pendant le processus.

Il est difficile d'anticiper quelle option est préférable, pour chaque cas dépend non seulement des données, mais aussi du matériel. Par exemple, comme une mise en cache moindre entraîne une charge supplémentaire sur le serveur de base de données, il n'est probablement judicieux d'utiliser cette option si votre serveur de base de données est déjà surchargé.

Vous pouvez définir le paramètre **Utilisation du cache** dans la section **Performances** de l'onglet **Général** de la page **Paramètres de planification** (**Planification \> Paramétrage \> Paramètres de Planification**). L'efficacité de la mise en cache dépend fortement des données client. Par exemple, si les données mises en cache ne sont jamais nécessaires, vous gaspillez simplement de la mémoire si vous enregistrez des données jusqu'à la fin du processus de planification. Dans ce cas, si vous configurez une mise en cache moindre, les performances peuvent augmenter, car l'AOS a besoin de moins de mémoire et les ressources du serveur sont libérées pour d'autres tâches.

> [!TIP]
> En général, nous recommandons de définir le paramètre **Utilisation du cache** sur **Maximum**, car ce paramètre est prévu comme facteur d'amélioration des performances. Il est recommandé de définir le paramètre sur **Minimum** si vous exécutez localement et que votre mémoire est limitée (environ 2 gigaoctets \[Go\]).

### <a name="number-of-orders-in-firming-bundle"></a>Nombre de commandes lors de la confirmation de l'offre groupée

Le paramètre **Nombre d'ordres dans le paquet de confirmation** spécifie le nombre total d'ordres qui seront traités à la fois par chaque thread/traitement par lots. Cela entraîne la parallélisation du processus de conformation automatique.

Vous pouvez définir le paramètre **Nombre d'ordres par paquet de confirmation** dans la section **Performances** de l'onglet **Général** de la page **Paramètres de planification** (**Planification \> Paramétrage \> Paramètres de Planification**). La parallélisation du processus de confirmation automatique est basée sur les ordres qui doivent être traités ensemble. Par exemple, si ce paramètre est défini sur **50**, chaque thread ou tâche de traitement par lots prendra 50 ordres à la fois pour les traiter ensemble. Il est recommandé de procéder par essai-erreur pour identifier le meilleur valeur. Toutefois, vous pouvez utiliser la formule suivante pour calculer une valeur initiale :

(Nombre d'ordres par offre groupée) = (Nombre d'articles de la demande ÷ Nombre de threads)

> [!NOTE]
> Si vous définissez le paramètre **Nombre d'ordres par paquet de confirmation** sur **0** (zéro), aucune parallélisation du processus de confirmation automatique ne se produira. Le processus entier sera exécuté sur une seule tâche de traitement par lots et son temps d'exécution sera cumulatif. Par conséquent, le temps d'exécution de votre planification augmentera. Pour cette raison, nous vous recommandons de définir ce paramètre à une valeur supérieure à **0** (zéro).

### <a name="time-fences"></a>Plages de gestion

Les plages de gestion indiquent la durée dans l'avenir des calculs par la planification des divers besoins et autres éléments. Plus la plage de gestion est longue, plus l'exécution de la planification prend du temps. Par conséquent, définissez les plages de gestion selon les besoins de l'entreprise. Pour plus d'informations sur les plages de gestion, voir [Paramétrer une planification](master-planning-setup.md).

### <a name="actions"></a>Actions

Parmi les plages de gestion, vous pouvez également trouver le paramètre **Message d'action**. Le calcul des messages d'action entraîne un temps d'exécution de la planification plus long. Si les messages d'action ne sont pas régulièrement analysés et mis en application (chaque jour, chaque semaine), songez à désactiver leur calcul lors de l'exécution de la planification. Pour désactiver le calcul, dans la page **Plans généraux** (**Planification \> Configuration \> Plans \> Plans généraux**), définissez la plage de gestion **Message d'action** sur **0** (zéro). Assurez-vous également que le paramètre **Message d'action** est désactivé pour tous les groupes de couverture.

### <a name="futures"></a>Perspectives

Le calcul des perspectives entraîne un temps d'exécution de la planification plus long. Si vous ne planifiez pas de nomenclature, ou sil n'est pas nécessaire de propager des retards entre l'approvisionnement et la demande lors de la planification, envisagez de désactiver le calcul des perspectives lors de la planification. Pour désactiver les calculs, définissez la plage de gestion **Perspectives** sur **0** (zéro) pour le plan général que vous exécutez. Assurez-vous également que le paramètre **Perspectives** est désactivé pour tous les groupes de couverture.

## <a name="one-heavy-routine-at-a-time"></a>Une routine lourde à la fois

Lorsque vous programmez la planification, ne programmes aucun autre traitement par lots en même temps. Veillez particulièrement à ne pas programmez d'autre routine lourde en même temps, telles que la clôture du stock.

## <a name="review-the-session-log"></a>Examiner le journal des sessions

Le système peut collecter d'autres informations sur les tâches exécutées durant la planification. Pour que le système collecte ces informations, activez le paramètre **Suivre la durée du traitement** dans la boîte de dialogue **Exécution de planification**. Les informations collectées vous aident à détecter les goulots d'étranglement dans l'exécution. Par exemple, lorsque le paramètre **Nombre de tâches par paquet de tâches de l'application d'assistance** est défini sur **1**, vous pouvez identifier l'article ayant le délai le plus long. Vous pouvez comparer les temps d'exécution pour les différents threads qui ont le statut **Couverture** et comparer la durée pour chaque tâche.

Pour examiner l'exécution de la planification sur votre système, suivez l'une de ces étapes.

- Dans l'espace de travail **Planification**, sélectionnez un plan général dans le champ déroulant, puis, dans la vignette **Planification**, sélectionnez **Historique**. Sélectionnez une tâche, sélectionnez **Recherches** dans l'organisateur, puis sélectionnez **Durée de tâche du processus**.
- Dans la page **Plans généraux**, sélectionnez un plan dans le volet de gauche, puis sélectionnez **Historique** dans l'organisateur. Sélectionnez une tâche, sélectionnez **Recherches** dans l'organisateur, puis sélectionnez **Durée de tâche du processus**.

Lorsque vous parcourez le journal de session, prenez en compte ce qui suit :

- **Mise à jour** ne doit pas durer longtemps (en général, elle doit prendre 30 minutes), toutefois, c'est une tâche à thread unique.
- **Copier un plan** ne doit pas durer longtemps (en général, cela doit prendre 1 minute).
- **Confirmation automatique** prend généralement environ 30 minutes. Toutefois, cette tâche peut prendre plusieurs heures, selon le nombre d'ordres et la complexité des articles.
- **Confirmation automatique** doit prendre moins de temps que **Couverture**.
- **Couverture** doit prendre la durée la plus longue, comparativement au reste.
- **Action** et **Futurs messages** peuvent prendre du temps, selon les données et le nombre de nomenclatures.

## <a name="filtering-of-items"></a>Filtrage des articles

Les filtres appliqués dans la boîte de dialogue **Exécution de la planification** affectent la durée d'exécution de la planification. Accédez à **Planification \> Planification \> Exécution \> Planification**, ou sélectionnez **Exécuter** dans l'espace de travail **Planification**. Pour exclure des articles de l'exécution, nous recommandons de les filtrer par état du cycle de vie (pas par numéro d'article). Lorsque vous filtrez les articles par état du cycle de vie, le processus de mise à jour prend moins de temps que lorsque vous filtrez par numéro d'article.

## <a name="automatically-filter-by-items-with-direct-demand"></a>Filtrer automatiquement par articles à demande directe

Pour améliorer le temps d'exécution de la planification, vous pouvez choisir d'inclure uniquement les articles avec demande directe. Ce filtre ne peut être utilisé que pour un cycle de planification complet sans aucun autre filtre appliqué dans le champ **Enregistrements à inclure**. Un cycle de planification avec des filtres ignorera le paramètre **Filtrer automatiquement par articles avec demande directe**.

Le champ **Filtrer automatiquement par articles avec demande directe** se trouve sur la page **Paramètres de planification** et peut être utilisé avec les paramètres de prétraitement et de post-traitement.

### <a name="pre-processing"></a>Pré-traitement
Le paramètre **Prétraitement : filtrer automatiquement par articles à demande directe** garantit que la phase de prétraitement de la planification inclut uniquement les articles qui remplissent au moins l'une des conditions suivantes :
  - L'article a une réception ou un problème attendu, tel qu'un bon de commande, une commande client, un devis, un ordre de transfert ou un ordre de fabrication. 
  - L'article a une couverture d'articles avec un stock de sécurité (inventaire minimal en stock).
  - La demande prévue pour après aujourd'hui existe pour l'article.
  - L'approvisionnement prévu pour après aujourd'hui existe pour l'article.
  - L'article comprend toutes les lignes de continuité du module de centre d'appels qui n'ont pas encore été créées.

> [!NOTE]
> Un article qui dispose d'un stock physique disponible n'affichera pas de transaction de besoin car il n'y a pas de demande pour l'article.

### <a name="post-processing"></a>Post-traitement
L'option **Post-traitement : filtrer automatiquement par articles à demande directe** n'est pertinente que si vous définissez **Version de nomenclature obligatoire** dans vos groupes de couverture. Sinon, vous n'avez pas besoin d'activer le paramètre. 

Avant le début de l'étape de couverture, il existe une étape de pré-couverture au cours de laquelle les articles avec le paramètre de couverture **Version de nomenclature obligatoire** activé sera retraité. Cette opération permet de garantir la planification des articles de la version de nomenclature obligatoire. Les articles considérés comme ayant une demande lors du prétraitement n'ont plus de demande et doivent donc être exclus du cycle de planification.

## <a name="performance-checklist-summary"></a>Récapitulatif de la liste de contrôle des performances

- **Nombre de threads** – Défini sur une valeur supérieure à **0** (zéro).
- **Nombre de tâches par paquet de tâches de l'application d'assistance** – Défini sur une valeur supérieure à **0** (zéro). (Utilisez les formules données plus haut dans cette rubrique.)
- **Utilisation du cache** – Défini sur **Maximum** à moins que le système ait peu de mémoire.
- **Nombre d'ordres par paquet de confirmation** – Défini sur une valeur supérieure à **0** (zéro). (Utilisez la formule donnée plus haut dans cette rubrique.)
- **Plages de gestion** – Ajustées à votre activité.
- **Actions et perspectives** – Désactivez les actions et les perspectives si vous ne les utilisez pas.
- **Une routine lourde à la fois** – N'exécutez pas la planification simultanément avec aucune autre routine lourde.
- **Examiner le journal des sessions**.
- **Filtrage des articles** – Utilisez l'état de cycle de vie pour exclure des articles de l'exécution de la planification. (N'utilisez pas les numéros d'article.)
