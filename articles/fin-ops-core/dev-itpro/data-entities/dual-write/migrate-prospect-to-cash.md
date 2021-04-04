---
title: Migrer les données de prospect en disponibilités de l'intégrateur de données vers la double écriture
description: Cette rubrique décrit comment migrer les données de prospect en disponibilités de l'intégrateur de données vers la double écriture.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/04/2021
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
ms.search.validFrom: 2021-01-04
ms.openlocfilehash: 93614e43b108671de686458887c1d6dd6fe04f7a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570562"
---
# <a name="migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>Migrer les données de prospect en disponibilités de l'intégrateur de données vers la double écriture

[!include [banner](../../includes/banner.md)]

Pour migrer vos données de prospect en disponibilités de l'intégrateur de données vers la double écriture, procédez comme suit.

1. Exécutez les tâches de l'intégrateur de données de prospect en disponibilités pour effectuer une dernière synchronisation complète. De cette manière, vous vous assurez que les deux systèmes (applications Finance and Operations et applications Customer Engagement) ont toutes les données.
2. Pour éviter toute perte de données potentielle, exportez les données de prospect en disponibilités de Microsoft Dynamics 365 Sales vers un fichier Excel ou un fichier de valeurs séparées par des virgules (CSV). Exportez les données des entités suivantes :

    - [Compte](#account-table)
    - [Contact](#contact-table)
    - [Facture](#invoice-table)
    - Produits de facture
    - [Commande](#order-table)
    - [Produits de la commande](#order-products-table)
    - [Produits](#products-table)
    - [Devis](#quote-and-quote-product-tables)
    - [Produits de devis](#quote-and-quote-product-tables)

3. Désinstallez la solution Prospect en disponibilités de l'environnement Sales. Cette étape supprime les colonnes et les données correspondantes introduites par la solution Prospect en disponibilités.
4. Installez la solution de double écriture.
5. Créez une connexion de double écriture entre l'application Finance and Operations et l'application Customer Engagement pour une ou plusieurs entités juridiques.
6. Activez les mappages de table de double écriture et exécutez la synchronisation initiale pour les données de référence requises. (Pour plus d'informations, voir [Considérations pour la synchronisation initiale](initial-sync-guidance.md).) Les exemples de données requises comprennent les groupes de clients, les conditions de paiement et les échéanciers de paiement. N'activez pas les mappages de double écriture pour les tables qui nécessitent une initialisation, telles que les tables de compte, devis, ligne de devis, commande et ligne de commande.
7. Dans l'application Customer Engagement, accédez à **Paramètres avancés \> Paramètres système \> Gestion des données \> Règles de détection des doublons** et désactivez toutes les règles.
8. Initialisez les tables répertoriées à l'étape 2. Pour obtenir des instructions, consultez les autres sections de cette rubrique.
9. Ouvrez l'application Finance and Operations et activez les mappages de table, telles que les mappages de table de compte, devis, ligne de devis, commande et ligne de commande. Exécutez ensuite la synchronisation initiale. (Pour plus d'informations, voir [Considérations pour la synchronisation initiale](initial-sync-guidance.md).) Ce processus synchronisera les informations supplémentaires de l'application Finance and Operations, telles que le statut de traitement, les adresses d'expédition et de facturation, les sites et les entrepôts.

## <a name="account-table"></a>Table Compte

1. Dans la colonne **Société**, entrez le nom de la société, par exemple **USMF**.
2. Dans la colonne **Type de relation**, entrez **Client** comme valeur statique. Vous ne souhaiterez peut-être pas classer chaque enregistrement de compte comme client dans votre logique métier.
3. Dans la colonne **ID de groupe de clients**, entrez le numéro du groupe de clients de l'application Finance and Operations. La valeur par défaut de la solution Prospect en disponibilités est **10**.
4. Si vous utilisez la solution Prospect en disponibilités sans aucune personnalisation du **Numéro de compte**, entrez une valeur **Numéro de compte** dans la colonne **Numéro de partie**. S'il existe des personnalisations et que vous ne connaissez pas le numéro de partie, extrayez ces informations de l'application Finance and Operations.

## <a name="contact-table"></a>Table Contact

1. Dans la colonne **Société**, entrez le nom de la société, par exemple **USMF**.
2. Définissez les colonnes suivantes, en fonction de la valeur **IsActiveCustomer** du fichier CSV :

    - Si **IsActiveCustomer** est défini sur **Oui** dans le fichier CSV, définissez la colonne **Vendable** sur **Oui**. Dans la colonne **ID de groupe de clients**, entrez le numéro du groupe de clients de l'application Finance and Operations. La valeur par défaut de la solution Prospect en disponibilités est **10**.
    - Si **IsActiveCustomer** est défini sur **Non** dans le fichier CSV, définissez la colonne **Vendable** sur **Non** et définissez la colonne **Contact pour** sur **Client**.

3. Si vous utilisez la solution Prospect en disponibilités sans aucune personnalisation du **Numéro de contact**, définissez les colonnes suivantes :

    - Migrez le numéro de contact du fichier CSV (**msdynce\_contactnumber**) vers le numéro de contact dans la table **Contact** (**msdyn\_contactnumber**).
    - Utilisez les valeurs de la table **Numéro de contact** dans la colonne **Numéro de partie**.
    - Utilisez les valeurs de la table **Numéro de contact** dans la colonne **Numéro de compte/ID personne à contacter**.

## <a name="invoice-table"></a>Table Facture

Comme les données de la table **Facture** sont conçues pour circuler dans un sens, de l'application Finance and Operations vers l'application Customer Engagement, l'initialisation n'est pas nécessaire. Exécutez la synchronisation initiale pour migrer toutes les données requises de l'application Finance and Operations vers l'application Customer Engagement. Pour plus d'informations, voir [Considérations pour la synchronisation initiale](initial-sync-guidance.md).

## <a name="order-table"></a>Table Commande

1. Dans la colonne **Société**, entrez le nom de la société, par exemple **USMF**.
2. Copiez la valeur de la colonne **ID de commande** du fichier CSV dans la colonne **Numéro de commande client**.
3. Copiez la valeur de la colonne **Client** du fichier CSV dans la colonne **Numéro de facture du client**.
4. Copiez la valeur de la colonne **Pays/région d'expédition** du fichier CSV dans la colonne **Pays/région d'expédition**. Des exemples de cette valeur comprennent **US** et **États Unis**.
5. Définissez la colonne **Date de réception demandée**. Si vous n'utilisez pas de date de réception, utilisez les colonnes **Date de livraison demandée**, **Date de traitement** et **Date d'envoi** du fichier CSV. Un exemple de cette valeur est **2020-03-27T00:00:00Z**.
6. Définissez la colonne **Langue**. Un exemple de cette valeur est **en-us**.
7. Définissez la colonne **Type de commande** en utilisant la colonne **Basé sur l'article**.

## <a name="order-products-table"></a>Table Produits de commande

- Dans la colonne **Société**, entrez le nom de la société, par exemple **USMF**.

## <a name="products-table"></a>Table Produits

Comme les données de la table **Produits** sont conçues pour circuler dans un sens, de l'application Finance and Operations vers l'application Customer Engagement, l'initialisation n'est pas nécessaire. Exécutez la synchronisation initiale pour migrer toutes les données requises de l'application Finance and Operations vers l'application Customer Engagement. Pour plus d'informations, voir [Considérations pour la synchronisation initiale](initial-sync-guidance.md).

## <a name="quote-and-quote-product-tables"></a>Table Devis et Produit de devis

Pour la table **Devis**, suivez les instructions de la section [Table Commande](#order-table) plus haut dans cette rubrique. Pour la table **Produit de devis**, suivez les instructions de la section [Table Produits de commande](#order-products-table) plus haut dans cette rubrique.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]