---
title: Vérifier l'accessibilité du contenu de la page
description: Cette rubrique décrit comment vérifier l'accessibilité du contenu des pages dans Microsoft Dynamics 365 Commerce.
author: arotkin
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: retail
ms.author: arotkin
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 70604ed16d72e519724aeb2c33bd4a91a8b26c8c
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "2946009"
---
# <a name="verify-page-content-accessibility"></a>Vérifier l'accessibilité du contenu de la page

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique décrit comment vérifier l'accessibilité du contenu des pages dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Lorsque vous avez terminé de modifier une page, vous devez vous assurer que le contenu est accessible à tous sur le web. Dans les outils de création de Commerce, vous pouvez facilement vérifier l'accessibilité du contenu de la page en utilisant le service [Informations sur l'accessibilité de Microsoft](https://accessibilityinsights.io/). Ce service vérifie le contenu de votre page par rapport aux dernières lignes directrices d'[accessibilité au World Wide Web Consortium (W3C)](https://www.w3.org/standards/webdesign/accessibility).

L'intégration des [Informations sur l'accessibilité de Microsoft](https://accessibilityinsights.io/) doit être activée au niveau du client ou du site avant de pouvoir l'utiliser.

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a>Activer les Informations sur l'accessibilité de Microsoft pour tous les sites de votre client

Pour activer l'intégration des [Informations sur l'accessibilité de Microsoft](https://accessibilityinsights.io/) pour tous les sites Commerce de votre client, procédez comme suit.

> [!NOTE]
> Pour accéder aux paramètres du client, vous devez être connecté à Commerce en tant qu'administrateur système.

1. Connectez-vous à Commerce en tant qu'administrateur système.
1. Dans le volet de navigation de gauche, sélectionnez **Paramètres du client** (à côté du symbole d'engrenage) pour l'agrandir.
1. Sous **Paramètres du client**, cliquez sur **Fonctionnalités**.
1. Définissez l'option **Vérification de l'accessibilité** sur **Activé**.

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a>Activer Informations sur l'accessibilité de Microsoft pour un seul site

Pour activer l'intégration des [Informations sur l'accessibilité de Microsoft](https://accessibilityinsights.io/) pour un seul site Commerce, procédez comme suit.

1. Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).
1. Dans le volet de navigation de gauche, cliquez sur **Paramètres du site** pour les étendre.
1. Sous **Paramètres du site**, cliquez sur **Fonctionnalités**.
1. Définissez l'option **Vérification de l'accessibilité** sur **Activé**.

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a>Vérifier l'accessibilité du contenu sur la page d'accueil

Pour utiliser le service [Informations sur l'accessibilité de Microsoft](https://accessibilityinsights.io/) intégré pour analyser et vérifier le contenu de votre page d'accueil dans Commerce, procédez comme suit.

1. Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).
1. Dans le volet de navigation de gauche, sélectionnez **Pages**.
1. Recherchez et sélectionnez la page d'accueil pour l'ouvrir dans l'éditeur de page.
1. Dans la barre de commande, sélectionnez **Vérifier l'accessibilité**. La page **Vérifier l'accessibilité** apparaît.
1. Une fois l'analyse terminée, examinez le contenu du rapport.
1. Si des vérifications ont échoué, sélectionnez chaque élément de vérification ayant échoué pour le développer afin de pouvoir afficher plus de détails.
1. Pour fermer le rapport après l'avoir examiné, faites défiler vers le bas de la page **Vérifier l'accessibilité** et sélectionnez **OK**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Modifier une page de site existante](modify-existing-page.md)

[Ajouter une nouvelle page de site](add-new-page.md)

[Sélectionner des dispositions de page](select-page-layouts.md)

[Gestion des métadonnées SEO](manage-seo-metadata.md)

[Enregistrer, afficher un aperçu et publier une page](save-preview-publish-page.md)

[Enrichir une page de produit](enrich-product-page.md)

[Enrichir une page d'arrivée de catégorie](enrich-category-page.md)
