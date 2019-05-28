---
title: Présentation de la gestion des fonctionnalités
description: Cette rubrique décrit la fonctionnalité de gestion des fonctionnalités et son utilisation.
author: mikefalkner
manager: AnnBe
ms.date: 04/18/2019
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
ms.openlocfilehash: e75e42926db22d4fccda86c755b12d9d121a9c0e
ms.sourcegitcommit: be447fc81bc874982bc0185fcb4d87d99bd742c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538687"
---
# <a name="feature-management-overview"></a>Présentation de la gestion des fonctionnalités

[!include[banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

Les fonctionnalités sont ajoutées et mises à jour dans chaque version de Microsoft Dynamics 365 for Finance and Operations. L'expérience de gestion des fonctionnalités fournit un espace de travail dans lequel vous pouvez afficher une liste des fonctionnalités fournies dans chaque version. Par défaut, les nouvelles fonctionnalités sont désactivées. Vous pouvez utiliser l'espace de travail pour les activer et consulter la documentation les concernant.

## <a name="the-feature-management-workspace"></a>L'espace de travail Gestion des fonctionnalités

Vous pouvez ouvrir l'espace de travail **Gestion des fonctionnalités** en sélectionnant la vignette appropriée sur le tableau de bord. Une page s'affichera, indiquant une liste des fonctionnalités pour toutes les versions prises en charge par l'expérience de Gestion des fonctionnalités. Au fil du temps, Microsoft améliorera l'expérience de Gestion des fonctionnalités afin qu'elle comprenne des fonctionnalités supplémentaires pour vous aider à gérer les fonctionnalités.

La liste des fonctionnalités inclut les informations suivantes :

- **Nom de fonctionnalité** – Description de la fonctionnalité ajoutée.
- **Statut Activé** – Un symbole indique si une fonctionnalité a été activée (coche), n'est pas activée (vide), a été planifiée pour être activée (horloge), ou est obligatoirement activée (verrou). Le paramètre affiché ici est utilisé pour toutes les entités juridiques. Notez que même si une fonctionnalité a été activée, elle est toujours contrôlée par la sécurité. Par conséquent, la fonctionnalité est disponible uniquement aux utilisateurs qui ont accès à celle-ci, selon son rôle de sécurité. Elle n'est également disponible que pour les entités juridiques auxquelles l'utilisateur a accès.
- **Date d'activation** – Date à laquelle la fonctionnalité a été activée ou sera activée si la date est ultérieure.
- **Fonctionnalité ajoutée** – Date à laquelle la fonctionnalité a été ajoutée à votre environnement. Cette date est entrée automatiquement lorsque vous mettez votre environnement à jour lors des cycles de version mensuels.
- **Module** – Module affecté par la nouvelle fonctionnalité.

Lorsque vous sélectionnez une fonctionnalité, les informations supplémentaires apparaissent dans le volet des détails à droite de la liste de fonctionnalités. En haut du volet, vous verrez le nom de fonctionnalité, la date à laquelle elle a été ajoutée, le module affecté par celle-ci, et un lien **En savoir plus**. Sélectionnez ce lien pour afficher la documentation pour la fonctionnalité. Si la documentation n'est pas disponible, vous êtes dirigé vers une page temporaire. Le volet des détails inclut également un champ **Commentaires** dans lequel vous pouvez ajouter vos propres commentaires sur la fonctionnalité.

L'espace de travail **Gestion des fonctionnalités** contient également plusieurs onglets avec une liste des fonctionnalités. 
- **Nouveau** - Affiche toutes les fonctionnalités qui ont été ajoutées depuis la dernière mise à jour mensuelle. Si vous avez ignoré des mises à jour mensuelles, il contient toutes les nouvelles fonctionnalités depuis la dernière fois que vous avez effectué une mise à jour. Les fonctionnalités les plus récentes s'affichent en haut de la liste. Le nombre total des nouvelles fonctionnalités s'affiche également dans une vignette en haut de la page.
- **Non activé** - Affiche toutes les fonctionnalités qui n'ont pas été activées. Les fonctionnalités les plus récentes s'affichent en haut de la liste. Le nombre total des nouvelles fonctionnalités s'affiche également dans une vignette en haut de la page.
- **Planifié** - Affiche toutes les fonctionnalités qui ont été planifiées pour être activées à une date ultérieure. Les fonctionnalités qui ont la date planifiée la plus proche apparaissent en haut de la liste. Le nombre total des nouvelles fonctionnalités s'affiche également dans une vignette en haut de la page.
- **Tous** - Affiche toutes les fonctionnalités. Les fonctionnalités les plus récentes s'affichent en haut de la liste.


## <a name="enable-a-feature"></a>Activer une fonctionnalité

Si une fonctionnalité n'a pas été activée, un bouton **Activer** s'affiche dans le volet des détails. Vous pouvez utiliser ce bouton pour activer la fonctionnalité.

1. Sélectionnez la fonctionnalité à activer, puis, dans le volet des détails, sélectionnez **Activer**.
2. Un curseur s'affiche, dans lequel vous pouvez spécifier la date à laquelle la fonctionnalité doit être activée. Par défaut, cette date est définie sur la date actuelle.
3. Sélectionnez **Activer** pour activer la fonctionnalité.

Certains fonctionnalités ne peuvent pas être désactivées après leur activation. Si la fonctionnalité que vous tentez d'activer ne peut pas être désactivée, vous recevez un avertissement. À ce stade, vous pouvez sélectionner **Annuler** pour annuler l'opération et laisser la fonctionnalité désactivée. Toutefois, si vous sélectionnez **Activer** et que vous activez la fonctionnalité, vous ne pourrez pas la désactiver ultérieurement.

Une fois la fonctionnalité activée, un message apparaît sous du lien **En savoir plus** dans le volet des détails. Ce message indique que la fonctionnalité a été activée ou indique quand la fonctionnalité sera activée dans le futur. Si vous utilisez une date future, la fonctionnalité s'affichera dans la liste **Planifié**. Ce message s'affichera chaque fois que vous sélectionnerez la fonctionnalité dans la liste des fonctionnalités. Les fonctionnalités qui sont planifiées à l'avenir seront activées à minuit par un processus de traitement par lots selon le fuseau horaire représenté par la date système. 

## <a name="reschedule-a-feature"></a>Replanifier une fonctionnalité

Si une fonctionnalité a pas été activée dans le futur, un bouton **Replanifier** s'affiche dans le volet des détails. Vous pouvez utiliser ce bouton pour modifier la **Date d'activation** à une date différente.

1. Sélectionnez une fonctionnalité planifiée à replanifier, puis, dans le volet des détails, sélectionnez **Replanifier**.
2. Un curseur s'affiche, dans lequel vous pouvez spécifier la date à laquelle la fonctionnalité doit être activée. 
3. Sélectionnez **Activer** pour replanifier la fonctionnalité ou **Désactiver** pour annuler la planification.

## <a name="disable-a-feature"></a>Désactiver une fonctionnalité

Si une fonctionnalité a déjà été activée, un bouton **Désactiver** s'affiche dans le volet des détails. Vous pouvez utiliser ce bouton pour désactiver la fonctionnalité. Le bouton **Désactiver** n'est pas disponible si la fonctionnalité ne peut pas être désactivée une fois activée.

- Sélectionnez la fonctionnalité à désactiver, puis, dans le volet des détails, sélectionnez **Désactiver**.

- La fonctionnalité est désactivée et la date est effacée.

Une fois la fonctionnalité désactivée, un message apparaît sous du lien **En savoir plus** dans le volet des détails. Ce message indique que la fonctionnalité n'a pas encore été activée et qu'elle s'affichera dans la liste **Non activé**. Le message s'affichera chaque fois que vous sélectionnerez la fonctionnalité dans la liste des fonctionnalités.

## <a name="features-that-must-be-enabled"></a>Fonctionnalités à activer

Une fonctionnalité essentielle peut être fournie qui doit être activée automatiquement lors de la mise à jour. Elle est automatiquement activée sur **Date d'activation**. Un message s'affiche sous du lien **En savoir plus** dans le volet des détails. Ce message indiquera que la fonctionnalité a été activée ou sera activée automatiquement à la **Date d'activation**. Il s'affichera chaque fois que vous sélectionnerez la fonctionnalité dans la liste des fonctionnalités.

## <a name="assigning-roles"></a>Attribution de rôles

L'espace de travail **Gestion des fonctionnalités** peut être ouvert par les administrateurs système, et par les utilisateurs auxquels des rôles de Gestionnaire de fonctionnalités ou de Visionneuse de fonctionnalité leur ont été attribués qui ont été créés pour prendre en charge l'expérience de Gestion des fonctionnalités. Les utilisateurs ayant le rôle de Gestionnaire de fonctionnalités peuvent activer ou désactiver n'importe quelle fonctionnalité. Ils peuvent également mettre à jour la section des commentaires de la fonctionnalité. Les utilisateurs ayant le rôle de Visionneuse de fonctionnalité peuvent uniquement consulter l'espace de travail **Gestion des fonctionnalités**. Ils ne peuvent pas activer ou désactiver des fonctionnalités.

Le rôle de Gestionnaire de fonctionnalités et rôle de Visionneuse de fonctionnalité ne remplacent pas la sécurité existante dont un utilisateur dispose. Les rôles contrôle uniquement l'accès à l'activation des fonctionnalités. Ils ne permettent pas d'accéder aux fonctionnalités elles-mêmes.

## <a name="using-feature-management-to-enable-isv-features-or-custom-features"></a>Utilisation de la Gestion des fonctionnalités pour activer des fonctionnalités de fournisseur de logiciels indépendant ou des fonctions personnalisées

Le processus de Gestion de fonctionnalités n'est actuellement pas disponible pour les fonctionnalités de fournisseur de logiciels indépendant ou les fonctionnalités personnalisées. Nous ajoutons des fonctionnalités supplémentaires pour optimiser la Gestion des fonctionnalités et, lorsque ces fonctionnalités seront terminées, nous ouvrirons la Gestion des fonctionnalités à toutes les fonctionnalités et fournirons des instructions spécifiques sur la procédure de mise à jour de votre fonctionnalité pour l'utiliser.

## <a name="feature-management-and-flighting"></a>Gestion des fonctionnalités et distribution de version d'évaluation

La Gestion des fonctionnalités vous permet de contrôler les fonctionnalités qui sont fournies dans chaque version. La distribution de version d'évaluation permet à Microsoft Teams de fournir des fonctionnalités à un nombre limité de clients afin que celles-ci puissent être testées et validées sans affecter tous les clients. La Gestion des fonctionnalités ne contrôle pas la distribution de version d'évaluation des fonctionnalités.
