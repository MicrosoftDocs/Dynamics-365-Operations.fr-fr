---
title: Répartition des vagues
description: Cette rubrique décrit comment configurer l’étape de répartition d’une vague, y compris l’activation du traitement parallèle pour celle-ci.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 527bd24d7f2e9a05f6e617c222005186520f9968
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103786"
---
# <a name="wave-allocation"></a>Répartition des vagues

[!include [banner](../includes/banner.md)]

Le traitement des vagues peut prendre du temps et la majeure partie du temps de traitement est consacrée à l’étape de répartition et à l’étape de création du travail.

Il est maintenant possible d’exécuter chacune de ces étapes en parallèle, ce qui peut améliorer les performances du traitement des vagues et permettre un plus grand débit de vagues dans le même entrepôt. Cette rubrique explique comment configurer la méthode de répartition des vagues pour qu’elle s’exécute en parallèle. Pour plus d’informations sur la configuration de la création de travaux pour qu’elle s’exécute en parallèle, voir [Planifier la création du travail pendant la vague](configure-wave-schedule-work-creation.md).

Auparavant, il n’était possible d’allouer qu’une seule vague à la fois dans un entrepôt. Cette contrainte a été supprimée et remplacée par une nouvelle contrainte qui verrouille uniquement l’article et les dimensions qui se trouvent au-dessus de l’emplacement dans la hiérarchie de réservation. Les dimensions au-dessus de l’emplacement incluent toujours les dimensions du produit. Par exemple, si un article est configuré à l’aide de la *Couleur*, alors les variantes *Rouge*, *Bleu* et *Jaune* peuvent être chacune traitée en parallèle.

Cela signifie que si le même article avec les mêmes dimensions au-dessus de l’emplacement est en cours de répartition par une vague, d’autres vagues devront attendre pour acquérir un verrou sur le même article et les mêmes dimensions. S’il n’est pas possible d’acquérir le verrou en temps opportun, une erreur se produira et le traitement de la vague échouera.

Afin d’utiliser le traitement en parallèle, la vague doit être exécutée dans un traitement par lots.

## <a name="performance-improvements"></a>Améliorations des performances

Les avantages en termes de performances du traitement en parallèle se répartissent en deux catégories :

- **Amélioration du débit** : le débit des vagues s’améliorera généralement, même si le traitement parallèle n’est pas configuré, en particulier pour les scénarios où il n’y a pas de chevauchement des articles dans les vagues.
- **Amélioration de la répartition pour une seule vague** : les tests effectués sur les données clients ont montré une amélioration des performances de près de 50 % après le passage à la répartition en parallèle. Le traitement en parallèle est effectué sur les articles et les dimensions au-dessus de l’emplacement, de sorte que les améliorations dépendent du nombre d’articles différents contenus dans une vague, de l’infrastructure disponible et de la durée de la répartition par rapport à la durée de la création du travail.

## <a name="configure-parallel-allocation"></a>Configuration de la répartition en parallèle

### <a name="warehouse-management-parameters"></a>Paramètres de gestion des entrepôts

Pour utiliser le traitement de la répartition en parallèle, accédez à **Gestion d’entrepôt > Configuration > Paramètres de gestion d’entrepôt**, ouvrez l’onglet **Traitement des vagues** et définissez les paramètres suivants :

- **Groupe de traitements par lots pour le traitement de la vague** : sélectionnez le groupe de traitement par lots que le traitement initial des vagues doit utiliser. Le traitement ultérieur de la répartition peut être effectué à l’aide de différents groupes de traitement par lots.
- **Traiter les vagues dans des traitements par lots** : réglez cette option sur *Oui* pour utiliser le traitement en parallèle.
- **Attendre le verrouillage (ms)**  : permet d’entrer le temps, exprimé en millisecondes, pendant lequel une étape de répartition attendra une ressource système qui est verrouillée par une autre étape de répartition. Lorsque ce temps est dépassé, la vague n’est pas traitée et un message d’erreur s’affiche. Nous vous recommandons d’attendre au moins quelques secondes pour permettre d’achever la répartition d’une unité logique.

Pour plus d’informations sur ces options de traitement de vague et d’autres options de la page **Paramètres de gestion d’entrepôt**, voir [Paramètres d’entrepôt pour le traitement des vagues](wave-warehouse-parameters.md).

## <a name="wave-process-methods"></a>Méthodes de traitement de la vague

Pour configurer le traitement en parallèle :

1. Accédez à **Gestion des entrepôts > Paramétrage > Vagues > Méthodes de traitement de la vague**.
1. Sélectionnez la méthode `allocateWave` dans la grille.
1. Dans le volet Actions, sélectionnez **Configuration de tâche**.
1. La page **Configuration de la tâche de la méthode de validation de vague** s’ouvre. Cette grille répertorie chaque entrepôt dans lequel vous avez configuré la méthode `allocateWave`. Le traitement en parallèle ne sera utilisé que pour les entrepôts répertoriés. Utilisez les boutons du volet Actions pour ajouter ou supprimer des entrepôts dans la grille, selon vos besoins. 
1. Pour chaque entrepôt, définissez les paramètres suivants :
    - **Nombre maximum de tâches de traitement par lots** : indiquez le nombre de tâches de traitement par lots à utiliser pour la répartition pour l’entrepôt sélectionné. Le nombre optimal de tâches de traitement par lots dépend de l’infrastructure disponible et des autres traitements par lots en cours d’exécution sur le serveur. Les tests effectués sur un environnement à quatre cœurs dédié au traitement des vagues ont montré que l’utilisation de huit tâches produisait de bons résultats.
    - **Groupe de traitements par lots pour le traitement de la vague** : des groupes de traitements par lots spécifiques peuvent être utilisés pour différents entrepôts pour permettre de dimensionner pour chaque entrepôt le traitement de la répartition.

## <a name="enable-or-disable-parallelization-across-all-legal-entities"></a>Activer ou désactiver la parallélisation sur toutes les entités juridiques

Nous vous recommandons de définir la méthode `allocateWave` pour qu’elle s’exécute en parallèle sur toutes les entités juridiques, car cela contribue à améliorer les performances du traitement des vagues. À partir de la version 10.0.17 de Supply Chain Management, la fonctionnalité *Parallélisation des vagues pour la méthode Allocate Wave* est activée par défaut pour toutes les installations nouvelles et mises à jour, et ne peut pas être désactivée. Après avoir activé cette fonctionnalité, les événements suivants se produisent :

- La méthode `allocateWave` est mise à jour pour inclure un paramètre de configuration de tâche qui vous permet d’utiliser la page **Méthodes de traitement des vagues** pour définir le nombre de tâches qui s’exécuteront simultanément, équivalent au nombre de processus parallèles. En conséquence, le temps utilisé sur l’étape de répartition de vague (qui est généralement de 30 % à 60 % du temps de traitement total) est réduit d’un facteur à peu près équivalent au nombre de tâches. Il est également possible de sélectionner le traitement par lots qui sera affecté au traitement de ces tâches. Il est important de noter que toutes vos entités juridiques seront configurées pour traiter les vagues par lots. Pour les entrepôts déjà configurés pour traiter les vagues par lots, et pour les entrepôts déjà configurés pour utiliser la méthode `allocateWave` en parallèle, la configuration existante sera conservée.
- Par défaut, toutes les nouvelles entités juridiques sont configurées pour traiter les vagues en par lots. Tous les nouveaux entrepôts où l’option **Processus de gestion des entrepôts** est activée aura la méthode `allocateWave` configurée pour s’exécuter en parallèle, par défaut.
- Sur la page **Paramètres de gestion d’entrepôt**, l’option **Processus enregistrés par lots** est définie sur *Oui* et l’option **Attendre le verrouillage (ms)** est définie sur la valeur par défaut de 15 secondes. Cela signifie que toutes les vagues seront exécutées par lots. Lorsqu’une vague est en cours, elle applique un verrou sur l’article et les dimensions au-dessus de l’emplacement pendant l’étape de répartition. Si une autre tâche de traitement de vagues tente d’acquérir le même verrou pour l’enregistrement identique, elle est bloquée jusqu’à ce que le processus en cours soit terminé. Le paramètre **Attendre le verrouillage (ms)** définit la durée maximale pendant laquelle le système attendra avant que le verrou ne soit relâché.

Le traitement en parallèle de la répartition implique de exécuter en traitement par lots le traitement des vagues. Par conséquent, vous réduirez vos performances de traitement des vagues si vous désactivez le paramètre **Processus enregistrés par lots**, en particulier si le traitement de la vague utilise un processus parallèle tel que défini par la configuration de la tâche pour les méthodes de traitement de vague pertinentes.

Si nécessaire, vous pouvez annuler chacun des paramètres définis par défaut lorsque la fonctionnalité *Parallélisation des vagues pour la méthode Allocate Wave* est automatiquement activée pour votre instance. Pour ce faire :

- Accédez à **Gestion des entrepôts \> Paramétrage \> Paramètres de gestion des entrepôts**. Sur l’onglet **Traitement des vagues**, appliquez vos valeurs préférées pour **Traiter les vagues par lots** et **Attendre le verrouillage (ms)**.
- Accédez à **Gestion des entrepôts \> Paramétrage \> Vagues \> Méthodes de traitement de la vague**. Sélectionnez la méthode `allocateWave`. Dans le volet Actions, sélectionnez **Configuration des tâches** pour ouvrir une page qui répertorie chaque entrepôt où la méthode est définie pour s’exécuter en parallèle. Modifiez ou supprimez le nombre de tâches de traitement par lots et le groupe de vagues affecté pour chaque entrepôt répertorié, selon vos besoins.

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="troubleshoot-using-the-infolog"></a>Résolution des problèmes à l’aide du fichier Infolog

Étant donné que la structure de traitement par lots est utilisée, les erreurs qui se produisent pendant le traitement des vagues seront capturées dans les fichiers Infolog des traitements par lots. Pour lire les traitements par lots associés à une vague :

1. Accédez à **Gestion des entrepôts \> Vagues sortantes \> Vagues de l’expédition \> Tous les vagues**.
1. Sélectionnez la vague que vous souhaitez inspecter.
1. Dans le volet Action, ouvrez l’onglet **Vague** et, dans le groupe **Vague**, sélectionnez **Traitements par lots**.

Le traitement de vague est auto-correcteur, donc toute erreur détectée pendant le traitement doit être signalée à l’aide du fichier Infolog.

Une erreur typique du traitement en parallèle correspond au fait que deux vagues tentent de répartir le même article en même temps, et que l’une ne se termine pas, de sorte que l’autre vague est incapable d’acquérir un verrou dans le délai spécifié. Si cette situation se produit, le journal des traitements par lots contiendra des informations indiquant que le verrou n’a pas pu être acquis sur l’article, auquel cas la vague qui a échoué doit être traitée à nouveau.

Étant donné que le traitement se déroule en parallèle, les données doivent être conservées dans différentes tables pour suivre l’état du traitement. Cela signifie que les journaux des traitements par lots peuvent contenir des erreurs telles que des erreurs de doublon de clé.

Les erreurs des tâches de traitement par lots font également partie du journal des traitements par lots. Les informations les plus importantes se trouvent généralement en bas.

Dans de rares cas, par exemple si la connexion SQL a été interrompue, il est possible que le traitement de la vague prenne fin dans un état incohérent où le traitement par lots semble être en cours d’exécution mais où le traitement est arrêté. La vague ne peut pas gérer des erreurs telles que celle-ci. Une tentative de nettoyage des vagues échouées est donc effectuée lorsque la prochaine exécution de vague. Sinon, si la vague actuelle est dans un état incohérent, procédez comme suit :

1. Accédez à **Gestion des entrepôts \> Vagues sortantes \> Vagues de l’expédition \> Tous les vagues**.
1. Sélectionnez la vague que vous devez nettoyer.
1. Dans le volet Action, ouvrez l’onglet **Vague** et, dans le groupe **Vague**, sélectionnez **Nettoyage des données de vague**.

### <a name="troubleshoot-using-the-wave-progress-log"></a>Résolution des problèmes à l’aide du journal de progression de la vague

Si l’option **Créer un journal de progression de la vague** est activée sur la page **Paramètres de gestion d’entrepôt**, un enregistrement de journal est créé à chaque début et fin de la répartition d’un article et de ses dimensions. Vous ne devez activer ce journal que lorsque vous en avez besoin, par exemple, lors des tests initiaux ou pour la résolution des problèmes. Lorsque cette option est activée, vous pouvez afficher le journal en procédant comme suit :

1. Accédez à **Gestion des entrepôts \> Vagues sortantes \> Vagues de l’expédition \> Tous les vagues**.
1. Sélectionnez la vague que vous souhaitez inspecter.
1. Dans le volet Actions, ouvrez l’onglet **Vague** et, dans le groupe **Vague**, sélectionnez **Progression**.
