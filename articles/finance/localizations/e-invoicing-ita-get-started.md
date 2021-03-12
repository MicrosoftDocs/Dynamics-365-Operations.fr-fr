---
title: Démarrage du module complémentaire de facturation électronique pour l’Italie
description: Cette rubrique donne des informations qui vous aideront à démarrer le module complémentaire de facturation électronique pour l’Italie dans Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 08d41244d3ec785127db8f69e37dd522a463c388
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988538"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-italy"></a>Démarrage du module complémentaire de facturation électronique pour l’Italie

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> Le module complémentaire de facturation électronique pour l’Italie peut ne pas prendre actuellement en charge toutes les fonctions disponibles pour les factures électroniques dans Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management. 

Cette rubrique donne des informations qui vous aideront à démarrer le module complémentaire de facturation électronique pour l’Italie. Elle vous guide tout au long des étapes de configuration spécifiques au pays dans Regulatory Configuration Services (RCS) et Finance. Elle vous guide également tout au long du processus d’envoi de factures électroniques générées au format **FatturaPA** propre à l’Italie via le service. Elle explique aussi comment passer en revue les résultats du traitement.

## <a name="prerequisites"></a>Conditions préalables

Avant d’effectuer les étapes de cette rubrique, vous devez effectuer les étapes de la rubrique [Démarrage du module complémentaire de facturation électronique](e-invoicing-get-started.md).

## <a name="rcs-setup"></a>Paramétrage RCS

Lors du paramétrage de RCS, vous effectuerez les tâches suivantes :

1. Importer la fonctionnalité de facturation électronique pour l’exportation des factures électroniques client au format **FatturaPA**.
2. Passer en revue les configurations de format nécessaires pour générer, envoyer et recevoir des réponses concernant les factures électroniques.
3. Configurer les événements prenant en charge les scénarios d’envoi de factures électroniques.
4. Publier la fonctionnalité de facturation électronique.

> [!NOTE]
> La « Fonctionnalité de facturation électronique » est le nom générique de la ressource configurée et publiée pour utiliser le serveur complémentaire de facturation électronique. Dans ce cas, l’exportation des factures électroniques client est la fonctionnalité de facturation électronique que vous allez paramétrer.

## <a name="import-the-e-invoicing-feature"></a>Importer la fonctionnalité de facturation électronique

1. Connectez-vous à votre compte RCS.
2. Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Fonctionnalités**, sélectionnez la vignette **Facturation électronique**.
3. Sur la page **Fonctionnalités de facturation électronique**, sélectionnez **Importer** pour importer la fonctionnalité de facturation électronique à partir du référentiel global.

    > [!NOTE]
    > Si vous ne voyez pas la liste des fonctionnalités disponibles, sélectionnez **Synchroniser**. 

4. Sélectionnez la fonctionnalité **Exportation de factures électroniques (IT)**, puis sélectionnez **Importer**.

![Importation de la fonctionnalité Exportation de factures électroniques (IT)](media/e-Invoicing-services-get-started-ITA-Select-Import-e-Invoicing-feature.png)

Lorsque vous importez la fonctionnalité **Exportation de factures électroniques (IT)** à partir du référentiel global, tous les paramètres décrits dans les sections suivantes sont également importés.

## <a name="create-a-new-version-of-the-e-invoices-export-it-feature"></a>Créer une nouvelle version de la fonctionnalité Exportation de factures électroniques (IT)

1. Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Versions**, sélectionnez **Nouveau**. 

    ![Ajout d’une nouvelle version de la fonctionnalité de facturation électronique](media/e-Invoicing-services-get-started-ITA-Select-New-e-Invoicing-feature-version.png)

    Ensuite, vous allez configurer les formats d’états électroniques (ER) associés à la fonctionnalité de facturation électronique.

2. Dans l’onglet **Configurations**, sélectionnez **Ajouter** pour gérer les versions de configuration.

    ![Gestion des versions de configuration de la fonctionnalité de facturation électronique](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-configurations.png)

    Dans cette étape, vous ajoutez et configurez les formats ER de différents fichiers utilisés pour exporter des factures électroniques italiennes. Pour les factures électroniques FatturaPA italiennes, utilisez les configurations standard suivantes ou les configurations personnalisées réelles que vous utilisez pour la facturation électronique :

    - Facture client (IT)
    - Facture de projet (IT)

    Lorsque vous créez une fonctionnalité de facturation électronique dérivée d’une autre fonctionnalité de facturation électronique, tous les formats ER sont hérités de la fonctionnalité d’origine.

3. Sélectionnez une configuration de format de fichier ER spécifique.
4. Sélectionnez **Modifier** ou **Afficher** pour ouvrir la page **Concepteur de formats**.

    ![Ouverture de la page Concepteur de formats](media/e-Invoicing-services-get-started-ITA-Configuration-ER-format-designer.png)

5. Utilisez la page **Concepteur de formats** pour modifier ou afficher les configurations de format de fichier ER.

    ![Page Concepteur de formats](media/e-Invoicing-services-get-started-ITA-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a>Gérer les paramétrages de la fonctionnalité de facturation électronique

- Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Paramétrages**, sélectionnez **Ajouter**, **Supprimer** ou **Modifier** pour gérer les paramétrages de la fonctionnalité de facturation électronique.

![Gestion des paramétrages de la fonctionnalité de facturation électronique](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-setup.png)

Dans cette étape, vous configurez les événements applicables aux factures électroniques, notamment la génération des fichiers de sortie XML au format **FatturaPA** et la signature numérique (si nécessaire).

### <a name="configure-the-sales-invoice-feature-setup"></a>Configurer le paramétrage de la fonctionnalité Facture client

1. Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Paramétrages**, dans la colonne **Paramétrage de fonctionnalité**, sélectionnez **Facture client**.
2. Sélectionnez **Modifier**.
3. Sur la page **Paramétrage de version de fonctionnalité**, sélectionnez l’onglet **Actions** pour gérer la liste des actions. Les actions définissent une liste d’opérations qui doivent être exécutées dans un ordre séquentiel pour permettre l’exécution complète de l’événement.

    ![Onglet Actions](media/e-Invoicing-services-get-started-ITA-Select-Actions.png)

    | ID action | Nom de l’action        | Description de l’action                                     |
    |-----------|--------------------|--------------------------------------------------------|
    | 1         | Transformer le document | Créez le fichier XML de la facture électronique au format **FatturaPA**. |
    | 2         | Signer le document      | Appliquez une certificat numérique au fichier XML.             |

4. Sélectionnez l’onglet **Règles d’applicabilité** pour afficher et gérer les règles d’applicabilité. Les règles d’applicabilité définissent le contexte d’exécution de l’action.

    ![Onglet Règles d’applicabilité](media/e-Invoicing-services-get-started-ITA-Select-Applicability-rules.png)

5. Sélectionnez l’onglet **Variables** pour afficher et gérer les variables.

    ![Onglet Variables](media/e-Invoicing-services-get-started-ITA-Select-Variables.png)

6. Définissez les variables publiques nécessaires pour exécuter les actions.

### <a name="configure-the-project-invoice-feature-setup"></a>Configurer le paramétrage de la fonctionnalité Facture de projet 

Les étapes et les paramètres nécessaires pour configurer le paramétrage de la fonctionnalité **Facture de projet** sont très similaires à ceux du paramétrage de la fonctionnalité **Facture client**. Lorsque vous utilisez des factures de projet, consultez les procédures pour les factures client.

## <a name="assign-the-e-invoicing-feature-to-the-environment"></a>Attribuer la fonctionnalité de facturation électronique à l’environnement

1. Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Environnements**, sélectionnez **Activer**.
2. Dans le champ **Environnement**, sélectionnez l’environnement.
3. Dans le champ **Date d’effet**, sélectionnez la date à laquelle l’environnement doit prendre effet.
4. Sélectionnez **Activer**. 

![Activation de l’environnement de facturation électronique](media/e-Invoicing-services-get-started-ITA-Enable-e-Invoicing-environment.png)

## <a name="publish-the-e-invoicing-feature"></a>Publier la fonctionnalité de facturation électronique

Vous pouvez publier la fonctionnalité de facturation électronique en modifiant le statut de la version en **Terminé** ou **Publié**.

### <a name="change-the-version-status-to-completed"></a>Modifier le statut de la version en Terminé

1. Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Versions**, sélectionnez la version de la fonctionnalité de facturation électronique présentant le statut **Brouillon**.
2. Sélectionnez **Modifier le statut \> Terminé**. 

### <a name="change-the-version-status-to-published"></a>Modifier le statut de la version en Publié 

1. Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Versions**, sélectionnez la version de la fonctionnalité de facturation électronique présentant le statut **Terminé**.
2. Sélectionnez **Modifier le statut \> Publier**.

![Modification du statut de la fonctionnalité de facturation électronique](media/e-Invoicing-services-get-started-ITA-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance"></a>Paramétrer l’intégration du module complémentaire de facturation électronique dans Finance

Lors du paramétrage de Finance, vous effectuerez les tâches suivantes :

1. Importer le modèle de données ER, le mappage du modèle de données ER et les configurations de contexte pour les factures électroniques FatturaPA.
2. Configurer le certificat nécessaire pour signer numériquement les factures électroniques italiennes.

### <a name="import-the-er-data-model-data-model-mapping-and-formats"></a>Importer le modèle de données ER, le mappage du modèle de données et les formats

1. Dans l’espace de travail **États électroniques**, vérifiez que le fournisseur de configuration **Service de documents commerciaux** est défini sur **Actif**.
2. Sélectionnez **Référentiels**.
3. Sélectionnez **Ressource globale \> Ouvrir**.
4. Importez **Modèle de facture**, **Mappage du modèle de facture** et **Modèle de contexte de facture client**.

#### <a name="turn-on-the-feature-for-exporting-customer-electronic-invoices-for-italy"></a>Activer la fonctionnalité d’exportation de factures électroniques client pour l’Italie

1. Allez dans **Administration de l’organisation \> Paramétrage \> Paramètres des documents électroniques**.
2. Dans l’onglet **Fonctionnalités**, cochez la case **Activé** dans la ligne de la référence de fonctionnalité **IT00036**.

![Activation de la fonctionnalité FatturaPA](media/e-Invoicing-services-get-started-ITA-Enable-FatturaPA-feature.png)

#### <a name="configure-electronic-documents"></a>Configurer des documents électroniques

1. Allez dans **Administration de l’organisation \> Paramétrage \> Paramètres des documents électroniques**.
2. Dans l’onglet **Document électronique**, sélectionnez **Ajouter** et entrez les tables nécessaires pour générer des factures électroniques italiennes :

    - **Nom de la table :** Journal des factures client
    - **Nom de la table :** Facture de projet

3. Pour chaque table, définissez un contexte de document associé :

    - Pour **Journal des factures client**, sélectionnez **Contexte de la facture client**.
    - Pour **Facture de projet**, sélectionnez **Contexte de la facture de projet**.

![Configuration des types de réponse](media/e-Invoicing-services-get-started-ITA-Set-up-response-types.png)

## <a name="electronic-invoice-processing"></a>Traitement de facture électronique

Lors du traitement dans Finance, vous effectuerez les tâches suivantes :

1. Générer des factures électroniques italiennes via le module complémentaire de facturation électronique
2. Afficher les journaux d’exécution et passer en revue les résultats du traitement

### <a name="generate-electronic-invoices"></a>Générer des factures électroniques

Après avoir activé la fonctionnalité **Intégration du module complémentaire de facturation électronique configurable** et activé la fonctionnalité **IT00036**, l’ancien processus Finance de génération de factures électroniques italiennes ne peut plus être utilisé. Il est remplacé par un nouveau processus appelé **Envoyer des documents électroniques**.

Vous pouvez envoyer les documents manuellement, en fonction de votre demande de documents de facture électronique.

> [!NOTE]
> Avant de continuer, vérifiez que la configuration nécessaire pour les factures électroniques italiennes a été effectuée. Pour plus d’informations, voir [Factures électroniques client](https://docs.microsoft.com/dynamics365/finance/localizations/emea-ita-e-invoices). Notez que certaines des étapes de configuration décrites dans cette rubrique peuvent ne pas être disponibles en raison de l’activation du module complémentaire de facturation électronique.

1. Allez dans **Administration de l’organisation \> Périodique \> Documents électroniques \> Envoyer des documents électroniques**.
2. Pour le premier envoi d’un document, définissez l’option **Envoyer de nouveau les documents** sur **Non**. Si vous devez envoyer à nouveau un document via le service, définissez cette option sur **Oui**.
3. Dans le raccourci **Enregistrements à inclure**, sélectionnez **Filtrer** pour ouvrir la boîte de dialogue **Recherche** dans laquelle vous pouvez créer une requête pour sélectionner des documents pour envoi.

![Boîte de dialogue Envoyer des documents électroniques](media/e-Invoicing-services-get-started-ITA-Submission-form.png)

#### <a name="filter-query"></a>Requête de filtre

1. Dans la boîte de dialogue **Recherche**, configurez les conditions de filtrage des factures client et des factures de projet, ou laissez les conditions vides pour inclure toutes les factures non envoyées.

    ![Configuration des critères de filtrage de l’envoi](media/e-Invoicing-services-get-started-ITA-Set-up-Submission-filter-criteria.png)

2. Cliquez sur **OK** pour fermer la boîte de dialogue **Recherche**.
3. Cliquez sur **OK** pour envoyer les documents sélectionnés.

> ![REMARQUE] Lors de votre première tentative d’envoi d’un document via le service, vous serez invité à confirmer la connexion avec le module complémentaire de facturation électronique. Sélectionnez **Cliquez ici pour vous connecter au service d’envoi de document électronique**.

#### <a name="view-submission-logs"></a>Afficher les journaux d’envoi

Vous pouvez afficher les journaux d’envoi pour tous les documents envoyés.

1. Allez dans **Administration de l’organisation \> Périodique \> Documents électroniques \> Journal d’envoi de documents électroniques**.
2. Dans le champ **Type de document**, sélectionnez **Journal des factures client** ou **Facture de projet** pour filtrer les documents électroniques requis.

    ![Sélection d’un type de document pour afficher les journaux d’envoi](media/e-Invoicing-services-get-started-ITA-Select-Document-type-for-viewing-submission-log.png)

    La valeur affichée dans la colonne **Statut d’envoi** représente le statut du processus d’envoi. Elle indique si le processus a été exécuté comme configuré et si une action supplémentaire est nécessaire.

3. Dans le volet Actions, sélectionnez **Recherches \> Détails de l’envoi** pour afficher les détails des journaux d’exécution de l’envoi.

    ![Affichage des détails du journal d’envoi](media/e-Invoicing-services-get-started-ITA-View-Submission-log-details.png)

4. Dans le raccourci **Actions de traitement**, vous pouvez afficher le journal d’exécution des actions configurées dans la version de fonctionnalité paramétrée dans RCS. La colonne **Statut** indique si l’exécution de l’action a réussi.
5. Dans le raccourci **Fichiers d’action**, vous pouvez afficher les fichiers intermédiaires générés lors de l’exécution des actions. Vous pouvez sélectionner **Afficher** pour télécharger le fichier XML de sortie au format **FatturaPA** et afficher son contenu.

## <a name="related-topics"></a>Rubriques connexes

- [Présentation du module complémentaire de facturation électronique](e-invoicing-service-overview.md)
- [Démarrage du module complémentaire de facturation électronique](e-invoicing-get-started.md)
- [Paramétrer le module complémentaire de facturation électronique](e-invoicing-setup.md)
