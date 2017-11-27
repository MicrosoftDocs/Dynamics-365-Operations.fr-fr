---
title: "Synchroniser les en-têtes et les lignes de commande client directement entre le module Finance and Operations et Sales"
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de commande client directement entre Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition et Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
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
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: cc0be50552ae680ba5291e72b7c482ee67e1e70e
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="synchronize-sales-order-headers-and-lines-directly-from-finance-and-operations-to-sales"></a>Synchroniser les en-têtes et les lignes de commande client directement entre le module Finance and Operations et Sales

[!include[banner](../includes/banner.md)]

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de commande client directement entre Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition et Microsoft Dynamics 365 for Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Flux de données dans Prospect en disponibilités

La solution Prospect en disponibilités utilise la fonction d'intégration de données pour synchroniser les données entre plusieurs instances de Finance and Operations et Sales. Les modèles de prospects en disponibilités disponibles avec la fonction d'intégration de données activent le flux de données relatifs aux comptes, contacts, produits, devis de vente, commandes client et factures client entre Finance and Operations et Sales. L'illustration ci-dessous indique comment les données sont synchronisées entre Finance and Operations et Sales.

[![Flux de données dans Prospect en disponibilités](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modèles et tâches

Pour accéder à des modèles disponibles, ouvrir [Centre d'administrateur PowerApps](https://preview.admin.powerapps.com/dataintegration). Sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner les modèles publics.

Le modèle et les tâches sous-jacentes suivants sont utilisés pour synchroniser les en-têtes et lignes de commande client entre Finance and Operations et Sales :

- **Nom du modèle dans l'intégration des données :** Commandes client (entre Fin and Ops et Sales) - Direct
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

Les commandes client sont créées dans Finance and Operations et synchronisées avec Sales.

Les filtres du modèle aident à garantir que seules les commandes client appropriées sont incluses dans la synchronisation :

- Sur la commande client, la commande et la facturation client provenant de Sales sont incluses dans la synchronisation. Dans Finance and Operations, les champs **OrderingCustomerIsExternallyMaintained** et **InvoiceCustomerIsExternallyMaintained** permettent de suivre la synchronisation dans les entités de données.
- La commande client dans Finance and Operations doit être confirmée. Seules les commandes client confirmées ou les commandes client dont le statut de traitement le plus élevé, par exemple, **Livré** ou **Facturé**, sont synchronisées avec Sales.
- Après avoir créé ou modifié une commande client, le traitement par lots **Calcule les totaux de vente** dans Finance and Operations doit être exécuté. Seules les commandes client où les totaux de vente sont calculés seront synchronisées avec Sales.

> [!NOTE]
> Actuellement, la taxe associée aux frais dans l'en-tête de commande client n'est pas incluse dans la synchronisation entre Finance and Operations et Sales. Sales ne prend pas en charge les informations fiscales au niveau de l'en-tête. Toutefois, la taxe associée aux frais au niveau de la ligne est incluse dans la synchronisation.

## <a name="prospect-to-cash-solution-for-sales"></a>Prospect pour une solution de disponibilités pour Sales

De nouveaux champs sont ajoutés à l'entité **Commande** et s'affichent sur la page :

- **Est conservé en externe** - Définissez cette option sur **Oui** lorsque la commande provient de Finance and Operations.
- **Statut de traitement** - Ce champ affiche le statut de traitement de la commande dans Finance and Operations. Les valeurs disponibles sont les suivantes :

    - Active
    - Confirmée
    - Bon de livraison
    - Facturé
    - Prélevé
    - Partiellement prélevé
    - Partiellement emballé
    - Expédié
    - Partiellement expédié
    - Partiellement facturé
    - Annulé

Le paramètre **Le devis a des produits mis à jour uniquement en externe** est utilisé dans d'autres scénarios de commande client (synchronisation entre Sales et Finance and Operation, par exemple) pour gérer de façon cohérente si la commande client comprend entièrement les produits gérés en externe. Si une commande client se compose uniquement des produits gérés en externe, les produits sont mis à jour dans Finance and Operations. Ceci permet de garantir que vous ne tenterez pas de synchroniser les lignes de commande client ayant des produits qui sont inconnus de Finance and Operations.

Les boutons **Créer une facture**, **Annuler la commande**, **Recalculer**, **Obtenir des produits** et **Adresse de recherche** sur la page **Commande client** sont masqués pour les commandes gérées en externe, car les factures sont créées dans Finance and Operations et synchronisées avec Sales. La page de commande ne peut pas être modifiée car les informations de commande client sont synchronisées à partir de Finance and Operations.

Le statut d'une commande client restera **Actif** pour garantir que les modifications effectuées dans Finance and Operations peuvent être répercutées dans la commande client avec Sales. Cette opération est contrôlée en définissant le paramètre par défaut **Statecode \[Statut\]** sur **Actif** dans le projet d'intégration de données.

## <a name="preconditions-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

Avant de synchroniser les commandes client, il est important de mettre les systèmes à jour avec le paramètre suivant :

### <a name="setup-in-sales"></a>Configuration dans Sales

- Vérifiez que les autorisations sont bien définies pour l'équipe à laquelle l'utilisateur est affecté (à partir de votre connexion dans Sales). Si vous utilisez des données de démonstration, généralement l'utilisateur dispose de l'accès Administrateur, mais pas l'équipe. Si l'équipe n'a pas accès d'administrateur, lors de l'exécution du projet à partir de l'intégrateur de données, vous recevrez un message d'erreur indiquant que l'équipe principale est manquante.

    Allez dans **Paramètres** > **Sécurité** > **Équipes**, sélectionnez l'équipe appropriée, cliquez sur **Gestion des rôles**, puis sélectionnez un rôle avec les autorisations souhaitées, par exemple, celles d'**Administrateur système**.

- Allez dans **Paramètres** > **Administration** > **Paramètres système** > **Sales**, et assurez-vous que les paramètres suivants sont utilisés :

    - L'option **Utiliser le système de calcul du prix du système** est définie **Oui**.
    - Le champ **Mode de calcul de remise** est défini sur **Ligne article**.

### <a name="setup-in-finance-and-operations"></a>Configuration dans Finance and Operations

Allez dans **Ventes et marketing** > **Tâches périodiques** > **Calcule les totaux de vente**, et configurez la tâche pour qu'elle s'exécute comme un traitement par lots. Définissez l'option **Calculer les totaux des commandes client** sur **Oui**. Cette étape est importante, car seules les commandes client où les totaux de vente ont été calculés sont synchronisées avec Sales. La fréquence du traitement par lots doit être alignée avec la fréquence de la synchronisation des commandes client.

### <a name="setup-in-the-data-integration-project"></a>Paramétrage du projet d'intégration des données

#### <a name="salesheader-task"></a>Tâche SalesHeader

- Assurez-vous que la mise en correspondance nécessaire existe pour **InvoiceCountryRegionId** et **BillingAddress\_Country** et pour **DeliveryCountryRegionId** et **DeliveryAddress\_Country**.

    La valeur du modèle est une mise en correspondance des valeurs où plusieurs pays ou régions sont mis en correspondance.

- Un tarif est requis pour créer des commandes dans Sales. Mettez à jour la mise en correspondance de la valeur pour **pricelevelid.name \[Nom des tarifs\]** sur la liste des prix utilisée dans Sales par devise. Vous pouvez utiliser le tarif par défaut pour une seule devise. Sinon, si vous avez un tarif dans plusieurs devises, vous pouvez utiliser une mise en correspondance des valeurs.

    La valeur de modèle par défaut pour **pricelevelid.name \[Nom des tarifs\]** est le **service CRM USA (exemple)**.

#### <a name="salesline-task"></a>Tâche SalesLine

- Assurez-vous que la mise en correspondance nécessaire existe pour **DeliveryCountryRegionId** et **DeliveryAddress\_Country**.

    La valeur du modèle est une mise en correspondance des valeurs où plusieurs pays ou régions sont mis en correspondance.

- Assurez-vous que la mise en correspondance des valeurs requise pour **SalesUnitSymbol** dans Finance and Operations existe.

    Une valeur de modèle ayant une mise en correspondance des valeurs est définie pour **SalesUnitSymbol** sur **Quantité\_UOM**.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

> [!NOTE]
> Les champs **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d'expédition** et **Mode de distribution** ne sont pas inclus dans les mises en correspondance par défaut. Pour mettre en correspondance ces champs, vous devez paramétrer une mise en correspondance des valeurs spécifique aux données des organisations entre lesquelles l'entité est synchronisée.

Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégration de données. 

> [!NOTE]
> La mise en correspondance indique quelles informations du champ sont synchronisées entre Sales et Finance and Operations.

### <a name="orderheader"></a>OrderHeader

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="orderline"></a>OrderLine

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-order-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a>Rubriques connexes

[Prospect en disponibilités](prospect-to-cash.md)

[Synchroniser directement les comptes provenant du module Sales sur les clients de Finance and Operations](accounts-template-mapping-direct.md)

[Synchroniser les produits directement de Finance and Operations sur les produits du module Sales](products-template-mapping-direct.md)

[Synchroniser directement les contacts de Sales avec les contacts ou clients de Finance and Operations](contacts-template-mapping-direct.md)

[Synchroniser les en-têtes et les lignes de facture client provenant directement du module Finance and Operations avec Sales](sales-invoice-template-mapping-direct.md)




