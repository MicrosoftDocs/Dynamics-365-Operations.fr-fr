---
title: Appliquer les paramètres d’unité de mesure
description: Cet article couvre les paramètres d’unité de mesure et décrit leur application dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/23/2021
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: ca95bd31af8f244f60f12120bc6df121f48cc7ea
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884813"
---
# <a name="apply-unit-of-measure-settings"></a>Appliquer les paramètres d’unité de mesure

[!include [banner](includes/banner.md)]

Cet article couvre les paramètres d’unité de mesure et décrit leur application dans Microsoft Dynamics 365 Commerce.

Un produit peut être vendu en différentes unités, par exemple en « unité », en « paire » et en « douzaine » Au siège de Commerce, l’unité de mesure de vente par produit peut être définie pour un produit et affichée sur un site de commerce électronique. Par exemple, si un détaillant vend un produit à la fois individuellement et par dizaines, les unités de mesure disponibles peuvent être affichées avec d’autres informations sur le produit.

Dans l’exemple de l’illustration suivante, une unité de mesure de vente par **unité** a été configuré pour un produit au siège de Commerce.

![Exemple de produit configuré avec une unité de mesure au siège de Commerce.](./media/Productunit-headquarters.PNG)

> [!NOTE]
> La prise en charge de l’application et de l’affichage de l’unité de mesure est disponible à partir de la version 10.0.19 de Commerce.

## <a name="unit-of-measure-settings"></a>Paramètres d’unité de mesure

Les paramètres d’affichage des unités de mesure sont définis dans le générateur de site Commerce, dans **Paramètres du site \> Extensions \> Afficher l’unité de mesure des produits**. Il existe trois paramètres pris en charge :

- **Ne pas afficher** – Lorsque ce paramètre est sélectionné, le site de commerce électronique n’affiche pas l’unité de mesure du produit. Ce comportement est celui par défaut.
- **Affichage dans l’expérience d’achat du produit** – Lorsque ce paramètre est sélectionné, l’unité de mesure est affichée sur les pages des détails du produit, du panier, de la caisse, de l’historique des commandes et des détails de la commande.
- **Affichage dans la navigation du produit et l’expérience d’achat** – Lorsque ce paramètre est sélectionné, l’unité de mesure est affichée sur les pages d’expérience d’achat du produit et également pendant l’expérience de navigation du produit. Les unités de mesure sont alors affichées dans les résultats de recherche et les modules de collecte de produits.

> [!IMPORTANT]
> Les paramètres d’affichage des unités de mesure sont disponibles à partir de la version 10.0.19 de Commerce. Si vous effectuez une mise à jour à partir d’une ancienne version de Commerce, vous devez mettre à jour manuellement le fichier appsettings.json. Pour plus d’informations, voir [Mise à jour des kits de développement logiciel (SDK) et des bibliothèques de modules](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="modules-that-use-unit-of-measure-settings"></a>Modules qui utilisent les paramètres d’unité de mesure

Les modules qui utilisent les paramètres d’unité de mesure incluent la zone d’achat, la liste de souhaits, le panier, l’icône du panier, le conteneur de résultats de recherche, la collection de produits, le paiement et les modules de détails de la commande.

Dans l’exemple de l’illustration suivante, une page de détails du produit (PDP) montre l’unité de mesure (**unité**) pour un produit.

![Exemple de PDP qui montre l’unité de mesure.](./media/Productunit-PDP.png)

Dans l’exemple de l’illustration suivante, un module de collecte de produits montre l’unité de mesure (**unité**) pour un produit.

![Exemple de module de collecte de produits affichant l’unité de mesure.](./media/Productunit-productcollection.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Module Panier](add-cart-module.md)

[Module de zone d’achat](add-buy-box.md)

[Pages et modules Gestion des comptes](account-management.md)

[Mise à jour des kits de développement logiciel (SDK) et des bibliothèques de modules](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
