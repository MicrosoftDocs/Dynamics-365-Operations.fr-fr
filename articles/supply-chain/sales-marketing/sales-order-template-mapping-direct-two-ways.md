---
title: Synchronisation des commandes client directement entre Sales et Supply Chain Management
description: La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les commandes client directement depuis Dynamics 365 Sales et Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 05/09/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: eb41a21395a5d115b779e6b1ef71e9eb1176e28e
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8061516"
---
# <a name="synchronization-of-sales-orders-directly-between-sales-and-supply-chain-management"></a>Synchronisation des commandes client directement entre Sales et Supply Chain Management

[!include [banner](../includes/banner.md)]



La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les commandes client directement depuis Dynamics 365 Sales et Dynamics 365 Supply Chain Management.

## <a name="data-flow-in-prospect-to-cash"></a>Flux de données dans Prospect en disponibilités

La solution Prospect en disponibilités utilise la fonction d’intégration de données pour synchroniser les données entre plusieurs instances de Supply Chain Management et Sales. Les modèles de prospects en disponibilités disponibles avec la fonction d’intégration de données activent le flux de données relatifs aux comptes, contacts, produits, devis de vente, commandes client et factures client entre Supply Chain Management et Sales. L’illustration ci-dessous indique comment les données sont synchronisées entre Supply Chain Management et Sales.

[![Flux de données dans Prospect en disponibilités.](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modèles et tâches

Pour accéder à des modèles disponibles, ouvrez [Centre d’administrateur Power Apps](https://preview.admin.powerapps.com/dataintegration). Sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner les modèles publics.

Les modèles et les tâches sous-jacentes suivants sont utilisés pour exécuter la synchronisation des commandes client directement entre Sales et Supply Chain Management.

- **Noms des modèles dans l’intégration des données :** 

    - Commandes client (Sales vers Supply Chain Management) – Direct
    - Commandes client (Supply Chain Management vers Sales) – Direct

- **Noms des tâches dans le projet d’intégration de données :**

    - OrderHeader
    - OrderLine

Les tâches suivantes de synchronisation sont requises avant que la synchronisation des en-têtes et des lignes de factures client puisse avoir lieu :

- Produits (Supply Chain Management vers Sales) – Direct
- Comptes (Sales vers Supply Chain Management) – Direct (si utilisé)
- Contacts vers Customers (Sales vers Supply Chain Management) – Direct (si utilisé)

## <a name="entity-set"></a>Ensemble d’entités

| Gestion de la chaîne d’approvisionnement  | Vente             |
|-------------------------|-------------------|
| En-têtes de commande client de Dataverse | SalesOrders       |
| Lignes de commande client de Dataverse   | SalesOrderDetails |

## <a name="entity-flow"></a>Flux d’entité

Les commandes client sont créées dans Sales et synchronisées avec Supply Chain Management lorsque **Exécuter le projet** est déclenché pour un projet basé sur le modèle **Commandes client (entre Sales et Supply Chain Management) – Direct**. Vous pouvez uniquement activer et synchroniser des commandes client à partir de Sales uniquement si tous les **Produits de la commande** se composent entièrement de produits gérés en externe. Par conséquent, il ne peut y avoir aucun produit hors catalogue. Une fois que la commande est activée, la commande client passe en lecture seule dans l’interface utilisateur (UI). À ce stade, les mises à jour sont effectuées à partir de Supply Chain Management. Une fois qu’une commande client a un statut **Confirmé**, le projet basé sur le modèle **Commandes client (entre Supply Chain Management et Sales) – Direct** peut être utilisé pour synchroniser toutes les mises à jour ou le statut d’exécution entre Supply Chain Management et Sales.

Vous n’avez pas à créer de commandes dans Sales. Vous pouvez les créer dans Supply Chain Management à la place. Une fois qu’une commande client a un statut **Confirmé**, elle est synchronisée avec Sales comme indiqué dans le paragraphe précédent.

Dans Supply Chain Management, les filtres du modèle permettent de garantir que seules les commandes client appropriées sont incluses dans la synchronisation :

- Sur la commande client, la commande et la facturation client doivent provenir de Sales pour être incluses dans la synchronisation. Dans Supply Chain Management, les colonnes **OrderingCustomerIsExternallyMaintained** et **InvoiceCustomerIsExternallyMaintained** sont utilisées pour filtrer les commandes client des tables de données.
- La commande client dans Supply Chain Management doit être confirmée. Seules les commandes client confirmées ou les commandes client dont le statut de traitement le plus élevé, par exemple, **Livré** ou **Facturé**, sont synchronisées avec Sales.
- Après avoir créé ou modifié une commande client, le traitement par lots **Calcule les totaux de vente** dans Supply Chain Management doit être exécuté. Seules les commandes client où les totaux de vente sont calculés seront synchronisées avec Sales.

## <a name="freight-tax"></a>Taxe relative au transport

Sales ne prend pas en charge la taxe au niveau de l’en-tête, car la taxe est enregistrée au niveau de la ligne. Pour prendre en charge la taxe au niveau de l’en-tête à partir de Finances et Opérations, comme la taxe sur le transport, le système synchronise la taxe avec Sales comme un produit hors catalogue appelé **Taxe de transport**, et le montant de sa taxe provient de Supply Chain Management. Ainsi, le calcul standard du prix dans Sales peut être utilisé pour les totaux, même s’il existe une taxe au niveau de l’en-tête à partir de Supply Chain Management.

## <a name="discount-calculation-and-rounding"></a>Calcul et arrondi de la remise

Le modèle de calcul de la remise dans Sales diffère du modèle de calcul de la remise dans Supply Chain Management. Dans Supply Chain Management, le montant de remise final sur une ligne de vente peut être le résultat d’une combinaison des montants de remise et des pourcentages de remise. Si ce montant de remise final est divisé par la quantité de la ligne, un arrondi peut se produire. Toutefois, cet arrondi n’est pas pris en considération si un montant de la remise Par unité qui est arrondi est synchronisé avec Sales. Pour vous assurer que le montant de remise total d’une ligne de vente dans Supply Chain Management soit synchronisé correctement avec Sales, le montant total doit être synchronisé sans être divisé par la quantité de ligne. Par conséquent, vous devez définir le champ **Mode de calcul de remise** sur **Ligne article** dans Sales.

Lorsqu’une ligne de commande client est synchronisée entre Sales et Supply Chain Management, le montant de remise total est utilisé. Comme Supply Chain Management n’a pas de champ pouvant enregistrer le montant de remise total pour une ligne, le montant est divisé par la quantité et enregistré dans le champ **Remise ligne**. L’arrondi qui survient dans cette division est stocké dans le champ **Frais de vente** sur la ligne de vente.

### <a name="example"></a>Exemple

**Synchronisation depuis Sales vers Supply Chain Management**

- **Sales :** Quantité = 3, remise par ligne = 10,00 €
- **Supply Chain Management :** Quantité = 3, montant de remise ligne = 3,33 EUR, frais de vente = -0,01 EUR 

**Synchronisation depuis Supply Chain Management vers Sales**

- **Supply Chain Management :** Quantité = 3, montant de remise ligne = 3,33 EUR, frais de vente = -0,01 EUR
- **Sales :** Quantité = 3, remise par ligne = (3 × 3,33 €) + 0,01 € = 10,00 €

## <a name="prospect-to-cash-solution-for-sales"></a>Prospect pour une solution de disponibilités pour Sales

De nouvelles colonnes sont ajoutées à la table **Commande** et s’affichent sur la page :

- **Est conservé en externe** – Définissez cette option sur **Oui** lorsque la commande provient de Supply Chain Management.
- **Statut de traitement** – Cette colonne affiche le statut de traitement de la commande dans Supply Chain Management. Les valeurs disponibles sont les suivantes :

    - **Brouillon** – Statut initial lorsqu’une commande est créée dans Sales. Dans Sales, seules les commandes ayant ce statut de traitement peuvent être modifiées.
    - **Actif** – Statut une fois que la commande est activée dans Sales à l’aide du bouton **Activer**.
    - **Confirmée**
    - **Bon de livraison**
    - **Facturé**
    - **Prélevé**
    - **Partiellement prélevé**
    - **Partiellement emballé**
    - **Expédié**
    - **Partiellement expédié**
    - **Partiellement facturé**
    - **Annulé**

Le paramètre **A des produits mis à jour en externe uniquement** est utilisé durant l’activation de la commande pour effectuer le suivi uniformément si une commande client se compose entièrement de produits gérés en externe. Si une commande client se compose uniquement des produits gérés en externe, les produits sont mis à jour dans Supply Chain Management. Ceci permet de garantir que vous ne tenterez pas d’activer et de synchroniser les lignes de commandes client ayant des produits qui sont inconnus de Supply Chain Management.

Les boutons **Créer une facture**, **Annuler la commande**, **Recalculer**, **Obtenir des produits** et **Adresse de recherche** sur la page **Commande client** sont masqués pour les commandes gérées en externe, car les factures sont créées dans Supply Chain Management et synchronisées avec Sales. Ces commandes ne peuvent pas être modifiées, car les informations de commande client sont synchronisées à partir de Supply Chain Management après cette activation.

Le statut d’une commande client restera **Actif** pour garantir que les modifications effectuées dans Supply Chain Management peuvent être répercutées dans la commande client avec Sales. Cette opération est contrôlée en définissant le paramètre par défaut **Statecode \[Statut\]** sur **Actif** dans le projet d’intégration de données.

## <a name="preconditions-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

Avant de synchroniser les commandes client, il est important de mettre les systèmes à jour avec le paramètre suivant :

### <a name="setup-in-sales"></a>Configuration dans Sales

- Vérifiez que les autorisations sont bien définies pour l’équipe à laquelle l’utilisateur est affecté (à partir de votre connexion dans Sales). Si vous utilisez des données de démonstration, généralement l’utilisateur dispose de l’accès Administrateur, mais pas l’équipe. Si l’équipe n’a pas accès d’administrateur lors de l’exécution du projet à partir de l’intégrateur de données, vous recevrez un message d’erreur indiquant que l’équipe principale est manquante.

    Allez dans **Paramètres** &gt; **Sécurité** &gt; **Équipes**, sélectionnez l’équipe appropriée, cliquez sur **Gestion des rôles**, puis sélectionnez un rôle avec les autorisations souhaitées, par exemple, celles d’**Administrateur système**.

- Pour garantir un calcul correct des remises dans Sales et Supply Chain Management, **Mode de calcul de remise** doit être défini sur **Ligne**.
- Allez dans **Paramètres** &gt; **Administration** &gt; **Paramètres système** &gt; **Sales**, et assurez-vous que les paramètres suivants sont utilisés :

    - L’option **Utiliser le système de calcul du prix du système** est définie **Oui**.
    - La colonne **Mode de calcul de remise** est définie sur **Ligne article**.

### <a name="setup-in-supply-chain-management"></a>Paramétrage dans Supply Chain Management

- Allez dans **Ventes et marketing** &gt; **Tâches périodiques** &gt; **Calcule les totaux de vente**, et configurez la tâche pour qu’elle s’exécute comme un traitement par lots. Définissez l’option **Calculer les totaux des commandes client** sur **Oui**. Cette étape est importante, car seules les commandes client où les totaux de vente ont été calculés sont synchronisées avec Sales. La fréquence du traitement par lots doit être alignée avec la fréquence de la synchronisation des commandes client.

Si vous utilisez également l’intégration de l’ordre d’exécution, vous devez paramétrer l’origine des ventes. L’origine des ventes utilisée pour distinguer les commandes client de Supply Chain Management créées à partir d’ordres de travail de Field Service. Lorsqu’une commande client a pour origine le type **Intégration de l’ordre d’exécution**, le champ **Statut de l’ordre d’exécution externe** apparaît dans l’en-tête de la commande client. En outre, l’origine des ventes garantit que les commandes client créées à partir d’ordres d’exécution dans Field Service sont filtrées lors de la synchronisation des commandes client entre Supply Chain Management et Field Service.

1. Allez à **Ventes et marketing** \> **Paramétrage** \> **Commandes client** \> **Origine des ventes**.
2. Sélectionnez **Nouveau** pour créer une origine des ventes.
3. Dans la colonne **Origine des ventes**, entrez un nom pour l’origine des ventes, par exemple **SalesOrder**.
4. Dans la colonne **Description**, entrez une description, comme **Commande client de Sales**.
5. Activez la case à cocher **Affectation du type d’origine**.
6. Définissez la colonne **Type d’origine des ventes** sur **Intégration de la commande client**.
7. Sélectionnez **Enregistrer**.

### <a name="setup-in-the-sales-orders-sales-to-supply-chain-management---direct-data-integration-project"></a>Configuration dans les commandes client (de Sales vers Supply Chain Management) – projet d’intégration Direct Data

- Assurez-vous que la mise en correspondance nécessaire existe pour **Shipto\_country** avec **DeliveryAddressCountryRegionISOCode**. Vous pouvez laisser une valeur par défaut vide dans la mise en correspondance des valeurs pour éviter d’avoir à entrer le pays pour des commandes nationales. Laissez le côté gauche vide, puis définissez le côté droit sur le pays ou la région souhaité(e).

    La valeur du modèle est une mise en correspondance des valeurs où plusieurs pays ou régions sont mis en correspondance, et où vide = US.

### <a name="setup-in-the-sales-orders-supply-chain-management-to-sales---direct-data-integration-project"></a>Configuration dans les commandes client (de Supply Chain Management vers Sales) – projet d’intégration Direct Data

#### <a name="salesheader-task"></a>Tâche SalesHeader

- Un tarif est requis pour créer des commandes dans Sales. Mettez à jour la mise en correspondance de la valeur pour **pricelevelid.name \[Nom des tarifs\]** sur la liste des prix utilisée dans Sales par devise. Vous pouvez utiliser le tarif par défaut pour une seule devise. Sinon, si vous avez un tarif dans plusieurs devises, vous pouvez utiliser une mise en correspondance des valeurs.

    La valeur de modèle par défaut pour **pricelevelid.name \[Nom des tarifs\]** est le **service CRM USA (exemple)**.

#### <a name="salesline-task"></a>Tâche SalesLine

- Assurez-vous que la mise en correspondance des valeurs requise existe pour **SalesUnitSymbol** dans Supply Chain Management.
- Vérifiez que les unités nécessaires sont définies dans Sales.

    Une valeur de modèle ayant une mise en correspondance des valeurs est définie pour **SalesUnitSymbol** sur **oumid.name**.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l’intégration de données

> [!NOTE]
> Les colonnes **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d’expédition** et **Mode de distribution** ne font pas partie des mises en correspondance par défaut. Pour mettre en correspondance ces colonnes, vous devez paramétrer une mise en correspondance des valeurs spécifique aux données des organisations entre lesquelles la table est synchronisée.

Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l’intégration de données.

> [!NOTE]
> La mise en correspondance indique quelles informations de la colonne sont synchronisées entre Sales et Supply Chain Management, ou entre Supply Chain Management et Sales.

### <a name="sales-orders-supply-chain-management-to-sales---direct-orderheader"></a>Commandes client (Supply Chain Management vers Sales) – Direct : OrderHeader

[![Mappage de modèles dans l’intégration de données, Commandes client (Supply Chain Management à Sales) – Direct: OrderHeader.](./media/sales-order-direct-template-mapping-data-integrator-1.png)](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="sales-orders-supply-chain-management-to-sales---direct-orderline"></a>Commandes client (Supply Chain Management vers Sales) – Direct : OrderLine

[![Mappage de modèles dans l’intégration de données, Commandes client (Supply Chain Management à Sales) – Direct: OrderLine.](./media/sales-order-direct-template-mapping-data-integrator-2.png)](./media/sales-order-direct-template-mapping-data-integrator-2.png)

### <a name="sales-orders-sales-to-supply-chain-management---direct-orderheader"></a>Commandes client (Sales vers Supply Chain Management) – Direct : OrderHeader

[![Mappage de modèles dans l’intégration de données, Commandes client (Sales à Supply Chain Management) – Direct: OrderHeader.](./media/sales-order-direct-template-mapping-data-integrator-3.png)](./media/sales-order-direct-template-mapping-data-integrator-3.png)

### <a name="sales-orders-sales-to-supply-chain-management---direct-orderline"></a>Commandes client (Sales vers Supply Chain Management) – Direct : OrderLine

[![Mappage de modèles dans l’intégration de données, Commandes client (Sales à Supply Chain Management) – Direct: OrderLine.](./media/sales-order-direct-template-mapping-data-integrator-4.png)](./media/sales-order-direct-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a>Rubriques connexes

[Prospect en disponibilités](prospect-to-cash.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]