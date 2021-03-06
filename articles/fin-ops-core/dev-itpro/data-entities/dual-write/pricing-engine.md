---
title: Synchroniser à la demande avec le moteur de tarification de Supply Chain Management
description: Cette rubrique décrit comment utiliser le moteur de tarification dans Microsoft Dynamics 365 Supply Chain Management depuis Dynamics 365 Sales.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: bf4154816f01040a236dde77b92ee69396158614
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750762"
---
# <a name="sync-on-demand-with-the-supply-chain-management-pricing-engine"></a>Synchroniser à la demande avec le moteur de tarification de Supply Chain Management

[!include [banner](../../includes/banner.md)]



Microsoft Dynamics 365 Supply Chain Management comprend un moteur de tarification qui gère les accords commerciaux, les listes de prix, les programmes de fidélisation de la clientèle, les promotions et les remises. Le moteur de tarification utilise des règles complexes pour déterminer le meilleur prix pour une offre ou une commande donnée. Lorsque vous utilisez la double écriture, vous utilisez la tarification statique ou le moteur de tarification de Dynamics 365 Supply Chain Management sur les pages Devis et Commande dans Dynamics 365 Sales.

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a>Utiliser le moteur de tarification de Supply Chain Management dans Sales

1. Dans Sales, accédez à **Ventes \> Commandes**.
2. Sélectionnez **Nouveau** pour créer une commande, ou sélectionnez une commande existante dans la liste **Mes commandes**.
3. Ajoutez une nouvelle ligne de commande.
4. Si vous créez une commande, sélectionnez **Ordre de prix** sur le volet Action. Si vous mettez à jour une commande existante, sélectionnez **Recalculer** sur le volet Actions.

    Les colonnes suivantes sont complétées automatiquement :

    + Montant détaillé
    + Remise %
    + Remise
    + Montant avant le transport
    + Montant du transport
    + Total des taxes
    + Montant total
    
5. Pour garantir que le système prend en compte les accords commerciaux et les contrats de vente pour calculer le prix :
    1. Accédez à votre environnement Supply Chain Management.
    2. Accédez à **Comptabilité client \> Configuration \> Paramètres de la comptabilité client**.
    3. Sélectionnez l’onglet **Prix** dans la barre de navigation latérale.
    4. Sous l’organisateur **Évaluation des accords commerciaux**, décochez l’option **Saisie manuelle**.

## <a name="how-it-works"></a>Comment ça fonctionne

Lorsque vous sélectionnez **Ordre de prix** dans Sales, la fonction **Totaux** sur l’onglet **Commande client \> Vue** dans Supply Chain Management est appelé pour la commande client associée. Les valeurs du total de la commande dans Sales sont utilisées pour remplir les colonnes correspondantes dans Supply Chain Management.

Lorsque le total de la commande client est calculé dans Supply Chain Management, le calcul évalue les accords commerciaux et les accords de vente existants pour le client et les produits répertoriés dans la commande client. Ces informations sont utilisées pour calculer les totaux. Quand **Ordre de prix** est sélectionné, Sales reflète automatiquement toute la configuration effectuée dans Supply Chain Management.

## <a name="limitations"></a>Limitations

Lorsque les colonnes dans Sales sont remplies, les limitations suivantes s’appliquent :

+ La configuration des frais et des allocations de frais dans Supply Chain Management n’est pas répliquée dans Sales.
+ Les prix ne tiennent pas compte des prix de détail spéciaux spécifiés dans la colonne **Canal de vente au détail** sur la page de ligne de commande client dans Supply Chain Management.
+ Les remises définies dans la section **Gestion des reprises** de Supply Chain Management ne sont pas prises en compte.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]