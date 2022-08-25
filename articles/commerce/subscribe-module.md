---
title: Module d’abonnement
description: Cet article couvre les modules d’abonnement et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 7ea9364f77455e7189b6f8784eabb793f9b6bad6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268258"
---
# <a name="subscribe-module"></a>Module d’abonnement

[!include [banner](includes/banner.md)]

Cet article couvre les modules d’abonnement et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Les modules d’abonnement peuvent être utilisés sur les pages du site pour capturer des informations sur les clients pour des newsletters ou des promotions.

L’illustration suivante montre un exemple de module d’abonnement dans le pied de page de la page du site Adventure Works.

![Exemple de module d’abonnement dans le pied de page d’une page du site Adventure Works](./media/Subscribe.PNG)

> [!IMPORTANT]
> - Le module d’abonnement est disponible dans la bibliothèque du module Commerce dès la version Dynamics 365 Commerce 10.0.20.
> - Le module d’abonnement est présenté dans le thème Adventure Works.
> - Le module d’abonnement nécessite une extension d’action de données pour fonctionner avec certains fournisseurs de messagerie marketing, afin que la newsletter ou les e-mails promotionnels puissent être envoyés après la capture des informations client.

## <a name="subscribe-module-properties"></a>Propriétés du module d’abonnement

| Nom de la propriété | Valeurs | Description |
|---------------|--------|-------------|
| Titre       | Texte d’en-tête et balise d’en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Un en-tête de texte pour le module d’abonnement, tel que **Abonnez-vous à la newsletter** ou **Inscrivez-vous pour 10 % de réduction**. |
| Paragraphe     | Texte du paragraphe | Le module d’abonnement prend en charge le texte de paragraphe au format de texte enrichi, pour fournir des détails supplémentaires pour l’appel à l’action dans l’en-tête. |

## <a name="add-a-subscribe-module-to-a-new-page"></a>Ajouter un module d’abonnement à une nouvelle page

Pour ajouter un module de liste d’abonnement à une nouvelle page et définir les propriétés requises dans le générateur de site Commerce, procédez comme suit.

1. Accédez à **Modèles** et ouvrez le modèle marketing pour la page d’accueil de votre site (ou créez un nouveau modèle marketing).
1. Dans l’emplacement **Principal** de la page par défaut, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner les modules**, sélectionnez le module **S’abonner**, puis sélectionnez **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier.
1. Accédez à **Pages** et ouvrez la page d’accueil du site (ou créez une nouvelle page d’accueil à l’aide du modèle marketing).
1. À l’emplacement **Principal** de la page par défaut, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajoutez un module**.
1. Dans la boîte de dialogue **Sélectionner les modules**, sélectionnez le module **S’abonner**, puis sélectionnez **OK**.
1. Dans le volet des propriétés du module d’abonnement, ajoutez un en-tête, comme **S’abonner**.
1. Ajoutez du texte de paragraphe, par exemple **Dernières tendances, styles et promotions. Êtes-vous sur la liste ? Abonnez-vous et bénéficiez des dernières offres exceptionnelles !**
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.
1. Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Thème Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
