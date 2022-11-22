---
title: Configurer un locataire B2C dans Commerce
description: Cet article décrit comment configurer vos locataires Azure Active Directory (Azure AD) B2C pour l’authentification du site de l’utilisateur dans Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 3421dd3d67198a99ac236a56cbb4f300cb591a03
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785135"
---
# <a name="set-up-a-b2c-tenant-in-commerce"></a>Configurer un locataire B2C dans Commerce

[!include [banner](includes/banner.md)]

Cet article décrit comment configurer vos locataires Azure Active Directory (Azure AD) B2C pour l’authentification du site de l’utilisateur dans Dynamics 365 Commerce.

Dynamics 365 Commerce fait appel à Azure AD B2C pour prendre en charge les flux d’informations d’identification et d’authentification des utilisateurs. Un utilisateur peut s’inscrire, se connecter et réinitialiser son mot de passe via ces flux. Azure AD B2C stocke les informations d’authentification sensibles d’un utilisateur, telles que son nom d’utilisateur et son mot de passe. L’enregistrement utilisateur du locataire B2C stocke un enregistrement de compte local B2C ou un enregistrement de fournisseur d’identité sociale B2C. Ces enregistrements B2C seront liés à l’enregistrement client dans l’environnement Commerce.

> [!WARNING] 
> Azure AD B2C supprimera les anciens flux d’utilisateurs (hérités) d’ici le 1er août 2021. Par conséquent, vous devez prévoir de migrer vos flux d’utilisateurs vers la nouvelle version recommandée. La nouvelle version offre la parité des fonctionnalités ainsi que de nouvelles fonctionnalités. La bibliothèque de modules pour Commerce version 10.0.15 ou supérieure doit être utilisée avec les flux d’utilisateurs B2C recommandés. Pour plus d’informations, voir [Flux d’utilisateurs dans Azure Active Directory B2C](/azure/active-directory-b2c/user-flow-overview).
 
 > [!NOTE]
 > Les environnements d’évaluation de Commerce sont fournis avec un locataire Azure AD B2C à des fins de démonstration. Il n’est pas nécessaire que vous chargiez votre propre locataire Azure AD B2C en suivant les étapes ci-dessous pour les environnements d’évaluation.

> [!TIP]
> Vous pouvez protéger davantage les utilisateurs de votre site et améliorer la sécurité de vos locataire B2C Azure AD avec la protection d’identité et l’accès conditionnel Azure AD. Pour passer en revue les capacités disponibles pour les locataires Azure AD B2C Premium P1 et Premium P2, voir [Protection de l’identité et accès conditionnel pour Azure AD B2C](/azure/active-directory-b2c/conditional-access-identity-protection-overview).

## <a name="dynamics-environment-prerequisites"></a>Prérequis de l’environnement dynamique

Avant de commencer, assurez-vous que votre environnement Dynamics 365 Commerce et le canal de commerce électronique sont configurés de manière appropriée en remplissant les conditions préalables suivantes.

- Définissez la valeur **AllowAnonymousAccess** des opérations de PDV sur « 1 » dans Commerce Headquarters :
    1. Accédez aux **Opérations de PDV**.
    1. Dans la grille des opérations, cliquez avec le bouton droit de la souris et sélectionnez **Personnaliser**.
    1. Sélectionnez **Ajouter un champ**.
    1. Dans la liste des colonnes disponibles, sélectionnez la colonne **AllowAnonymousAccess** pour l’ajouter.
    1. Sélectionnez **Mettre à jour**.
    1. Pour l’opération « Ajout de client » **612**, modifiez **AllowAnonymousAccess** sur « 1 ».
    1. Exécutez la tâche **1090 (Registres)**.
- Définissez l’attribut **Manuel** du compte client de la souche de numéros sur **Non** dans Commerce Headquarters :
    1. Accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres Comptabilité client**.
    1. Sélectionnez des **Souches de numéros**.
    1. Dans la ligne **Compte client**, double-cliquez sur la valeur **Code de souches de numéros**.
    1. Sur le raccourci **Général** de la souche de numéros, définissez **Manuel** sur **Non**.

Après le déploiement de votre environnement Dynamics 365 Commerce, il est également recommandé d’[Initialiser les données d’origine](enable-configure-retail-functionality.md) dans l’environnement.

## <a name="next-steps"></a>Étapes suivantes

Pour poursuivre la configuration d’un locataire B2C dans Commerce, passez à [Créer ou insérer un lien vers un locataire Azure AD B2C existant dans le portail Azure](create-link-aad-b2c-tenant.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Créer ou insérer un lien vers un locataire Azure AD B2C existant dans le portail Azure](create-link-aad-b2c-tenant.md)

[Créer l’application B2C](create-b2c-app.md)

[Créer des stratégies de flux d’utilisateur](create-user-flow-policies.md)

[Ajouter des fournisseurs d’identité sociale (facultatif)](add-social-identity-providers.md)

[Mettre à jour Commerce Headquarters avec les nouvelles informations Azure AD B2C](update-hq-aad-b2c-info.md)

[Configurer votre locataire B2C dans le générateur de site Commerce](config-b2c-tenant-site-builder.md)

[Informations B2C supplémentaires](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
