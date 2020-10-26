---
title: Configurer le mappage pour les champs de statut de la commande client
description: Cette rubrique explique comment configurer les champs de statut de la commande client pour la double écriture.
author: dasani-madipalli
manager: tonyafehr
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: damadipa
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-06-25
ms.openlocfilehash: dce4b6310e2f6d31a115302efa7fbc132799e48f
ms.sourcegitcommit: 4ba10abe5be8a21b95370cd970a622e954970984
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "3829283"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-fields"></a>Configurer le mappage pour les champs de statut de la commande client

[!include [banner](../../includes/banner.md)]

Les champs qui indiquent le statut de la commande client ont des valeurs d'énumération différentes dans Microsoft Dynamics 365 Supply Chain Management et Dynamics 365 Sales. Une configuration supplémentaire est requise pour mapper ces champs en double écriture.

## <a name="fields-in-supply-chain-management"></a>Champs dans Supply Chain Management

Dans Supply Chain Management, deux champs reflètent le statut de la commande client. Les champs que vous devez mapper sont **Statut** et **Statut du document**.

L'énumération de **Statut** spécifie le statut global de la commande. Ce statut est indiqué sur l'en-tête de la commande.

L'énumération de **Statut** a les valeurs suivantes :

- Commande en cours
- Livré(e)
- Facturé(e)
- Annulé(e)

L'énumération de **Statut du document** spécifie le document le plus récent généré pour la commande. Par exemple, si la commande est confirmée, ce document est une confirmation de commande client. Si une commande client est partiellement facturée et que la ligne restante est confirmée, le statut du document reste **Facture**, car la facture est générée plus tard dans le processus.

L'énumération de **Statut du document** a les valeurs suivantes :

- Confirmation
- Prélèvements
- Bon de livraison
- Facture

## <a name="fields-in-sales"></a>Champs dans Sales

Dans Sales, deux champs indiquent le statut de la commande. Les champs que vous devez mapper sont **Statut** et **Statut de traitement**.

L'énumération de **Statut** spécifie le statut global de la commande. Il présente les valeurs suivantes :

- Actif.ve
- Soumis
- Exécuté
- Facturé(e)
- Annulé(e)

L'énumération de **Statut de traitement** a été introduite afin que le statut puisse être mappé plus précisément avec Supply Chain Management.

Le tableau suivant montre le mappage du **Statut de traitement** dans Supply Chain Management.

| Statut de traitement   | Statut dans Supply Chain Management | Statut de document dans Supply Chain Management |
|---------------------|-----------------------------------|--------------------------------------------|
| Actif.ve              | Commande en cours                        | None                                       |
| Confirmée           | Commande en cours                        | Confirmation                               |
| Prélevé(e)              | Commande en cours                        | Prélèvements                               |
| Partiellement livré | Commande en cours                        | Bon de livraison                               |
| Livré(e)           | Livré(e)                         | Bon de livraison                               |
| Partiellement facturé  | Livré(e)                         | Facture                                    |
| Facturé(e)            | Facturé(e)                          | Facture                                    |
| Annulé(e)           | Annulé(e)                         | Non applicable                             |

Le tableau suivant montre le mappage du **Statut de traitement** entre Sales et Supply Chain Management.

| Statut de traitement   | Statut dans Sales | Statut dans Supply Chain Management |
|---------------------|-----------------|-----------------------------------|
| Actif.ve              | Actif.ve          | Commande en cours                        |
| Confirmée           | Soumis       | Commande en cours                        |
| Prélevé(e)              | Soumis       | Commande en cours                        |
| Partiellement livré | Actif.ve          | Commande en cours                        |
| Partiellement facturé  | Actif.ve          | Commande en cours                        |
| Partiellement facturé  | Exécuté       | Livré(e)                         |
| Facturé(e)            | Facturé(e)        | Facturé(e)                          |
| Annulé(e)           | Annulé(e)       | Annulé(e)                         |

## <a name="setup"></a>Paramétrage

Pour configurer le mappage des champs de statut de la commande client, vous devez activer les attributs **IsSOPIntegrationEnabled** et **isIntegrationUser**.

Pour activer l'attribut **IsSOPIntegrationEnabled**, procédez comme suit.

1. Dans un navigateur, accédez à `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`. Remplacez **\<test-name\>** avec le lien de votre entreprise vers Sales.
2. Sur la page qui s'ouvre, recherchez **organisationid**, et notez la valeur.

    ![Recherche de Organizationid](media/sales-map-orgid.png)

3. Dans Sales, ouvrez la console du navigateur et exécutez le script suivant. Utilisez la valeur **organisationid** de l'étape 2.

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on record update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![Code JavaScript dans la console du navigateur](media/sales-map-script.png)

4. Vérifiez que **IsSOPIntegrationEnabled** est défini sur **true**. Utilisez l'URL de l'étape 1 pour vérifier la valeur.

    ![IsSOPIntegrationEnabled défini sur true](media/sales-map-integration-enabled.png)

Pour activer l'attribut **isIntegrationUser**, procédez comme suit.

1. Dans Sales, accédez à **Paramètre \> Personnalisation \> Personnaliser le système**, sélectionnez **Entité utilisateur**, puis ouvrez **Écran \> Utilisateur**.

    ![Ouverture de l'écran utilisateur](media/sales-map-user.png)

2. Dans Field Explorer, recherchez **Mode utilisateur de l'intégration** et double-cliquez dessus pour l'ajouter à l'écran. Enregistrez votre modification.

    ![Ajout du champ Mode utilisateur de l'intégration à l'écran](media/sales-map-field-explorer.png)

3. Dans Sales, accédez à **Paramètre \> Sécurité \> Utilisateurs** et changez les vues de **Utilisateurs activés** à **Utilisateurs de l'application**.

    ![Modification de la vue de Utilisateurs activés à Utilisateurs de l'application](media/sales-map-enabled-users.png)

4. Sélectionnez les deux entrées pour **DualWrite IntegrationUser**.

    ![Liste des utilisateurs d'application](media/sales-map-user-mode.png)

5. Changer la valeur du champ **Mode utilisateur de l'intégration** sur **Oui**.

    ![Changement de la valeur du champ Mode utilisateur de l'intégration](media/sales-map-user-mode-yes.png)

Vos commandes client sont maintenant mappées.