---
title: Démarrage du module complémentaire de facturation électronique pour le Brésil
description: Cette rubrique donne des informations qui vous aideront à démarrer le module complémentaire de facturation électronique pour le Brésil dans Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/04/2020
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
ms.openlocfilehash: fb3ec2d60875d7a0747d64b397aafaa0a3d26348
ms.sourcegitcommit: f860ac2b18f6bbbfc4a46b497baec2477105b116
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/19/2020
ms.locfileid: "4443353"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-brazil"></a>Démarrage du module complémentaire de facturation électronique pour le Brésil 

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> Le module complémentaire de facturation électronique pour le Brésil ne prend pas actuellement en charge toutes les fonctions disponibles dans l’intégration de document fiscal intégrée dans Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management.

Cette rubrique donne des informations qui vous aideront à démarrer le module complémentaire de facturation électronique pour le Brésil. Elle vous guide tout au long des étapes de configuration spécifiques au pays dans Regulatory Configuration Services (RCS) et dans Finance et Supply Chain Management. Elle vous guide également tout au long du processus d’envoi d’un document fiscal NF-e (modèle 55 de document fiscal électronique) via le service. Elle explique comment passer en revue les résultats du traitement et le statut des documents fiscaux.

## <a name="prerequisites"></a>Conditions préalables

Avant d’effectuer les étapes de cette rubrique, vous devez effectuer les étapes de la rubrique [Démarrage du module complémentaire de facturation électronique](e-invoicing-get-started.md).

## <a name="rcs-setup"></a>Paramétrage RCS

Lors du paramétrage de RCS, vous effectuerez les tâches suivantes :

1. Importer la fonctionnalité de facturation électronique pour les documents fiscaux NF-e.
2. Passer en revue les formats de fichier requis pour envoyer des documents fiscaux NF-e pour autorisation.
3. Passer en revue les formats de fichier requis pour demander l’annulation d’un document NF-e approuvé.
4. Configurer l’événement requis pour envoyer des documents fiscaux NF-e pour autorisation.
5. Configurer l’élément requis pour demander l’annulation d’un document NF-e approuvé.
6. Attribuer la fonctionnalité de facturation électronique à un environnement complémentaire de facturation électronique.
7. Publier la fonctionnalité de facturation électronique.

> [!NOTE]
> La « Fonctionnalité de facturation électronique » est le nom générique de la ressource configurée et publiée pour utiliser le serveur complémentaire de facturation électronique. Le paramétrage de la fonctionnalité de facturation électronique combine, entre autres, l’utilisation de formats de configuration d’états électroniques pour créer des fichiers d’exportation et d’importation configurables, et l’utilisation d’actions et de flux d’actions pour permettre la création de règles configurables pour envoyer des demandes, importer les réponses et analyser le contenu des réponses.

## <a name="import-the-e-invoicing-feature"></a>Importer la fonctionnalité de facturation électronique

1. Connectez-vous à votre compte RCS
2. Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Fonctionnalités**, sélectionnez la vignette **Facturation électronique**.
3. Sur la page **Fonctionnalités de facturation électronique**, sélectionnez **Importer** pour importer une fonctionnalité de facturation électronique de document fiscal NF-e à partir du référentiel global.

    ![Bouton Importer](media/e-Invoicing-services-get-started-BRA-Select-Import-e-Invoicing-feature.png)

4. Sélectionnez la fonctionnalité de document fiscal NF-e, puis sélectionnez **Importer**.

    ![Importation de la fonctionnalité NF-e](media/e-Invoicing-services-get-started-BRA-Select-Import-NF-e-feature.png)

### <a name="create-a-new-version-of-the-nf-e-fiscal-document-feature"></a>Créer une nouvelle version de la fonctionnalité de document fiscal NF-e

- Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Versions**, sélectionnez **Nouveau**.

![Ajout d’une nouvelle version de la fonctionnalité de facturation électronique](media/e-Invoicing-services-get-started-BRA-Select-New-e-Invoicing-feature-version.png)

### <a name="update-the-configuration-version"></a>Mettre à jour la version de la configuration

1. Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Configurations**, sélectionnez **Ajouter** ou **Supprimer** pour gérer les versions de configuration (configurations de format de fichier ER).

    ![Gestion des configurations de la fonctionnalité de facturation électronique](media/e-Invoicing-services-get-started-BRA-Manage-e-Invoicing-feature-configurations.png)

    - Lorsque vous créez une nouvelle version de la fonctionnalité de document fiscal NF-e, toutes les versions de configuration (formats de fichier ER) sont héritées de la dernière version.
    - Pour envoyer le document fiscal NF-e pour autorisation, les versions de configuration suivantes sont requises :

        - Format d’exportation de l’envoi NFe
        - Importation du message de réponse NFe
        - Importation du journal des erreurs NFe

    - Pour envoyer l’annulation NF-e, la version de configuration suivante est requise :

        - Format d’exportation de l’annulation NFe

2. Dans la liste, sélectionnez une version de configuration, puis sélectionnez **Modifier** ou **Afficher** pour ouvrir la page **Concepteur de formats** dans laquelle vous pouvez modifier ou afficher la configuration.

    ![Ouverture de la page Concepteur de formats](media/e-Invoicing-services-get-started-BRA-Configuration-ER-fomat-designer.png)

3. Utilisez la page **Concepteur de formats** pour modifier ou afficher les configurations de format de fichier ER. Pour plus d’informations, voir [Créer des configurations de document électronique](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration).

    ![Page Concepteur de formats](media/e-Invoicing-services-get-started-BRA-ER-Format-designer.png)

### <a name="manage-the-e-invoicing-feature-setups"></a>Gérer les paramétrages de la fonctionnalité de facturation électronique

- Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Paramétrages**, sélectionnez **Ajouter** ou **Supprimer** pour gérer les paramétrages de la fonctionnalité de facturation électronique (c’est-à-dire les événements NF-e).

![Gestion des paramétrages de la fonctionnalité de facturation électronique](media/e-Invoicing-services-get-started-BRA-Manage-e-Invoicing-feature-setup.png)

Lorsque vous créez une nouvelle version de la fonctionnalité de document fiscal NF-e qui est dérivée d’une autre fonctionnalité de facturation électronique, tous les paramétrages de fonctionnalité (événements NF-e) sont hérités de la dernière version.

Pour envoyer des documents fiscaux NF-e pour autorisation, le paramétrage de la fonctionnalité **Envoyer** est requis.

Pour envoyer une annulation NF-e, le paramétrage de la fonctionnalité **Annulation** est requis.

#### <a name="configure-the-submit-feature-setup"></a>Configurer le paramétrage de la fonctionnalité Envoyer

1. Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Paramétrages**, dans la colonne **Paramétrage de fonctionnalité**, sélectionnez **Envoyer**.
2. Sélectionnez **Modifier**.

    ![Modifier le paramétrage de la fonctionnalité de facturation électronique](media/e-Invoicing-services-get-started-BRA-Edit-e-Invoicing-feature-setup.png)

3. Sur la page **Paramétrage de version de fonctionnalité**, sélectionnez l’onglet **Actions** pour gérer la liste des actions.

    ![Onglet Actions](media/e-Invoicing-services-get-started-BRA-Select-Actions.png)

4. Passez en revue les actions requises pour envoyer un document NF-e pour autorisation.

    | ID action | Nom de l’action                  | Description de l’action                                                |
    |-----------|------------------------------|-------------------------------------------------------------------|
    | 1         | Transformer le document           | Créez le fichier XML NF-e pour envoi.                          |
    | 2         | Signer le document                | Appliquez le certificat numérique au fichier XML.                    |
    | 3         | Appeler le service SEFAZ brésilien | Envoyez le fichier XML signé aux services web pour autorisation. |
    | 4         | Réponse du processus             | Obtenez la réponse du service web.                                     |
    | 5         | Transformer le document           | Analysez le contenu du fichier reçu en réponse.     |
    | 6         | Transformer le document           | Créez le fichier XML pour demander le statut de l’envoi.    |
    | 7         | Appeler le service SEFAZ brésilien | Envoyez le fichier XML qui demande le statut d’envoi.          |
    | 8         | Réponse du processus             | Obtenez la réponse du service web.                                     |

#### <a name="set-up-the-url-for-sefaz-web-services"></a>Paramétrer l’URL des services web SEFAZ 

1. Sur la page **Paramétrage de version de fonctionnalité**, dans l’onglet **Actions**, dans le raccourci **Actions**, sélectionnez **Appeler le service SEFAZ brésilien** (ID d’action **3**).
2. Dans le raccourci **Paramètres**, dans le champ **Paramètre d’adresse URL**, entrez l’URL du service web SEFAZ pour l’envoi NF-e.
3. Dans le raccourci **Actions**, sélectionnez **Appeler le service SEFAZ brésilien** (ID d’action **7**).
4. Dans le raccourci **Paramètres**, dans le champ **Paramètre d’adresse URL**, entrez l’URL du service web SEFAZ pour l’envoi NF-e.

#### <a name="configure-the-cancellation-feature-setup"></a>Configurer le paramétrage de la fonctionnalité Annulation

1. Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Paramétrages**, dans la colonne **Paramétrage de fonctionnalité**, sélectionnez **Annulation**.
2. Sélectionnez **Modifier**.
3. Sur la page **Paramétrage de version de fonctionnalité**, sélectionnez l’onglet **Actions** pour gérer la liste des actions.
4. Passez en revue les actions requises pour demander l’annulation d’un document NF-e approuvé.

    | ID action | Nom de l’action                  | Description de l’action                                               |
    |-----------|------------------------------|------------------------------------------------------------------|
    | 1         | Transformer le document           | Créez le fichier XML d’annulation NF-e pour envoi.            |
    | 2         | Signer le document                | Appliquez le certificat numérique au fichier XML.                   |
    | 3         | Appeler le service SEFAZ brésilien | Envoyez le fichier XML signé aux services web pour annulation. |
    | 4         | Réponse du processus             | Obtenez la réponse du service web.                                    |

#### <a name="set-up-the-url-for-sefaz-web-services"></a>Paramétrer l’URL des services web SEFAZ

1. Sur la page **Paramétrage de version de fonctionnalité**, dans l’onglet **Actions**, dans le raccourci **Actions**, sélectionnez **Appeler le service SEFAZ brésilien** (ID d’action **3**).
2. Dans le raccourci **Paramètres**, dans le champ **Paramètre d’adresse URL**, entrez l’URL du service web SEFAZ pour l’annulation d’un document NF-e approuvé.

### <a name="make-an-e-invoicing-environment-available-and-assign-a-draft-version"></a>Rendre un environnement de facturation électronique disponible et attribuer une version brouillon

1. Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Environnements**, sélectionnez **Activer**.
2. Dans le champ **Environnement**, sélectionnez l’environnement.
3. Dans le champ **Date d’effet**, sélectionnez la date à laquelle l’environnement doit prendre effet.
4. Sélectionnez **Activer**.

![Activation d’un environnement de facturation électronique](media/e-Invoicing-services-get-started-BRA-Enable-e-Invoicing-environment.png)

### <a name="change-the-status-to-completed"></a>Modifier le statut en Terminé

1. Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Versions**, sélectionnez la version de la fonctionnalité de facturation électronique présentant le statut **Brouillon**.
2. Sélectionnez **Modifier le statut \> Terminé**.

### <a name="change-the-status-to-publish"></a>Modifier le statut en Publier

1. Sur la page **Fonctionnalités de facturation électronique**, dans l’onglet **Versions**, sélectionnez la version de la fonctionnalité de facturation électronique présentant le statut **Terminé**.
2. Sélectionnez **Modifier le statut \> Publier**.

![Publication de la fonctionnalité de facturation électronique](media/e-Invoicing-services-get-started-BRA-Publish-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance-or-supply-chain-management"></a>Paramétrer l’intégration du module complémentaire de facturation électronique dans Finance ou Supply Chain Management

Lors du paramétrage, vous effectuerez les tâches suivantes :

1. Activer la fonctionnalité NF-e fédéral pour le Brésil.
2. Importer le modèle de données ER spécifique, le mappage du modèle de données et les formats requis pour les documents fiscaux NF-e.
3. Importer la configuration ER et configurer les types de réponse nécessaires pour mettre à jour le statut du document fiscal une fois le processus d’envoi renvoyé.

### <a name="turn-on-the-nf-e-federal-feature-for-brazil"></a>Activer la fonctionnalité NF-e fédéral pour le Brésil

1. Allez dans **Administration de l’organisation \> Paramétrage \> Paramètres des documents électroniques**.
2. Dans l’onglet **Fonctionnalités**, cochez la case **Activer** dans la ligne de la référence de fonctionnalité **BR00053**.

### <a name="import-the-er-data-model-mapping-required-for-nf-e-fiscal-documents"></a>Importer le mappage du modèle de données ER requis pour les documents fiscaux NF-e

1. Connectez-vous à Finance.
2. Dans l’espace de travail **États électroniques**, dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Microsoft**. Vérifiez que ce fournisseur de configuration est défini sur **Actif**. Pour plus d’informations sur la définition d’un fournisseur sur **Actif**, voir [Créer des fournisseurs de configuration et les marquer comme actifs](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).
3. Sélectionnez **Référentiels**.
4. Sélectionnez **Ressource globale \> Ouvrir**.
5. Importez les configurations **Mappage de documents fiscaux**.

### <a name="import-er-configurations-and-set-up-the-response-types-for-fiscal-documents"></a>Importer les configurations ER et configurer les types de réponse pour les documents fiscaux

1. Dans l’espace de travail **États électroniques**, dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Microsoft**.
2. Sélectionnez **Référentiels**.
3. Sélectionnez **Ressource globale \> Ouvrir**.
4. Importez **Importation du journal des erreurs NF-e (BR)**, **Format d’importation des données de réponse NF-e (BR)** et **Importation du message de réponse NF-e (BR)**.
5. Allez dans **Administration de l’organisation \> Paramétrage \> Paramètres des documents électroniques**.
6. Dans l’onglet **Document électronique**, sélectionnez **Ajouter**.
6. Dans le champ **Nom de la table**, entrez **En-tête du document fiscal**.
7. Dans le champ **Contexte du document**, sélectionnez **Modèle de contexte de facture client - Contexte du document fiscal**.
8. Sélectionnez **Types de réponse**.
9. Sélectionnez **Nouveau**, puis, dans dans le champ **Type de réponse**, sélectionnez **Réponse**.
10. Dans le champ **Statut d’envoi**, sélectionnez **En attente**.
11. Dans le champ **Mappage de modèle**, sélectionnez **Format d’importation du message de réponse - Mappage de modèle à partir du message de réponse**.
12. Sélectionnez **Enregistrer**.
13. Sélectionnez **Nouveau**, puis, dans dans le champ **Type de réponse**, entrez **ResponseData**.
14. Dans le champ **Statut d’envoi**, sélectionnez **En attente**.
15. Dans le champ **Mappage de modèle**, sélectionnez **Format d’importation des données de réponse NFe - Importation des données de réponse**.
16. Sélectionnez **Enregistrer**.

## <a name="electronic-invoice-processing"></a>Traitement de facture électronique

Lors du traitement dans Finance, vous effectuerez les tâches suivantes :

1. Envoyer un document fiscal via le module complémentaire de facturation électronique.
2. Afficher les journaux d’exécution de l’envoi et passer en revue les résultats du traitement.
3. Envoyer l’annulation d’un document fiscal via le module complémentaire de facturation électronique.

### <a name="submit-nf-e-fiscal-documents-for-sefaz-authorization"></a>Envoyer des documents fiscaux NF-e pour autorisation SEFAZ 

Après avoir activé la fonctionnalité **Intégration du module complémentaire de facturation électronique configurable**, l’ancien processus d’envoi des documents fiscaux NF-e pour autorisation (**Exporter/Importer le processus NF-e**) ne peut plus être utilisé. Il est remplacé par un nouveau processus appelé **Envoyer des documents électroniques**.

> [!NOTE]
> Avant de continuer, assurez-vous de disposer d’un ou de plusieurs modèles 55 de document fiscal client (modèle 55) qui ont été émis par l’établissement fiscal du client. La direction de ces documents fiscaux doit être définie sur **Sortant**, et le statut doit être **Créé**. Pour plus d’informations, voir [Émettre un document fiscal client (Brésil)](https://docs.microsoft.com/dynamics365/finance/localizations/tasks/br-00038-issuing-customer-fiscal-document).

1. Allez dans **Administration de l’organisation \> Périodique \> Documents électroniques \> Envoyer des documents électroniques**.
2. Pour le premier envoi d’un document, définissez toujours l’option **Envoyer de nouveau les documents** sur **Non**. Si vous devez envoyer à nouveau un document via le service, définissez cette option sur **Oui**.
3. Dans le raccourci **Enregistrements à inclure**, sélectionnez **Filtrer** pour ouvrir la boîte de dialogue **Recherche** dans laquelle vous pouvez créer une requête pour sélectionner des documents pour envoi.
4. Sous l’onglet **Plage**, sélectionnez **Ajouter**.
5. Dans le champ **Table**, sélectionnez **En-tête du document fiscal**.
6. Dans le champ **Table dérivée**, sélectionnez **En-tête du document fiscal**.
6. Dans le champ **Champ**, sélectionnez **Numéro**.
7. Dans le champ **Critères**, entrez le numéro du document fiscal à envoyer.
8. Cliquez sur **OK** pour fermer la boîte de dialogue **Recherche**.
8. Cliquez sur **OK** pour envoyer les documents sélectionnés.

> [!NOTE]
> Lors de votre première tentative d’envoi d’un document via le service, vous serez invité à confirmer la connexion avec le module complémentaire de facturation électronique. Sélectionnez **Cliquez ici pour vous connecter au service d’envoi de document électronique**.

### <a name="view-all-submission-logs"></a>Afficher tous les journaux d’envoi

Après avoir activé la fonctionnalité **Intégration du module complémentaire de facturation électronique configurable**, une nouvelle page vous permet de suivre le processus d’envoi de document. Vous pouvez utiliser cette page pour afficher les journaux d’envoi de tous les documents envoyés.

1. Allez dans **Administration de l’organisation \> Périodique \> Documents électroniques \> Journal d’envoi de documents électroniques**.
2. Dans le champ **Type de document**, sélectionnez **En-tête du document fiscal** pour filtrer les documents fiscaux uniquement.
3. Dans le volet Actions, sélectionnez **Recherches \> Détails de l’envoi** pour afficher les détails des journaux d’exécution de l’envoi.

![Affichage des détails du journal d’envoi](media/e-Invoicing-services-get-started-BRA-View-Submission-log-details.png)

> [!NOTE] 
> Pour les documents fiscaux NF-e, la colonne **Code d’erreur** affiche le code de retour renvoyé par les services web SEFAZ.

### <a name="view-submission-logs-through-the-fiscal-document-page"></a>Afficher les journaux d’envoi via la page des documents fiscaux

Après avoir activé la fonctionnalité **Intégration du module complémentaire de facturation électronique configurable**, vous pouvez également afficher les journaux d’envoi via la page des documents fiscaux.

1. Allez dans **Comptabilité \> Recherches et états \> Documents fiscaux \> Tous les documents fiscaux**.
2. Sélectionnez un document fiscal qui a été précédemment envoyé via le module complémentaire de facturation électronique.
3. Dans le volet Actions, dans l’onglet **NF-e fédéral**, sélectionnez **Journal des documents électroniques**.

![Affichage des journaux d’envoi à partir de la page des documents fiscaux](media/e-Invoicing-services-get-started-BRA-View-Submission-log-from-Fiscal-document-viewer.png)

### <a name="submit-approved-nf-e-fiscal-documents-for-sefaz-cancellation"></a>Envoyer des documents fiscaux NF-e approuvés pour annulation SEFAZ

Après avoir activé la fonctionnalité **Intégration du module complémentaire de facturation électronique configurable**, l’ancien processus d’annulation des documents fiscaux NF-e ne peut plus être utilisé. Il est remplacé par un nouveau processus d’annulation intégré à la page **Journal d’envoi de documents électroniques**.

> [!NOTE]
> Vérifiez que vous avez exécuté l’annulation du document fiscal client pour un document fiscal NF-e approuvé. Pour plus d’informations, voir [Annuler un document fiscal client (Brésil)](https://docs.microsoft.com/dynamics365/finance/localizations/latam-bra-cancel-customer-fiscal-documents).

1. Allez dans **Administration de l’organisation \> Périodique \> Documents électroniques \> Journal d’envoi de documents électroniques**.
2. Sélectionnez le document fiscal, puis sélectionnez **Fonctions \> Envoyer les envois associés**.
3. Entrez une description de l’envoi associé, puis cliquez sur **OK**.

### <a name="view-cancellation-submission-logs"></a>Afficher les journaux d’envoi de l’annulation

1. Allez dans **Administration de l’organisation \> Périodique \> Documents électroniques \> Journal d’envoi de documents électroniques**.
2. Dans le champ **Type de document**, sélectionnez **En-tête du document fiscal** pour filtrer les documents fiscaux uniquement.
3. Sélectionnez le document fiscal, puis, dans le volet Actions, sélectionnez **Recherches \> Envoi associé**.

    Les envois associés sont des envois associés à un envoi principal qui a été effectué en premier. Par exemple, l’envoi qui autorise un document NF-e spécifique est l’envoi principal. L’envoi qui demande l’annulation du même document NF-e dans SEFAZ est un envoi associé. Il n’existe que parce qu’il demande l’annulation de la tâche effectuée via un autre envoi.

    La page **Envois associés** affiche tous les envois associés et leur statut d’envoi pour un document fiscal donné. Dans l’illustration suivante, la première ligne représente l’envoi qui a demandé l’approbation du document fiscal. La deuxième ligne représente l’envoi qui a annulé ce document fiscal.

    ![Affichage des journaux d’envoi de l’annulation](media/e-Invoicing-services-get-started-BRA-View-Cancellation-Submission-log.png)

4. Dans le volet Actions, sélectionnez **Recherches \> Détails de l’envoi** pour afficher les détails des journaux d’exécution de l’envoi.

    ![Affichage des détails du journal d’envoi de l’annulation](media/e-Invoicing-services-get-started-BRA-View-Cancellation-Submission-log-details.png)

## <a name="privacy-notice"></a>Avis de confidentialité
L’activation de la fonctionnalité BR-00053 (NF-e fédéral) peut nécessiter l’envoi de données limitées, notamment l’ID d’enregistrement fiscal de l’organisation. Ces données seront transmises à des organismes tiers autorisés par l’administration fiscale aux fins d’envoi de factures électroniques à cette administration fiscale dans le format prédéfini requis pour l’intégration avec le service web du gouvernement. Un administrateur peut activer et désactiver la fonctionnalité BR-00053 (NF-e fédéral) en accédant à **Administration de l’organisation \> Paramétrage \> Paramètres des documents électroniques**. Sélectionnez l’onglet **Fonctionnalités**, sélectionnez la ligne contenant la fonctionnalité BR-00053, puis effectuez la sélection appropriée. Les données importées depuis ces systèmes externes vers ce service en ligne Dynamics 365 sont soumises à notre [déclaration de confidentialité](https://go.microsoft.com/fwlink/?LinkId=512132). Pour plus d’informations, consultez les sections Déclaration de confidentialité dans la documentation de la fonctionnalité spécifique au pays.


## <a name="additional-resources"></a>Ressources supplémentaires

- [Présentation du module complémentaire de facturation électronique](e-invoicing-service-overview.md)
- [Démarrage du module complémentaire de facturation électronique](e-invoicing-get-started.md)
- [Paramétrer le module complémentaire de facturation électronique](e-invoicing-setup.md)
