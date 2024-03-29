---
title: Prospect en disponibilités en double écriture
description: Cet article fournit des informations sur le prospect en disponibilités en double écriture.
author: RamaKrishnamoorthy
ms.date: 01/07/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 4321d980f56e321a653ca4f4c5738ebd1bb0153d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289606"
---
# <a name="prospect-to-cash-in-dual-write"></a>Prospect en disponibilités en double écriture

[!include [banner](../../includes/banner.md)]

Un objectif important de la plupart des entreprises consiste à convertir les prospects en clients, puis de maintenir une relation commerciale continue avec ces clients. Dans les applications Microsoft Dynamics 365, le processus prospect en disponibilités se fait via des flux de travail de traitement des commandes ou des devis, et les données financières sont rapprochées et reconnues. L’intégration de prospect en disponibilités à double écriture crée un flux de travail qui prend un devis et une commande provenant de Dynamics 365 Sales ou Dynamics 365 Supply Chain Management, et rend l’offre et la commande disponibles dans les deux applications.

Dans les interfaces de l’application, vous pouvez accéder en temps réel aux statuts de traitement et aux informations de facturation. Par conséquent, vous pouvez gérer plus facilement des fonctions telles que le stockage de produits, la gestion des stocks et l’exécution dans Supply Chain Management, sans avoir à recréer les devis et les commandes.

![Flux de données en double écriture dans les prospects en disponibilités.](../dual-write/media/dual-write-prospect-to-cash[1].png)

Pour plus d’informations sur l’intégration des clients et des contacts, voir [Données principales client intégrées](customer-mapping.md). Pour plus d’informations sur l’intégration de produit, voir [Expérience produit uniformisée](product-mapping.md).

> [!NOTE]
> Dans Dynamics 365 Sales, le prospect et le client font référence à un enregistrement dans la table **Compte** où la colonne **RelationshipType** est définie sur **Prospect** ou sur **Client**. Si votre logique métier inclut un processus de qualification **Compte** où l’enregistrement **Compte** est créé et qualifié d’abord en tant que prospect, puis en tant que client, cet enregistrement se synchronise avec l’application de finances et d’opérations uniquement lorsqu’il s’agit d’un client (`RelationshipType=Customer`). Si vous voulez que la ligne **Compte** se synchronise en tant que prospect, vous avez alors besoin d’une carte personnalisée pour intégrer les données du prospect.

## <a name="prerequisites-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

Avant de pouvoir synchroniser les devis de vente, vous devez mettre à jour les paramètres suivants.

### <a name="setup-in-sales"></a>Configuration dans Sales

Dans Sales, accédez à **Paramètres \> Administration \> Paramètres système \> Sales**, et assurez-vous que les paramètres suivants sont utilisés :

- L’option **Utiliser le système de calcul du prix du système** est définie **Oui**.
- La colonne **Mode de calcul de remise** est définie sur **Ligne article**.

### <a name="sites-and-warehouses"></a>Sites et entrepôts

Dans Supply Chain Management, les colonnes **Site** et **Entrepôt** sont obligatoires pour les lignes de devis et les lignes de commande. Si vous définissez le site et l’entrepôt dans les paramètres de commande par défaut, ces colonnes seront automatiquement définies lorsque vous ajoutez un produit à une ligne de devis ou à une ligne de commande. 

### <a name="number-sequences-for-quotations-and-orders"></a>Séquences de numéros pour les devis et les commandes

Les souches de numéros pour Supply Chain Management et Sales ne sont pas connectées lorsque les devis et les commandes sont créés et synchronisés dans Sales et Supply Chain Management. Si une commande client créée dans Sales est synchronisée avec Supply Chain Management, elle porte le même numéro de commande client dans Supply Chain Management. Pour vous assurer que le numéro de commande client n’est pas dupliqué, vous devez utiliser différents systèmes de souches de numéros dans les deux applications.

Par exemple, la souche de numéros dans Supply Chain Management est **1, 2, 3, 4, 5, ...** et la souche de numéros dans Sales est **100, 99, 98, ...**. Si vous créez 100 commandes client dans Sales, un numéro de commande sera éventuellement généré qui existe déjà dans Supply Chain Management. En d’autres termes, les deux souches de numéros finiront par se chevaucher à mesure que les commandes client sont créées dans Supply Chain Management et Sales. Au lieu de cela, vous pouvez utiliser une souche de numéros telle que **F1, F2, F3, ...** dans Supply Chain Management et une souche de numéros telle que **C1, C2, C3, ...** dans Sales. Ces souches de numéros ne produiront jamais de numéros de commande client en double.

## <a name="sales-quotations"></a>Devis de vente

Les devis sont créés dans Sales ou Supply Chain Management. Si vous créez un devis dans Sales, il est synchronisé avec Supply Chain Management en temps réel. De la même façon, si vous créez un devis dans Supply Chain Management, il est synchronisé avec Sales en temps réel. Notez les points suivants :

+ Vous pouvez ajouter une remise sur le produit sur le devis. Dans ce cas, la remise sera synchronisée avec Supply Chain Management. Les colonnes **Remise**, **Frais** et **Taxe** sont de l’en-tête sont contrôlés par un paramétrage complexe dans Supply Chain Management. Ce paramétrage ne prend pas en charge la mise en correspondance d’intégration. En lieu et place, les colonnes **Prix**, **Remise**, **Charge** et **Taxe** sont préservés et gérés dans Supply Chain Management.
+ Les colonnes **% de remise**, **Remise** et **Volume de transport** sur l’en-tête de devis sont en lecture seule uniquement.
+ Les colonnes **Conditions de transport**, **Conditions de livraison**, **Méthode d’expédition** et **Mode de distribution** ne font pas partie des mises en correspondance par défaut. Pour mettre en correspondance ces colonnes, vous devez paramétrer une mise en correspondance des valeurs spécifique aux données des organisations entre lesquelles la table est synchronisée.

Si vous utilisez également la solution Field Service, assurez-vous de réactiver le paramètre **Création rapide de ligne de devis**. La réactivation du paramètre vous permet de continuer à créer des lignes de devis à l’aide de la fonction de création rapide.

1. Accédez à votre application Dynamics 365 Sales.
2. Sélectionnez l’icône des paramètres dans la barre de navigation supérieure.
3. Sélectionnez **Paramètres avancés**.
4. Choisissez l’option **Personnalisez le système**.
5. Sélectionnez l’élément du menu **Ligne de devis**.
6. Allez à la section **Services de données** et cochez la case **Autoriser la création rapide**.

## <a name="sales-orders"></a>Commandes client

Les commandes client sont créées dans Sales ou Supply Chain Management. Si vous créez une commande client dans Sales, il est synchronisé avec Supply Chain Management en temps réel. De la même façon, si vous créez une commande client dans Supply Chain Management, il est synchronisé avec Sales en temps réel. Notez les points suivants :

+ Les produits hors catalogue sur Dynamics 365 Sales apparaîtront en tant que catégories de produits dans Dynamics 365 Supply Chain Management.
+ Calcul et arrondi de la remise :

    - Le modèle de calcul de la remise dans Sales diffère du modèle de calcul de la remise dans Supply Chain Management. Dans Supply Chain Management, le montant de remise final sur une ligne de vente peut être le résultat d’une combinaison des montants de remise et des pourcentages de remise. Si ce montant de remise final est divisé par la quantité de la ligne, un arrondi peut se produire. Toutefois, cet arrondi n’est pas pris en considération si un montant de la remise Par unité qui est arrondi est synchronisé avec Sales. Pour vous assurer que le montant de remise total d’une ligne de vente dans Supply Chain Management soit synchronisé correctement avec Sales, le montant total doit être synchronisé sans être divisé par la quantité de ligne. Par conséquent, vous devez définir le champ Mode de calcul de remise sur **Ligne article** dans Sales.
    - Lorsqu’une ligne de commande client est synchronisée entre Sales et Supply Chain Management, le montant de remise total est utilisé. Comme Supply Chain Management n’a pas de colonne pouvant enregistrer le montant de remise total pour une ligne, le montant est divisé par la quantité et enregistré dans le colonne **Remise ligne**. L’arrondi qui survient lors de cette division est stocké dans la colonne **Frais de vente** sur la ligne de vente.

### <a name="example-synchronization-from-sales-to-supply-chain-management"></a>Exemple : Synchronisation depuis Sales vers Supply Chain Management

Les commandes client disponibles sont les suivantes :

+ **Sales :** Quantité = 3, remise par ligne = 10,00 €
+ **Supply Chain Management :** Quantité = 3, montant de remise ligne = 3,33 EUR, frais de vente = -0,01 EUR

Si vous synchronisez de Supply Chain Management vers Sales, vous obtenez le résultat suivant :

+ **Supply Chain Management :** Quantité = 3, montant de remise ligne = 3,33 EUR, frais de vente = -0,01 EUR
+ **Sales :** Quantité = 3, remise par ligne = (3 × 3,33 €) + 0,01 € = 10,00 €

## <a name="dual-write-solution-for-sales"></a>Solution en double écriture pour Sales

De nouvelles colonnes sont ajoutées à la table **Commande** et s’affichent sur la page. La plupart de ces colonnes apparaissent sur l’onglet **Intégration** dans Sales. Pour en savoir plus sur le mappage des colonnes de statut, voir [Configurer le mappage pour les colonnes de statut de la commande client](sales-status-map.md).

+ Les boutons **Créer une facture** et **Annuler une commande** sur la page **Commande client** sont masquées dans Sales.
+ Le **Statut d’une commande client** restera **Actif** pour garantir que les modifications effectuées dans Supply Chain Management peuvent être répercutées dans la commande client avec Sales. Cette opération est contrôlée en définissant le paramètre par défaut **Statecode \[Statut\]** sur **Actif**.

## <a name="invoices"></a>Factures

Les factures sont créées dans Supply Chain Management et synchronisées vers Sales. Notez les points suivants :

+ Une colonne **Numéro de facture** a été ajouté à la table **Facture** et apparaît sur la page.
+ Le bouton **Créer une facture** sur la page **Commande client** est masqué car les factures sont créées dans Supply Chain Management et synchronisées avec Sales. La page **Facture** ne peut pas être modifiée car les factures sont synchronisées à partir de Supply Chain Management.
+ La valeur **Statut de la commande client** passe automatiquement à **Facturé** lorsque la facture concernée dans Supply Chain Management a été synchronisée avec Sales. En outre, le propriétaire de la commande client pour laquelle la facture a été créée est désigné propriétaire de la facture. Par conséquent, le propriétaire de la commande client peut afficher la facture.
+ Les colonnes **Conditions de transport**, **Conditions de livraison** et **Mode de distribution** ne sont pas incluses dans les mises en correspondance par défaut. Pour mettre en correspondance ces colonnes, vous devez paramétrer une mise en correspondance des valeurs spécifique aux données des organisations entre lesquelles la table est synchronisée.

## <a name="templates"></a>Modèles

Prospect en disponibilité comprend un ensemble de mappages de tables de base qui fonctionnent ensemble pendant l’interaction des données client, comme indiqué dans le tableau suivant.

| Applications de finances et d’opérations | Applications Customer Engagement | Description |
|-----------------------------|-----------------------------------|-------------|
[Tous les produits](mapping-reference.md#138) | msdyn_globalproducts | |
[Clients V3](mapping-reference.md#101) | comptes | |
[Clients V3](mapping-reference.md#116) | contacts | |
[Contacts V2](mapping-reference.md#221) | msdyn_contactforparties | |
[En-têtes de commande client CDS](mapping-reference.md#217) | salesorders | |
[Lignes de commande client CDS](mapping-reference.md#216) | salesorderdetails | |
[En-tête de devis de vente CDS](mapping-reference.md#215) | devis | |
[Lignes de devis de vente CDS](mapping-reference.md#214) | quotedetails | |
[Produits lancés V2](mapping-reference.md#189) | msdyn_sharedproductdetails | |
[En-têtes de facture client V2](mapping-reference.md#118) | factures | La table En-têtes de facture de vente V2 de l’application de finances et d’opérations contient des factures pour les commandes client et des factures en texte libre. Un filtre est appliqué dans Dataverse pour la double écriture qui filtrera tous les documents de facture financière. |
[Lignes de facture client V2](mapping-reference.md#117) | invoicedetails | |
[Codes d’origine des commandes client](mapping-reference.md#186) | msdyn_salesorderorigins | |

Pour plus d’informations sur les tarifs, voir [Expérience produit uniformisée](product-mapping.md).

## <a name="limitations"></a>Limitations

- Les commandes de retour ne sont pas prises en charge.
- Les notes de crédit ne sont pas prises en charge.
- Les dimensions financières doivent être définies pour les données principales, par exemple, client et fournisseur. Lorsqu’un client est ajouté à une offre ou à une commande client, les dimensions financières associées à l’enregistrement client sont automatiquement transmises à la commande. Actuellement, la double écriture n’inclut pas les données de dimensions financières pour les données principales.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

