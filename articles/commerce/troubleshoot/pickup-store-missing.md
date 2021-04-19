---
title: Le magasin de vente au détail n’apparaît pas dans la liste des magasins disponibles pour le retrait
description: Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsqu’un magasin de vente au détail n’apparaît pas dans la liste des magasins où les articles peuvent être retirés.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9974b3e10bbdcd2e8a8723a3be4b70401bb9e546
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801601"
---
# <a name="retail-store-doesnt-appear-in-the-list-of-stores-to-pick-up-from"></a>Le magasin de vente au détail n’apparaît pas dans la liste des magasins disponibles pour le retrait

[!include [banner](../../includes/banner.md)]

Cette rubrique fournit des conseils de résolution des problèmes qui peuvent aider lorsqu’un magasin de vente au détail n’apparaît pas dans la liste des magasins où les articles peuvent être retirés.

## <a name="description"></a>Description

Un magasin de détail n’apparaît pas dans la liste des magasins où les articles peuvent être retirés.

## <a name="resolution"></a>Résolution

### <a name="configure-the-longitude-and-latitude-for-the-store-address-in-commerce-headquarters"></a>Configurer la longitude et la latitude de l’adresse du magasin dans Commerce Headquarters

Pour configurer la longitude et la latitude de l’adresse du magasin dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Retail et Commerce \> Canaux \> Magasins \> Tous les magasins**.
1. Trouvez le magasin que vous souhaitez voir apparaître parmi les options de retrait sur le site d’e-commerce. Notez la valeur du champ **Numéro d’unité opérationnelle**.
1. Accédez à **Administration d’organisation \> Organisations \> Unités opérationnelles**.
1. Recherchez le numéro d’unité opérationnelle que vous avez noté précédemment, puis sélectionnez l’unité opérationnelle dans les résultats de la recherche.
1. Sur le raccourci **Adresses**, sélectionnez **Plus d’options**, puis sélectionnez **Avancé**.
1. Sur le raccourci **Général**, assurez-vous que les champs **Longitude** et **Latitude** sont correctement définis. Dans le cadre de cette étape, assurez-vous que les valeurs sont correctement spécifiées sous forme de nombres positifs ou négatifs.

### <a name="configure-fulfillment-groups-in-commerce-headquarters"></a>Configurer les groupes d’exécution dans Commerce Headquarters

Pour configurer les groupes d’exécution dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> Canaux \> Magasins en ligne**.
1. Sélectionnez le magasin en ligne à configurer.
1. Dans le volet Actions, sélectionnez **Paramétrer**, puis **Affectation du groupe d’exécution**.
1. Sur la page **Affectation du groupe d’exécution**, sélectionnez le groupe d’exécution pour le magasin en ligne.
1. Sous **Paramétrer**, assurez-vous que le magasin de vente au détail est correctement configuré pour le groupe d’exécution.

## <a name="additional-resources"></a>Ressources supplémentaires 

[Créer une unité opérationnelle](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit)

[Paramétrer un canal en ligne](../channel-setup-online.md)
