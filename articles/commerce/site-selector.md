---
title: Module de sélection de site
description: Cette rubrique couvre le module de sélecteur de sites et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 02/11/2022
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
ms.openlocfilehash: 381163fdd6180a76def2e1bfb733f597b611c517
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109704"
---
# <a name="site-picker-module"></a>Module de sélection de site

[!include [banner](includes/banner.md)]

Cette rubrique couvre le module de sélecteur de sites et décrit comment l’ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Lorsqu’une entreprise possède différents sites sur des marchés, des régions et des paramètres régionaux, les utilisateurs des sites ont besoin d’un moyen simple de basculer entre les sites et de sélectionner leur site d’achat préféré. Pour s’adapter à ce scénario, le module de sélecteur de sites permet aux utilisateurs de parcourir plusieurs sites.

Le module de sélecteur de sites doit être configuré avec la liste des sites (marchés, régions ou paramètres régionaux) que les utilisateurs des sites peuvent parcourir.

> [!NOTE]
> Le module de sélecteur de sites est disponible dans la version 10.0.14 de Dynamics 365 Commerce.

L’illustration suivante montre un exemple de module de sélecteur de sites qui figure dans l’en-tête d’une page de site.

![Exemple de module de sélecteur de sites dans l’en-tête d’une page de site.](./media/ecommerce-sitepicker.PNG)

## <a name="site-picker-module-properties"></a>Propriétés du module de sélecteur de sites

| Nom de la propriété | Valeur                  | Description |
|---------------|-----------------------|-------------|
| Titre       | Détails                  | En-tête du module. |
| Options de site  | Nom, image, URL      | Cette propriété spécifie un nom, un lien vers la page d’accueil du site et une image facultative à afficher pour chaque site inclus dans le module. L’image peut être un drapeau ou une représentation d’un marché, d’une région ou d’un lieu. |

## <a name="add-a-site-picker-module-to-a-page"></a>Ajouter un module de sélecteur de sites à une page

Le module de sélecteur de sites peut être ajouté à l’emplacement **Sélecteur de sites** du [module d’en-tête](author-header-module.md). Une le module de sélection de sites ajouté, vous pouvez définir l’en-tête du module et les options du site. Généralement, un module d’en-tête est contenu dans un fragment d’en-tête qui peut être partagé entre les pages e-commerce d’un site. Dans l’exemple suivant, le module de sélection de site a été ajouté à l’emplacement **Sélecteur de site** d’un module d’en-tête contenu dans un fragment d’en-tête nommé **HeaderContainer**.

![Exemple de module de sélecteur de sites dans un fragment d’en-tête.](./media/ecommerce-sitepicker-2.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Module d’en-tête](author-header-module.md)

[Module de barre de navigation](add-breadcrumb.md)

[Module du menu de navigation](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
