---
title: Présentation de la gestion des fonctionnalités
description: Cette rubrique décrit la fonctionnalité de gestion des fonctionnalités et son utilisation.
author: ChrisGarty
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: IT Pro, Application user
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: ae2c7a0d089c81a62932c415eed5f752e7fb4ffa
ms.sourcegitcommit: 17a8e3d48da4354ba74e35031c320a16369bfcd5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "3499617"
---
# <a name="feature-management-overview"></a>Présentation de la gestion des fonctionnalités

[!include [banner](../../includes/banner.md)]

Les fonctionnalités sont ajoutées et mises à jour dans chaque version. L'expérience de gestion des fonctionnalités fournit un espace de travail dans lequel vous pouvez afficher une liste des fonctionnalités fournies dans chaque version. Par défaut, les nouvelles fonctionnalités sont désactivées. Vous pouvez utiliser l'espace de travail pour les activer et consulter la documentation les concernant.

## <a name="the-feature-management-workspace"></a>L'espace de travail Gestion des fonctionnalités

Vous pouvez ouvrir l'espace de travail **Gestion des fonctionnalités** en sélectionnant la vignette appropriée sur le tableau de bord. Une page s'affichera, indiquant une liste des fonctionnalités pour toutes les versions prises en charge par l'expérience de Gestion des fonctionnalités. Au fil du temps, Microsoft améliorera l'expérience de Gestion des fonctionnalités afin qu'elle comprenne des fonctionnalités supplémentaires pour vous aider à gérer les fonctionnalités.

La liste des fonctionnalités inclut les informations suivantes :

- **Nom de fonctionnalité** – Description de la fonctionnalité ajoutée.
- **Statut Activé** – Un symbole indique si une fonctionnalité a été activée (coche), n'a pas été activée (vide), est planifiée pour être activée (horloge), ou est obligatoirement activée (verrou), nécessite votre attention avant de l'activer (avertissement) ou ne peut pas être activée (X). Le paramètre affiché est utilisé pour toutes les entités juridiques. Notez que même si une fonctionnalité a été activée, elle est toujours contrôlée par la sécurité. Par conséquent, la fonctionnalité est disponible uniquement aux utilisateurs qui ont accès à celle-ci, selon son rôle de sécurité. Elle n'est également disponible que dans les entités juridiques auxquelles l'utilisateur a accès.
- **Activer la date** – Date à laquelle la fonctionnalité a été activée ou est planifiée pour être activée.
- **Fonctionnalité ajoutée** – Date à laquelle la fonctionnalité a été ajoutée à votre environnement. Cette date est entrée automatiquement lorsque vous mettez votre environnement à jour lors des cycles de version mensuels.
- **Module** – Module affecté par la nouvelle fonctionnalité.

Lorsque vous sélectionnez une fonctionnalité, les informations supplémentaires apparaissent dans le volet des détails à droite de la liste de fonctionnalités. En haut du volet, vous verrez le nom de fonctionnalité, la date à laquelle elle a été ajoutée, le module affecté par celle-ci, et un lien **En savoir plus**. Sélectionnez ce lien pour afficher la documentation pour la fonctionnalité. Si la documentation n'est pas disponible, vous êtes dirigé vers une page temporaire. Le volet des détails inclut également un champ **Commentaires** dans lequel vous pouvez ajouter vos propres commentaires sur la fonctionnalité.

L'espace de travail **Gestion des fonctionnalités** dispose également de plusieurs onglets, chacun desquels affiche une liste des fonctionnalités.

- **Nouveau** – Cet onglet affiche toutes les fonctionnalités qui ont été ajoutées depuis la dernière mise à jour mensuelle. Si vous avez ignoré des mises à jour mensuelles, l'onglet affiche toutes les nouvelles fonctionnalités ajoutées depuis la dernière fois que vous avez effectué une mise à jour. Les fonctionnalités les plus récentes s'affichent en haut de la liste. Le nombre total des nouvelles fonctionnalités s'affiche également sur une vignette en haut de la page.
- **Non activé** – Cet onglet affiche toutes les fonctionnalités qui n'ont pas été activées. Les fonctionnalités les plus récentes s'affichent en haut de la liste. Le nombre total des nouvelles fonctionnalités qui n'ont pas été activées s'affiche également sur une vignette en haut de la page.
- **Planifié** – Cet onglet affiche toutes les fonctionnalités qui ont été planifiées pour être activées à l'avenir. Les fonctionnalités qui ont la date planifiée la plus proche apparaissent en haut de la liste. Le nombre total des nouvelles fonctionnalités planifiées s'affiche également sur une vignette en haut de la page.
- **Tous** – Cet onglet affiche toutes les fonctionnalités. Les fonctionnalités les plus récentes s'affichent en haut de la liste.

## <a name="turn-on-a-feature"></a>Activer une fonctionnalité

Si une fonctionnalité n'a pas été activée, un bouton **Activer maintenant** s'affiche dans le volet des détails. Vous pouvez utiliser ce bouton pour activer la fonctionnalité.

- Sélectionnez la fonctionnalité à activer, puis, dans le volet des détails, sélectionnez **Activer maintenant**. La fonctionnalité est activée.

Certaines fonctionnalités ne peuvent pas être désactivées après avoir été activées. Si la fonctionnalité que vous essayez d'activer ne peut pas être désactivée, vous recevez un avertissement. À ce stade, vous pouvez sélectionner **Annuler** pour annuler l'opération et laisser la fonctionnalité désactivée. Toutefois, si vous sélectionnez **Activer** pour activer la fonctionnalité, vous ne pourrez pas la désactiver ultérieurement.

Certaines fonctionnalités affichent un message qui fournit des informations supplémentaires avant de les activer. Ces fonctionnalités sont indiquées par un symbole d'avertissement jaune. Vous devez lire les informations supplémentaires soigneusement afin de mieux comprendre ce qui se produit quand la fonctionnalité est activée. Toutefois, vous pouvez toujours sélectionner **Activer** pour activer la fonctionnalité.

Certaines fonctionnalités affichent un message indiquant que la fonctionnalité ne peut pas être activée avant qu'une action soit effectuée. Ces fonctionnalités sont indiquées par un symbole X rouge. Vous devez effectuer les actions décrites dans la description avant que la fonctionnalité soit activée. Par exemple, si vous ne pouvez pas utiliser une fonctionnalité tant qu'une clé de configuration n'est pas désactivée, vous devez désactiver la clé de configuration, puis revenir à la gestion des fonctionnalités pour activer la fonctionnalité.

Une fois une fonctionnalité activée, un message apparaît sous du lien **En savoir plus** dans le volet des détails. Ce message indique que la fonctionnalité a été activée ou indique la date future à laquelle la fonctionnalité est prévue pour être activée. Il s'affiche chaque fois que vous sélectionnez la fonctionnalité dans la liste des fonctionnalités.

Les fonctionnalités prévues pour être activées à l'avenir apparaissent sur l'onglet **Planifié**. Un processus de traitement par lots les activera à minuit à la date spécifiée, selon le fuseau horaire représenté par la date système.

## <a name="reschedule-a-feature"></a>Replanifier une fonctionnalité

Si une fonctionnalité a été prévue pour être activée dans le futur, un bouton **Planifier** s'affiche dans le volet des détails. Vous pouvez utiliser ce bouton pour modifier la valeur **Date d'activation** à une date différente.

1. Sélectionnez la fonctionnalité planifiée à replanifier, puis, dans le volet des détails, sélectionnez **Planifier**.
2. Dans la boîte de dialogue qui s'affiche, dans le champ **Date d'activation**, spécifiez la nouvelle date à laquelle la fonctionnalité doit être activée.
3. Sélectionnez **Activer** pour replanifier la fonctionnalité ou **Désactiver** pour annuler la planification.

## <a name="turn-off-a-feature"></a>Désactiver une fonctionnalité

Si une fonctionnalité a déjà été activée, un bouton **Désactiver** s'affiche dans le volet des détails. Vous pouvez utiliser ce bouton pour désactiver la fonctionnalité. Le bouton **Désactiver** n'est pas disponible si la fonctionnalité ne peut pas être désactivée une fois activée.

- Sélectionnez la fonctionnalité à désactiver, puis, dans le volet des détails, sélectionnez **Désactiver**. La fonction est désactivée, et le champ **Date d'activation** est supprimé.

Une fois une fonctionnalité désactivée, un message apparaît sous du lien **En savoir plus** dans le volet des détails. Ce message indique que la fonctionnalité n'a pas encore été activée. Il s'affiche chaque fois que vous sélectionnez la fonctionnalité dans la liste des fonctionnalités. Les fonctionnalités qui n'ont pas été activées s'affichent sous l'onglet **Non activé**.

## <a name="features-that-must-be-turned-on"></a>Fonctionnalités à activer

Parfois, une fonctionnalité essentielle est fournie qui doit être activée automatiquement lors de la mise à jour. Ces fonctions sont activées automatiquement à la date spécifiée dans le champ **Date d'activation**. Pour ces fonctionnalités, un message apparaît sous du lien **En savoir plus** dans le volet des détails. Ce message indique que la fonctionnalité a été activée ou indique la date future à laquelle la fonctionnalité sera activée. Il s'affiche chaque fois que vous sélectionnez la fonctionnalité dans la liste des fonctionnalités.

## <a name="enable-all-features"></a>Activer toutes les fonctionnalités

Par défaut, toutes les fonctionnalités ajoutées à votre environnement sont désactivées. Vous pouvez activer toutes les fonctionnalités en sélectionnant le bouton **Activer tout**. 

Lorsque vous sélectionnez **Activer tout**, une option s'affiche dans laquelle vous devez entrer les informations suivantes :
- Une liste de toutes les fonctionnalités ce qui nécessitent une confirmation pour pouvoir être activées. Si vous souhaitez activer les fonctionnalités de la liste, sélectionnez **Oui** pour le bouton **Activer les fonctionnalités nécessitant une confirmation**.
- Une liste de toutes les fonctionnalités qui ne peuvent pas être activées s'affiche. Ces fonctionnalités ne sont pas activées.

Toutes les fonctionnalités pouvant être activées sont activées. Si une fonctionnalité est déjà planifiée pour être activée dans le futur, le programme ne change pas. 

## <a name="turn-on-all-features-automatically"></a>Activer toutes les fonctionnalités automatiquement

Par défaut, toutes les fonctionnalités ajoutées à votre environnement sont désactivées, à moins qu'elles soient obligatoires. Cependant, si vous souhaitez activer automatiquement toutes les nouvelles fonctionnalités, vous pouvez utiliser la liste déroulante sous le titre de l'espace de travail pour modifier ce qui se produit lorsque de nouvelles fonctionnalités sont ajoutées.

- Sélectionnez **Activer les nouvelles fonctionnalités automatiquement** pour activer automatiquement toutes les nouvelles fonctionnalités lorsqu'elles sont ajoutées à votre environnement.
- Sélectionnez **Ne pas activer les nouvelles fonctionnalités automatiquement** pour désactiver toutes les nouvelles fonctionnalités lorsqu'elles sont ajoutées à votre environnement.


Lorsque vous activez toutes les fonctionnalités automatiquement, cela active toutes les fonctionnalités qui sont activées lorsque vous cliquez sur le bouton **Activer tout**. Cela n'active pas les fonctionnalités qui nécessitent une confirmation ou les fonctionnalités qui ne peut pas être activées tant qu'aucune action n'est effectuée.

## <a name="check-for-updates"></a>Rechercher des mises à jour

Les fonctionnalités sont ajoutées à votre environnement après chaque mise à jour. Toutefois, vous pouvez rechercher manuellement les mises à jour en cliquant sur le bouton **Rechercher des mises à jour**. Toute fonctionnalité ajoutée au système après la mise à jour est ajoutée à la liste de fonctionnalités. Par exemple, si une fonction en version d'évaluation est activée après sa sortie, vous pouvez vérifier les mises à jour et la fonctionnalité est ajouté à la liste.

## <a name="assigning-roles"></a>Attribution de rôles

L'espace de travail **Gestion des fonctionnalités** peut être ouvert par les administrateurs système, ainsi que par les utilisateurs auxquels des rôles de Gestionnaire de fonctionnalités ou de Visionneuse de fonctionnalité ont été attribués. Ces deux rôles ont été créés pour prendre en charge l'expérience Gestion des fonctionnalités. Les utilisateurs ayant le rôle de Gestionnaire de fonctionnalités peuvent activer ou désactiver n'importe quelle fonctionnalité. Ils peuvent également mettre à jour le champ **Commentaires** de la fonctionnalité. Les utilisateurs ayant le rôle de Visionneuse de fonctionnalité peuvent uniquement consulter l'espace de travail **Gestion des fonctionnalités**. Ils ne peuvent pas activer ou désactiver des fonctionnalités.

Le rôle de Gestionnaire de fonctionnalités et rôle de Visionneuse de fonctionnalité ne remplacent pas la sécurité existante dont un utilisateur dispose. Ils contrôlent seulement si l'utilisateur peut faire activer et désactiver des fonctionnalités. Ils ne fournissent pas d'accès aux fonctionnalités elles-mêmes.

## <a name="features-that-use-configuration-keys"></a>Fonctionnalités qui utilisent des clés de configuration

Si une fonctionnalité utilise une clé de configuration, mais que la clé de configuration n'est pas activée, l'espace de travail **Gestion des fonctionnalités** n'affiche pas la fonctionnalité dans la liste des fonctionnalités disponibles. Après avoir activé la clé de configuration, vous devez mettre à jour la liste des fonctionnalités à l'aide de l'option de menu **Rechercher une mise à jour**. La fonctionnalité apparaît ensuite dans la liste des fonctionnalités.

Si vous désactivez la clé de configuration, la fonctionnalité n'est pas supprimée de la liste des fonctionnalités.

## <a name="data-entities"></a>Entités de données

Une entité de données appelée **Gestion des fonctionnalités** vous permet d'exporter les paramètres de Gestion des fonctionnalités depuis un environnement puis de les importer dans un autre environnement. Cette entité met à jour uniquement les fonctionnalités existantes. La logique métier de l'entité permet également de garantir que les mêmes règles que celles utilisées dans l'espace de travail **Gestion des fonctionnalités** seront appliquées une fois l'importation terminée. Par exemple, vous ne pouvez pas remplacer un paramètre de fonctionnalité obligatoire en supprimant la date lors de l'importation.

Les exemples suivants décrivent ce qui se produit lorsque vous utilisez l'entité **Gestion des fonctionnalités** pour importer des données.

- Si vous modifiez la valeur du champ **Activé** sur **Oui**, la fonctionnalité est activée, et le champ **Date d'activation** est défini sur la date actuelle.
- Si vous modifiez la valeur du champ **Activé** sur **Non** ou que vous laissez le champ **EnableDate** vide, la fonctionnalité est désactivée, et le champ **Date d'activation** est supprimé. Vous ne pouvez pas désactiver une fonctionnalité obligatoire ou une fonctionnalité qui ne peut pas être désactivée après avoir été activée.
- Si vous modifiez la valeur du champ **EnableDate** à une date ultérieure, la fonctionnalité est prévue pour cette date.
- Si vous modifiez la valeur du champ **Activé** sur **Oui** et que vous modifiez la valeur du champ **EnableDate** à une date future, la fonctionnalité est prévue à cette date. 
- Si vous modifiez la valeur du champ **Activé** sur **Non** mais que vous également modifiez la valeur du champ **EnableDate** à une date future, la fonctionnalité est prévue à cette date.
- Si une fonctionnalité est activée, et que vous ajoutez un champ **EnableDate** défini sur une date ultérieure, la fonctionnalité reste activée. Pour replanifier la fonctionnalité, vous devez modifier le champ **Activé** sur **Non**.

## <a name="feature-management-and-flighting"></a>Gestion des fonctionnalités et distribution de version d'évaluation

La Gestion des fonctionnalités vous permet de contrôler les fonctionnalités qui sont fournies dans chaque version. La distribution de version d'évaluation permet à Microsoft Teams de fournir des fonctionnalités à un nombre limité de clients, afin que celles-ci puissent être testées et validées sans affecter tous les clients. La Gestion des fonctionnalités ne contrôle pas la distribution de version d'évaluation des fonctionnalités.

## <a name="new-features-are-optional-for-12-months"></a>Les nouvelles fonctionnalités sont facultatives pendant 12 mois

Lorsqu'une nouvelle fonctionnalité non critique est installée, elle sera facultative pour une période de 12 mois. Ainsi, vous et votre organisation, avez le temps de planifier à l'avance quand utiliser une fonctionnalité et la tester sur vos opérations quotidiennes. Pour plus d'informations, voir [FAQ sur les mises à jour de service One Version](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/one-version#what-about-new-features).

## <a name="using-feature-management-to-turn-on-isv-features-or-custom-features"></a>Utilisation de la Gestion des fonctionnalités pour activer des fonctionnalités de fournisseur de logiciels indépendant ou des fonctions personnalisées

La gestion des fonctionnalités n'est actuellement pas disponible pour les fonctionnalités des éditeurs de logiciels indépendants (ISV) et les fonctionnalités personnalisées. Toutefois, Microsoft ajoute des fonctionnalités supplémentaires pour améliorer la Gestion des fonctionnalités. Une fois ces améliorations terminées, Microsoft rendra la Gestion des fonctionnalités disponible pour toutes les fonctionnalités et fournira des instructions pour la mise à jour de vos fonctionnalités à utiliser.

## <a name="frequently-asked-questions-faq"></a>Forum aux questions (FAQ)

### <a name="when-are-features-added-removed-or-changed"></a>Quand les fonctionnalités sont-elles ajoutées, supprimées ou modifiées ? 
Les fonctionnalités sont ajoutées, supprimées et modifiées par des modifications de code. Les environnements doivent être mis à jour pour recevoir ces modifications.

### <a name="does-a-feature-become-mandatory-automatically"></a>Une fonctionnalité devient-elle obligatoire automatiquement ? 
Non, une fonctionnalité devenue obligatoire n'est pas une action automatique. Les équipes produit doivent effectuer un changement de code.

### <a name="when-do-features-become-mandatory"></a>Quand les fonctionnalités deviennent-elles obligatoires ? 
La stratégie est que toutes les nouvelles fonctionnalités seront activées pour une période de 12 mois et ne nécessiteront aucune gestion des modifications jusqu'à ce que vous activiez la fonctionnalité. Les équipes de produits peuvent choisir de rendre une fonctionnalité obligatoire après la fin de cette période. 

### <a name="why-isnt-there-a-specific-mandatory-enabled-date"></a>Pourquoi n'y a-t-il pas de "date activée obligatoire" spécifique ? 
Le calendrier de publication des mises à jour est variable, le calendrier de mise à jour de l'environnement est variable et les clients peuvent choisir d'ignorer certaines mises à jour. Par conséquent, des dates précises sont difficiles à déterminer. 

### <a name="wheres-the-documentation-for-features-that-are-being-made-mandatory"></a>Où se trouve la documentation des fonctionnalités rendues obligatoires ? 
Cette documentation provient des équipes d'application. Souvent, ceux-ci seront mentionnés dans [Fonctionnalités supprimées ou obsolètes](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features). 

### <a name="is-there-an-in-product-notification-or-signal-that-a-feature-is-going-to-be-mandatory-enabled"></a>Y a-t-il une notification ou un signal dans le produit qu'une fonctionnalité va être activée de manière obligatoire ? 
Il n'existe pas aujourd'hui de mécanisme de notification pour rendre obligatoire une fonctionnalité.

### <a name="do-features-ever-get-enabled-without-the-customer-knowing-about-it"></a>Les fonctionnalités sont-elles jamais activées à l'insu du client ? 
Oui, si les fonctionnalités n'ont pas d'impact fonctionnel, elles peuvent être activées par défaut.

### <a name="what-is-feature-flighting-and-how-does-it-relate-to-feature-management"></a>Qu'est-ce que le vol de fonctionnalités et comment est-il lié à la gestion des fonctionnalités ? 
Les vols de fonctionnalités sont des commutateurs marche/arrêt en temps réel que Microsoft contrôle. Ils sont distincts du contrôle client fourni par la gestion des fonctionnalités. 
- Les fonctionnalités de préversion privée ne seront pas répertoriées dans la gestion des fonctionnalités tant qu'elles ne seront pas activées. En production, le client doit accepter de faire partie d'un programme spécial pour que cela se produise.
- Les fonctionnalités de prévisualisation publique et publiées (généralement disponibles) seront répertoriées dans la gestion des fonctionnalités, sauf si elles sont désactivées. La désactivation d'une fonctionnalité est considérée comme une option de dernier recours pour les équipes de produits si un problème critique est détecté et serait généralement une opération par client.

### <a name="do-features-ever-get-flighted-off-without-the-customer-knowing-about-it"></a>Les fonctionnalités sont-elles jamais désactivées à l'insu du client ? 
Oui, si une fonctionnalité a un impact sur le fonctionnement d'un environnement qui n'a pas d'impact fonctionnel, elle peut être activée par défaut.
