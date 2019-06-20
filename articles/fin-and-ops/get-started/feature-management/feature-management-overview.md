---
title: Présentation de la gestion des fonctionnalités
description: Cette rubrique décrit la fonctionnalité de gestion des fonctionnalités et son utilisation.
author: mikefalkner
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: IT Pro, Application user
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: b200156a623c67a562cc1a5952899e3a77517528
ms.sourcegitcommit: bbc9aa0d6b94a942e1f4d5b038601509dcc87937
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2019
ms.locfileid: "1619142"
---
# <a name="feature-management-overview"></a>Présentation de la gestion des fonctionnalités

[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

Les fonctionnalités sont ajoutées et mises à jour dans chaque version de Microsoft Dynamics 365 for Finance and Operations. L'expérience de gestion des fonctionnalités fournit un espace de travail dans lequel vous pouvez afficher une liste des fonctionnalités fournies dans chaque version. Par défaut, les nouvelles fonctionnalités sont désactivées. Vous pouvez utiliser l'espace de travail pour les activer et consulter la documentation les concernant.

## <a name="the-feature-management-workspace"></a>L'espace de travail Gestion des fonctionnalités

Vous pouvez ouvrir l'espace de travail **Gestion des fonctionnalités** en sélectionnant la vignette appropriée sur le tableau de bord. Une page s'affichera, indiquant une liste des fonctionnalités pour toutes les versions prises en charge par l'expérience de Gestion des fonctionnalités. Au fil du temps, Microsoft améliorera l'expérience de Gestion des fonctionnalités afin qu'elle comprenne des fonctionnalités supplémentaires pour vous aider à gérer les fonctionnalités.

La liste des fonctionnalités inclut les informations suivantes :

- **Nom de fonctionnalité** – Description de la fonctionnalité ajoutée.
- **Statut Activé** – Un symbole indique si une fonctionnalité a été activée (coche), n'a pas été activée (vide), est planifiée pour être activée (horloge), ou est obligatoirement activée (verrou). Le paramètre affiché ici est utilisé pour toutes les entités juridiques. Notez que même si une fonctionnalité a été activée, elle est toujours contrôlée par la sécurité. Par conséquent, la fonctionnalité est disponible uniquement aux utilisateurs qui ont accès à celle-ci, selon son rôle de sécurité. Elle n'est également disponible que dans les entités juridiques auxquelles l'utilisateur a accès.
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

## <a name="turn-on-all-features-automatically"></a>Activer toutes les fonctionnalités automatiquement

Par défaut, toutes les fonctionnalités ajoutées à votre environnement sont désactivées, à moins qu'elles soient obligatoires. Cependant, si vous souhaitez activer automatiquement toutes les nouvelles fonctionnalités, vous pouvez utiliser la liste déroulante sous le titre de l'espace de travail pour modifier ce qui se produit lorsque de nouvelles fonctionnalités sont ajoutées.

- Sélectionnez **Toutes les nouvelles fonctionnalités seront activées par défaut** pour activer automatiquement toutes les nouvelles fonctionnalités lorsqu'elles sont ajoutées à votre environnement.
- Sélectionnez **Toutes les nouvelles fonctionnalités seront désactivées par défaut** pour désactiver automatiquement toutes les nouvelles fonctionnalités lorsqu'elles sont ajoutées à votre environnement.

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

## <a name="using-feature-management-to-turn-on-isv-features-or-custom-features"></a>Utilisation de la Gestion des fonctionnalités pour activer des fonctionnalités de fournisseur de logiciels indépendant ou des fonctions personnalisées

La gestion des fonctionnalités n'est actuellement pas disponible pour les fonctionnalités des éditeurs de logiciels indépendants (ISV) et les fonctionnalités personnalisées. Toutefois, Microsoft ajoute des fonctionnalités supplémentaires pour améliorer la Gestion des fonctionnalités. Une fois ces améliorations terminées, Microsoft rendra la Gestion des fonctionnalités disponible pour toutes les fonctionnalités et fournira des instructions pour la mise à jour de vos fonctionnalités à utiliser.
