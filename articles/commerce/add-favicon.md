---
title: Ajouter une icône de favori
description: Cette rubrique explique comment ajouter une icône de favori à votre site.
author: bicyclingfool
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 58cb6c592351a96876532ef53d5d477ff93fafa1
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2696989"
---
# <a name="add-a-favicon"></a>Ajouter une icône de favori

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique explique comment ajouter une icône de favori à votre site.

## <a name="overview"></a>Vue d'ensemble

Une icône de favori est un petit fichier graphique affiché sous un onglet du navigateur web, dans la barre d'adresse, dans l'historique de navigation, et dans les signets ou les favoris, entre autres. Nous vous recommandons d'ajouter une icône de favori à votre site, car elle représente et renforce votre marque, et aide à distinguer votre site d'autres sites que vos clients visitent.

Bien que vous puissiez ajouter plusieurs icônes de favori de différentes tailles et types de fichiers à votre site, cette rubrique explique comment ajouter une icône de favori unique. Toutefois, les mêmes processus et emplacement sont utilisés pour ajouter des une icônes de favori.

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a>Chargement de l'icône de favori dans la collection d'actifs du site

Pour charger l'icône de favori dans la collection d'actifs du site, procédez comme suit.

1. Accédez à **Actifs \> Charger \> Charger des actifs**.
1. Recherchez et sélectionnez l'icône de favori sur votre système de fichiers local.
1. Entrez un titre, puis sélectionnez **OK**. 
1. Dans le volet de propriété de droite, copiez l'URL publique de l'icône de favori.

> [!NOTE]
> Si vous ne sélectionnez pas l'option **Publier les actifs après chargement**, vous devez retourner à la page **Actifs** et publier manuellement l'icône de favori ultérieurement.

## <a name="create-the-html-for-the-favicon"></a>Créer l'HTML pour l'icône de favori

Pour créer le fichier HTML pour l'icône de favori, utilisez l'extrait de code HTML. Pour l'attribut **href**, remplacez **« Public\_URL\_pour\_votre\_icône_de_favori »** par l'URL publique copiée précédemment.

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="add-the-html-for-the-favicon-to-the-head-element-of-your-pages"></a>Ajoutez l'HTML pour l'icône de favori à l'élément \<en-tête\> de vos pages

Pour ajouter une icône de favori à votre site, utilisez la même procédure que pour ajouter un type de HTML ou un script à l'élément **\<en-tête\>** des pages de votre site.

## <a name="additional-resources"></a>Ressources supplémentaires

[Ajouter un logo](add-logo.md)

[Sélectionner un thème pour le site](select-site-theme.md)

[Ajouter un message de bienvenue](add-welcome-message.md)

[Ajouter un avis de droits d'auteur](add-copyright-notice.md)

[Ajouter des langues à votre site](add-languages-to-site.md)

[Ajout d'un code de script aux pages de site pour prendre en charge la télémétrie](add-telemetry.md)

