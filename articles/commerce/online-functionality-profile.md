---
title: Créer un profil de fonctionnalité en ligne
description: Cet article décrit comment créer un profil de fonctionnalité en ligne dans Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 686bc6440c31f3a4d729f2d92e3e57a1cc7b641f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895424"
---
# <a name="create-an-online-functionality-profile"></a>Créer un profil de fonctionnalité en ligne

[!include [banner](includes/banner.md)]

Cet article présente une vue d’ensemble de la configuration d’un profil de fonctionnalité en ligne pour Microsoft Dynamics 365 Commerce.

Le profil de fonctionnalité en ligne fournit divers paramètres utilisés pour les canaux en ligne. Chaque canal en ligne doit spécifier un profil de fonctionnalité en ligne.

## <a name="create-an-online-functionality-profile"></a>Créer un profil de fonctionnalité en ligne

La procédure suivante explique comment créer un profil de fonctionnalité en ligne à partir de l’application Commerce Headquarters.

1. Dans le volet de navigation, accédez à **Modules \> Paramétrage du canal \> Paramétrage du magasin en ligne \> Profils de fonctionnalité**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le champ **Profil**, saisissez un ID pour le profil.
1. Dans le champ **Description**, saisissez une valeur (« Profil Adventure Works » dans l’exemple d’image ci-dessous).
1. Dans la section **Fonctions**, modifiez les paramètres **PANIER**, **CLIENTS DE VENTE AU DÉTAIL** ou **CAISSE** si nécessaire.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

L’image suivante présente un exemple de profil de fonctionnalité en ligne.
  
![Exemple de profil de fonctionnalité en ligne.](media/online-functionality-profile.png)

## <a name="functions"></a>Fonctions

- **Produits agrégés** : si activée, cette fonction permet au panier de mettre à jour la quantité lorsque le même article est ajouté plusieurs fois.
- **Autoriser l’extraction sans paiement** : si activée, cette fonction gère le scénario lorsque les articles ajoutés au panier atteignent 0,00 $.
- **Créer un client en mode asynchrone** : paramètre hérité qui s’applique aux canaux de commerce électronique tiers et ne s’applique pas au site de commerce électronique Dynamics 365.

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation des canaux](channels-overview.md)

[Conditions préalables au paramétrage du canal](channels-prerequisites.md)

[Paramétrer un canal en ligne](channel-setup-online.md)

[Paramétrer un canal de vente au détail](channel-setup-retail.md)

[Paramétrer un canal de centre d’appels](channel-setup-callcenter.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
