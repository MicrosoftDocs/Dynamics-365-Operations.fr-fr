---
title: Configurer le mappage des colonnes de statut des commandes client
description: Cet article explique comment configurer les colonnes de statut de la commande client pour la double écriture.
author: dasani-madipalli
ms.date: 06/25/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: damadipa
ms.search.validFrom: 2020-06-25
ms.openlocfilehash: 2035985f16b5972e02f1ed60c6f02d306217f3be
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288882"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-columns"></a>Configurer le mappage des colonnes de statut des commandes client

[!include [banner](../../includes/banner.md)]

Les colonnes qui indiquent le statut de la commande client ont des valeurs d’énumération différentes dans Microsoft Dynamics 365 Supply Chain Management et Dynamics 365 Sales. Une configuration supplémentaire est requise pour mapper ces colonnes en double écriture.

## <a name="columns-in-supply-chain-management"></a>colonnes dans Supply Chain Management

Dans Supply Chain Management, deux colonnes reflètent le statut de la commande client. Les colonnes que vous devez mapper sont **Statut** et **Statut du document**.

L’énumération de **Statut** spécifie le statut global de la commande. Ce statut est indiqué sur l’en-tête de la commande.

L’énumération de **Statut** a les valeurs suivantes :

- Commande en cours
- Livré(e)
- Facturé(e)
- Annulé(e)

L’énumération de **Statut du document** spécifie le document le plus récent généré pour la commande. Par exemple, si la commande est confirmée, ce document est une confirmation de commande client. Si une commande client est partiellement facturée et que la ligne restante est confirmée, le statut du document reste **Facture**, car la facture est générée plus tard dans le processus.

L’énumération de **Statut du document** a les valeurs suivantes :

- Confirmation
- Prélèvements
- Bon de livraison
- Facture

## <a name="columns-in-sales"></a>colonnes dans Sales

Dans Sales, deux colonnes indiquent le statut de la commande. Les colonnes que vous devez mapper sont **Statut** et **Statut de traitement**.

L’énumération de **Statut** spécifie le statut global de la commande. Il présente les valeurs suivantes :

- Actif.ve
- Soumis
- Exécuté
- Facturé(e)
- Annulé(e)

L’énumération de **Statut de traitement** a été introduite afin que le statut puisse être mappé plus précisément avec Supply Chain Management.

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

Pour configurer le mappage des colonnes de statut de la commande client, vous devez activer les attributs **IsSOPIntegrationEnabled** et **isIntegrationUser**.

Pour activer l’attribut **IsSOPIntegrationEnabled**, procédez comme suit.

1. Dans un navigateur, accédez à `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`. Remplacez **\<test-name\>** avec le lien de votre entreprise vers Sales.
2. Sur la page qui s’ouvre, recherchez **organisationid**, et notez la valeur.

    ![Recherche de Organizationid.](media/sales-map-orgid.png)

3. Dans Sales, ouvrez la console du navigateur et exécutez le script suivant. Utilisez la valeur **organisationid** de l’étape 2.

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on row update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![Code JavaScript dans la console du navigateur.](media/sales-map-script.png)

4. Vérifiez que **IsSOPIntegrationEnabled** est défini sur **true**. Utilisez l’URL de l’étape 1 pour vérifier la valeur.

    ![IsSOPIntegrationEnabled défini sur true.](media/sales-map-integration-enabled.png)

Pour activer l’attribut **isIntegrationUser**, procédez comme suit.

1. Dans Sales, accédez à **Paramètre \> Personnalisation \> Personnaliser le système**, sélectionnez **Table utilisateur**, puis ouvrez **Écran \> Utilisateur**.

    ![Ouverture de l’écran utilisateur.](media/sales-map-user.png)

2. Dans Field Explorer, recherchez **Mode utilisateur de l’intégration** et double-cliquez dessus pour l’ajouter à l’écran. Enregistrez votre modification.

    ![Ajout de la colonne Mode utilisateur de l’intégration à l’écran.](media/sales-map-field-explorer.png)

3. Dans Sales, accédez à **Paramètre \> Sécurité \> Utilisateurs** et changez les vues de **Utilisateurs activés** à **Utilisateurs de l’application**.

    ![Modification de la vue de Utilisateurs activés à Utilisateurs de l’application.](media/sales-map-enabled-users.png)

4. Sélectionnez les deux entrées pour **DualWrite IntegrationUser**.

    ![Liste des utilisateurs d’application.](media/sales-map-user-mode.png)

5. Changez la valeur de la colonne **Mode utilisateur de l’intégration** sur **Oui**.

    ![Changement de la valeur de la colonne Mode utilisateur de l’intégration.](media/sales-map-user-mode-yes.png)

Vos commandes client sont maintenant mappées.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
