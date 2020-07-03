---
title: Module d'accordéon
description: Cette rubrique couvre les modules accordéon et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 06/01/2020
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: e06a0e0289e8c0c718aff4beab2c7a6ceb0a8cb1
ms.sourcegitcommit: 2683aacb426bfb3b541637edf1f8ec2d6cb5a745
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2020
ms.locfileid: "3417252"
---
# <a name="accordion-module"></a>Module d'accordéon

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules accordéon et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Les modules accordéon sont des modules de type conteneur qui sont utilisés pour organiser les informations ou les modules d'une page en fournissant une fonctionnalité de réduction de type tiroir. Un module d'accordéon peut être utilisé sur n'importe quelle page.

À l'intérieur de chaque module d'accordéon, un ou plusieurs modules d'élément d'accordéon peuvent être ajoutés. Chaque module d'élément d'accordéon représente un tiroir réductible. À l'intérieur de chaque module d'élément d'accordéon, un ou plusieurs modules peuvent être ajoutés. Il n'y a aucune restriction quant aux types de modules qui peuvent être ajoutés à un module d'élément d'accordéon.

L'image suivante montre un exemple de module d'accordéon utilisé pour organiser les informations sur la page des questions fréquemment posées (FAQ) d'un magasin.

![Exemple d'un module d'accordéon](./media/ecommerce-accordion.PNG)

## <a name="accordion-module-properties"></a>Propriétés du module d'accordéon

| Nom de la propriété | Valeurs | Description |
|---------------|--------|-------------|
| En-tête | Détails | Cette propriété spécifie un en-tête de texte facultatif pour le module d'accordéon. |
| Développer tout | **Vrai** ou **Faux** | Si la valeur est définie sur **Vrai**, la fonctionnalité de développement/réduction est activée, de sorte que tous les éléments du module d'accordéon peuvent être développés et réduits. |
| Style d'interaction | **Indépendant** ou **Développer un seul élément** | Cette propriété définit le style d'interaction des éléments d'accordéon. Si la valeur est définie sur **Indépendant**, chaque élément d'accordéon peut être développé ou réduit indépendamment. Si la valeur est définie sur **Développer un seul élément**, un seul élément peut être développé à la fois. À mesure que les éléments sont développés, les éléments précédemment développés sont réduits. |

## <a name="accordion-item-module-properties"></a>Propriétés du module d'élément d'accordéon

| Nom de la propriété | Valeurs | Description |
|----------------|--------|-------------|
| Titre | Détails | Cette propriété spécifie le texte du titre du module d'élément d'accordéon. En sélectionnant la région du titre, les utilisateurs peuvent développer ou réduire la section. |
| Développer par défaut | **Vrai** ou **Faux** | Si la valeur est définie sur **Vrai**, l'élément d'accordéon est développé par défaut lors du chargement de la page. |

## <a name="add-an-accordion-module-to-a-faq-page"></a>Ajouter un module d'accordéon à une page de FAQ

Pour ajouter un module d'accordéon à une page de FAQ et définir ses propriétés dans le générateur de site, procédez comme suit.

1. Accédez à **Pages** et utilisez le modèle de marketing Fabrikam (ou tout modèle dénué de restriction) pour créer une nouvelle page nommée **FAQ du magasin**.
1. Dans l'emplacement **Principal** de la **Page par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Dans l'emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Accordéon**, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module d'accordéon, sélectionnez **En-tête** à côté du symbole du crayon.
1. Dans la boîte de dialogue **En-tête**, sous **Texte d'en-tête**, entrez **Questions fréquemment posées**. Puis sélectionnez **OK**.
1. Dans le volet des propriétés du module d'accordéon, cochez la case **Afficher Tout développer** puis, dans le champ **Style d'interaction**, sélectionnez **Indépendant**.
1. Dans l'emplacement **Accordéon**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Élément d'accordéon**, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module d'élément d'accordéon, sous **Titre**, saisissez le texte du titre (par exemple, **Comment fonctionnent les retours ?**).
1. Dans l'emplacement **Élément d'accordéon**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Bloc de texte**, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module de bloc de texte, entrez un paragraphe de texte (par exemple, **Les retours doivent être traités par le centre d'appels. Contactez le 1-800-FABRIKAM pour les retours. Les produits sont soumis à une politique de retour de 30 jours. Les retours doivent être initiés dans ce délai.**).
1. Dans l'emplacement **Accordéon**, ajoutez quelques autres modules d'élément d'accordéon. Dans chaque module d'élément d'accordéon, ajoutez un module de bloc de texte portant du contenu.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page. La page affichera un module d'accordéon portant le contenu que vous avez ajouté.
1. Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Conteneur](add-container-module.md)

[Module d'onglet](add-tab.md)

[Module de bloc de texte](add-content-rich-block.md)
