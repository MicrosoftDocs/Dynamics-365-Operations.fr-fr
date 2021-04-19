---
title: Paramétrer un entrepôt
description: Cette rubrique décrit comment paramétrer un entrepôt à utiliser avec un nouveau canal dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 154ec719e16e4826b0e24deb5ecadf587d938e3c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800493"
---
# <a name="warehouse-set-up"></a>Paramétrer un entrepôt

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment paramétrer un entrepôt à utiliser avec un nouveau canal dans Microsoft Dynamics 365 Commerce.

Chaque canal Commerce requiert un entrepôt configuré pour lui être associé. Les procédures suivantes fournissent la configuration minimale requise pour paramétrer un entrepôt pour un canal Commerce. Pour plus d’informations sur le paramétrage de l’entrepôt, veuillez consulter la [Vue d’ensemble de gestion des entrepôts](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).

## <a name="configure-a-warehouse-site"></a>Configurer un site d’entrepôt

Avant de paramétrer un entrepôt, vous devez configurer un site d’entrepôt.

Pour configurer un site d’entrepôt, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Sites**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le champ **Site**, entrez une valeur.
1. Dans le champ **Nom**, entrez une valeur.
1. Dans la section **Général**, définissez le **Fuseau horaire** adéquat.
1. Dans la section **Adresses**, entrez une adresse.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

L’image suivante présente un exemple de site d’entrepôt.

![Exemple de site d’entrepôt](media/warehouse-site.png)

## <a name="set-up-a-warehouse"></a>Paramétrer un entrepôt

Pour paramétrer un entrepôt, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Entrepôts**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le champ **Entrepôt**, saisissez une valeur.  S’il s’agit d’un mappage 1:1 avec un magasin, envisagez d’utiliser le nom du magasin ou le nom d’un centre de distribution régional.
1. Dans le champ **Nom**, entrez une valeur.
1. Dans la liste déroulante **Site**, sélectionnez un site d’entrepôt créé précédemment.
1. Dans le champ **Type**, sélectionnez **Par défaut**.
    - Si vous souhaitez définir un **Entrepôt de contrôle**, vous devez d’abord suivre ces étapes pour créer un entrepôt supplémentaire dans lequel **Type** est réglé sur **Contrôle**.
    - Si vous souhaitez définir un **Entrepôt de transit**, vous devez d’abord suivre ces étapes pour créer un entrepôt supplémentaire dans lequel **Type** est réglé sur **Transit**.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

## <a name="set-up-inventory-aisles"></a>Paramétrer les allées de stock

Pour paramétrer des allées de stockage, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Paramétrage d’emplacement \> Allées de stockage**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la liste déroulante **Entrepôt**, sélectionnez l’entrepôt créé précédemment.
1. Entrez un nom dans le champ **Allée** (par exemple « Déf »).
1. Entrez un nom dans le champ **Nom** (par exemple « Allée par défaut »).
1. Dans le volet Actions, sélectionnez **Enregistrer**.

## <a name="set-up-warehouse-inventory-locations"></a>Paramétrer des emplacements de stockage d’entrepôt

Pour paramétrer des emplacements de stockage d’entrepôt pour le stock standard, endommagé et retourné, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Entrepôts**.
1. Sélectionnez l’entrepôt que vous avez précédemment créé.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans le volet Actions, sélectionnez **Entrepôt**, puis sélectionnez **Emplacement de stockage**.
1. Dans le volet Actions, sélectionnez **Nouveau**. La liste déroulante **Entrepôt** devrait par défaut être celle de votre nouvel entrepôt.
    1. Dans la zone **Allée**, entrez le nom de l’allée que vous avez spécifiée précédemment. 
    1. Paramétrez **Mise à jour manuelle** sur **Oui**
    1. Dans la zone **Emplacement**, entrez le nom de l’entrepôt.
    1. Dans le volet Actions, sélectionnez **Enregistrer**.
 1. Dans le volet Actions, sélectionnez **Nouveau**.  La liste déroulante **Entrepôt** devrait par défaut être celle de votre nouvel entrepôt.
    1. Dans la zone **Allée**, entrez le nom de l’allée que vous avez spécifiée précédemment.  
    1. Paramétrez **Mise à jour manuelle** sur **Oui**
    1. Dans la zone **Emplacement**, entrez « Endommagé ».
    1. Dans le volet Actions, sélectionnez **Enregistrer**.
 1. Dans le volet Actions, sélectionnez **Nouveau**.  La liste déroulante **Entrepôt** devrait par défaut être celle de votre nouvel entrepôt.
    1. Dans la zone **Allée**, entrez le nom de l’allée que vous avez spécifiée précédemment. 
    1. Paramétrez **Mise à jour manuelle** sur **Oui**
    1. Dans la zone **Emplacement**, entrez « Retours ».
    1. Dans le volet Actions, sélectionnez **Enregistrer**.
    
L’image suivante montre une configuration de l’emplacement de stockage de l’entrepôt de San Francisco.

![Exemple de configuration d’emplacement de stockage](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a>Paramétrage d’entrepôt complet

Pour terminer le paramétrage de l’entrepôt, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Entrepôts**.
1. Sélectionnez l’entrepôt que vous avez précédemment créé.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Sous **Gestion des entrepôts et des stocks** :
    1. Paramétrez **Emplacement de réception par défaut** sur l’emplacement par défaut créé ci-dessus.
    1. Sélectionnez **Emplacement de sortie par défaut** sur l’emplacement par défaut créé ci-dessus.
1. Sous la section **Adresses**, entrez une adresse d’entrepôt.
1. Sous la section **Vente au détail** : 
    1. Dans la zone **Emplacement de retour par défaut**, entrez l’emplacement de retour créé précédemment.
    1. Paramétrez **Magasin** sur **Oui**.
    1. Paramétrez **Poids** sur **1,00**. 
    1. Dans la zone **Dimensions de stockage**, entrez l’emplacement par défaut créé précédemment.
1. Sous la section **Entrepôt**, paramétrez **Stock physique négatif** sur **Oui**.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

L’image suivante montre les détails d’un entrepôt configuré.

![Exemple d’entrepôt configuré](media/warehouse-sample.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de gestion des entrepôts](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json)

[Présentation des canaux](channels-overview.md)

[Conditions préalables au paramétrage du canal](channels-prerequisites.md)

[Paramétrer un canal de vente au détail](channel-setup-retail.md)
    
[Paramétrer un canal en ligne](channel-setup-online.md)

[Paramétrer un canal de centre d’appels](channel-setup-callcenter.md)







[!INCLUDE[footer-include](../includes/footer-banner.md)]
