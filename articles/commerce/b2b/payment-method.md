---
title: Configurer le mode de paiement du compte client pour les sites de commerce électronique B2B
description: Cette rubrique décrit comment configurer le mode de paiement du compte client pour les sites de commerce électronique interentreprises (B2B).
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 754e2f83d6c8ff5d3698d98062e54bba7ccd9836
ms.sourcegitcommit: f9df202aefef761be52c0360b0e22da88773914c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035906"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a>Configurer le mode de paiement du compte client pour les sites de commerce électronique B2B

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit comment configurer le mode de paiement du compte client pour les sites de commerce électronique interentreprises (B2B).

Les détaillants peuvent accepter différents types de paiement en échange des produits et des services qu’ils vendent dans un canal d'e-commerce. Chaque type de paiement accepté par le détaillant doit être configurée dans Microsoft Dynamics 365 Commerce lors du paramétrage du système. Le mode de paiement du compte client (ou « en compte ») doit être pris en charge sur les sites de commerce électronique B2B. 

## <a name="prerequisites"></a>Conditions préalables

1. Ajoutez le mode de paiement du compte client dans Commerce Headquarters.
2. Associez le mode de paiement du compte client au canal e-commerce.
3. Vérifiez que **Autoriser en compte** est activé pour le client dans **Retail et Commerce \> Clients \> Tous les clients \> Valeurs par défaut du paiement** dans Commerce Headquarters. Assurez-vous également que les paramètres **Limite de crédit** sont définis de manière appropriée pour le client dans **Retail et Commerce \> Clients \> Tous les clients \> Crédit et relances** dans Commerce Headquarters. 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a>Activer le mode de paiement du compte client dans le générateur de site Commerce 

Pour activer le mode de paiement du compte client dans le générateur de site Commerce, procédez comme suit :

1. Accédez à **Paramètres du site \> Extensions**.
1. Définissez la propriété **Activer les paiements du compte client** sur **Activé pour les clients B2B**. 
1. Sélectionnez **Enregistrer et publier**.

> [!NOTE]
> Les nouveaux paramètres de site ne prennent effet qu'après la mise à jour du fichier app.settings.json. Pour plus d’informations, voir [Mise à jour des kits de développement logiciel (SDK) et des bibliothèques de modules](../e-commerce-extensibility/sdk-updates.md).

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a>Activer le mode de paiement du compte client sur la page de paiement du site e-commerce B2B

Pour activer le mode de paiement du compte client sur la page de paiement du site e-commerce B2B, procédez comme suit :

1. Dans le générateur de site Commerce, recherchez et modifiez la page de paiement ou le fragment contenant le module de paiement du site de commerce électronique B2B.
1. Dans l'emplacement **Conteneur de section de caisse**, sélectionnez **Ajouter un module**, puis ajoutez un module **Paiement du compte client**.
1. Positionnez le module **Paiement du compte client** en sélectionnant les points de suspension (**...**), puis en sélectionnant **Déplacer vers le haut** ou **Déplacer vers le bas** selon les besoins.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a>Confirmer que le mode de paiement du compte client a été activé et publié

Pour confirmer que le mode de paiement du compte client a été activé et publié, procédez comme suit :

1. Connectez-vous au site d’e-commerce.
1. Ajoutez un produit dans le panier.
1. Allez sur la page de caisse. Vous devriez voir le nouveau mode de paiement **Compte client**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer un site d'e-commerce B2B](set-up-b2b-site.md)

[Créer des hiérarchies de modélisation organisationnelle pour les organisations B2B](org-model.md)

[Gérer les partenaires commerciaux sur les sites de commerce électronique B2B](manage-b2b-users.md)

[Définir des limites de quantité de produits pour les sites de commerce électronique B2B](quantity-limits.md)

[Mise à jour du kit de développement logiciel et de la bibliothèque de modules](../e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]