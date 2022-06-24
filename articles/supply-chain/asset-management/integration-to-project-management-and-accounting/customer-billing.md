---
title: Facture de maintenance sur les actifs appartenant au client
description: Cet article explique comment créer, traiter et facturer les tâches de maintenance effectuées sur les actifs appartenant à vos clients.
author: johanhoffmann
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjProjectContractsListPage, ProjInvoiceTable, ProjProjectsListPage, ProjTable, EntAssetWorkOrderType, EntAssetWorkOrderProjectSetup, EntAssetObjectTable, EntAssetWorkOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: d6ad25ec49a329c16b0290278fb614293a507eae
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887687"
---
# <a name="bill-for-maintenance-on-customer-owned-assets"></a>Facture de maintenance sur les actifs appartenant au client

[!include [banner](../../includes/banner.md)]

La fonctionnalité *Facturation des ordres de travail* vous permet de créer, traiter et facturer les tâches de maintenance effectuées sur les actifs appartenant à vos clients. Cette fonctionnalité vous permet d’effectuer les tâches suivantes :

- Connectez les clients aux actifs dont ils sont propriétaires.
- Sélectionnez un client et affichez les actifs qu’il possède lorsque vous créez un ordre de travail.
- Configurez un projet parent pour chaque client.
- Enregistrez les heures, les articles, les dépenses et les frais par rapport à l’ordre de travail, puis créez une proposition de facture pour le client ultérieurement.

En outre, la fonctionnalité offre les fonctionnalités suivantes :

- Le contrat de projet du projet parent d’un client est automatiquement copié dans le projet d’ordre de travail correspondant.
- La gestion des actifs peut désormais utiliser la transaction de projet de type *frais* sur les prévisions des ordres de travail et les journaux des ordres de travail.

## <a name="turn-on-the-customer-billing-feature"></a>Activer la fonctionnalité Facturation client

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion et comptabilité des projets*
- **Nom de la fonctionnalité :** *Facturation des ordres de travail*

## <a name="example-scenario"></a>Exemple de scénario

Pour savoir comment cette fonctionnalité fonctionne, suivez l’exemple de scénario suivant.

Pour utiliser ce scénario à l’aide des exemples d’enregistrements et de valeurs spécifiés ici, vous devez utiliser un système sous lequel les [données de démonstration](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard sont installées. Vous devez sélectionner l’entité juridique **USMF** avant de commencer.

Vous pouvez également utiliser ce scénario comme orientation pour utiliser la fonctionnalité lorsque vous travaillez sur un système de production. Cependant, dans ce cas, vous devez remplacer vos propres valeurs, et il se peut que certains types d’enregistrements requis que les données de démonstration standard fournissent manquent.

### <a name="step-1-create-a-new-project-contract-for-the-customer"></a>Étape 1 : Créer un contrat de projet pour le client

1. Accédez à **Gestion et comptabilité des projets \> Projets \> Contrats de projets**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Nouveau contrat de projet**, sélectionnez les valeurs suivantes :

    - **Nom :** *Pelican Wholesales*
    - **Type de financement :** *Client*
    - **Source de financement :** *US-013* (*Pelican Wholesales*)

1. Cliquez sur **OK**.

### <a name="step-2-create-a-new-parent-project-for-the-customer"></a>Étape 2 : Créer un projet parent pour le client

Le projet parent que vous créez ici sera utilisé lors de la création des ordres de travail pour le client.

1. Accédez à **Gestion et comptabilité des projets \> Projets \> Tous les projets**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Nouveau projet**, définissez les valeurs suivantes :

    - **Type de projet :** *Régie*
    - **Nom du projet :** *Ordres de travail Pelican Wholesales*
    - **Groupe de projets :** *TM*
    - **ID du contrat de projet :** *Pelican Wholesales* (le contrat que vous avez créé précédemment)
    - **Date de début :** sélectionnez la date d’aujourd’hui.

1. Sélectionnez **Créer un projet**.
1. Le nouveau projet est ouvert. Prenez note de la valeur **ID de projet**. Vous devrez le saisir plus tard.

### <a name="step-3-create-a-new-work-order-type-in-asset-management"></a>Étape 3 : Créer un nouveau type d’ordre de travail dans Gestion des actifs

1. Accédez à **Gestion des actifs \> Paramétrage \> Ordre de travail \> Types d’ordre de travail**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Un nouvel enregistrement est ajouté à la liste. Définissez les valeurs suivantes pour cette ligne :

    - **Type d’ordre d’exécution :** *Service*
    - **Nom :** *Ordres de travail de service*
    - **État du cycle de vie de l’ordre de travail :** *Standard*

### <a name="step-4-link-the-customer-account-to-the-parent-project"></a>Étape 4 : Associer le compte client au projet parent

Vous devez maintenant associer le compte client au projet parent dans la configuration du projet dans Gestion des actifs.

1. Accédez à **Gestion des actifs \> Paramétrage \> Ordres de travail \> Paramétrage du projet**.
1. Sous l’onglet **Projet parent**, sélectionnez **Ajouter** pour ajouter une ligne.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Compte client :** *US-013* (*Pelican Wholesales*)
    - **ID de projet** : saisissez l’ID de projet que vous avez noté précédemment.

### <a name="step-5-link-the-project-group-and-type-to-the-work-order-project"></a>Étape 5 : Associer le groupe de projets et le type au projet d’ordre de travail

Vous devriez toujours être sur la page **Configuration du projet** (**Gestion des actifs \> Configurer \> Ordres de travail \> Configuration du projet**).

1. Sous l’onglet **Groupe de projets**, sélectionnez **Ajouter** pour ajouter une ligne.
1. Sur la nouvelle ligne, définissez les valeurs suivantes :

    - **Type d’ordre de travail :** *Service* (le type d’ordre de travail que vous avez créé précédemment)
    - **Groupe de projets :** *TM*

> [!NOTE]
> Le contrat de projet sur le projet d’ordre de travail est toujours hérité du projet parent.

### <a name="step-6-link-an-asset-to-the-customer-id"></a>Étape 6 : Associer un élément à l’identifiant client

1. Accédez à **Gestion des actifs \> Actifs \> Tous les Actifs (ou Actifs actifs)**.
1. Dans le champ **Filtre**, entrez *VE-102*, et sélectionnez pour filtrer par **Actif**.
1. Sélectionnez l’actif pour ouvrir ses paramètres.
1. Dans l’organisateur **Client**, définissez le champ **Compte client** sur *US-013* (*Pelican Wholesales*).

    Le champ **Nom** est automatiquement mis à jour pour *Pelican Wholesales*.

### <a name="step-7-create-a-new-work-order-on-the-asset"></a>Étape 7 : Créer un nouveau type d’ordre de travail sur l’actif

1. Accédez à **Gestion des actifs \> Ordres de travail \> Ordres de travail actifs**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer un ordre de travail**, définissez les valeurs suivantes :

    - **Type d’ordre d’exécution :** *Service*
    - **Description :** *Camion de réparation*
    - **Compte client :** *US-013* (*Pelican Wholesales*)
    - **Actif :** *VE-102*

        > [!NOTE]
        > La recherche n’affiche que les actifs liés au compte client sélectionné.

    - **Type de tâche de maintenance :** *Réparation*
    - **Commerce :** *Mécanique*
    - **Niveau de service :** *4*

1. Cliquez sur **OK**.

### <a name="step-8-review-the-work-order-and-start-to-work-on-it"></a>Étape 8 : Passer en revue l’ordre de travail et commencer à l’utiliser

Dans cette section, vous allez travailler sur l’ordre de travail que vous avez créé dans la section précédente.

1. Suivez ces étapes pour vérifier que le projet parent est le projet *Ordre de travail Pelican Wholesales* :

    1. Dans la section **Tâches de maintenance des ordres de travail**, sélectionnez une ligne.
    1. Sur l’organisateur **Détails de la ligne**, inspectez la valeur **ID de projet**. Il doit s’agir d’un nombre avec trait d’union sous la forme *\<Parent-Project-ID\>-\<Project-ID\>*. Cette valeur est un lien.
    1. Sélectionnez le lien de l’ID de projet pour ouvrir une page dans laquelle vous pouvez afficher le projet parent et les noms de projet.

1. Dans le volet Actions, sous l’onglet **Ordre de travail**, dans le groupe **État du cycle de vie**, sélectionnez **Mettre à jour l’état de l’ordre de travail**.
1. Dans la boîte de dialogue **Mettre à jour l’état de l’ordre de travail**, dans la colonne **Sélectionner**, cochez la case de la ligne où le champ **État du cycle de vie** est défini sur *En cours*.
1. Cliquez sur **OK**.
1. Dans la boîte de dialogue **État du cycle de vie : en cours**, sélectionnez **OK**.

### <a name="step-9-post-the-hours-that-were-spent-on-the-work-order-and-create-a-new-invoice-proposal"></a>Étape 9 : Publier les heures passées sur l’ordre de travail et créer une proposition de facture

Dans cette section, vous continuerez à travailler sur l’ordre de travail sur lequel vous avez travaillé dans la section précédente.

1. Dans le volet Actions, sous l’onglet **Ordre de travail**, dans le groupe **Projet**, sélectionnez **Journaux**.

    La page **Journaux des ordres de travail** apparaît. Ici, vous pouvez enregistrer le temps que vous avez passé sur l’ordre de travail.

1. Dans l’organisateur **Heures**, sélectionnez **Ajouter une ligne**.
1. Sur la nouvelle ligne, définissez le champ **Heures** sur *4*.
1. Dans le volet Actions, sélectionnez **Publier les journaux**.
1. Fermez la page **Journaux des ordres de travail** pour revenir à l’ordre de travail.
1. Dans le volet Actions, sous l’onglet **Facturation**, sélectionnez **Nouvelle proposition de facture**.
1. Dans la boîte de dialogue **Créer une proposition de facture**, dans la section **Transactions de projet**, cochez la case **Sélectionner** pour chaque ligne que vous souhaitez facturer.
1. Sélectionnez **OK** pour fermer la boîte de dialogue et afficher la nouvelle proposition de facture.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]