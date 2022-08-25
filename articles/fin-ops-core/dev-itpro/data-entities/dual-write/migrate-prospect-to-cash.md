---
title: Migrer les données de prospect en disponibilités de l’intégrateur de données vers la double écriture
description: Cet article décrit comment migrer les données de prospect en disponibilités de l’intégrateur de données vers la double écriture.
author: RamaKrishnamoorthy
ms.date: 02/01/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-26
ms.openlocfilehash: bbf5a7c2f409003816e2becf1a58ee7d7d5aafb2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289078"
---
# <a name="migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>Migrer les données de prospect en disponibilités de l’intégrateur de données vers la double écriture

[!include [banner](../../includes/banner.md)]

La solution Prospect en disponibilités disponible pour l’intégrateur de données n’est pas compatible avec la double écriture. La raison n’est autre que l’index msdynce_AccountNumber sur la table de compte fournie dans le cadre de la solution Prospect en disponibilités. Si cet index existe, vous ne pouvez pas créer le même numéro de compte client dans deux entités juridiques différentes. Vous pouvez soit choisir de repartir à neuf avec la double écriture en migrant les données Prospect en disponibilités de l’Intégrateur de données vers la double écriture, soit installer la dernière version « dormante » de la solution Prospect en disponibilités. Cet article couvre les deux approches.

## <a name="install-the-last-dorman-version-of-the-data-integrator-prospect-to-cash-solution"></a>Installer la dernière version « dormante » de la solution Prospect en disponibilités de l’intégrateur de données

**P2C Version 15.0.0.2** est considérée comme la dernière version « dormante » de la solution Prospect en disponibilités de l’intégrateur de données. Vous pouvez la télécharger depuis [FastTrack for Dynamics 365](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/P2C).

Vous devez l’installer manuellement. Après installation, tout reste exactement pareil, sauf que l’index msdynce_AccountNumber est supprimé.

## <a name="steps-to-migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>Étapes pour migrer les données de prospect en disponibilités de l’intégrateur de données vers la double écriture

Pour migrer vos données de prospect en disponibilités de l’intégrateur de données vers la double écriture, suivez ces étapes.

1. Exécutez les tâches de l’intégrateur de données de prospect en disponibilités pour effectuer une dernière synchronisation complète. De cette manière, vous vous assurez que les deux systèmes (applications de finances et d’opérations et applications de customer engagement) ont toutes les données.
2. Pour éviter toute perte de données potentielle, exportez les données de prospect en disponibilités de Microsoft Dynamics 365 Sales vers un fichier Excel ou un fichier de valeurs séparées par des virgules (CSV). Exportez les données des entités suivantes :

    - [Compte](#account-table)
    - [Contact](#contact-table)
    - [Facture](#invoice-table)
    - Facturation de produits
    - [Commande](#order-table)
    - [Commande de produits](#order-products-table)
    - [Produits](#products-table)
    - [Devis](#quote-and-quote-product-tables)
    - [Devis de produits](#quote-and-quote-product-tables)

3. Désinstallez la solution Prospect en disponibilités de l’environnement Ventes. Cette étape supprime les colonnes et les données correspondantes introduites par la solution Prospect en disponibilités.
4. Installez la solution de double écriture.
5. Créez une connexion de double écriture entre l’application de finances et d’opérations et l’application customer engagement pour une ou plusieurs entités juridiques.
6. Activez les mappages de table de double écriture et exécutez la synchronisation initiale pour les données de référence requises. (Pour plus d’informations, voir [Considérations pour la synchronisation initiale](initial-sync-guidance.md).) Les exemples de données requises comprennent les groupes de clients, les conditions de paiement et les programmes de paiement. N’activez pas les mappages de double écriture pour les tables qui nécessitent une initialisation, telles que les tables de compte, devis, ligne de devis, commande et ligne de commande.
7. Dans l’application customer engagement, accédez à **Paramètres avancés \> Paramètres système \> Gestion des données \> Règles de détection des doublons** et désactivez toutes les règles.
8. Initialisez les tables répertoriées à l’étape 2. Pour des instructions, consultez les sections restantes de cet article.
9. Ouvrez l’application de finances et d’opérations et activez les mappages de table, telles que les mappages de table de compte, devis, ligne de devis, commande et ligne de commande. Exécutez ensuite la synchronisation initiale. (Pour plus d’informations, voir [Considérations pour la synchronisation initiale](initial-sync-guidance.md).) Ce processus synchronisera les informations supplémentaires de l’application de finances et d’opérations, telles que le statut de traitement, les adresses d’expédition et de facturation, les sites et les entrepôts.

## <a name="account-table"></a>Table Compte

1. Dans la colonne **Société**, entrez le nom de la société, par exemple **USMF**.
2. Dans la colonne **Type de relation**, entrez **Client** comme une valeur statique. Vous ne souhaiterez peut-être pas classer chaque enregistrement de compte comme un client dans votre logique métier.
3. Dans la colonne **ID de groupe de clients**, entrez le numéro du groupe de clients de l’application de finances et d’opérations. La valeur par défaut de la solution Prospect en disponibilités est **10**.
4. Si vous utilisez la solution Prospect en disponibilités sans aucune personnalisation du **Numéro de compte**, entrez une valeur **Numéro de compte** dans la colonne **Numéro de partie**. S’il existe des personnalisations et que vous ne connaissez pas le numéro de partie, extrayez ces informations de l’application de finances et d’opérations.

## <a name="contact-table"></a>Table de contact

1. Dans la colonne **Société**, entrez le nom de la société, par exemple **USMF**.
2. Définissez les colonnes suivantes, en fonction de la valeur **IsActiveCustomer** du fichier CSV :

    - Si **IsActiveCustomer** est défini sur **Oui** dans le fichier CSV, définissez la colonne **Vendable** sur **Oui**. Dans la colonne **ID de groupe de clients**, entrez le numéro du groupe de clients de l’application de finances et d’opérations. La valeur par défaut de la solution Prospect en disponibilités est de **10**.
    - Si **IsActiveCustomer** est défini sur **Non** dans le fichier CSV, définissez la colonne **Vendable** sur **Non** et définissez la colonne **Contact pour** sur **Client**.

3. Si vous utilisez la solution Prospect en disponibilités sans aucune personnalisation du **Numéro de contact**, définissez les colonnes suivantes :

    - Migrez le numéro de contact du fichier CSV (**msdynce\_contactnumber**) vers le numéro de contact dans la table **Contact** (**msdyn\_contactnumber**).
    - Utilisez les valeurs de la table **Numéro de contact** dans la colonne **Numéro de partie**.
    - Utilisez les valeurs de la table **Numéro de contact** dans la colonne **Numéro de compte/ID personne à contacter**.

## <a name="invoice-table"></a>Table Facture

Comme les données de la table **Facture** sont conçues pour circuler dans un sens, de l’application de finances et d’opérations vers l’application customer engagement, l’initialisation n’est pas nécessaire. Exécutez la synchronisation initiale pour migrer toutes les données requises de l’application de finances et d’opérations vers l’application customer engagement. Pour plus d’informations, voir [Considérations pour la synchronisation initiale](initial-sync-guidance.md).

## <a name="order-table"></a>Table de commande

1. Dans la colonne **Société**, entrez le nom de la société, par exemple **USMF**.
2. Copiez la valeur de la colonne **ID commande** du fichier CSV dans la colonne **Numéro de commande client**.
3. Copiez la valeur de la colonne **Client** du fichier CSV dans la colonne **Numéro de facture du client**.
4. Copiez la valeur de la colonne **Pays/région d’expédition** du fichier CSV dans la colonne **Pays/région d’expédition**. Des exemples de cette valeur comprennent **US** et **États Unis**.
5. Définissez la colonne **Date de réception demandée**. Si vous n’utilisez pas de date de réception, utilisez les colonnes **Date de livraison demandée**, **Date d'exécution** et **Date d’envoi** du fichier CSV. Un exemple de cette valeur est **2020-03-27T00:00:00Z**.
6. Définissez la colonne **Langue**. Un exemple de cette valeur est **en-us**.
7. Définissez la colonne **Type de commande** en utilisant la colonne **Basé sur l’article**.

## <a name="order-products-table"></a>Table produits de commande

- Dans la colonne **Société**, entrez le nom de la société, par exemple **USMF**.

## <a name="products-table"></a>Table de produits

Comme les données de la table **Produits** sont conçues pour circuler dans un sens, de l’application de finances et d’opérations vers l’application customer engagement, l’initialisation n’est pas nécessaire. Exécutez la synchronisation initiale pour migrer toutes les données requises de l’application de finances et d’opérations vers l’application customer engagement. Pour plus d’informations, voir [Considérations pour la synchronisation initiale](initial-sync-guidance.md).

## <a name="quote-and-quote-product-tables"></a>Table Devis et Devis de produit

Pour la table **Devis**, suivez les instructions de la section [Table commande](#order-table) plus haut dans cet article. Pour la table **Devis de produit**, suivez les instructions de la section [Table produits de commande](#order-products-table) plus haut.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

