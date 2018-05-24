---
title: "Synchroniser les ordres d'exécution de Field Service sur les commandes client de Finance and Operations"
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les ordres d'exécution de Field Service sur les commandes client de Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 04/09/2018
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
ms.sourcegitcommit: ace66c037953f4b1b2e8b93a315faefdb090b1eb
ms.openlocfilehash: 933d9755085d507310dd46d96a492d2124647ec3
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="synchronize-work-orders-in-field-service-to-sales-orders-in-finance-and-operations"></a>Synchroniser les ordres d'exécution de Field Service sur les commandes client de Finance and Operations

[!include[banner](../includes/banner.md)]

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les ordres d'exécution de Microsoft Dynamics 365 for Field Service sur les commandes client de Microsoft Dynamics 365 for Finance and Operations.

[![Synchronisation des processus d'entreprise entre Finance and Operations et Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les ordres d'exécution de Field Service sur les commandes client de Finance and Operations.

## <a name="templates-and-tasks"></a>Modèles et tâches

Les modèles et les tâches sous-jacentes sont utilisés pour exécuter la synchronisation des ordres d'exécution de Field Service sur les commandes client de Finance and Operations.

### <a name="names-of-the-templates-in-data-integration"></a>Noms des modèles dans l'intégration des données

Le modèle **Ordres d'exécution sur Commandes client (Field Service à Fin and Ops)** est utilisé pour exécuter la synchronisation.

### <a name="names-of-the-tasks-in-the-data-integration-project"></a>Noms des tâches dans le projet d'intégration de données

- WorkOrderHeader
- WorkOrderServiceLineEstimate
- WorkOrderServiceLineUsed
- WorkOrderProductLineEstimate
- WorkOrderProductLineUsed

Les tâches suivantes de synchronisation sont requises avant que la synchronisation des en-têtes et des lignes de commande client puisse avoir lieu :

- Produits Field Service (Fin and Ops vers Field Service)
- Comptes (Sales vers Fin and Ops) - Direct

## <a name="entity-set"></a>Ensemble d'entités

| **Field Service** | **Finance and Operations** |
|-------------------------|-------------------------|
| msdyn_workorders        | En-têtes de commande client CDS |
| msdyn_workorderservices | Lignes de commande client CDS   |
| msdyn_workorderproducts | Lignes de commande client CDS   |

## <a name="entity-flow"></a>Flux d'entité

Les ordres d'exécution sont créés dans Field Service. Si les ordres d'exécution incluent uniquement des produits conservés en externe, et si la valeur de **Statut des ordres d'exécution** est différente de **En cours - Non planifié** et **Clôturé - Annulé**, les ordres d'exécution peuvent être synchronisés sur Finance and Operations via un projet d'intégration de données CDS. Les mises à jour sur les ordres d'exécution sont synchronisés comme commandes client dans Finance and Operations. Ces mises à jour incluent les informations sur le type et le statut d'origine.

## <a name="estimated-versus-used"></a>Estimé versus Utilisé

Dans Field Service, les produits et services sur les ordres d'exécution ont des valeurs **Estimé** et **Utilisé** pour les quantités et les montants. Toutefois, dans Finance and Operations, les commandes client n'ont pas le même concept des valeurs **Estimé** et **Utilisé**. Pour prendre en charge la répartition par produit qui utilise la quantité prévue sur la commande client dans Finance and Operations, tout en conservant la quantité utilisée qui doit être consommée et facturée, deux ensembles de tâches synchronisent les produits et les services sur l'ordre d'exécution. Un ensemble de tâches concerne les valeurs **Estimé**, et l'autre ensemble de tâches concerne les valeurs **Utilisé**.

Ce comportement permet de créer des scénarios dans lesquels les valeurs estimées sont utilisées pour la répartition ou la réservation dans Finance and Operations, tandis que les valeurs utilisées sont utilisées pour la consommation et la facturation.

### <a name="estimated"></a>Estimé

Pour la synchronisation des lignes de produit, les valeurs **Estimé** sont utilisées lorsque la valeur **Statut de ligne** est **Estimé**, l'option **Affecté** est définie sur **Oui**, et la valeur **Statut du système** n'est pas **Clôturé – Validé**.

Pour la synchronisation des lignes de service, les valeurs **Estimé** sont utilisées lorsque la valeur **Statut de ligne** est **Estimé** et la valeur **Statut du système** n'est pas **Clôturé – Validé**.

### <a name="used"></a>Utilisé(e)

Les valeurs **Utilisé** sont utilisées pour la consommation et la facturation. Dans ces cas, les valeurs **Utilisé** sont synchronisées.

Le tableau suivant fournit une vue d'ensemble des différentes combinaisons pour les lignes de produits.

| Statut du système <br>(Field Service) | Statut de ligne <br>(Field Service) | Affecté <br>(Field Service) |Valeur synchronisée <br>(Finance and Operations) |
|--------------------|-------------|-----------|---------------------------------|
| En cours - Planifié   | Estimé   | Oui       | Estimé                       |
| En cours - Planifié   | Estimé   | N°        | Utilisé(e)                            |
| En cours - Planifié   | Utilisé(e)        | Oui       | Utilisé(e)                            |
| En cours - Planifié   | Utilisé(e)        | N°        | Utilisé(e)                            |
| En cours - En cours | Estimé   | Oui       | Estimé                       |
| En cours - En cours | Estimé   | N°        | Utilisé(e)                            |
| En cours - En cours | Utilisé(e)        | Oui       | Utilisé(e)                            |
| En cours - En cours | Utilisé(e)        | N°        | Utilisé(e)                            |
| En cours - Terminé   | Estimé   | Oui       | Estimé                       |
| En cours - Terminé   | Estimé   | N°        | Utilisé(e)                            |
| En cours - Terminé   | Utilisé(e)        | Oui       | Utilisé(e)                            |
| En cours - Terminé   | Utilisé(e)        | N°        | Utilisé(e)                            |
| Clôturé - Validé    | Estimé   | Oui       | Utilisé(e)                            |
| Clôturé - Validé    | Estimé   | N°        | Utilisé(e)                            |
| Clôturé - Validé    | Utilisé(e)        | Oui       | Utilisé(e)                            |
| Clôturé - Validé    | Utilisé(e)        | N°        | Utilisé(e)                            |

Le tableau suivant fournit une vue d'ensemble des différentes combinaisons pour les lignes de services.

| Statut du système <br>(Field Service) | Statut de ligne <br>(Field Service) | Valeur synchronisée <br>(Finance and Operations) |
|--------------------|-------------|-----------|
| En cours - Planifié   | Estimé   | Estimé |
| En cours - Planifié   | Utilisé(e)        | Utilisé(e)      |
| En cours - En cours | Estimé   | Estimé |
| En cours - En cours | Utilisé(e)        | Utilisé(e)      |
| En cours - Terminé   | Estimé   | Estimé |
| En cours - Terminé   | Utilisé(e)        | Utilisé(e)      |
| Clôturé - Validé    | Estimé   | Utilisé(e)      |
| Clôturé - Validé    | Utilisé(e)        | Utilisé(e)      |

La synchronisation des valeurs **Estimé** comparées aux valeurs **Utilisé** est gérée via les deux ensembles de tâches pour les lignes de produit et les lignes de service. Les filtres prédéfinis déclenchent la tâche appropriée, et la mise en correspondance sous-jacentes garantit que les valeurs correctes pour **Prévu** et **Utilisé** sont synchronisées.

### <a name="example"></a>Exemple

1. Un ordre d'exécution est créé et planifié dans Field Service.

    La valeur **Statut du système** est **En cours - Planifié**.

    - **Ligne de produit :** Qté estimée = 5ea, Qté utilisée = 0ea, Statut de ligne = Estimé, Affecté = Non
    - **Ligne service :** Qté estimée = 2 h, Qté utilisée = 0 h, Statut de ligne = Estimé

    Dans cet exemple, la valeur **Qté utilisée** du produit de **0** (zéro) et la valeur **Qté estimée** du service de **2 h** sont synchronisées sur Finance and Operations.

2. Les produits sont affectés dans Field Service.

    La valeur **Statut du système** est **En cours - Planifié**.

    - **Ligne de produit :** Qté estimée = 5ea, Qté utilisée = 0ea, Statut de ligne = Estimé, Affecté = Oui
    - **Ligne service :** Qté estimée = 2 h, Qté utilisée = 0 h, Statut de ligne = Estimé

    Dans cet exemple, la valeur **Qté estimée** du produit de **5ea** et la valeur **Qté estimée** du service de **2 h** sont synchronisées sur Finance and Operations.

3. Les technicien de service commence à utiliser l'ordre d'exécution et enregistre une utilisation des matières de 6.

    La valeur **Statut du système** est **En cours - En cours**.

    - **Ligne de produit :** Qté estimée = 5ea, Qté utilisée = 6ea, Statut de ligne = Utilisé, Affecté = Oui
    - **Ligne service :** Qté estimée = 2 h, Qté utilisée = 0 h, Statut de ligne = Estimé

    Dans cet exemple, la valeur **Qté utilisée** du produit de **6** et la valeur **Qté estimée** du service de **2 h** sont synchronisées sur Finance and Operations.

4. Le technicien de service renseigne l'ordre d'exécution et enregistre la durée utilisée de 1,5 heure.

    La valeur **Statut du système** est **En cours - Terminé**.

    - **Ligne de produit :** Qté estimée = 5ea, Qté utilisée = 6ea, Statut de ligne = Utilisé, Affecté = Oui
    - **Ligne service :** Qté estimée = 2 h, Qté utilisée = 1,5 h, Statut de ligne = Utilisé

    Dans cet exemple, la valeur **Qté utilisée** du produit de **6** et la valeur **Qté estimée** du service de **1,5 h** sont synchronisées sur Finance and Operations.

## <a name="sales-order-origin-and-status"></a>Origine et statut de la commande client

### <a name="sales-origin"></a>Origine des ventes

Pour effectuer le suivi des commandes client dans Finance and Operations qui proviennent des ordres d'exécution, vous pouvez créer une origine des ventes dans laquelle l'option **Affectation du type d'origine** est définie sur **Oui** et le champ **Type d'origine des ventes** est défini **Intégration de l'ordre d'exécution**.

Par défaut, la mise en correspondance sélectionne l'origine des ventes pour le type d'origine des ventes **Intégration de l'ordre d'exécution** pour toutes les commandes client créées à partir des ordres d'exécution. Ceci peut s'avérer utile lorsque vous utilisez la commande client dans Finance and Operations. Vous devez vous assurer que les commandes client provenant des ordres d'exécution ne sont pas resynchronisées sur Field Service comme ordres d'exécution.

Pour plus d'informations sur la création du paramétrage correct de l'origine des ventes dans Finance and Operations, voir la section « Conditions préalables et paramétrage de mise en correspondance » de cette rubrique.

### <a name="status"></a>État

Lorsque la commande client provient d'un ordre d'exécution, le champ **Statut de l'ordre d'exécution externe** apparaît sur l'onglet **Paramétrage** dans l'en-tête de la commande client. Ce champ affiche le statut système de l'ordre d'exécution dans Field Service, afin de suivre le statut de l'ordre d'exécution synchronisé des commandes client dans Finance and Operations. Ce champ peut également aider l'utilisateur de Finance and Operations à déterminer quand la commande client doit être livrée ou facturée.

Le champ **Statut de l'ordre d'exécution externe** peut avoir les valeurs suivantes :

- En cours - Planifié
- En cours - En cours
- En cours - Terminé
- Clôturé - Validé

## <a name="field-service-crm-solution"></a>Solution Field Service CRM

Pour permettre l'intégration entre Field Service et Finance and Operations, des fonctionnalités supplémentaires de la solution Field Service CRM sont requises. La solution inclut les modifications suivantes.

### <a name="work-order-entity"></a>Entité d'ordre d'exécution

Le champ **A des produits mis à jour uniquement en externe** a été ajouté à l'entité **Ordre d'exécution** et apparaît sur la page. Il permet de vérifier uniformément si un ordre d'exécution consiste entièrement en produits mis à jour en externe. Un ordre d'exécution se compose uniquement des produits gérés en externe quand tous les produits associés sont mis à jour dans Finance and Operations. Ce champ permet de garantir que les utilisateurs ne synchronisent pas les ordres d'exécution ayant des produits qui sont inconnus de Finance and Operations.

### <a name="work-order-product-entity"></a>Entité de produit d'ordre d'exécution

- Le champ **La commande a des produits mis à jour uniquement en externe** a été ajouté à l'entité **Produit d'ordre d'exécution** et apparaît sur la page. Il est utilisé pour vérifier uniformément si le produit d'ordre d'exécution est mis à jour dans Finance and Operations. Ce champ permet de garantir que les utilisateurs ne synchronisent pas les produits d'ordre d'exécution ayant des produits qui sont inconnus de Finance and Operations.
- Le champ **Statut du système d'en-tête** a été ajouté à l'entité **Produit d'ordre d'exécution** et apparaît sur la page. Il est utilisé pour suivre uniformément le statut du système de l'ordre d'exécution et garantir un filtrage correct lorsque les produits d'ordre d'exécution sont synchronisés sur Finance and Operations. Lorsque des filtres sont définis sur les tâches d'intégration, l'information **Statut du système d'en-tête** permet également de déterminer si les valeurs estimées ou utilisées doivent être synchronisées.
- Le champ **Montant unitaire facturé** affiche le montant facturé par unité réelle utilisée. La valeur est calculée comme valeur de **Montant total** divisée par la valeur **Quantité réelle**. Le champ est utilisé pour l'intégration dans des systèmes qui ne prennent pas en charge différentes valeurs de la quantité utilisée et de la quantité facturée. Ce champ ne s'affiche pas dans l'interface utilisateur (IU). 
- Le champ **Montant de remise facturé** est calculé comme valeur de **Montant de remise** plus l'arrondi du calcul de la valeur du **Montant unitaire facturé**. Ce champ est utilisé pour l'intégration et n'apparaît pas dans l'IU.
- Le champ **Quantité décimale** enregistre la valeur du champ **Quantité** comme nombre décimal. Ce champ est utilisé pour l'intégration et n'apparaît pas dans l'IU. 
- La valeur dans les champs **Utilisé** est réinitialisée sur **0** (zéro) si la valeur de **Statut de ligne** du produit de l'ordre d'exécution est passée de **Utilisé** à **Estimé**. Cette modification permet d'éviter des situations où une quantité utilisée qui est entrée par erreur est utilisée pour la synchronisation lorsque la valeur de **Statut de ligne** est **Estimé** et que l'option **Affecté** est définie sur **Non**.

### <a name="work-order-service-entity"></a>Entité de service d'ordre d'exécution

- Le champ **La commande a des produits mis à jour uniquement en externe** a été ajouté à l'entité **Service d'ordre d'exécution** et apparaît sur la page. Il est utilisé pour vérifier uniformément si le service d'ordre d'exécution est mis à jour dans Finance and Operations. Ce champ permet de garantir que les utilisateurs ne synchronisent pas les services d'ordre d'exécution ayant des produits qui sont inconnus de Finance and Operations.
- Le champ **Statut du système d'en-tête** a été ajouté à l'entité **Service d'ordre d'exécution** et apparaît sur la page. Il est utilisé pour suivre uniformément le statut du système de l'ordre d'exécution et garantir un filtrage correct lorsque les services d'ordre d'exécution sont synchronisés sur Finance and Operations. Lorsque des filtres sont définis sur les tâches d'intégration, l'information **Statut du système d'en-tête** permet également de déterminer si les valeurs estimées ou utilisées doivent être synchronisées.
- Le champ **Durée en heures** enregistre la valeur du champ **Durée** après que la valeur est convertie de minutes en heures. Ce champ est utilisé pour l'intégration et n'apparaît pas dans l'IU.
- Le champ **Durée en heures estimée** enregistre la valeur du champ **Durée estimée** après que la valeur est convertie de minutes en heures. Ce champ est utilisé pour l'intégration et n'apparaît pas dans l'IU.
- Le champ **Montant unitaire facturé** stocke le montant facturé par unité réelle utilisée. La valeur est calculée comme valeur de **Montant total** divisée par la valeur **Quantité réelle**. Ce champ est utilisé pour l'intégration dans des systèmes qui ne prennent pas en charge différentes valeurs de la quantité utilisée et de la quantité facturée. Le champ ne s'affiche pas dans l'IU.
- Le champ **Montant de remise facturé** est calculé comme valeur de **Montant de remise** plus l'arrondi du calcul de la valeur du **Montant unitaire facturé**. Ce champ est utilisé pour l'intégration et n'apparaît pas dans l'IU.
- Le champ **Ligne de commande externe** est un numéro de commande de ligne négatif calculé qui peut être utilisé dans les systèmes externes où les lignes de produit et service d'ordre d'exécution sont combinés. Ce champ permet aux produits d'ordre d'exécution qui sont insérés d'avoir des numéros de ligne positifs et aux services d'ordre d'exécution d'avoir des numéros de ligne négatifs. La valeur de ce champ est calculée comme valeur **Ordre de ligne** multipliée par -1. Ce champ ne s'affiche pas dans l'IU.
- La valeur dans les champs **Utilisé** est réinitialisée sur **0** (zéro) si la valeur de **Statut de ligne** du service de l'ordre d'exécution est passée de **Utilisé** à **Estimé** pour une raison quelconque. Cette modification permet d'éviter des situations où une quantité utilisée qui est entrée par erreur est utilisée pour la synchronisation lorsque la valeur de **Statut de ligne** est **Estimé** et que la valeur **Statut système de l'en-tête** est **Clôturé - Validé**.

## <a name="preconditions-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

Avant de synchroniser les ordres d'exécution, il est important de mettre les systèmes à jour avec le paramètre suivant :

### <a name="setup-in-field-service"></a>Paramétrage dans Field Service

- Assurez-vous que la souche de numéros utilisée pour les ordres d'exécution dans Field Service ne chevauche pas la souche de numéros utilisée pour les commandes client dans Finance and Operations. Sinon, les commandes client existantes peuvent être incorrectement mises à jour dans Field Service ou Finance and Operations.
- Le champ **Création d'une facture d'ordre d'exécution** doit être défini sur **Jamais**, car la facturation est effectuée dans Finance and Operations. Accédez à **Field Service** \> **Paramètres** \> **Administration** \> **Paramètres de Field Service**, puis vérifiez que le champ **Création d'une facture d'ordre d'exécution** est défini sur **Jamais**.

### <a name="setup-in-finance-and-operations"></a>Configuration dans Finance and Operations

L'intégration d'ordre d'exécution requiert que vous définissiez l'origine des ventes. L'origine des ventes utilisée pour distinguer les commandes client de Finance and Operations créées à partir d'ordres d'exécution de Field Service. Lorsqu'une commande client a pour origine le type **Intégration de l'ordre d'exécution**, le champ **Statut de l'ordre d'exécution externe** apparaît dans l'en-tête de la commande client. En outre, l'origine des ventes garantit que les commandes client créées à partir d'ordres d'exécution dans Field Service sont filtrées lors de la synchronisation des commandes client entre Finance and Operations et Field Service.

1. Allez à **Ventes et marketing** \> **Paramétrage** \> **Commandes client** \> **Origine des ventes**.
2. Sélectionnez **Nouveau** pour créer une origine des ventes.
3. Dans le champ **Origine des ventes**, entrez un nom pour l'origine des ventes, par exemple **WorkOrder**.
4. Dans le champ **Description**, entrez une description, comme **Ordre d'exécution Field Service**.
5. Activez la case à cocher **Affectation du type d'origine**.
6. Définissez le champ **Type d'origine des ventes** sur **Intégration de l'ordre d'exécution**.
7. Sélectionnez **Enregistrer**.


### <a name="setup-in-data-integration"></a>Paramétrage dans le module Intégration des données

Vérifiez que la **Clé d'intégration** existe pour **msdyn_workorders**
1. Accédez au module Intégration des données
2. Sélectionnez l'onglet **Ensemble de connexions**
3. Sélectionnez l'ensemble de connexions utilisé pour la synchronisation des ordres d'exécution
4. Sélectionnez l'onglet **Clé d'intégration**
5. Recherchez msdyn_workorders et vérifiez que la clé **msdyn_name (numéro d'ordre de travail)** est ajoutée. Si elle n'est pas affichée, ajoutez-la en cliquant sur **Ajouter une clé**, puis sur **Enregistrer** en haut de la page

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.

### <a name="work-orders-to-sales-orders-field-service-to-fin-and-ops-workorderheader"></a>Ordres d'exécution sur commandes client (Field Service vers Fin and Ops) : WorkOrderHeader

Filtre : (msdyn_systemstatus ne 690970005) et (msdyn_systemstatus ne 690970000) et (msdynce_hasexternallymaintainedproductsonly eq true)

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWorkOrder1.png )](./media/FSWorkOrder1.png)

### <a name="work-orders-to-sales-orders-field-service-to-fin-and-ops-workorderservicelineestimate"></a>Ordres d'exécution sur commandes client (Field Service vers Fin and Ops) : WorkOrderServiceLineEstimate

Filtre : (msdynce_headersystemstatus ne 690970005) et (msdynce_headersystemstatus ne 690970000) et (msdynce_orderhasexternalmaintainedproductsonly eq true) et (msdyn_linestatus eq 690970000) and (msdynce_headersystemstatus ne 690970004)

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWorkOrder2.png )](./media/FSWorkOrder2.png)

### <a name="work-orders-to-sales-orders-field-service-to-fin-and-ops-workorderservicelineused"></a>Ordres d'exécution sur commandes client (Field Service vers Fin and Ops) : WorkOrderServiceLineUsed

Filtre : (msdynce_headersystemstatus ne 690970005) et (msdynce_headersystemstatus ne 690970000) et (msdynce_orderhasexternalmaintainedproductsonly eq true) et ((msdyn_linestatus eq 690970001) ou (msdynce_headersystemstatus eq 690970004))

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWorkOrder3.png )](./media/FSWorkOrder3.png)

### <a name="work-orders-to-sales-orders-field-service-to-fin-and-ops-workorderproductlineestimate"></a>Ordres d'exécution sur commandes client (Field Service vers Fin and Ops) : WorkOrderProductLineEstimate

Filtre : (msdynce_headersystemstatus ne 690970005) et (msdynce_headersystemstatus ne 690970000) et (msdynce_orderhasexternalmaintainedproductsonly eq true) et (msdyn_linestatus eq 690970000) and (msdynce_headersystemstatus ne 690970004) et (msdyn_allocated eq true)

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWorkOrder4.png )](./media/FSWorkOrder4.png)

### <a name="work-orders-to-sales-orders-field-service-to-fin-and-ops-workorderproductlineused"></a>Ordres d'exécution sur commandes client (Field Service vers Fin and Ops) : WorkOrderProductLineUsed

Filtre : (msdynce_headersystemstatus ne 690970005) et (msdynce_headersystemstatus ne 690970000) et (msdynce_orderhasexternalmaintainedproductsonly eq true) et ((msdyn_linestatus eq 690970001) ou (msdynce_headersystemstatus eq 690970004) ou (msdyn_allocated ne true))

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSWorkOrder5.png )](./media/FSWorkOrder5.png)

