---
title: Créer un canal en ligne et définir les attributs du canal
description: Cette procédure décrit la création d'un canal en ligne et son ajout à la hiérarchie d'organisation.
author: jashanno
manager: AnnBe
ms.date: 06/04/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailSPOnlineStoreDetailPage, SysLookupMultiSelectGrid, DimensionLookup, OMHierarchyManager, HierarchyDesigner, OMNodeSelection, HierarchyPublishAndCloseForm
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8e92e28c721692ed92fa931ed899c48678622349
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964792"
---
# <a name="create-online-channel-and-define-channel-attributes"></a>Créer un canal en ligne et définir les attributs du canal

[!include [banner](../includes/banner.md)]

Cette procédure décrit la création d'un canal en ligne et son ajout à la hiérarchie d'organisation. Vous devez créer la hiérarchie d'organisation avant de créer un canal en ligne. La société fictive USRT sert d'exemple dans cette procédure.


## <a name="create-a-new-online-channel"></a>Créer un canal en ligne
1. Accédez à Commerce et vente au détail > Canaux > Magasins en ligne.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom.
4. Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.
5. Dans le champ Fuseau horaire du magasin, sélectionnez une option.
6. Dans le champ Client par défaut, saisissez ou sélectionnez une valeur.
7. Dans le champ Carnet d'adresses du client, saisissez ou sélectionnez une valeur.
8. Dans le champ Conditions de paiement, saisissez ou sélectionnez une valeur.
9. Entrez ou sélectionnez une valeur dans le champ Mode de paiement.
10. Dans le champ Profil de notification par e-mail, saisissez ou sélectionnez une valeur.
11. Développez la section Dimensions financières.
12. Dans le champ Unité commerciale, saisissez ou sélectionnez une valeur.
    * De même, définissez la valeur de toutes les autres dimensions par défaut.  
13. Cliquez sur Enregistrer.

## <a name="add-the-online-channel-to-organization-hierarchy"></a>Ajouter le canal en ligne à la hiérarchie d'organisation
1. Fermez la page.
2. Accédez à Administration d'organisation > Organisations > Hiérarchies d'organisation.
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
4. Cliquez sur Afficher.
5. Cliquez sur Modifier.
    * Vous pouvez sélectionner un nœud de hiérarchie sous lequel vous souhaitez insérer le nouveau canal.  
6. Cliquez sur Insérer
7. Cliquez sur canal de commerce.
8. Cliquez sur OK.
9. Cliquez sur Publier pour ouvrir l'écran de boîte de dialogue.
10. Entrez une date et une heure dans le champ Date d'effet.
11. Cliquez sur Publier.

## <a name="configure-orders-for-near-real-time-notification"></a>Configurez les commandes de la notification en temps quasi réel
1. Accédez à Commerce et vente au détail > Configuration du siège > Paramètres > Paramètres Commerce.
2. Définissez Utiliser le service en temps réel pour la création de commandes de commerce électronique sur « Oui ».
3. Exécutez le programme de distribution 1070 pour synchroniser les modifications avec la base de données des canaux. 




[!INCLUDE[footer-include](../../includes/footer-banner.md)]