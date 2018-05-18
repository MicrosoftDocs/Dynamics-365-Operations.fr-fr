---
title: Synchronisation entre les commandes client directement entre Sales et Finance and Operations
description: "La rubrique présente les modèles et les tâches sous-jacentes utilisés pour exécuter la synchronisation des commandes client directement entre Microsoft Dynamics 365 for Sales et Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: e26244ffc380291a40edfbd2c2cb5911b0d8b3cb
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="synchronization-of-sales-orders-directly-between-sales-and-finance-and-operations"></a>Synchronisation entre les commandes client directement entre Sales et Finance and Operations

[!include [banner](../includes/banner.md)]

La rubrique présente les modèles et les tâches sous-jacentes utilisés pour exécuter la synchronisation des commandes client directement entre Microsoft Dynamics 365 for Sales et Microsoft Dynamics 365 for Finance and Operations.

## <a name="templates-and-tasks"></a>Modèles et tâches

Pour accéder à des modèles disponibles, ouvrir [Centre d'administrateur PowerApps](https://preview.admin.powerapps.com/dataintegration). Sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner les modèles publics.

Les modèles et les tâches sous-jacentes suivants sont utilisés pour exécuter la synchronisation des commandes client directement entre Sales et Finance and Operations :

- **Noms des modèles dans l'intégration des données :** 

    - Commandes client (entre Sales et Fin and Ops) - Direct
    - Commandes client (entre Fin and Ops et Sales) - Direct

- **Noms des tâches dans le projet d'intégration de données :**

    - OrderHeader
    - OrderLine

Les tâches suivantes de synchronisation sont requises avant que la synchronisation des en-têtes et des lignes de factures client puisse avoir lieu :

- Produits (entre Fin and Ops et Sales) - Direct
- Comptes (entre Sales et Fin and Ops) - Direct (en cas d'utilisation)
- Contacts vers Clients (entre Sales et Fin and Ops) - Direct (en cas d'utilisation)

## <a name="entity-set"></a>Ensemble d'entités

| Finance and Operations  | Vente             |
|-------------------------|-------------------|
| En-têtes de commande client CDS | SalesOrders       |
| Lignes de commande client CDS   | SalesOrderDetails |

## <a name="entity-flow"></a>Flux d'entité

Les commandes client sont créées dans Sales et synchronisées avec Finance and Operations lorsque **Exécuter le projet** est déclenché pour un projet basé sur le modèle **Commandes client (entre Sales et Fin and Ops) - Direct**. Vous pouvez uniquement activer et synchroniser des commandes client à partir de Sales uniquement si tous les **Produits de la commande** se composent entièrement de produits gérés en externe. Par conséquent, il ne peut y avoir aucun produit hors catalogue. Une fois que la commande est activée, la commande client passe en lecture seule dans l'interface utilisateur (UI). À ce stade, les mises à jour sont effectuées à partir de Finance and Operations. Une fois qu'une commande client a un statut **Confirmé**, le projet basé sur le modèle **Commandes client (entre Fin and Ops et Sales) - Direct** peut être utilisé pour synchroniser toutes les mises à jour ou le statut d'exécution entre Finance and Operations et Sales.

Vous n'avez pas à créer de commandes dans Sales. Vous pouvez les créer dans Finance and Operations à la place. Une fois qu'une commande client a un statut **Confirmé**, elle est synchronisée avec Sales comme indiqué dans le paragraphe précédent.

Dans Finance and Operations, les filtres du modèle permettent de garantir que seules les commandes client appropriées sont incluses dans la synchronisation :

- Sur la commande client, la commande et la facturation client doivent provenir de Sales pour être incluses dans la synchronisation. Dans Finance and Operations, les champs **OrderingCustomerIsExternallyMaintained** et **InvoiceCustomerIsExternallyMaintained** sont utilisés pour filtrer les commandes client à partir des entités de données.
- La commande client dans Finance and Operations doit être confirmée. Seules les commandes client confirmées ou les commandes client dont le statut de traitement le plus élevé, par exemple, **Livré** ou **Facturé**, sont synchronisées avec Sales.
- Après avoir créé ou modifié une commande client, le traitement par lots **Calcule les totaux de vente** dans Finance and Operations doit être exécuté. Seules les commandes client où les totaux de vente sont calculés seront synchronisées avec Sales.

## <a name="freight-tax"></a>Taxe relative au transport

Sales ne prend pas en charge la taxe au niveau de l'en-tête, car la taxe est enregistrée au niveau de la ligne. Pour prendre en charge la taxe au niveau de l'en-tête à partir de Finance and Operations, comme la taxe sur le transport, le système synchronise la taxe avec Sales comme un produit hors catalogue appelé **Taxe de transport**, et le montant de sa taxe provient de Finance and Operations.. Ainsi, le calcul standard du prix dans Sales peut être utilisé pour les totaux, même s'il existe une taxe au niveau de l'en-tête à partir de Finance and Operations.

## <a name="discount-calculation-and-rounding"></a>Calcul et arrondi de la remise

Le modèle de calcul de la remise dans Sales diffère du modèle de calcul de la remise dans Finance and Operations. Dans Finance and Operations, le montant de remise final sur une ligne de vente peut être le résultat d'une combinaison des montants de remise et des pourcentages de remise. Si ce montant de remise final est divisé par la quantité de la ligne, un arrondi peut se produire. Toutefois, cet arrondi n'est pas pris en considération si un montant de la remise Par unité qui est arrondi est synchronisé avec Sales. Pour vous assurer que le montant de remise total d'une ligne de vente dans Finance and Operations soit synchronisé correctement avec Sales, le montant total doit être synchronisé sans être divisé par la quantité de ligne. Par conséquent, vous devez définir le champ **Mode de calcul de remise** sur **Ligne article** dans Sales.

Lorsqu'une ligne de commande client est synchronisée entre Sales et Finance and Operations, le montant de remise total est utilisé. Comme Finance and Operations n'a pas de champ pouvant enregistrer le montant de remise total pour une ligne, le montant est divisé par la quantité et enregistré dans le champ **Remise ligne**. L'arrondi qui survient dans cette division est stocké dans le champ **Frais de vente** sur la ligne de vente.

### <a name="example"></a>Exemple

**Synchronisation entre Sales et Finance and Operations**

- **Sales :** Quantité = 3, remise par ligne = 10,00 €
- **Finance and Operations :** Quantité = 3, montant de remise ligne = 3,33 €, frais de vente = -0,01 € 

**Synchronisation entre Finance and Operations et Sales**

- **Finance and Operations :** Quantité = 3, montant de remise ligne = 3,33 €, frais de vente = -0,01 €
- **Sales :** Quantité = 3, remise par ligne = (3 × 3,33 €) + 0,01 € = 10,00 €

## <a name="prospect-to-cash-solution-for-sales"></a>Prospect pour une solution de disponibilités pour Sales

De nouveaux champs sont ajoutés à l'entité **Commande** et s'affichent sur la page :

- **Est conservé en externe** - Définissez cette option sur **Oui** lorsque la commande provient de Finance and Operations.
- **Statut de traitement** - Ce champ affiche le statut de traitement de la commande dans Finance and Operations. Les valeurs disponibles sont les suivantes :

    - **Brouillon** – Statut initial lorsqu'une commande est créée dans Sales. Dans Sales, seules les commandes ayant ce statut de traitement peuvent être modifiées.
    - **Actif** – Statut une fois que la commande est activée dans Sales à l'aide du bouton **Activer**.
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

Le paramètre **A des produits mis à jour en externe uniquement** est utilisé durant l'activation de la commande pour effectuer le suivi uniformément si une commande client se compose entièrement de produits gérés en externe. Si une commande client se compose uniquement des produits gérés en externe, les produits sont mis à jour dans Finance and Operations. Ceci permet de garantir que vous ne tenterez pas d'activer et de synchroniser les lignes de commandes client ayant des produits qui sont inconnus de Finance and Operations.

Les boutons **Créer une facture**, **Annuler la commande**, **Recalculer**, **Obtenir des produits** et **Adresse de recherche** sur la page **Commande client** sont masqués pour les commandes gérées en externe, car les factures sont créées dans Finance and Operations et synchronisées avec Sales. Ces commandes ne peuvent pas être modifiées, car les informations de commande client sont synchronisées à partir de Finance and Operations après cette activation.

Le statut d'une commande client restera **Actif** pour garantir que les modifications effectuées dans Finance and Operations peuvent être répercutées dans la commande client avec Sales. Cette opération est contrôlée en définissant le paramètre par défaut **Statecode \[Statut\]** sur **Actif** dans le projet d'intégration de données.

## <a name="preconditions-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

Avant de synchroniser les commandes client, il est important de mettre les systèmes à jour avec le paramètre suivant :

### <a name="setup-in-sales"></a>Configuration dans Sales

- Vérifiez que les autorisations sont bien définies pour l'équipe à laquelle l'utilisateur est affecté (à partir de votre connexion dans Sales). Si vous utilisez des données de démonstration, généralement l'utilisateur dispose de l'accès Administrateur, mais pas l'équipe. Si l'équipe n'a pas accès d'administrateur lors de l'exécution du projet à partir de l'intégrateur de données, vous recevrez un message d'erreur indiquant que l'équipe principale est manquante.

    Allez dans **Paramètres** &gt; **Sécurité** &gt; **Équipes**, sélectionnez l'équipe appropriée, cliquez sur **Gestion des rôles**, puis sélectionnez un rôle avec les autorisations souhaitées, par exemple, celles d'**Administrateur système**.

- Pour garantir un calcul correct des remises dans Sales et Finance and Operations, **Mode de calcul de remise** doit être défini sur **Ligne**.
- Allez dans **Paramètres** &gt; **Administration** &gt; **Paramètres système** &gt; **Sales**, et assurez-vous que les paramètres suivants sont utilisés :

    - L'option **Utiliser le système de calcul du prix du système** est définie **Oui**.
    - Le champ **Mode de calcul de remise** est défini sur **Ligne article**.

### <a name="setup-in-finance-and-operations"></a>Configuration dans Finance and Operations

- Allez dans **Ventes et marketing** &gt; **Tâches périodiques** &gt; **Calcule les totaux de vente**, et configurez la tâche pour qu'elle s'exécute comme un traitement par lots. Définissez l'option **Calculer les totaux des commandes client** sur **Oui**. Cette étape est importante, car seules les commandes client où les totaux de vente ont été calculés sont synchronisées avec Sales. La fréquence du traitement par lots doit être alignée avec la fréquence de la synchronisation des commandes client.

### <a name="setup-in-the-sales-orders-sales-to-fin-and-ops---direct-data-integration-project"></a>Configuration dans les commandes client (entre Sales et Fin and Ops) - projet d'intégration Direct Data

- Assurez-vous que la mise en correspondance nécessaire existe pour **Shipto\_country** avec **DeliveryAddressCountryRegionISOCode**. Vous pouvez laisser une valeur par défaut vide dans la mise en correspondance des valeurs pour éviter d'avoir à entrer le pays pour des commandes nationales. Laissez le côté gauche vide, puis définissez le côté droit sur le pays ou la région souhaité(e).

    La valeur du modèle est une mise en correspondance des valeurs où plusieurs pays ou régions sont mis en correspondance, et où vide = US.

### <a name="setup-in-the-sales-orders-fin-and-ops-to-sales---direct-data-integration-project"></a>Configuration dans les commandes client (entre Fin and Ops et Sales) - projet d'intégration Direct Data

#### <a name="salesheader-task"></a>Tâche SalesHeader

- Un tarif est requis pour créer des commandes dans Sales. Mettez à jour la mise en correspondance de la valeur pour **pricelevelid.name \[Nom des tarifs\]** sur la liste des prix utilisée dans Sales par devise. Vous pouvez utiliser le tarif par défaut pour une seule devise. Sinon, si vous avez un tarif dans plusieurs devises, vous pouvez utiliser une mise en correspondance des valeurs.

    La valeur de modèle par défaut pour **pricelevelid.name \[Nom des tarifs\]** est le **service CRM USA (exemple)**.

#### <a name="salesline-task"></a>Tâche SalesLine

- Assurez-vous que la mise en correspondance des valeurs requise pour **SalesUnitSymbol** dans Finance and Operations existe.
- Vérifiez que les unités nécessaires sont définies dans Sales.

    Une valeur de modèle ayant une mise en correspondance des valeurs est définie pour **SalesUnitSymbol** sur **oumid.name**.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

> [!NOTE]
> Les champs **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d'expédition** et **Mode de distribution** ne font pas partie des mises en correspondance par défaut. Pour mettre en correspondance ces champs, vous devez paramétrer une mise en correspondance des valeurs spécifique aux données des organisations entre lesquelles l'entité est synchronisée.

Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégration de données.

> [!NOTE]
> La mise en correspondance indique quelles informations du champ sont synchronisées entre Sales et Finance and Operations, ou entre Finance and Operations et Sales.

### <a name="sales-orders-fin-and-ops-to-sales---direct-orderheader"></a>Commandes client (entre Fin and Ops et Sales) - Direct : OrderHeader

[![Mise en correspondance de modèles dans l'intégration de données](./media/sales-order-direct-template-mapping-data-integrator-1.png)](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="sales-orders-fin-and-ops-to-sales---direct-orderline"></a>Commandes client (entre Fin and Ops et Sales) - Direct : OrderLine

[![Mise en correspondance de modèles dans l'intégration de données](./media/sales-order-direct-template-mapping-data-integrator-2.png)](./media/sales-order-direct-template-mapping-data-integrator-2.png)

### <a name="sales-orders-sales-to-fin-and-ops---direct-orderheader"></a>Commandes client (entre Sales et Fin and Ops) - Direct : OrderHeader

[![Mise en correspondance de modèles dans l'intégration de données](./media/sales-order-direct-template-mapping-data-integrator-3.png)](./media/sales-order-direct-template-mapping-data-integrator-3.png)

### <a name="sales-orders-sales-to-fin-and-ops---direct-orderline"></a>Commandes client (entre Sales et Fin and Ops) - Direct : OrderLine

[![Mise en correspondance de modèles dans l'intégration de données](./media/sales-order-direct-template-mapping-data-integrator-4.png)](./media/sales-order-direct-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a>Rubriques connexes

[Prospect en disponibilités](prospect-to-cash.md)

