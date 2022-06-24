---
title: Incorporer des applications tierces
description: Cet article explique comment incorporer des applications tierces pour augmenter la fonctionnalité du produit.
author: jasongre
ms.date: 09/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, UserWorkspaceAdd, UserWorkspaceConfigureWebsite
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2021-04-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3c07befc7150ff0a121fd3aaa0b5233df9f431e5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868606"
---
# <a name="embed-third-party-apps"></a>Incorporer des applications tierces

[!include [banner](../includes/banner.md)]

De nombreux clients utilisent une gamme d’applications pour gérer leur entreprise. Certaines de ces applications sont des applications Web tierces qui fonctionnent conjointement aux applications de finances et d’opérations. Pour offrir une expérience utilisateur plus transparente, vous pouvez utiliser la fonctionnalité **Applications pleine page** pour intégrer ces applications tierces directement dans vos applications de finances et d’opérations (à condition que les applications tierces soient configurées pour être incorporées). De cette manière, les utilisateurs peuvent accéder aux sites Web et aux applications dont ils ont besoin sans avoir à changer d’onglet ou de fenêtre.

Avant de pouvoir intégrer des applications tierces dans le produit, vous devez activer la fonctionnalité **Applications pleine page** dans la gestion des fonctionnalités. Vous pouvez ensuite utiliser l’une des méthodes suivantes pour intégrer une application ou un site Web tiers. Ces méthodes sont analogues aux méthodes utilisées pour incorporer des applications de canevas à partir de Microsoft Power Apps dans les applications de finances et d’opérations.

- Incorporez l’application ou le site Web sur une page existante en tant que nouvelle page d’onglet (section d’onglet pivotant, de raccourci, de panneau ou d’espace de travail).
- Créez une nouvelle expérience pleine page pour l’application ou le site Web à partir du tableau de bord.

## <a name="embed-a-website-on-an-existing-page"></a>Incorporer un site Web sur une page existante

Utilisez cette procédure si vous souhaitez ajouter une page existante au système avec une application incorporée.

1. Ouvrez la page où vous souhaitez incorporer l’application.
2. Ouvrez le volet **Ajouter une application** :

    1. Sélectionnez **Paramètres**, puis **Personnaliser** pour ouvrir la barre d’outils **Personnalisation**.
    2. Sélectionner **Plus \> Ajouter une application**.

3. Sélectionnez la région de la page à laquelle vous souhaitez ajouter l’application. Cette région doit être un *conteneur d’onglets* pour une section d’onglet pivotant, de raccourci, de panneau ou d’espace de travail.
4. Sélectionnez **Site Internet**.
5. Configurez l’application incorporée :

    - **Nom** - Saisissez le texte à afficher pour l’onglet contenant l’application incorporée. Le plus souvent, ce texte sera le nom de l’application.
    - **URL** – Spécifiez l’emplacement de l’application.

    > [!IMPORTANT]
    > - Pour des raisons de sécurité, l’URL doit utiliser le protocole HTTPS (Hypertext Transfer Protocol Secure).
    > - L’application ou le site Web doit être configuré pour être intégré.

6. Sélectionnez **Enregistrer** pour intégrer l’application sur la page. L’application est ajoutée en tant que dernier onglet ou section dans le groupe.
7. Confirmez que l’application s’affiche comme prévu. Si l’application n’est pas rendue, consultez la section [Dépannage](#troubleshooting) plus loin dans cet article.
8. Ouvrez le sélecteur de vue et sélectionnez soit **Enregistrer** (si l’application doit être associée à la vue actuelle) ou **Enregistrer sous** (pour enregistrer l’application dans une vue différente).

    Si la page n’a pas de sélecteur d’affichage (par exemple, si la page est une boîte de dialogue ou un espace de travail), vous pouvez ignorer cette étape.

## <a name="embed-a-website-as-a-full-page-experience-from-the-dashboard"></a>Intégrer un site Web en tant qu’expérience pleine page à partir du tableau de bord

Utilisez cette procédure si l’application que vous souhaitez intégrer n’est pas liée à une page existante, ou si vous souhaitez simplement une expérience pleine page pour l’application dans l’application de finances et d’opérations.

1. Ouvrez le tableau de bord.
2. Sélectionnez et maintenez sélectionnée (ou cliquez avec le bouton droit) le tableau de bord, sélectionnez **Personnaliser**, puis sélectionnez **Ajouter une page**.
3. Dans le volet **Ajouter une page**, sélectionnez **Site Web**.
4. Configurez l’application incorporée :

    - **Nom** - Entrez le texte qui doit être affiché sur la mosaïque qui est ajoutée pour l’application incorporée sur le tableau de bord. Le plus souvent, ce texte sera le nom de l’application.
    - **URL** – Spécifiez l’emplacement de l’application.

    > [!IMPORTANT]
    > - Pour des raisons de sécurité, l’URL doit utiliser HTTPS.
    > - L’application ou le site Web doit être configuré pour être intégré.

5. Sélectionnez **Sauvegarder** pour ajouter l’application au tableau de bord en tant que nouvelle mosaïque.
6. Sélectionnez la nouvelle mosaïque sur le tableau de bord et confirmez que l’application apparaît comme prévu. Si l’application n’est pas rendue, consultez la section [Résolution des problèmes](#troubleshooting) ultérieurement dans cet article.

## <a name="sharing-embedded-apps"></a>Partage d’applications incorporées

Après avoir intégré une application à l’aide de l’une des méthodes décrites dans les sections précédentes, vous souhaiterez peut-être partager la vue avec d’autres utilisateurs du système. Pour partager une application incorporée, utilisez l’une des méthodes suivantes :

- **Publier la vue (recommandé) :** Si l’application incorporée a été enregistrée dans une vue, la méthode recommandée et préférée pour la partager consiste à publier la vue auprès des utilisateurs disposant des rôles de sécurité appropriés dans les entités juridiques ciblées. Dans ce cas, seuls les utilisateurs souhaités voient l’application intégrée sur cette page. Pour plus d’informations sur la publication d’une vue, voir [Publier des vues](saved-views.md#publishing-views).

    Vous pouvez également publier une application qui a été incorporée en tant qu’expérience pleine page à partir du tableau de bord. Sur le tableau de bord, sélectionnez et maintenez sélectionnée (ou cliquez avec le bouton droit) la mosaïque associée à l’application, sélectionnez **Personnaliser**, puis sélectionnez **Publier la page**. Une expérience qui ressemble à l’expérience *Publier des vues* est affichée et vous pouvez sélectionner les rôles de sécurité sur lesquels publier. Dans la mise à jour 10.0.21 ou ultérieure, si la fonction **Prise en charge améliorée des entités juridiques pour les vues enregistrées** est activée, vous pouvez également publier l’application sur les entités juridiques souhaitées.

- **Copiez la personnalisation :** Pour les pages qui ne prennent pas en charge les vues (par exemple, les boîtes de dialogue ou les espaces de travail), ou pour l’expérience d’application pleine page, vous pouvez copier la personnalisation vers les utilisateurs appropriés. Pour plus d’informations, consultez [Partage des personnalisations](personalize-user-experience.md#sharing-personalizations).

## <a name="viewing-embedded-apps"></a>Affichage d’applications incorporées

Pour afficher une application canevas incorporée sur une page dans les applications de finances et d’opérations, ouvrez la page contenant l’application incorporée. N’oubliez pas que, sur certaines pages, les applications incorporées sont accessibles à l’aide du bouton **Power Apps** sur le volet Actions standard. Elles peuvent également apparaître directement sur la page en tant que nouvel onglet, raccourci ou panneau, ou en tant que nouvelle section dans un espace de travail.

## <a name="editing-or-removing-embedded-apps"></a>Modifier ou supprimer des applications incorporées

Une fois qu’une application a été incorporée à une page, vous devrez peut-être modifier sa configuration (par exemple, en modifiant le libellé de la section ou l’URL). Vous devrez peut-être également la supprimer de la page. Utilisez l’une des procédures suivantes pour modifier la configuration d’une application incorporée ou la supprimer complètement.

### <a name="apps-that-are-embedded-on-existing-pages"></a>Applications incorporées à des pages existantes

1. Ouvrez la page où l’application est incorporée.
2. Sélectionnez **Paramètres**, puis **Personnaliser** pour ouvrir la barre d’outils **Personnalisation**.
3. Sélectionnez l’outil **Sélectionner**, puis sélectionnez l’application incorporée.
4. Pour modifier l’application, apportez les modifications requises à sa configuration, puis sélectionnez **Enregistrer**.

    Sinon, pour supprimer l’application, sélectionnez **Supprimer**.

5. Réenregistrez ou republiez la vue. Notez que si vous quittez la page sans enregistrer explicitement la vue, aucune des actions que vous avez effectuées dans le volet **Modifier le site Web** sera conservée.

### <a name="apps-that-are-embedded-from-the-dashboard"></a>Applications incorporées à partir du tableau de bord

1. Ouvrez le tableau de bord.
2. Sélectionnez et maintenez sélectionnée (ou cliquez avec le bouton droit) la mosaïque associée à l’application incorporée, puis sélectionnez **Personnaliser**.
3. Pour modifier l’application, sélectionnez **Modifier la page**. Dans le volet **Modifier le site Web**, apportez les modifications requises à la configuration de l’application, puis sélectionnez **Enregistrer**.

    Sinon, pour supprimer l’application, sélectionnez **Supprimer la page**.

## <a name="appendix"></a>Annexe

### <a name="troubleshooting"></a>Résolution des problèmes

Si un site Web n’est pas rendu correctement après avoir été intégré dans une application Finance and Operation, ou si vous recevez un message d’erreur indiquant que la connexion à l’URL a été refusée, le site Web est probablement configuré pour empêcher l’intégration dans une iframe. Suivez ces étapes pour déterminer si le site Web peut être intégré.

1. Ouvrez les outils de développement du navigateur que vous utilisez.
2. Sur l’onglet **Réseau**, recherchez et sélectionnez la réponse sur le site intégré.
3. Sur l’onglet **En-têtes**, sous **En-têtes de réponse**, cherchez **x-frame-options**. Si **x-frame-options** existe dans les en-têtes de réponse et a la valeur **DENY** ou alors **SAMEORIGIN**, le site Web ne peut actuellement pas être intégré. Vous devrez contacter le propriétaire de l’application pour l’intégrer en toute sécurité.

### <a name="developer-modeling-a-website-on-a-form"></a>[Développeur] Modélisation d’un site Web sur un formulaire

Bien que cet article traite de l’intégration d’applications ou de sites Web tiers via la personnalisation, les développeurs peuvent également les intégrer dans un formulaire à l’aide de l’expérience de développement Visual Studio. Ajoutez simplement un contrôle **Site WebHostControl** au formulaire. Les propriétés de métadonnées disponibles pour le contrôle offrent les mêmes fonctionnalités que l’expérience de personnalisation.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
