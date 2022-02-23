---
title: Démarrage du module complémentaire de facturation électronique pour le Mexique
description: Cette rubrique donne des informations qui vous aideront à démarrer le module complémentaire de facturation électronique pour le Mexique dans Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management.
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
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 6d15a79a359b3c708b2b33893d700377a57c3eb7
ms.sourcegitcommit: cfd84321fba38e02e270d361df369a536a48efa3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2020
ms.locfileid: "4512232"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-mexico"></a>Démarrage du module complémentaire de facturation électronique pour le Mexique

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Le module complémentaire de facturation électronique pour le Mexique peut ne pas prendre en charge actuellement toutes les fonctions disponibles dans le document Comprobante Fiscal Digital por Internet (CFDI) et dans l’intégration associée intégrée dans Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management.

Cette rubrique donne des informations qui vous aideront à démarrer le module complémentaire de facturation électronique pour le Mexique. Elle vous guide tout au long des étapes de configuration spécifiques au pays dans Regulatory Configuration Services (RCS) et Finance. Elle vous guide également tout au long des étapes que vous devez suivre dans Finance pour envoyer des factures CFDI via le service. Elle explique aussi comment passer en revue les résultats du traitement et le statut des factures CFDI.

## <a name="prerequisites"></a>Conditions préalables

Avant d’effectuer les étapes de cette rubrique, vous devez effectuer les étapes de la rubrique [Démarrage du module complémentaire de facturation électronique](e-invoicing-get-started.md).

## <a name="rcs-setup"></a>Paramétrage RCS

Lors du paramétrage de RCS, vous effectuerez les tâches suivantes :

1. Importer la fonctionnalité de facturation électronique pour le traitement des factures CFDI.
2. Passer en revue les configurations de format nécessaires pour générer, envoyer et recevoir des réponses concernant les factures CFDI, ainsi que pour envoyer et recevoir des réponses concernant l’annulation.
3. Configurer les événements prenant en charge les scénarios d’envoi de factures CFDI.
4. Publier la fonctionnalité de facturation électronique pour les factures CFDI.

> [!NOTE]
> La « Fonctionnalité de facturation électronique » est le nom générique de la ressource configurée et publiée pour utiliser le serveur complémentaire de facturation électronique. Dans ce cas, les factures CFDI (MX) sont la fonctionnalité de facturation électronique que vous allez paramétrer.

## <a name="import-the-e-invoicing-feature"></a>Importer la fonctionnalité de facturation électronique

1. Connectez-vous à votre compte RCS.
2. Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Fonctionnalités**, sélectionnez la vignette **Facturation électronique**.
3. Sur la page **Fonctionnalités de facturation électronique**, sélectionnez **Importer** pour importer la fonctionnalité **Factures CFDI (MX)** à partir du référentiel global.

    > [!NOTE]
    > Si vous ne voyez pas la fonctionnalité dans la liste, sélectionnez **Synchroniser**, puis répétez l’étape 3.

![Importation de la fonctionnalité Factures CFDI (MX)](media/e-Invoicing-services-get-started-MEX-Select-Import-CFDI-feature.png)

Lorsque vous importez la fonctionnalité **Factures CFDI (MX)** à partir du référentiel global, tous les paramètres de la fonctionnalité, y compris les configurations et les actions, sont également importés.

### <a name="create-a-new-version-of-the-cfdi-invoices-mx-feature"></a>Créer une nouvelle version de la fonctionnalité Factures CFDI (MX)

Vous pouvez créer une nouvelle version si, par exemple, les URL doivent être mises à jour. Pour plus d’informations, voir [Facturation électronique CFDI](tasks/mx-00010-e-invoicing-cfdi.md).

- Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Versions**, sélectionnez **Nouveau**.

![Ajout d’une nouvelle version de la fonctionnalité de facturation électronique](media/e-Invoicing-services-get-started-MEX-Select-New-e-Invoicing-feature.png)

### <a name="update-the-configuration-version"></a>Mettre à jour la version de la configuration

1. Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Configurations**, sélectionnez **Ajouter** ou **Supprimer** pour gérer les versions de configuration (configurations de format de fichier ER).

    ![Gestion des configurations de la fonctionnalité de facturation électronique](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Configurations.png)

    Lorsque vous créez une nouvelle version, toutes les configurations sont héritées de la dernière version publiée. Pour traiter les factures CFDI, les configurations suivantes sont requises :

    - Facture CFDI (BusinessDocumentService)
    - Importation du message de réponse CFDI
    - Importation du journal des erreurs CFDI
    - Demande d’annulation CFDI (MX) (BusinessDocumentService)
    - Facture CFDI (BusinessDocumentService)

2. Dans la liste, sélectionnez une version de configuration, puis sélectionnez **Modifier** ou **Afficher** pour ouvrir la page **Concepteur de formats** dans laquelle vous pouvez modifier ou afficher la configuration.

    ![Ouverture de la page Concepteur de formats](media/e-Invoicing-services-get-started-MEX-Configuration-ER-format-designer.png)

3. Utilisez la page **Concepteur de formats** pour modifier ou afficher les configurations de format de fichier ER. Pour plus d’informations, voir [Créer des configurations de document électronique](../../dev-itpro/analytics/electronic-reporting-configuration.md).

    ![Page Concepteur de formats](media/e-Invoicing-services-get-started-MEX-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a>Gérer les paramétrages de la fonctionnalité de facturation électronique

- Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Paramétrages**, sélectionnez **Ajouter**, **Supprimer** ou **Modifier** pour gérer les paramétrages de la fonctionnalité de facturation électronique.

![Gestion des paramétrages de la fonctionnalité de facturation électronique](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Setup.png)

Pour envoyer des factures CFDI pour autorisation (générer le fichier XML, envoyer le fichier XML et traiter la réponse), le paramétrage de la fonctionnalité **Facture client** est nécessaire.

Pour envoyer une annulation de facture CFDI, le paramétrage des fonctionnalités **Annulation** et **Annuler** est nécessaire.

### <a name="configure-the-sales-invoice-feature-setup"></a>Configurer le paramétrage de la fonctionnalité Facture client

1. Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Paramétrages**, dans la colonne **Paramétrage de fonctionnalité**, sélectionnez **Facture client**.
2. Sélectionnez **Modifier** pour configurer les actions, les règles d’applicabilité et les variables.

    ![Modification du paramétrage de la fonctionnalité de facturation électronique](media/e-Invoicing-services-get-started-MEX-Edit-e-Invoicing-feature-setup.png)

3. Sur la page **Paramétrage de version de fonctionnalité**, sélectionnez l’onglet **Actions** pour gérer la liste des actions. Les actions définissent une liste d’opérations qui doivent être exécutées dans un ordre séquentiel pour permettre l’exécution complète de l’événement.

    ![Onglet Actions](media/e-Invoicing-services-get-started-MEX-Select-Actions.png)

    | ID action | Action                   | Nom de l’action                                  | Description de l’action                                          |
    |-----------|--------------------------|----------------------------------------------|-------------------------------------------------------------|
    | 1         | Transformer le document       | Générer la facture électronique CFDI sans signature numérique | Générez la facture électronique CFDI.                                |
    | 2         | Signer le document            | Signature numérique                                 | Signez numériquement la facture électronique pour envoi.                |
    | 3         | Appeler le service PAC mexicain | Envoyer la facture électronique CFDI                        | Le client Windows Communication Foundation (WCF) envoie la facture électronique CFDI. |
    | 4         | Réponse du processus         | Analyser la réponse du service web                 | Analysez la réponse du service web et renvoyez le journal des erreurs. |

### <a name="set-up-the-url-for-mexican-pac-web-services"></a>Paramétrer l’URL des services web PAC mexicains 

1. Sur la page **Paramétrage de version de fonctionnalité**, dans l’onglet **Actions**, dans le raccourci **Actions**, sélectionnez **Appeler le service PAC méxicain**.
2. Dans le raccourci **Paramètres**, dans le champ **Adresse URL**, entrez l’URL du service web pour l’envoi de facture CFDI.

> [!NOTE]
> Suivez les mêmes étapes pour mettre à jour l’URL de l’action **Appeler le service PAC mexicain** pour le paramétrage des fonctionnalités **Annuler** et **Demande d’annulation**.

## <a name="assign-the-draft-version-to-an-e-invoicing-environment"></a>Attribuer la version brouillon à un environnement de facturation électronique

1. Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Environnements**, sélectionnez **Activer**.
2. Dans le champ **Environnement**, sélectionnez l’environnement.
3. Dans le champ **Date d’effet**, sélectionnez la date à laquelle l’environnement doit prendre effet.
3. Sélectionnez **Activer**.

![Activation d’un environnement de facturation électronique](media/e-Invoicing-services-get-started-MEX-Enable-e-Invoicing-Environment.png)

## <a name="change-the-version-status-to-completed"></a>Modifier le statut de la version en Terminé

1. Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Versions**, sélectionnez la version de la fonctionnalité de facturation électronique présentant le statut **Brouillon**.
2. Sélectionnez **Modifier le statut \> Terminé**.

## <a name="change-the-version-status-to-published"></a>Modifier le statut de la version en Publié

- Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Versions**, sélectionnez **Modifier le statut \> Publier**.

## <a name="publish-the-e-invoicing-feature"></a>Publier la fonctionnalité de facturation électronique

1. Sur la page **Fonctionnalités de facturation électronique**, sélectionnez l’onglet **Versions** pour gérer le statut de la fonctionnalité **Factures CFDI (MX)**.
2. Sélectionnez **Modifier le statut** pour modifier le statut de la fonctionnalité.

![Modification du statut de la fonctionnalité de facturation électronique](media/e-Invoicing-services-get-started-MEX-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance"></a>Paramétrer l’intégration du module complémentaire de facturation électronique dans Finance

Pour paramétrer le module complémentaire de facturation électronique dans Finance, vous effectuerez les tâches suivantes :

1. Importer le modèle de données ER, le mappage du modèle de données ER et les formats requis pour les factures CFDI.
2. Configurer les types de réponse pour mettre à jour les factures CFDI. Ces types de réponse sont utilisés pour la réponse du serveur du fournisseur de certification autorisé (PAC).

### <a name="import-the-er-data-model-er-data-model-mapping-and-context-configurations-for-cfdi-invoices"></a>Importer le modèle de données ER, le mappage du modèle de données ER et les configurations de contexte pour les factures CFDI

1. Connectez-vous à Finance.
2. Dans l’espace de travail **États électroniques**, dans la section **Fournisseurs de configuration**, sélectionnez le titre **Microsoft**. Vérifiez que ce fournisseur de configuration est défini sur **Actif**. Pour plus d’informations sur la définition d’un fournisseur sur **Actif**, voir [Créer des fournisseurs de configuration et les marquer comme actifs](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).
3. Sélectionnez **Référentiels**.
4. Sélectionnez **Ressource globale \> Ouvrir**.
5. Importez **Modèle de facture**, **Mappage du modèle de facture**, **Format de facture CFDI (MX)**, **Format de demande d’annulation de facture CFDI (MX)** et **Format d’annulation de facture CFDI (MX)**.

### <a name="turn-on-the-feature-for-processing-cfdi-invoices"></a>Activer la fonctionnalité de traitement des factures CFDI

1. Allez dans **Administration de l’organisation \> Paramétrage \> Paramètres des documents électroniques**.
2. Dans l’onglet **Fonctionnalités**, cochez la case **Activer** dans les lignes des références de fonctionnalité **MX-00010** et **MX-00016**.

![Activation des fonctionnalités de traitement des factures CFDI](media/e-Invoicing-services-get-started-MEX-Enable-CFDI-feature.png)

### <a name="import-er-configurations-and-set-up-the-response-types-for-updating-cfdi-invoices"></a>Importer les configurations ER et configurer les types de réponse pour la mise à jour des factures CFDI

#### <a name="import-er-configurations"></a>Importer les configurations ER

1. Dans l’espace de travail **États électroniques**, dans la section **Fournisseurs de configuration**, sélectionnez le titre **Microsoft**.
3. Sélectionnez **Référentiels**.
4. Sélectionnez **Ressource globale \> Ouvrir**.
5. Importez **Modèle de message de réponse**, **Importation du journal des erreurs CFDI (MX)** et **Importation du message de réponse CFDI (MX)**.

#### <a name="set-up-the-response-types"></a>Configurer les types de réponse

1. Allez dans **Administration de l’organisation \> Paramétrage \> Paramètres des documents électroniques**.
2. Dans l’onglet **Document électronique**, sélectionnez **Ajouter**.
3. Entrez le journal des factures client, puis, dans le champ **Nom de la table**, sélectionnez la facture du projet.
4. Pour chaque table, définissez un contexte de document associé :

    - Pour **Journal des factures client**, entrez **Contexte de la facture client**.
    - Pour **Facture de projet**, entrez **Contexte de la facture de projet**.

4. Sélectionnez **Types de réponse** pour configurer les types de réponse pouvant être renvoyés à partir du module complémentaire de facturation électronique et inclus dans un journal des factures client ou une facture de projet.
5. Sélectionnez **Nouveau**, puis, dans dans le champ **Type de réponse**, sélectionnez **Réponse**.
6. Dans le champ **Statut d’envoi**, sélectionnez **En attente**.
7. Dans le champ **Mappage de modèle**, sélectionnez **Format d’importation du message de réponse - Mappage de modèle à partir du message de réponse**.
8. Sélectionnez **Enregistrer**.
9. Sélectionnez **Nouveau**, puis, dans dans le champ **Type de réponse**, sélectionnez **ResponseData**.
10. Dans le champ **Statut d’envoi**, sélectionnez **En attente**.
11. Dans le champ **Mappage de modèle**, sélectionnez **Format d’importation des données de réponse CFDI (détails) - Importation des données de réponse**.
12. Sélectionnez **Enregistrer**.

## <a name="process-electronic-invoices-in-finance"></a>Traiter les factures électroniques dans Finance 

Lors du traitement des factures CFDI dans Finance via le module complémentaire de facturation électronique, vous pouvez effectuer les tâches suivantes :

- Envoyer des factures CFDI.
- Afficher les journaux d’exécution de l’envoi.
- Envoyer l’annulation d’une facture CFDI.

### <a name="submit-cfdi-invoices"></a>Envoyer des factures CFDI

Après avoir activé la fonctionnalité **Intégration du module complémentaire de facturation électronique configurable**, le processus **Exporter/Importer la facture électronique** (**Comptabilité client \> Factures \> Factures électroniques**) pour l’envoi des factures CFDI n’est plus utilisé. Il est remplacé par un nouveau processus appelé **Envoyer des documents électroniques**.

> [!NOTE]
> Avant d’utiliser le nouveau processus **Envoyer des documents électroniques**, vérifiez que le paramétrage requis pour les factures électroniques mexicaines a été effectué. Pour plus d’informations, voir [Version 3.3 de la disposition CFDI](https://docs.microsoft.com/dynamics365/finance/localizations/latam-mex-cfdi-3-3).

1. Allez dans **Administration de l’organisation \> Périodique \> Documents électroniques \> Envoyer des documents électroniques**.
2. Pour le premier envoi d’un document, définissez toujours l’option **Envoyer de nouveau les documents** sur **Non**. Si vous devez envoyer à nouveau un document via le service, définissez cette option sur **Oui**.
3. Dans le raccourci **Enregistrements à inclure**, sélectionnez **Filtrer** pour ouvrir la boîte de dialogue **Recherche** dans laquelle vous pouvez créer une requête pour sélectionner des documents pour envoi.

![Envoyer un document CFDI](media/e-Invoicing-services-get-started-MEX-Submit-CFDI-document.png)

> [!NOTE]
> Lors de votre première tentative d’envoi d’un document via le service, vous serez invité à confirmer la connexion avec le module complémentaire de facturation électronique. Sélectionnez **Cliquez ici pour vous connecter au service d’envoi de document électronique**.

### <a name="view-submission-logs"></a>Afficher les journaux d’envoi

Vous pouvez afficher les journaux d’envoi pour tous les documents envoyés ou pour un seul document envoyé.

#### <a name="view-all-submission-logs"></a>Afficher tous les journaux d’envoi

Après avoir activé la fonctionnalité **Intégration du module complémentaire de facturation électronique configurable**, une nouvelle page vous permet de suivre le processus d’envoi de document. Vous pouvez utiliser cette page pour afficher les journaux d’envoi de tous les documents envoyés.

1. Allez dans **Administration de l’organisation \> Périodique \> Documents électroniques \> Journal d’envoi de documents électroniques**.
2. Dans le champ **Type de document**, sélectionnez **Journal des factures client** pour filtrer les documents électroniques requis.

    ![Sélection d’un type de document pour afficher les journaux d’envoi](media/e-Invoicing-services-get-started-MEX-Select-document-type-for-viewing-submission-log.png)

3. Dans le volet Actions, sélectionnez **Recherches \> Détails de l’envoi** pour afficher les détails des journaux d’exécution de l’envoi.

    ![Affichage des détails du journal d’envoi](media/e-Invoicing-services-get-started-MEX-View-submission-log-details.png)

Les informations des journaux d’envoi sont réparties en trois raccourcis :

- **Actions de traitement** : ce raccourci affiche le journal d’exécution des actions configurées dans la version de fonctionnalité paramétrée dans RCS. La colonne **Statut** indique si l’exécution de l’action a réussi.
- **Fichiers d’action** : ce raccourci affiche les fichiers intermédiaires générés lors de l’exécution des actions. Vous pouvez sélectionner **Afficher** pour télécharger et afficher le fichier.
- **Journal des actions de traitement** : ce raccourci affiche les résultats de la communication entre le module complémentaire de facturation électronique et le service web cible. Il indique également ce qui a été renvoyé par le traitement du service web. La colonne **Code d’erreur** affiche le code de retour renvoyé par le service web d’autorisation.

Lorsque la facture CFDI envoyée est autorisée, son statut est mis à jour sur **Approuvé**.

#### <a name="view-submission-logs-from-cfdi-invoices"></a>Afficher les journaux d’envoi à partir des factures CFDI

Après avoir activé la fonctionnalité **Intégration du module complémentaire de facturation électronique configurable**, vous pouvez également afficher les journaux d’envoi à partir des documents fiscaux.

1. Allez dans **Comptabilité client \> Recherches et états \> CFDI (factures électroniques)**.
2. Sélectionnez une facture CFDI qui a été envoyée après l’activation de la fonctionnalité **Intégration du module complémentaire de facturation électronique configurable**.
3. Dans le volet Actions, dans l’onglet **Historique**, sélectionnez **Journal des documents électroniques**.

![Affichage des journaux d’envoi à partir des factures CFDI](media/e-Invoicing-services-get-started-MEX-View-submission-log-from-CFDI-invoice.png)

> [!NOTE]
> Pour les factures CFDI envoyées avant l’activation de la fonctionnalité **Intégration du module complémentaire de facturation électronique configurable**, le bouton **Historique** est disponible. Le bouton **Historique** n’est pas disponible pour les factures CFDI envoyées après l’activation de la fonctionnalité **Intégration du module complémentaire de facturation électronique configurable**.

### <a name="submit-cancellation-of-cfdi-invoices"></a>Envoyer l’annulation des factures CFDI

Après avoir activé la fonctionnalité **Intégration du module complémentaire de facturation électronique configurable**, l’ancien processus d’annulation des factures CFDI ne peut plus être utilisé. Il est remplacé par un nouveau processus d’annulation intégré à la page **Journal d’envoi de documents électroniques**.

1. Allez dans **Comptabilité client \> Recherches et états \> CFDI (factures électroniques)**.
2. Si la facture CFDI a le statut **Approuvé**, sélectionnez **Fonctions \> Annuler CFDI**.
3. Allez dans **Administration de l’organisation \> Périodique \> Documents électroniques \> Journal d’envoi de documents électroniques**.
4. Sélectionnez la facture CFDI, puis sélectionnez **Fonctions \> Envoyer les envois associés**.
5. Entrez une description de l’envoi associé, puis cliquez sur **OK**.

#### <a name="view-cancellation-submission-logs"></a>Afficher les journaux d’envoi de l’annulation

1. Allez dans **Administration de l’organisation \> Périodique \> Documents électroniques \> Journal d’envoi de documents électroniques**.
2. Dans le champ **Type de document**, sélectionnez **Journal des factures client** pour filtrer les documents du journal des factures client uniquement.
3. Sélectionnez la facture CFDI, puis, dans le volet Actions, sélectionnez **Recherches \> Envoi associé**.

    La page **Envois associés** affiche tous les envois associés et leur statut d’envoi pour une facture CFDI donnée. Dans l’illustration suivante, la première ligne représente l’envoi qui a demandé l’approbation de la facture CFDI. La deuxième ligne représente l’envoi qui a annulé cette facture CFDI.

    ![Affichage des journaux d’envoi de l’annulation](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log.png)

4. Dans le volet Actions, sélectionnez **Recherches \> Détails de l’envoi** pour afficher les détails des journaux d’exécution de l’envoi.

    ![Affichage des détails du journal d’envoi de l’annulation](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log-details.png)

## <a name="privacy-notice"></a>Avis de confidentialité
L’activation des fonctionnalités MX-00010 et MX-00016 (Facture CFDI et Annulation CFDI) peut nécessiter l’envoi de données limitées, notamment l’ID d’enregistrement fiscal de l’organisation. Ces données seront transmises à des organismes tiers autorisés par l’administration fiscale aux fins d’envoi de factures électroniques à cette administration fiscale dans le format prédéfini requis pour l’intégration avec le service web du gouvernement. Un administrateur peut activer et désactiver les fonctionnalités MX-00010 et MX-00016 (Facture CFDI et Annulation CFDI) en accédant à **Administration de l’organisation \> Paramétrage \> Paramètres des documents électroniques**. Sélectionnez l’onglet **Fonctionnalités**, sélectionnez les lignes contenant les fonctionnalités MX-00010 et MX-00016, puis effectuez la sélection appropriée. Les données importées depuis ces systèmes externes vers ce service en ligne Dynamics 365 sont soumises à notre [déclaration de confidentialité](https://go.microsoft.com/fwlink/?LinkId=512132). Pour plus d’informations, consultez les sections Déclaration de confidentialité dans la documentation de la fonctionnalité spécifique au pays.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Présentation du module complémentaire de facturation électronique](e-invoicing-service-overview.md)
- [Démarrage du module complémentaire de facturation électronique](e-invoicing-get-started.md)
- [Paramétrer le module complémentaire de facturation électronique](e-invoicing-setup.md)
