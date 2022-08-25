---
title: Synchroniser à la demande avec le moteur de tarification de Supply Chain Management
description: Cet article décrit comment utiliser le moteur de tarification dans Microsoft Dynamics 365 Supply Chain Management depuis Microsoft Dynamics 365 Sales.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 727e60ceee3f5c8c33d2da93128eedc1dc7bcb9f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288952"
---
# <a name="sync-on-demand-with-the-supply-chain-management-pricing-engine"></a>Synchroniser à la demande avec le moteur de tarification de Supply Chain Management

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management comprend un moteur de tarification qui gère les accords commerciaux, les listes de prix, les programmes de fidélisation de la clientèle, les promotions et les remises. Le moteur de tarification utilise des règles complexes pour déterminer le meilleur prix pour une offre ou une commande donnée. Lorsque vous utilisez la double écriture, vous utilisez la tarification statique ou le moteur de tarification de Supply Chain Management sur les pages **Devis** et **Commande** dans Microsoft Dynamics 365 Sales.

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a>Utiliser le moteur de tarification de Supply Chain Management dans Sales

1. Dans Sales, accédez à **Ventes \> Commandes**.
1. Sélectionnez **Nouveau** pour créer une commande, ou sélectionnez une commande existante dans la liste **Mes commandes**.
1. Ajoutez une nouvelle ligne de commande.
1. Si vous créez une commande, sélectionnez **Ordre de prix** sur le volet Action. Si vous mettez à jour une commande existante, sélectionnez **Recalculer** sur le volet Actions.
1. Les colonnes suivantes sont complétées automatiquement :

    - Montant détaillé
    - Remise %
    - Remise
    - Montant avant le transport
    - Montant du transport
    - Total des taxes
    - Montant total

> [!NOTE]
> Un processus similaire s’applique lorsque vous créez des devis.

## <a name="how-it-works"></a>Comment ça fonctionne

Lorsque vous créez une commande dans Sales, cette commande est immédiatement synchronisée avec Supply Chain Management à l’aide des valeurs que vous avez saisies dans Sales. Lorsque vous sélectionnez **Ordre de prix** ou **Devis** dans Sales, Supply Chain Management calcule le prix de chaque ligne de commande et la commande totale, en fonction des règles de l’accord commercial définies dans Supply Chain Management. Les nouvelles valeurs calculées sont ensuite synchronisées avec Sales.

## <a name="set-trade-agreement-evaluation-options-in-supply-chain-management"></a>Définir les options d’évaluation des accords commerciaux dans Supply Chain Management

Vous pouvez configurer Supply Chain Management pour respecter ou ignorer les accords commerciaux lorsqu’il calcule le prix d’une commande créée dans Sales. Procédez comme suit pour configurer cette option.

1. Connectez-vous à votre environnement Supply Chain Management.
1. Accédez à **Comptabilité client \> Configuration \> Paramètres de la comptabilité client**.
1. Sur l’onglet **Prix**, sur le raccourci **Évaluation des accords commerciaux**, ajoutez ou supprimez la ligne pour la stratégie de **Saisie manuelle** selon vos besoins. La présence ou l’absence de cette stratégie contrôle si le moteur de tarification de Supply Chain Management annule automatiquement le prix de vente qui a été saisi dans Sales.

    - Si la stratégie de **Saisie manuelle** *n’est pas* présente dans la configuration **Évaluation des accords commerciaux**, Supply Chain Management est le maître des prix. Lorsqu’un utilisateur sélectionne **Ordre de prix** ou **Devis** dans le volet Actions de Sales, le moteur de tarification de Supply Chain Management est appelé et le prix de vente saisi dans Sales est remplacé, sauf s’il est égal au prix de vente calculé dans Supply Chain Management.
    - Si la stratégie de **Saisie manuelle** *n’est pas* présente dans la configuration **Évaluation des accords commerciaux**, Sales est le maître des prix. Le prix de vente qui a été saisi dans Sales ne peut pas être automatiquement remplacé lorsqu’un utilisateur sélectionne **Ordre de prix** ou **Devis** dans le volet Actions de Sales.
    - Les lignes de commande et les lignes de devis qui ont une valeur **Prix par unité** et/ou **Remise** de *0* (zéro) dans Sales sont traitées comme un cas particulier. Si un prix d’accord commercial pertinent est disponible, Supply Chain Management l’appliquera *toujours* à ces champs, quel que soit la configuration **Évaluation des accords commerciaux**.

    Pour un exemple de chacun de ces cas, consultez les scénarios qui suivent.

## <a name="example-scenario-1-trade-agreement-evaluation-without-the-manual-entry-option"></a>Exemple de scénario 1 : Évaluation des accords commerciaux sans l’option Saisie manuelle

Dans ce scénario, la configuration **Évaluation des accords commerciaux** dans Supply Chain Management *n’* inclut pas la stratégie de **Saisie manuelle**. Un utilisateur Sales saisit une ligne de commande dont le prix de vente est différent de zéro dans Sales et aucun prix de vente n’est défini pour l’article dans Supply Chain Management.

1. Dans Sales, un utilisateur crée une ligne de commande avec une valeur **Prix par unité** de 1 dollar américain (USD).
1. La ligne de commande est synchronisée avec Supply Chain Management avec un prix de vente de 1 USD.
1. Dans Sales, l’utilisateur sélectionne **Commande de prix** dans le volet Actions.
1. Supply Chain Management recherche les prix et remises pertinents, puis calcule les totaux. Étant donné que l’article n’a pas de prix de vente dans Supply Chain Management, le calcul met à jour la ligne afin qu’elle ait un prix de vente de 0 USD.
1. Le nouveau prix de vente de la ligne est synchronisé avec Sales.
1. Le résultat est une ligne de commande dans Sales avec un prix de vente de 0 USD.

## <a name="example-scenario-2-trade-agreement-evaluation-with-the-manual-entry-option"></a>Exemple de scénario 2 : Évaluation des accords commerciaux avec l’option Saisie manuelle

Dans ce scénario, la configuration **Évaluation des accords commerciaux** dans Supply Chain Management *n’* inclut pas la stratégie de **Saisie manuelle**. Un utilisateur Sales saisit une ligne de commande dont le prix de vente est différent de zéro dans Sales. Supply Chain Management comprend un accord commercial qui fixe un prix de vente de 2 USD pour l’article commandé.

1. Dans Sales, un utilisateur crée une ligne de commande pour un article avec une valeur **Prix par unité** de 1 dollar américain (USD).
1. La ligne de commande est synchronisée avec Supply Chain Management avec un prix de vente de 1 USD.
1. Dans Sales, l’utilisateur sélectionne **Commande de prix** dans le volet Actions.
1. Parce que la configuration **Évaluation des accords commerciaux** dans Supply Chain Management inclut la stratégie **Saisie manuelle**, le prix de vente n’est pas modifié, même si un accord commercial applicable spécifie un autre prix de vente.
1. Le prix de vente reste inchangé dans Sales et dans Supply Chain Management.

## <a name="example-scenario-3-trade-agreement-evaluation-for-an-item-that-has-a-sales-price-of-zero-in-sales"></a>Exemple de scénario 3 : évaluation d’un accord commercial pour un article dont le prix de vente est nul dans Sales

Dans ce scénario, la configuration **Évaluation des accords commerciaux** dans Supply Chain Management *n’* inclut pas la stratégie de **Saisie manuelle**. L’utilisateur Sales saisit une ligne de commande dont le prix de vente est 0 (zéro) dans Sales. Supply Chain Management comprend un accord commercial qui fixe un prix de vente de 2 USD pour un article commandé.

1. Dans Sales, un utilisateur crée une ligne de commande qui a une valeur **Prix par unité** définie sur 0 USD et une valeur **Remise de ligne** définie sur 0 USD.
1. La ligne de commande est synchronisée avec Supply Chain Management avec un prix de vente de 0 USD.
1. Étant donné qu’il a reçu une ligne de commande dont le prix de vente est de 0 (zéro), Supply Chain Management appelle son moteur de tarification, même si l’option **Saisie manuelle** est activée. Le moteur de tarification renvoie le prix de vente de 2 USD établi par l’accord commercial et met à jour la ligne de commande dans Supply Chain Management.
1. Le prix de vente mis à jour n’est pas encore synchronisé avec la ligne de commande dans Sales.
1. Dans Sales, l’utilisateur sélectionne **Commande de prix** dans le volet Actions.
1. La ligne de commande dans Supply Chain Management conserve son prix de vente de 2 USD, qui est désormais synchronisé avec Sales. Par conséquent, la valeur **Prix par unité** de la ligne de commande dans Sales est mise à jour de 0 USD à 2 USD.
1. Dans Sales, l’utilisateur saisit une nouvelle valeur **Remise de ligne** de 0,50 USD. Sales calcule maintenant que la valeur **Montant étendu** de la ligne est 1,50 USD.
1. La ligne de commande est synchronisée avec Supply Chain Management avec une valeur **Remise de ligne** de 0,50 USD.
1. Dans Sales, l’utilisateur sélectionne **Commande de prix** dans le volet Actions.
1. Aucun prix ou remise ne change pour la ligne de commande dans Sales.

## <a name="limitations"></a>Limitations

Lorsque les colonnes dans Sales sont remplies, les limitations suivantes s’appliquent :

- La configuration des frais et des allocations de frais dans Supply Chain Management n’est pas répliquée dans Sales.
- Les prix ne tiennent pas compte des prix de détail spéciaux spécifiés dans la colonne **Canal de vente au détail** sur la page de ligne de commande client dans Supply Chain Management.
- Les remises définies dans la section **Gestion des reprises** de Supply Chain Management ne sont pas prises en compte.
- La tarification ne tient pas compte des accords de vente.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
