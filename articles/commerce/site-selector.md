---
title: Module Sélecteur de sites
description: Cette rubrique couvre le module de sélecteur de sites et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: bd54695f54b501631f916328c05bfd47e538d50d
ms.sourcegitcommit: 765056b5dc1d0a8c27e56ff2cbd310ad3349ff09
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2020
ms.locfileid: "4055828"
---
# <a name="site-selector-module"></a>Module Sélecteur de sites

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cette rubrique couvre le module de sélecteur de sites et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Lorsqu'une entreprise possède différents sites sur des marchés, des régions et des paramètres régionaux, les utilisateurs des sites ont besoin d'un moyen simple de basculer entre les sites et de sélectionner leur site d'achat préféré. Pour s'adapter à ce scénario, le module de sélecteur de sites permet aux utilisateurs de parcourir plusieurs sites.

Le module de sélecteur de sites doit être configuré avec la liste des sites (marchés, régions ou paramètres régionaux) que les utilisateurs des sites peuvent parcourir.

> [!NOTE]
> Le module de sélecteur de sites est disponible dans la version 10.0.14 de Dynamics 365 Commerce.

L'illustration suivante montre un exemple de module de sélecteur de sites qui figure dans l'en-tête d'une page de site.

![Exemple de module de sélecteur de sites dans l'en-tête d'une page de site](./media/ecommerce-sitepicker.PNG)

## <a name="site-selector-module-properties"></a>Propriétés du module de sélecteur de sites

| Nom de la propriété | Valeur                  | Description  |
|---------------|-----------------------|-------------|
| Titre       | Détails                  | En-tête du module. |
| Options de site  | Nom, image, URL      | Cette propriété spécifie un nom, un lien vers la page d'accueil du site et une image facultative à afficher pour chaque site inclus dans le module. L'image peut être un drapeau ou une représentation d'un marché, d'une région ou d'un lieu. |

## <a name="add-a-site-selector-module-to-a-page"></a>Ajouter un module de sélecteur de sites à une page

Le module de sélecteur de sites peut être ajouté au [Module d'en-tête](author-header-module.md) sous l'emplacement du sélecteur de sites. Une fois ajouté, vous pouvez définir l'en-tête du module et les options du site.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Module En-tête](author-header-module.md)

[Module de barre de navigation](add-breadcrumb.md)

[Module du menu de navigation](nav-menu-module.md)
