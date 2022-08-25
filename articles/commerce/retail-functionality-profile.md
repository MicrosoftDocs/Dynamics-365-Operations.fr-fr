---
title: Créer un profil de fonctionnalité de vente au détail
description: Cet article décrit comment créer un profil de fonctionnalité dans Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: f006aaf594f1df097f80c77794e34f9b831e9949
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280239"
---
# <a name="create-a-retail-functionality-profile"></a>Créer un profil de fonctionnalité de vente au détail

[!include [banner](includes/banner.md)]

Cet article décrit comment créer un profil de fonctionnalité dans Microsoft Dynamics 365 Commerce.

Le profil de fonctionnalité Commerce fournit divers paramètres utilisés pour les canaux en ligne. Chaque canal doit préciser un profil de fonctionnalité.

## <a name="create-a-functionality-profile"></a>Créer un profil de fonctionnalité

Pour créer un profil de fonctionnalité, procédez comme suit :

1. Dans le volet de navigation, accédez à **Modules \> Paramétrage du canal \> Profils POS \> Profils de fonctionnalité**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le champ **Profil**, saisissez un ID pour le profil (« FN006 » dans l’exemple d’image ci-dessous).
1. Dans le champ **Description**, saisissez une valeur (« Profil Adventure Works » dans l’exemple d’image ci-dessous).
1. Dans la section **Général**, sélectionnez un pays pour la valeur **ISO** locale.
1. Dans la section **Général**, modifiez les autres paramètres, si nécessaire.
1. Dans la section **Général**, sélectionnez un **ID profil du ticket de caisse** pour les tickets de caisse par e-mail.
1. Dans la section **Fonctions**, modifiez les autres paramètres, si nécessaire.
1. Dans la section **Montant**, modifiez les paramètres, si nécessaire.
1. Dans la section **Codes info**, modifiez les paramètres, si nécessaire.
1. Dans la section **Numérotation des tickets de caisse**, modifiez les paramètres, si nécessaire. 
  
L’image suivante présente un exemple de profil de fonctionnalité.
  
![Exemple de profil de fonctionnalité.](media/retail-functionality-profile.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Codes info et groupes de codes info](info-codes-retail.md)           

[Créer un carnet d’adresses](new-address-book.md) 

[Aperçu de la mise en page de l’écran](pos-screen-layouts.md)       

[Configuration et installation d’une station matérielle de vente au détail](retail-hardware-station-configuration-installation.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
