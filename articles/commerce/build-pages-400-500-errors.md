---
title: Établir des pages personnalisées de réponse pour les erreurs de code statut 4xx/5xx
description: Cet article décrit la procédure de création de pages de réponse personnalisées pour les erreurs de code statut 4xx et 5xx à l’aide des outils de création dans Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 4a3b1762cebc74c1b77f9ca60925608bc966e306
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276398"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a>Établir des pages personnalisées de réponse pour les erreurs de code statut 4xx/5xx

[!include [banner](includes/banner.md)]

Cet article décrit la procédure de création de pages de réponse personnalisées pour les erreurs de code statut 4xx et 5xx à l’aide des outils de création dans Microsoft Dynamics 365 Commerce.

Si une demande échoue, le serveur publie des réponses d’erreur du code statut HTTP. Le code statut 404 est capturé et renvoyé si une page est introuvable, et le code statut 500 est capturé et renvoyé si une erreur de serveur est produit. Dans Dynamics 365 Commerce, les utilisateurs de l’application peuvent générer les pages de réponse d’erreur du code statut personnalisées affichées aux utilisateurs pour ces réponses d’erreur du code statut.

## <a name="build-a-status-code-error-response-page"></a>Générer une page de réponse d’erreur du code statut

Pour commencer à générer une page de réponse d’erreur du code statut, procédez comme suit.

1. Dans votre navigateur web préféré, connectez-vous à Dynamics 365 Commerce. 
1. Sélectionnez le site pour lequel vous souhaitez créer une page de réponse d’erreur du code statut 4xx/5xx.

### <a name="build-the-template"></a>Générer le modèle

Pour générer le modèle pour une page de réponse d’erreur du code statut, procédez comme suit.

1. Accédez à **Modèles**.
1. Sélectionnez **Nouveau** pour créer un modèle de page.
1. Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez un nom pour le nouveau modèle, puis cliquez sur **OK**.
1. Paramétrez le modèle, selon la structure de votre choix que vous voulez que la page de réponse d’erreur du code statut ait.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier. 

### <a name="build-the-status-code-error-response-page"></a>Générer la page de réponse d’erreur du code statut

Pour générer la page de réponse d’erreur du code statut, procédez comme suit.

1. Accédez à **Pages**.
1. Sélectionnez **Nouveau** pour créer une page.
1. Dans la boîte de dialogue **Choisir un modèle**, sélectionnez un modèle, puis, sous **Nom de la page**, entrez un nom pour la page de réponse d’erreur du code statut. Laissez le champ **URL de la page** vide.
1. Générez la page.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

> [!NOTE]
> Vous pouvez créer des pages séparées de réponse d’erreur du code statut pour les erreurs du code statut 4xx et 5xx. Sinon, vous pouvez utiliser la même page générale de réponse d’erreur du code statut pour les deux catégories d’erreur.

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a>Paramétrer une redirection pour la page de réponse d’erreur du code statut

Pour configurer une redirection de la page de réponse d’erreur du code statut, procédez comme suit.

1. Accédez à **URL \> Nouveau \> Nouvel alias**, puis sélectionnez la page de réponse d’erreur du code statut que vous avez paramétrée auparavant.
1. Dans le champ **Alias**, entrez **default-4xx** ou **default-5xx**, en fonction de la page de réponse d’erreur du code statut pour laquelle vous paramétrez une redirection. Ces alias doivent être publiés. Sinon, la redirection ne fonctionnera pas.
1. Sélectionnez **OK** pour valider la liaison.

> [!NOTE]
> Si vous utilisez une seule page de réponse d’erreur du code statut pour les deux catégories d’erreur, répétez la procédure pour lier un alias pour l’autre catégorie d’erreur à la même page.

## <a name="additional-resources"></a>Ressources supplémentaires

[Utiliser des modèles](work-with-templates.md)

[Ajouter une nouvelle page de site](add-new-page.md)

[Créer une URL de page](create-page-url.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
