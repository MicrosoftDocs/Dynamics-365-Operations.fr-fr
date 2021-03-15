---
title: Ajouter une page de stratégie de confidentialité
description: Cette rubrique décrit comment ajouter une page de stratégie de confidentialité à votre site dans Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0a9e09a1d0dbd6c0dc94b5668bb29de6605e2ca9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980205"
---
# <a name="add-a-privacy-policy-page"></a>Ajouter une page de stratégie de confidentialité


[!include [banner](includes/banner.md)]

Cette rubrique décrit comment ajouter une page de stratégie de confidentialité à votre site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Le respect de la confidentialité comprend des mesures organisationnelles qui informent les utilisateurs du site sur la façon dont leurs données sont collectées et traitées. Les utilisateurs peuvent alors décider comment ils souhaitent que leurs données personnelles soient traitées et peuvent prendre les mesures appropriées.

## <a name="review-the-microsoft-privacy-statement-in-dynamics-365-commerce"></a>Consulter la Déclaration de confidentialité Microsoft dans Dynamics 365 Commerce

Pour consulter la Déclaration de confidentialité Microsoft lorsque vous êtes connecté aux outils de création Dynamics 365 Commerce, cliquez sur le bouton **Aide** (**?**) dans le coin supérieur droit, puis sélectionnez **Confidentialité et cookies**. Un nouvel onglet s’ouvre avec un lien vers la [Déclaration de confidentialité Microsoft](https://privacy.microsoft.com/privacystatement).

## <a name="build-a-privacy-policy-page-for-your-site"></a>Générer une page de stratégie de confidentialité pour votre site

Dans Dynamics 365 Commerce, il existe plusieurs façons de permettre aux utilisateurs de votre site d’accéder à votre stratégie de confidentialité. Cette section montre comment créer une page de stratégie de confidentialité, puis référencer la page à l’aide d’un fragment de pied de page.

Les conseils qui suivent sont un exemple qui montre comment créer une page de stratégie de confidentialité générique pour un site Commerce. Vous êtes responsable de la conception et de la mise en œuvre d’une solution de page de stratégie de confidentialité qui répond le mieux aux exigences légales de votre entreprise.

Pour commencer, dans les outils de création, accédez au site pour lequel vous souhaitez créer une page de stratégie de confidentialité.

### <a name="create-a-template"></a>Créer un modèle

> [!NOTE]
> Si un modèle pouvant être utilisé pour la page de stratégie de confidentialité a déjà été créé, passez directement à la section [Créer une page de stratégie de confidentialité](#build-a-privacy-policy-page).

Pour créer un modèle, procédez comme suit.

1. Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un modèle de page.
1. Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle de bannière promotionnelle**, puis cliquez sur **OK**.
1. Dans le modèle, ajoutez tous les modules requis aux emplacements de page requis. Pour vous guider, passez la souris sur les points d’exclamation rouges. (Par exemple, l’emplacement **En-tête HTML** peut nécessiter un module de **Script externe par défaut**.)
1. Dans l’emplacement **Corps**, ajoutez un module de **Page par défaut**.
1. Dans le module **Page par défaut**, à l’emplacement **Principal**, ajoutez un module de **Bloc de contenu riche**.
1. Dans le module **Bloc riche en contenu**, ajoutez un module **Élément de bloc riche en contenu**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.

### <a name="build-a-privacy-policy-page"></a>Générer une page de stratégie de confidentialité

Pour générer une page de stratégie de confidentialité, procédez comme suit.

1. Accédez à **Pages**, puis cliquez sur **Nouveau** pour créer une page.
1. Dans la boîte de dialogue **Choisir un modèle**, sélectionnez le modèle de la page de politique de confidentialité.
1. Entrez le nom et l’URL d’une page, puis sélectionnez **OK**. 
1. À l’emplacement **Principal** de la page, ajoutez un module **Bloc de contenu riche**.
1. Dans le module **Bloc riche en contenu**, ajoutez un module **Élément de bloc riche en contenu**.
1. Dans le volet des propriétés du module **Bloc riche en contenu**, sélectionnez **Ajouter une source de données**, puis sélectionnez **Contenu en texte enrichi**.
1. Dans l’éditeur de texte enrichi, entrez le contenu de la page de stratégie de confidentialité. Développez l’éditeur de texte enrichi en mode plein écran selon vos besoins.
1. Une fois le contenu saisi, sélectionnez **Aperçu** pour prévisualiser la page dans le navigateur web.
1. Effectuez tous les ajouts restants aux propriétés de la page et du module.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

Pour publier l’URL de la page de stratégie de confidentialité, procédez comme suit.

1. Allez à **URL** et sélectionnez l’URL de la page de stratégie de confidentialité.
1. Sélectionnez **Publier** pour publier l’URL sélectionnée.

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a>Créer un lien vers la page de stratégie de confidentialité dans un pied de page

Vous pouvez ajouter un lien vers la page de stratégie de confidentialité à un fragment. De cette façon, vous pouvez partager le lien et le mettre à jour sur plusieurs pages de site en référençant le fragment. Cet exemple montre comment ajouter un lien vers la page de stratégie de confidentialité à un fragment de pied de page.

Pour ajouter un lien à un fragment de pied de page, procédez comme suit.

1. Accédez à **Fragments**, puis cliquez sur **Nouveau** pour créer un fragment de page.
1. Dans la boîte de dialogue **Nouveau fragment**, sélectionnez le module **Pied de page**.
1. Sous **Nom du fragment**, entrez un nom pour le fragment, puis sélectionnez **OK**.
1. Dans l’emplacement **Catégorie de pied de page**, ajoutez un module **Élément de pied de page**.
1. Dans le volet de propriétés de droite, sélectionnez **Texte du lien**.
1. Dans la boîte de dialogue **Texte du lien**, entrez le texte du lien et la cible du lien de la page de stratégie de confidentialité, puis cliquez sur **OK**.
1. Pour obtenir l’URL de la page de stratégie de confidentialité, accédez à **Pages**, accédez à la page de stratégie de confidentialité et copiez l’URL à partir du volet des propriétés.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le fragment, puis **Publier** pour le publier.
1. Prévisualisez le fragment et testez le lien vers la page de la stratégie de confidentialité.

Le fragment peut maintenant être référencé dans le modèle pour d’autres pages de site. Lorsque ce fragment est référencé dans le module **Pied de page** d’un modèle, la référence du lien apparaîtra sur toutes les pages créées à l’aide de ce modèle.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la conformité](compliance-overview.md)

[Fonctionnalités d’accessibilité](accessibility.md)

[Conformité des cookies](cookie-compliance.md)

[Remplacer les ID utilisateur associés aux modifications de contenu suivies](replace-IDs-tracked-changes.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]