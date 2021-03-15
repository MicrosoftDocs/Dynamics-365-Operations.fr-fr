---
title: Ajouter un avis de droits d'auteur
description: Cette rubrique décrit la procédure d'ajout d'un avis de droits d'auteur à votre site web de commerce électronique.
author: psimolin
manager: AnnBe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 54d9ccbb56131333159cdf8858dfca23b75b61fd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980454"
---
# <a name="add-a-copyright-notice"></a>Ajouter un avis de droits d'auteur

[!include [banner](includes/banner.md)]

Cette rubrique décrit la procédure d'ajout d'un avis de droits d'auteur à votre site web de commerce électronique.

## <a name="prerequisites"></a>Conditions préalables

Avant de pouvoir ajouter un avis de droits d'auteur à votre site, vous devez avoir les options suivantes :

- Un modèle incluant un fragment de pied de page partagé.
- Une page qui utilise ce modèle.

## <a name="add-a-copyright-notice"></a>Ajouter un avis de droits d'auteur

Pour ajouter un avis de droits d'auteur au bas de chaque page qui utilise un modèle spécifique, procédez comme suit.

1. Accédez à **Fragments**, puis sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Nouveau fragment**, sélectionnez le module **Pied de page** et nommez le fragment. Par exemple, entrez **Pied de page - Droits d'auteur**.
1. Cliquez sur **OK**.
1. Dans le volet de navigation, sélectionnez le bouton représentant des points de suspension (**...**) en regard de **Pied de page**, et sélectionnez **Ajouter le module** ensuite.
1. Dans la boîte de dialogue, sélectionnez **Catégorie de pied de page**, puis sélectionnez **OK**.
1. Dans le volet de navigation, sélectionnez le bouton représentant des points de suspension en regard de **Catégorie de pied de page**, et sélectionnez **Ajouter le module** ensuite.
1. Dans la boîte de dialogue, sélectionnez **Bloc de texte**, puis sélectionnez **OK**.
1. Dans le volet de navigation, sélectionnez **Bloc de texte**.
1. Dans le volet de propriétés de droite, dans le champ **Paragraphe**, ajoutez le message sur les droits d'auteur. Par exemple, entrez **(C) Fabrikam 2019**.
1. Sélectionnez **Enregistrer**, sélectionnez **Terminer la modification**, puis sélectionnez **Publier**.
1. Accédez à **Modèles**, sélectionnez le modèle, puis sélectionnez **Modifier**.
1. Sous **Contour de la page**, développez **Corps**, puis développez **Page par défaut**.
1. Sélectionnez le bouton représentant des points de suspension en regard de **Emplacement du pied de page**, et sélectionnez **Ajouter un fragment** ensuite.
1. Sélectionnez le fragment créé précédemment, puis sélectionnez **Sélectionner**.
1. Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.

Le pied de page qui contient l'avis de droits d'auteur s'affiche automatiquement au bas de toutes les pages qui utilisent le modèle sélectionné.

## <a name="additional-resources"></a>Ressources supplémentaires

[Ajouter un logo](add-logo.md)

[Sélectionner un thème pour le site](select-site-theme.md)

[Utilisation de fichiers de remplacement CSS](css-override-files.md)

[Ajouter une icône de favori](add-favicon.md)

[Ajouter un message de bienvenue](add-welcome-message.md)

[Ajouter des langues à votre site](add-languages-to-site.md)

[Ajout d'un code de script aux pages de site pour prendre en charge la télémétrie](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]