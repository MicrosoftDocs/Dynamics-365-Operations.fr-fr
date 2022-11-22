---
title: Créer ou générer un lien vers un locataire Azure AD B2C existant dans le portail Azure
description: Cet article décrit comment créer ou insérer un lien vers un locataire Azure Active Directory (Azure AD) entreprise à consommateur (B2C) existant dans le portail Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 0aa12387f00ffc3dd10688c6385c7952f089ab12
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785249"
---
# <a name="create-or-link-to-an-existing-azure-ad-b2c-tenant-in-the-azure-portal"></a>Créer ou générer un lien vers un locataire Azure AD B2C existant dans le portail Azure

[!include [banner](includes/banner.md)]

Cet article décrit comment créer ou insérer un lien vers un locataire Azure Active Directory (Azure AD) entreprise à consommateur (B2C) dans le portail Microsoft Azure. Pour plus d’informations, voir [Didacticiel : Créer un client Azure Active Directory B2C](/azure/active-directory-b2c/tutorial-create-tenant).

Pour créer ou insérer un lien vers un locataire Azure AD B2C existant dans le portail Azure, suivez ces étapes.

1. Connectez-vous au [portail Azure](https://portal.azure.com/).
1. Dans le menu du portail Azure, sélectionnez **Créer une ressource**. Assurez-vous d’utiliser l’abonnement et le répertoire qui seront connectés à votre environnement Commerce.

    ![Créer une ressource dans le portail Azure.](./media/B2CImage_1.png)

1. Accédez à **Identité \> Azure Active Directory B2C**.
1. Une fois sur la page **Créer un locataire B2C ou lier à un locataire existant**, utilisez une des options ci-dessous qui répond le mieux aux besoins de votre entreprise :

    - **Créer un locataire Azure AD B2C** : utilisez cette option pour créer un locataire Azure AD B2C.
        1. Sélectionnez **Créer un locataire Azure AD B2C**.
        1. Sous **Nom de l’organisation**, entrez le nom de l’organisation.
        1. Sous **Nom de domaine initial**, entrez le nom de domaine initial.
        1. Pour **Pays ou région**, sélectionnez le pays ou la région.
        1. Sélectionnez **Créer** pour créer le locataire.

     ![Créer un locataire Azure AD.](./media/B2CImage_2.png)

     - **Lier un locataire Azure AD B2C existant à mon abonnement Azure** : utilisez cette option si vous avez déjà un locataire Azure AD B2C auquel vous souhaitez vous lier.
        1. Sélectionnez **Lier un locataire Azure AD B2C existant à mon abonnement Azure**.
        1. Pour **Locataire Azure AD B2C**, sélectionnez le locataire B2C approprié. Si le message « Aucun locataire B2C admissible trouvé » s’affiche dans la zone de sélection, vous n’avez pas de locataire B2C éligible existant et vous devez en créer un.
        1. Pour **Groupe de ressources**, sélectionnez **Créer**. Entrez un **Nom** pour le groupe de ressources qui contient le locataire, sélectionnez **Emplacement du groupe de ressources**, puis **Créer**.

    ![Lier un locataire Azure AD B2C existant à l’abonnement Azure.](./media/B2CImage_3.png)

1. Une fois le nouveau répertoire Azure AD B2C créé (cela peut prendre quelques instants), un lien vers le nouveau répertoire apparaît sur le tableau de bord. Ce lien vous emmène vers la page « Bienvenue dans Azure Active Directory B2C ».

    ![Lier au nouveau répertoire Azure AD](./media/B2CImage_4.png)

> [!NOTE]
> Si vous avez plusieurs abonnements dans votre compte Azure, ou si vous avez configuré le locataire B2C sans créer de lien vers un abonnement actif, une bannière **Résoudre les problèmes** vous demande d’associer le locataire à un abonnement. Sélectionnez le message de résolution du problème et suivez les instructions pour résoudre le problème d’abonnement.

L’image suivante montre un exemple d’une bannière Azure AD B2C **Résolution des problèmes**.

![Avertissement indiquant que le répertoire n’a pas d’abonnement actif.](./media/B2CImage_5.png)

## <a name="next-steps"></a>Étapes suivantes

Pour poursuivre la configuration d’un locataire B2C dans Commerce, passez à [Créer l’application B2C](create-b2c-app.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer un client B2C dans Commerce](set-up-b2c-tenant.md)

[Créer l’application B2C](create-b2c-app.md)

[Créer des stratégies de flux d’utilisateur](create-user-flow-policies.md)

[Ajouter des fournisseurs d’identité sociale (facultatif)](add-social-identity-providers.md)

[Mettre à jour Commerce Headquarters avec les nouvelles informations Azure AD B2C](update-hq-aad-b2c-info.md)

[Configurer votre locataire B2C dans le générateur de site Commerce](config-b2c-tenant-site-builder.md)

[Informations B2C supplémentaires](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
