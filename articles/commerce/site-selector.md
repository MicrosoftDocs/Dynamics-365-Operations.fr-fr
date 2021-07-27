---
title: Module Sélecteur de sites
description: Cette rubrique couvre le module de sélecteur de sites et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: b69156ee79dbbe8cbb8f5eb5988a751f0488d8e5
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6357736"
---
# <a name="site-selector-module"></a>Module de sélection de site

[!include [banner](includes/banner.md)]

Cette rubrique couvre le module de sélecteur de sites et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Lorsqu’une entreprise possède différents sites sur des marchés, des régions et des paramètres régionaux, les utilisateurs des sites ont besoin d’un moyen simple de basculer entre les sites et de sélectionner leur site d’achat préféré. Pour s’adapter à ce scénario, le module de sélecteur de sites permet aux utilisateurs de parcourir plusieurs sites.

Le module de sélecteur de sites doit être configuré avec la liste des sites (marchés, régions ou paramètres régionaux) que les utilisateurs des sites peuvent parcourir.

> [!NOTE]
> Le module de sélecteur de sites est disponible dans la version 10.0.14 de Dynamics 365 Commerce.

L’illustration suivante montre un exemple de module de sélecteur de sites qui figure dans l’en-tête d’une page de site.

![Exemple de module de sélecteur de sites dans l’en-tête d’une page de site.](./media/ecommerce-sitepicker.PNG)

## <a name="site-selector-module-properties"></a>Propriétés du module de sélecteur de sites

| Nom de la propriété | Valeur                  | Description  |
|---------------|-----------------------|-------------|
| Titre       | Détails                  | En-tête du module. |
| Options de site  | Nom, image, URL      | Cette propriété spécifie un nom, un lien vers la page d’accueil du site et une image facultative à afficher pour chaque site inclus dans le module. L’image peut être un drapeau ou une représentation d’un marché, d’une région ou d’un lieu. |

## <a name="add-a-site-selector-module-to-a-page"></a>Ajouter un module de sélecteur de sites à une page

Le module de sélecteur de sites peut être ajouté au [Module d’en-tête](author-header-module.md) sous l’emplacement du sélecteur de sites. Une fois ajouté, vous pouvez définir l’en-tête du module et les options du site.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Module En-tête](author-header-module.md)

[Module de barre de navigation](add-breadcrumb.md)

[Module du menu de navigation](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]