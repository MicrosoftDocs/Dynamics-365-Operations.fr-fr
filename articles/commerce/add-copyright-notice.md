---
title: Ajouter un avis de droits d’auteur
description: Cet article décrit la procédure d’ajout d’un avis de droits d’auteur à votre site web de commerce électronique.
author: josaw1
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 044fdd958a7233322553c8d9b03163c6ce5c4cb3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270453"
---
# <a name="add-a-copyright-notice"></a>Ajouter un avis de droits d’auteur

[!include [banner](includes/banner.md)]

Cet article décrit la procédure d’ajout d’un avis de droits d’auteur à votre site web de commerce électronique.

## <a name="prerequisites"></a>Conditions préalables

Avant de pouvoir ajouter un avis de droits d’auteur à votre site, vous devez avoir les options suivantes :

- Un modèle incluant un fragment de pied de page partagé.
- Une page qui utilise ce modèle.

## <a name="add-a-copyright-notice"></a>Ajouter un avis de droits d’auteur

Pour ajouter un avis de droits d’auteur au bas de chaque page qui utilise un modèle spécifique, procédez comme suit.

1. Accédez à **Fragments**, puis sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Nouveau fragment**, sélectionnez le module **Pied de page** et nommez le fragment. Par exemple, entrez **Pied de page - Droits d’auteur**.
1. Cliquez sur **OK**.
1. Dans le volet de navigation, sélectionnez le bouton représentant des points de suspension (**...**) en regard de **Pied de page**, et sélectionnez **Ajouter le module** ensuite.
1. Dans la boîte de dialogue, sélectionnez **Catégorie de pied de page**, puis sélectionnez **OK**.
1. Dans le volet de navigation, sélectionnez le bouton représentant des points de suspension en regard de **Catégorie de pied de page**, et sélectionnez **Ajouter le module** ensuite.
1. Dans la boîte de dialogue, sélectionnez **Bloc de texte**, puis sélectionnez **OK**.
1. Dans le volet de navigation, sélectionnez **Bloc de texte**.
1. Dans le volet de propriétés de droite, dans le champ **Paragraphe**, ajoutez le message sur les droits d’auteur. Par exemple, entrez **(C) Fabrikam 2019**.
1. Sélectionnez **Enregistrer**, sélectionnez **Terminer la modification**, puis sélectionnez **Publier**.
1. Accédez à **Modèles**, sélectionnez le modèle, puis sélectionnez **Modifier**.
1. Sous **Contour de la page**, développez **Corps**, puis développez **Page par défaut**.
1. Sélectionnez le bouton représentant des points de suspension en regard de **Emplacement du pied de page**, et sélectionnez **Ajouter un fragment** ensuite.
1. Sélectionnez le fragment créé précédemment, puis sélectionnez **Sélectionner**.
1. Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.

Le pied de page qui contient l’avis de droits d’auteur s’affiche automatiquement au bas de toutes les pages qui utilisent le modèle sélectionné.

## <a name="additional-resources"></a>Ressources supplémentaires

[Ajouter un logo](add-logo.md)

[Sélectionner un thème pour le site](select-site-theme.md)

[Utilisation de fichiers de remplacement CSS](css-override-files.md)

[Ajouter une icône de favori](add-favicon.md)

[Ajouter des langues à votre site](add-languages-to-site.md)

[Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
