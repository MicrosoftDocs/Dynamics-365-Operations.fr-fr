---
title: Utilisation de groupes de publication
description: Cette rubrique décrit la fonctionnalité de groupes de publication dans Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 0a4f19af0cdf9c72add0ec18be84e36c807af9ce
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969874"
---
# <a name="work-with-publish-groups"></a>Utilisation de groupes de publication


[!include [banner](includes/banner.md)]

Cette rubrique décrit la fonctionnalité de groupes de publication dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Les sites de commerce électronique sont constamment mis à jour avec de nouveaux contenus tout au long de l'année. Les mises à jour sont souvent publiées par lots autour d'événements de commerce électronique très fréquentés tels que les vacances, les campagnes marketing saisonnières ou les lancements promotionnels. Ces mises à jour nécessitent souvent que des groupes de contenu de site web (par exemple, des pages, des images, des fragments et des modèles) soient organisés, validés et publiés simultanément en une seule action.

La possibilité de regrouper des éléments en ensembles logiques qui publient des éléments ensemble, où chaque ensemble a son propre cycle de vie, offre de nombreux avantages aux auteurs de sites. Dans Commerce, ces ensembles logiques sont appelés des groupes de publication. Ils permettent aux auteurs de sites de suivre des ensembles de mises à jour comme leurs propres entités configurables, testables et publiables.

Les auteurs peuvent prévisualiser les mises à jour dans un groupe de publication par étapes sans affecter le site en direct ou d'autres groupes de publication autonomes. Les auteurs peuvent ensuite planifier l'action de publication pour publier simultanément tous les éléments du groupe de publication sur le site en ligne. La capacité de regrouper, de prévisualiser et de planifier des mises à jour pour la publication est importante pour de nombreuses entreprises au niveau de l'entreprise qui génèrent des revenus annuels considérables autour de jalons de mise à jour de site basés sur des événements.

Les entreprises peuvent subir des coûts liés à des déploiements de contenu lents ou non valides qui ne se déroulent pas sans heurts. Les groupes de publication permettent de garantir que les lancements soient organisés, validés et publiés à temps. Qu'ils soient grands ou petits, les groupes de publication fournissent un ensemble d'outils précieux qui aide les auteurs à organiser et à simplifier les tâches de mise à jour du site en cours.

## <a name="when-to-use-publish-groups"></a>Quand utiliser les groupes de publication

Vous pouvez utiliser des groupes de publication chaque fois que vous devez échelonner et publier plusieurs documents ensemble. Par exemple, si votre site web met à jour le contenu chaque saison, vous pouvez créer des groupes de publication pour ces mouvements marketing saisonniers. Votre groupe de publication « Mise à jour saisonnière d'automne » peut contenir de nouvelles images saisonnières, des fragments contenant des messages marketing saisonniers, des pages contenant des collections de produits saisonniers ou d'autres mises à jour saisonnières de sites web.

Un des avantages des groupes de publication est que vous pouvez organiser plusieurs mises à jour en parallèle. Par exemple, peu de temps après la mise à jour du groupe de publication « Mise à jour saisonnière d'automne », il peut y avoir une mise à jour de contenu pour un week-end de vacances spécifique. Dans ce cas, vous pouvez mettre en scène le contenu du groupe de publication « Mise à jour saisonnière d'automne » en même temps que vous mettez en scène le contenu d'un groupe de publication « Mise à jour des vacances d'automne » suivant. Chaque groupe de publication contient son propre ensemble unique de pages, images, fragments, modèles, etc. Vous pouvez échelonner, prévisualiser et valider ces deux groupes de publication indépendamment mais avec une chronologie simultanée. Chaque groupe de publication peut ensuite être programmé pour être mis en ligne sur votre site à des dates et heures spécifiques.

## <a name="turn-on-the-publish-groups-feature"></a>Activation de la fonctionnalité de groupes de publication

La fonctionnalité de groupes de publication est facultative et doit être activée pour votre site.

Pour activer la fonctionnalité de groupes de publication pour votre site dans les outils de création de Commerce, procédez comme suit.

1. Dans le volet de navigation de gauche, cliquez sur **Paramètres du site** pour les étendre.
1. Sous **Paramètres du site**, cliquez sur **Fonctionnalités**.
1. Définissez l'option **Groupes de publication** sur **Activé**.

## <a name="create-a-publish-group"></a>Création d'un groupe de publication

Pour créer un groupe de publication pour votre site dans les outils de création de Commerce, procédez comme suit.

1. Dans le volet de navigation de gauche, cliquez sur **Groupes de publication**.
1. Dans la barre de commande supérieure, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer un groupe de publication**, sous **Nom du groupe de publication**, entrez un nom descriptif. Puis sélectionnez **OK**.

## <a name="set-the-publish-group-authoring-context"></a>Définition du contexte de création du groupe de publication

Dans Commerce, le contexte de création par défaut est le contexte du site en direct. Le contexte de création de site en direct est la vue par défaut où vous pouvez afficher et apporter des modifications directement à votre site web sans utiliser de groupe de publication. Il représente les dernières mises à jour directes de la version publiée de votre site. Si le contrôle de contexte sous **Groupes de publication** dans le volet de navigation de gauche affiche le nom **Site en direct**, vous travaillez dans le contexte de création de site en direct. **Site en direct** est le nom par défaut du contrôle de contexte. Sinon, le contrôle de contexte affiche le nom d'un groupe de publication.

Pour utiliser un groupe de publication, vous devez basculer vers le contexte de création du groupe de publication correspondant. Pour définir le contexte du groupe de publication, suivez l'une de ces étapes.

- Dans le volet de navigation de gauche, sélectionnez le contrôle de contexte directement sous **Groupes de publication**, puis sélectionnez le nom du groupe de publication dans la liste des options qui s'affiche. Le contrôle de contexte est renommé et affiche le nom du groupe de publication.
- Dans le volet de navigation de gauche, cliquez sur **Groupes de publication**, puis, sous **Groupes de publication**, cliquez sur le nom du groupe de publication. Le contrôle de contexte est renommé et affiche le nom du groupe de publication.

Après avoir défini votre contexte de création de groupe de publication, vous utilisez ce contexte de groupe de publication lorsque vous prévisualisez et modifiez le contenu du site.

Pour revenir au contexte de création de site en direct par défaut, cliquez sur le contrôle de contexte, puis sur **Site en direct**.

## <a name="add-pages-or-other-items-to-a-publish-group"></a>Ajout de pages ou d'autres éléments à un groupe de publication

Une fois que vous avez sélectionné un contexte de création de groupe de publication et que le contrôle de contexte dans le volet de navigation de gauche affiche son nom, vous pouvez créer du contenu comme vous le faites dans le contexte de site en direct par défaut. Vous pouvez également ajouter des pages existantes ou d'autres éléments à partir d'autres groupes de publication ou à partir du contexte du site en direct.

Pour copier des pages existantes dans un groupe de publication, procédez comme suit.

1. Sélectionnez le contexte de création à partir duquel copier, puis, dans le volet de navigation de gauche, cliquez sur **Pages**.
1. Sélectionnez la page à ajouter à un groupe de publication.
1. Dans la barre de commandes, sélectionnez **Copier dans le groupe de publication**.
1. Dans la boîte de dialogue **Sélectionner un groupe de publication**, cliquez sur le groupe de publication auquel ajouter la page, puis sur **OK**.

Vous pouvez utiliser les mêmes étapes de base pour créer des pages de produit, des URL, des modèles, des dispositions, des fragments et des actifs de bibliothèque multimédia personnalisés, ou pour ajouter des éléments existants de ces types à un groupe de publication.

## <a name="validate-a-publish-group"></a>Validation d'un groupe de publication

Pour vous assurer que toutes les dépendances du contenu du groupe de publication sont satisfaites et que toutes les validations sont réussies, vous pouvez exécuter une validation pour identifier les problèmes qui doivent être résolus avant de planifier une action de publication.

Pour valider votre groupe de publication avant de le planifier, procédez comme suit.

1. Dans le volet de navigation de gauche, cliquez sur **Groupes de publication**.
1. Sélectionnez le groupe de publication à valider.
1. Dans la barre de commande, cliquez sur **Valider**.

La validation est exécutée sur tout le contenu du groupe de publication. Tous les problèmes qui empêcheront une action de publication réussie sont affichés dans une boîte de notification qui apparaît en haut à droite.

> [!NOTE]
> La validation est toujours exécutée automatiquement lorsqu'un groupe de publication est planifié. Cependant, le bouton **Valider** dans la barre de commandes est utile, car il permet d'identifier les problèmes que vous devez résoudre avant d'essayer de planifier la mise en ligne d'un groupe de publication.

## <a name="schedule-a-publish-group-to-go-live"></a>Planifier la mise en ligne d'un groupe de publication

Pour planifier la mise en ligne d'un groupe de publication sur votre site, procédez comme suit.

1. Dans le volet de navigation de gauche, cliquez sur **Groupes de publication**.
1. Sous **Groupes de publication**, cliquez sur le groupe de publication à planifier.
1. Dans la barre de commande, cliquez sur **Modifier le programme**. La boîte de dialogue **Modifier le programme** apparaît.
1. Sélectionnez la date et l'heure auxquelles votre groupe de publication doit être mis en ligne, puis cliquez sur **OK**.

Pour annuler la planification d'un groupe de publication, suivez les mêmes étapes, mais sélectionnez **Annuler la planification du groupe de publication** dans la boite de dialogue **Modifier le programme**.

> [!NOTE]
> Les très grands groupes de publication peuvent prendre jusqu'à une minute ou deux pour être publiés à l'heure prévue. Sachez qu'une action de publication n'est pas instantanée et que les petits groupes de publication seront publiés plus rapidement.

## <a name="publish-groups-faq"></a>FAQ sur les groupes de publication

**Combien d'éléments peuvent être dans un groupe de publication ?**

Actuellement, il y a une limite de 2 000 éléments par groupe de publication. Notez que les très grands groupes de publication peuvent prendre plusieurs minutes pour être publiés à l'heure prévue.

**Les groupes de publication sont-ils comme des « branches » de code dans la terminologie de développement logiciel ?**

Oui et non. Les groupes de publication peuvent être considérés comme des versions fourchues de votre site. De cette façon, ils agissent comme des branches. Cependant, il n'existe aucun concept de fusion au niveau des éléments individuels. L'article publié en dernier remplace simplement ce qui existait auparavant et l'action de publication la plus récente remplace toujours les actions de publication précédentes.

**Puis-je programmer deux groupes de publication pour qu'ils soient mis en ligne en même temps ?**

Non. Pour des raisons de performances et de conflit, le système vous obligera à échelonner les groupes de publication planifiés à au moins cinq minutes d'intervalle.

**Puis-je utiliser des groupes de publication pour planifier des éléments de back-office omnicanal, tels que des remises et des mises à jour de produits ?**

Actuellement, la fonctionnalité des groupes de publication ne prend en charge que le contenu du site web. Cependant, Microsoft est conscient que l'intégration avec des scénarios de promotion des ventes du back-office pourrait être utile pour la coordination et l'automatisation des lancements de campagnes omnicanales.

## <a name="additional-resources"></a>Ressources supplémentaires

[Manières d’ajouter du contenu](add-manage-content.md)

[Glossaire sur le modèle de page](page-elements-overview.md)

[États et cycle de vie des documents](document-states-overview.md)

[Activer et utiliser le partage intercanal](cross-channel-sharing.md)

[Utiliser des modules](work-with-modules.md)

[Utiliser des fragments](work-with-fragments.md)

[Vue d’ensemble des modèles et dispositions](templates-layouts-overview.md)

[Personnaliser la navigation dans le site](customize-site-navigation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]