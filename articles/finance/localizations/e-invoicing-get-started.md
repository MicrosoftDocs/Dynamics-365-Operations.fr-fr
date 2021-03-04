---
title: Démarrage du module complémentaire de facturation électronique
description: Cette rubrique donne des informations qui vous aideront à démarrer le module complémentaire de facturation électronique dans Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 10/08/2020
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
ms.openlocfilehash: 7b2a3aae43d42060c7fcd9e1ea3db814fc5d8f22
ms.sourcegitcommit: f860ac2b18f6bbbfc4a46b497baec2477105b116
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/19/2020
ms.locfileid: "4443354"
---
# <a name="get-started-with-the-electronic-invoicing-add-on"></a>Démarrage du module complémentaire de facturation électronique

[!include [banner](../includes/banner.md)]

Cette rubrique donne des informations qui vous aideront à démarrer le module complémentaire de facturation électronique. Tout d’abord, elle vous guide tout au long des étapes de configuration dans Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Services (RCS) et Dynamics 365 Finance. Ensuite, elle décrit le processus d’envoi de documents via le service en utilisant Dynamics 365 Finance ou Dynamics 365 Supply Chain Management. Vous apprendrez également à interpréter les journaux d’envoi.

## <a name="availability"></a>Disponibilité

Le module complémentaire de facturation électronique est initialement disponible pour plusieurs pays. Il prend en charge la création de factures électroniques et l’envoi des documents commerciaux suivants :

| Pays/région  | Document commercial                          |
|-----------------|--------------------------------------------|
| Autriche         | Factures client et projet                 |
| Belgique         | Factures client et projet                 |
| Brésil          | Modèle 55 de document fiscal électronique (NF-e) |
| Danemark         | Factures client et projet                 |
| Estonie         | Factures client et projet                 |
| Finlande         | Factures client et projet                 |
| France          | Factures client et projet                 |
| Allemagne         | Factures client et projet                 |
| Italie           | Factures client et projet                 |
| Mexique          | Facture CFDI                               |
| Pays-Bas     | Factures client et projet                 |
| Norvège          | Factures client et projet                 |
| Espagne           | Factures client et projet                 |
| Europe          | Factures client et projet PEPPOL          |
    
## <a name="licensing"></a>Gestionnaire de licences

Vous pouvez utiliser le module complémentaire de facturation électronique avec votre licence actuelle. Aucune licence supplémentaire n’est nécessaire pour utiliser le service.

## <a name="prerequisites"></a>Conditions préalables

Avant d’effectuer les étapes de cette rubrique, les conditions préalables suivantes doivent être remplies :

- Accès à votre compte LCS.
- Un projet de déploiement LCS incluant Finance ou Supply Chain Management version 10.0.13 ou ultérieure.
- Accès à votre compte RCS.
- Activation de la fonctionnalité de globalisation pour votre compte RCS via le module **Gestion des fonctionnalités**. Pour plus d’informations, voir [Regulatory Configuration Services (RCS) - Fonctionnalités de globalisation](rcs-globalization-feature.md)
- Création d’une ressource de coffre de clés et d’un compte de stockage dans Azure. Pour plus d’informations, voir [Créer un compte de stockage Azure et un coffre de clés](e-invoicing-create-azure-storage-account-key-vault.md).

## <a name="overview"></a>Vue d’ensemble

L’illustration suivante présente les cinq étapes principales que vous effectuerez dans cette rubrique.

![Vue d’ensemble des cinq étapes de cette rubrique](media/e-invoicing-services-get-started-overview-5-steps.png)

1. **Paramétrage des ressources Azure :** configurez le stockage Azure et le chargement des certificats numériques dans Azure Key Vault.
2. **Paramétrage de LCS :** installez le complément pour les microservices.
3. **Paramétrage de RCS :** configurez l’environnement, l’accès utilisateur et les fonctionnalités de facturation électronique.
4. **Paramétrage du client :** configurez la connexion entre le client et le module complémentaire de facturation électronique et désactivez les anciennes fonctionnalités d’envoi et de réception de réponses pour les documents électroniques.
5. **Envoyer des factures :** envoyez des documents électroniques via le module complémentaire de facturation électronique et recevez des réponses.

> [!NOTE]
> Certaines étapes de configuration décrites dans cette rubrique sont communes et indifférentes au pays/à la région. Les étapes et les procédures de configuration spécifiques au pays/à la région sont décrites dans les rubriques correspondantes.

## <a name="lcs-setup"></a>Paramétrage LCS

1. Connectez-vous à votre compte LCS.
2. Sélectionnez la vignette **Gestion des fonctionnalités d’aperçu**, et dans le groupe de champs **Fonctionnalités de version préliminaire publique**, sélectionnez **BusinessDocumentSubmission**.
3. Marquez le champ **Fonctionnalité de version préliminaire activée**.
4. Sélectionnez le projet de déploiement LCS. Avant de pouvoir sélectionner le projet, celui-ci doit être opérationnel.
5. Dans le raccourci **Compléments de l’environnement**, sélectionnez **Installer un nouveau complément**.
6. Sélectionnez **Envoi de documents commerciaux**.
7. Dans la boîte de dialogue **Configurer le complément**, dans le champ **ID application AAD**, entrez **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Cette valeur est une valeur fixe.
8. Dans le champ **ID client AAD**, entrez l’ID de votre compte d’abonnement Azure.

    ![Boîte de dialogue Configurer le complément dans LCS](media/e-invoicing-services-get-started-lcs-addin-setup.png)

9. Cochez la case pour accepter les termes et conditions.
10. Sélectionnez **Installer**.

## <a name="rcs-setup"></a>Paramétrage RCS

Lors du paramétrage de RCS, vous effectuerez les tâches suivantes :

1. Paramétrer le coffre de clés dans RCS.
2. Paramétrer l’intégration RCS avec le serveur complémentaire de facturation électronique.
3. Créer un environnement complémentaire de facturation électronique pour votre organisation.

### <a name="set-up-the-key-vault-in-rcs"></a>Paramétrer le coffre de clés dans RCS

1. Connectez-vous à votre compte RCS.
2. Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Environnements**, sélectionnez la vignette **Facturation électronique**.
3. Sélectionnez **Environnements de service**.

    ![Sélection des environnements de service](media/e-invoicing-services-get-started-select-service-environments.png)

> [!NOTE]
> L’option **Applications connectées** autorise l’accès à la configuration automatique du module complémentaire de facturation électronique dans Finance ou Supply Management via RCS. Cependant, cette fonctionnalité est toujours actuellement en cours de développement.

4. Dans le volet Actions, sélectionnez **Paramètres du coffre de clés**.

    ![Sélection des paramètres du coffre de clés](media/e-invoicing-services-get-started-select-key-vault-parameters.png)

5. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter un coffre de clés.
6. Dans le champ **URI du coffre de clés**, entrez la valeur d’attribut **Nom DNS** de la ressource de coffre de clés que vous avez configurée dans Azure. Pour savoir où trouver la valeur **Nom DNS**, voir [Créer un compte de stockage Azure et un coffre de clés](e-invoicing-create-azure-storage-account-key-vault.md).

    ![Champ URI du coffre de clés](media/e-invoicing-services-get-started-enter-key-vault-uri.png)

7. Sur le raccourci **Certificats**, sélectionnez **Ajouter** pour saisir tous les noms de certificats numériques et les secrets de coffre de clés nécessaires pour établir des connexions fiables. Dans la colonne **Type**, vous pouvez spécifier s’il s’agit d’un certificat ou d’un secret. Les deux ensembles de valeurs sont configurés sur la ressource du coffre de clés dans Azure.

    ![Ajout de certificats](media/e-invoicing-services-get-started-add-digital-certificates.png)

8. Si la facture spécifique à votre pays/région nécessite une chaîne de certificats pour appliquer une signature numérique, sélectionnez **Chaîne de certificats** dans le volet Actions, puis entrez la séquence de certificats ou de secrets de coffre de clés qui composent la chaîne.

### <a name="set-up-the-rcs-integration-with-the-electronic-invoicing-add-on-server"></a>Paramétrer l’intégration RCS avec le serveur complémentaire de facturation électronique

1. Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Paramètres associés**, sélectionnez le lien **Paramètres de la gestion des états électroniques**.
2. Sélectionnez **Cliquez ici pour vous connecter à Lifecycle Services**. Si vous ne souhaitez pas vous connecter à LCS, sélectionnez **Annuler**.
3. Sur l’onglet **Services de facturation électronique**, dans le champ **URI du point de terminaison de service**, entrez la valeur en fonction des zones géographiques disponibles : `https://businessdocumentsubmission.us.operations365.dynamics.com/` ou `https://businessdocumentsubmission.eu.operations365.dynamics.com/`.
4. Dans le champ **ID application**, vérifiez que l’ID **0cdb527f-a8d1-4bf8-9436-b352c68682b2** s’affiche. Cette valeur est une valeur fixe.
5. Dans le champ **ID environnement LCS**, entrez l’ID de votre compte d’abonnement LCS.

![Saisie des paramètres complémentaires de facturation électronique](media/e-invoicing-services-get-started-enter-e-invoicing-parameters.png)

### <a name="add-an-electronic-invoicing-add-on-environment"></a>Ajouter un environnement complémentaire de facturation électronique

Vous pouvez créer différents environnements pour le module complémentaire de facturation électronique, tels que des environnements de développement, de test ou de production.

1. Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Environnements**, sélectionnez la vignette **Facturation électronique**.
2. Sélectionnez **Nouveau** pour créer un environnement.
3. Dans le champ **Compte du jeton SAS de stockage**, entrez le nom du secret du coffre de clés que vous avez configuré dans le coffre de clés de RCS.

    ![Champ Compte du jeton SAS de stockage](media/e-invoicing-services-get-started-enter-sas-token-secret.png)

4. Dans le raccourci **Utilisateurs**, sélectionnez **Nouveau** pour autoriser l’accès des utilisateurs à cet environnement.

    ![Ajout d’utilisateurs de service](media/e-invoicing-services-get-started-enter-service-users.png)

5. Dans le volet Actions, sélectionnez **Publier** pour publier l’environnement sur le serveur complémentaire de facturation électronique.

    ![Bouton Publier](media/e-invoicing-services-get-started-publish-service-environment.png)

### <a name="e-invoicing-feature-setup"></a>Paramétrage de la fonctionnalité de facturation électronique

La « Fonctionnalité de facturation électronique » est le nom générique de la ressource configurée et publiée pour utiliser le serveur complémentaire de facturation électronique. Le paramétrage de la fonctionnalité de facturation électronique combine, entre autres, l’utilisation de formats de configuration d’états électroniques pour créer des fichiers d’exportation et d’importation configurables, et l’utilisation d’actions et de flux d’actions pour permettre la création de règles configurables pour envoyer des demandes, importer les réponses et analyser le contenu des réponses.

En raison des variations des formats de facture et des flux d’action, le paramétrage de la fonctionnalité de facturation électronique dépend du pays/de la région.

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance-or-supply-chain-management"></a>Paramétrer l’intégration du module complémentaire de facturation électronique dans Finance ou Supply Chain Management 

Lors de ce paramétrage, vous effectuerez les tâches suivantes :

1. Ouvrir la fonctionnalité en version d’évaluation
2. Activer la fonctionnalité d’intégration du module complémentaire de facturation électronique pour activer l’intégration avec Finance.
3. Paramétrer l’URL du point de terminaison du module complémentaire de facturation électronique.
4. Importer les configurations ER associées à la fonctionnalité de facturation électronique spécifique au pays/à la région.
5. Activer la fonctionnalité de facturation électronique spécifique au pays/à la région.
6. Importer les configurations ER et configurer les types de réponse nécessaires pour mettre à jour votre document de facture spécifique au pays/à la région à la suite du processus d’envoi.

### <a name="open-flighted-feature"></a>Ouvrir la fonctionnalité en version d’évaluation
La fonctionnalité d’intégration de facture électronique est activée via la distribution de version d’évaluation. La distribution de version d’évaluation est un concept qui permet d’activer ou de désactiver par défaut une fonctionnalité. Les étapes suivantes activent une version d’évaluation dans un environnement hors production. 

1. Exécutez la commande SQL suivante :

    INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES (’BusinessDocumentSubmissionServiceEnabled’, 1)
    
    INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES (’ElectronicInvoicingServiceIntegrationFeature’, 1)
    
2. Après avoir effectué la modification ci-dessus, exécutez un IISReset sur tous les AOS

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a>Activer la fonctionnalité d’intégration du module complémentaire de facturation électronique

1. Connectez-vous à Finance ou Supply Chain Management.
2. Dans l’espace de travail **Gestion des fonctionnalités**, recherchez la nouvelle fonctionnalité, **Intégration du module complémentaire de facturation électronique configurable**. Si la fonctionnalité ne s’affiche toujours pas dans la page Gestion des fonctionnalités, exécutez la fonction **Rechercher des mises à jour**
3. Sélectionnez la fonctionnalité, puis sélectionnez **Activer maintenant**.

### <a name="set-up-the-service-endpoint-url"></a>Paramétrer l’URL du point de terminaison de service

1. Allez dans **Administration de l’organisation \> Paramétrage \> Paramètres des documents électroniques**.
2. Dans l’onglet **Service d’envoi** dans le champ **URL du point de terminaison de service**, entrez `https://businessdocumentsubmission.us.operations365.dynamics.com/`.
3. Dans le champ **Environnement**, entrez le nom de l’environnement complémentaire de facturation électronique que vous avez créé lors du paramétrage RCS.

![Saisie des paramètres de service](media/e-invoicing-services-get-started-enter-service-endpoint.png)

### <a name="import-the-er-configurations"></a>Importer les configurations ER

Pour permettre la collecte et l’envoi des données commerciales au module complémentaire de facturation électronique, vous devez importer le modèle de données ER et la configuration du modèle de données ER qui sont associés à la fonctionnalité de facturation électronique spécifique au pays/à la région que vous souhaitez utiliser.

1. Dans l’espace de travail **États électroniques**, dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Microsoft**. Vérifiez que ce fournisseur de configuration est défini sur **Actif**. Pour plus d’informations sur la définition d’un fournisseur sur **Actif**, voir [Créer des fournisseurs de configuration et les marquer comme actifs](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).
3. Sélectionnez **Référentiels**.
4. Sélectionnez **Ressource globale**, puis sélectionnez **Ouvrir**.
5. Dans la boîte de dialogue **Se connecter à Lifecycle Services**, sélectionnez **Cliquez ici pour vous connecter à Lifecycle Services**.
6. Selon le pays ou la région où vous souhaitez utiliser la fonctionnalité de facturation électronique, vous devez importer le modèle de données, le mappage du modèle de données et les formats applicables. Pour plus d’informations sur les configurations ER que vous devez importer, consultez la rubrique « Démarrage du module complémentaire de facturation électronique » spécifique au pays/à la région.
7. Importez le **Modèle de contexte de facture client**. Ce modèle contient des paramètres supplémentaires qui décrivent, entre autres, l’environnement dans Finance utilisé pour le module complémentaire de facturation électronique lors de l’envoi de données commerciales.

### <a name="turn-on-countryregion-specific-e-invoicing-features"></a><a name="region-specific"></a>Activer les fonctionnalités de facturation électronique spécifiques au pays/à la région

Pour activer les fonctionnalités de facturation électronique spécifiques au pays/à la région afin qu’elles fonctionnent avec le module complémentaire de facturation électronique, vous devez activer la fonctionnalité dans chaque entité juridique où vous souhaitez l’utiliser. Ensuite, l’ancienne intégration de facturation électronique ne peut plus être utilisée et l’intégration avec le nouveau module complémentaire de facturation électronique est activée.

1. Allez dans **Administration de l’organisation \> Paramétrage \> Paramètres des documents électroniques**.
2. Dans l’onglet **Fonctionnalités**, dans la ligne de la fonctionnalité associée à la fonctionnalité de facturation électronique spécifique à votre pays/région, cochez la case dans la colonne **Activé**. Pour plus d’informations sur la fonctionnalité que vous devez activer, consultez la rubrique « Démarrage du module complémentaire de facturation électronique » spécifique au pays/à la région.

![Activation de la fonctionnalité de facturation électronique](media/e-invoicing-services-get-started-enable-invoicing-feature.png)

> [!NOTE]
> Si plusieurs entités juridiques sont configurées pour différents pays ou régions, vous pouvez activer la fonctionnalité de facturation électronique spécifique au pays/à la région pour chaque entité juridique.

### <a name="import-er-configurations-and-set-up-the-response-types-to-update-your-countryregion-specific-invoice-document"></a>Importer les configurations ER et configurer les types de réponse pour mettre à jour le document de facture spécifique à votre pays/région

Si le document de facture envoyé nécessite une mise à jour après la réponse de l’envoi aux services d’autorisation gouvernementaux, vous devez importer un modèle de données ER spécial et des configurations pour permettre la mise à jour du statut du document de facture ou de tout autre champ supplémentaire.

1. Dans l’espace de travail **États électroniques**, dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Microsoft**.
2. Sélectionnez **Référentiels**.
3. Sélectionnez **Ressource globale**, puis sélectionnez **Ouvrir**.
4. Importez **Modèle de message de réponse**, **Format d’importation du message de réponse**, **Mappage du modèle de message de réponse avec la destination** et **Format d’importation du contenu du fichier**.
5. Allez dans **Administration de l’organisation \> Paramétrage \> Paramètres des documents électroniques**.
6. Dans l’onglet **Document électronique**, sélectionnez **Ajouter** pour entrer le nom de la table associée au document de facture spécifique à votre pays/région. Pour plus d’informations sur les noms de table que vous devez sélectionner, consultez la rubrique « Démarrage du module complémentaire de facturation électronique » spécifique au pays/à la région.
7. Sélectionnez **Types de réponse** pour configurer les types de réponse. Pour plus d’informations sur les noms de table que vous devez sélectionner, consultez la rubrique « Démarrage du module complémentaire de facturation électronique » spécifique au pays/à la région.

![Configuration des types de réponse](media/e-invoicing-services-get-started-set-up-response-types.png)

## <a name="e-invoicing-feature-names-by-country"></a>Noms de fonctionnalité de facturation électronique par pays 
Le tableau suivant décrit d’autres fonctionnalités de facturation électronique qui peuvent être téléchargées à partir du référentiel global des états électroniques pour générer des factures électroniques.
Dans RCS, vous pouvez télécharger les fonctionnalités de facturation électronique répertoriées dans ce tableau, les configurations ER et les paramétrages de fonctionnalité de facturation électronique disponibles.
Dans Finance, vous pouvez activer les références de fonctionnalité associées sur la page **Paramètres des documents électroniques** pour émettre des factures électroniques pour ces pays. Pour plus d’informations, consultez la section, [Activer les fonctionnalités de facturation électronique spécifiques au pays/à la région](#region-specific) plus haut dans cette rubrique.

| Nom de la fonction                      | Description                                  | Configurations ER                                                                                                  | Paramétrages                                                                                                                                                         | Pays/région  | Référence de la fonctionnalité      |
|-----------------------------------|---------------------------------------------|--------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|------------------------|
| Factures électroniques autrichiennes (AT) | Factures client et projet pour l’Autriche      | - Facture client OIOUBL <br>- Facture de projet OIOUBL <br>- Avoir sur vente OIOUBL <br>- Avoir sur projet OIOUBL | - Génération de facture client (AT) <br>- Génération de facture de projet (AT) <br>- Génération d’avoir sur vente (AT) <br>- Génération d’avoir sur projet (AT)         | Autriche         | EUR-00023              |
| Facture électronique belge (BE)   | Factures client et projet pour la Belgique      | - Facture client UBL BE <br>- Facture de projet UBL BE <br>- Avoir sur projet UBL BE <br>- Avoir sur vente UBL BE | - Génération de facture client (BE)<br>- Génération de facture de projet (BE) <br>- Génération d’avoir sur vente (BE) <br>- Génération d’avoir sur projet (BE)         | Belgique         | EUR-00023              |
| Facture électronique danoise (DK)    | Factures client et projet pour le Danemark      | - Facture client OIOUBL <br>- Facture de projet OIOUBL <br>- Avoir sur vente OIOUBL <br>- Avoir sur projet OIOUBL | - Génération de facture client (DK) <br>- Génération de facture de projet (DK) <br>- Génération d’avoir sur vente (DK)<br>- Génération d’avoir sur projet (DK)         | Danemark         | EUR-00023<br> DK-00001 |
| Facture électronique néerlandaise (NL)     | Factures client et projet pour les Pays-Bas  | - Facture client UBL NL <br>- Facture de projet UBL NL <br>- Avoir sur vente UBL NL <br>- Avoir sur projet UBL NL | - Génération de facture client (NL) <br> - Génération de facture de projet (NL) <br> - Génération d’avoir sur vente (NL) <br>- Génération d’avoir sur projet (NL)          | Pays-Bas | EUR-00023              |
| Facture électronique estonienne (EE)  | Factures client et projet pour l’Estonie      | - Facture client (EE) <br> - Facture de projet (EE)                                                                     | - Génération de facture client (EE) <br>- Génération de facture de projet (EE)                                                                                           | Estonie         | EUR-00023              |
| Facture électronique finlandaise (DK)   | Factures client et projet pour la Finlande      | - Facture client (FI) <br>- Génération de facture de projet (FI)                                                          | - Génération de facture client (FI) <br>- Génération de facture de projet (FI)                                                                                           | Finlande         | EUR-00023              |
| Facture électronique française (FR)    | Factures client et projet pour la France    | - Facture client UBL FR <br> - Facture de projet UBL FR <br> - Avoir sur vente UBL FR <br>- Avoir sur projet UBL FR | - Génération de facture client (FR) <br> - Génération de facture de projet (FR) <br>- Génération d’avoir sur vente (FR) <br>- Génération d’avoir sur projet (FR)         | France          | EUR-00023              |
| Facture électronique allemande (DE)    | Factures client et projet pour l’Allemagne      |- Facture client (DE) <br> - Facture de projet <DE>                                                                     | - Génération de facture client (DE) <br>- Génération de facture de projet (DE)                                                                                           | Allemagne         | EUR-00023              |
| Facture électronique norvégienne (NO) | Factures client et projet pour la Norvège       | - Facture client OIOUBL <br>- Facture de projet OIOUBL <br>- Avoir sur vente OIOUBL <br>- Avoir sur projet OIOUBL | - Génération de facture client (NO) <br>- Génération de facture de projet (NO) <br>- Génération d’avoir sur vente (NO) <br>- Génération d’avoir sur projet (NO)          | Norvège          | EUR-00023<br> NO-00010 |
| Facture électronique espagnole (ES)   | Factures client et projet pour l’Espagne        | - Facture client (ES) <br>- Facture de projet (ES)                                                                     | - Génération de facture client (ES) <br>- Génération de facture de projet (ES)                                                                                           | Espagne           | EUR-00023 <br>ES-00025 |
| Facture électronique italienne (IT)   | Factures client et projet pour l’Italie        | - (Version préliminaire) Facture client (IT) <br> - Facture de projet (IT)                                                           | - Facture client <br> - Facture de projet                                                                                                                           | Italie           | EUR-00023 <br>IT-00036 |
| Facture électronique PEPPOL         | Génération de facture client et projet PEPPOL | - Facture client PEPPOL <br>- Facture de projet PEPPOL <br>- Avoir sur vente PEPPOL <br> - Avoir sur projet PEPPOL | - Génération de facture client PEPPOL <br>- Génération de facture de projet PEPPOL <br>- Génération d’avoir sur vente PEPPOL <br>- Génération d’avoir sur projet PEPPOL |                 | EUR-00023              |


## <a name="electronic-invoice-processing-in-finance-and-supply-chain-management"></a>Traitement de facture électronique dans Finance et Supply Chain Management

Lors du traitement, vous effectuerez les tâches suivantes :

1. Envoyer un document commercial (facture) via le module complémentaire de facturation électronique.
2. Afficher les journaux d’exécution de l’envoi.

### <a name="submit-business-documents"></a>Envoyer des documents commerciaux

Lors du processus d’envoi normal, la communication entre le client et le module complémentaire de facturation électronique est bidirectionnelle. Le but est d’accomplir deux tâches principales lors de l’envoi de documents électroniques :

1. Envoyer tous les documents électroniques en attente d’envoi par Finance qui présentent le statut d’envoi approprié et qui répondent aux critères de sélection.
2. Importer, dans Finance, la réponse renvoyée par le module complémentaire de facturation électronique pour les documents électroniques envoyés précédemment. Après l’importation, les réponses sont analysées et le statut des documents commerciaux est mis à jour en conséquence.

Vous pouvez envoyer des documents commerciaux manuellement ou en fonction de vos exigences de calendrier.

1. Allez dans **Administration de l’organisation \> Périodique \> Documents électroniques \> Envoyer des documents électroniques**.
2. Pour le premier envoi d’un document, définissez toujours l’option **Envoyer de nouveau les documents** sur **Non**. Si vous devez envoyer à nouveau un document via le service, définissez cette option sur **Oui**.
3. Dans le raccourci **Enregistrements à inclure**, sélectionnez **Filtrer** pour ouvrir la boîte de dialogue **Recherche** dans laquelle vous pouvez créer une requête pour sélectionner des documents pour envoi.

![Boîte de dialogue Envoyer des documents électroniques](media/e-invoicing-services-get-started-submission-form.png)

### <a name="filter-query"></a>Requête de filtre

1. Dans la boîte de dialogue **Recherche**, dans l’onglet **Plage**, entrez les critères de filtre à l’aide des champs **Table**, **Table dérivée**, **Champ** et **Critères**.
2. Sélectionnez **Ajouter** pour ajouter autant de critères supplémentaires que nécessaire pour sélectionner les documents commerciaux.

    ![Configuration des critères de filtrage de l’envoi](media/e-invoicing-services-get-started-set-up-submission-filter-criteria.png)

3. Cliquez sur **OK** pour fermer la boîte de dialogue **Recherche**.
4. Cliquez sur **OK** pour envoyer les documents commerciaux sélectionnés au module complémentaire de facturation électronique.

    > [!NOTE]
    > Lors de votre première tentative d’envoi d’un document via le service, vous serez invité à confirmer la connexion avec le module complémentaire de facturation électronique. Sélectionnez **Cliquez ici pour vous connecter au service d’envoi de document électronique**.
    >
    > ![Zone de message Connexion au service d’envoi de documents électroniques](media/e-invoicing-services-get-started-dialog-form-connect-e-Invoicing-services.png)
    >
    > Si la connexion aboutit, vous recevez un message de confirmation.
    >
    > ![Confirmation de la connexion au module complémentaire de facturation électronique](media/e-invoicing-services-get-started-confirmation-connection-e-invoicing-services.png)

5. Fermez la boîte de dialogue.

> [!NOTE]
> Après chaque envoi, le centre de notifications affiche le nombre de documents envoyés.
>
> ![Messages du centre de notifications](media/e-invoicing-services-get-started-view-action-center-messages.png)

### <a name="submission-by-batch"></a>Envoi par lots

Au lieu d’envoyer manuellement des documents, vous pouvez automatiser le processus d’envoi et l’exécuter en arrière-plan, selon une fréquence configurée d’exécution par lots.

1. Dans la boîte de dialogue **Envoyer des documents électroniques**, dans le raccourci **Exécuter en arrière-plan**, définissez l’option **Traitement par lots** sur **Oui**.
2. Dans l’onglet **Périodicité**, configurez la fréquence du traitement par lots.

![Configuration de l’envoi par lots](media/e-invoicing-services-get-started-set-up-submission-batch.png)

### <a name="view-all-submission-logs"></a>Afficher tous les journaux d’envoi

1. Allez dans **Administration de l’organisation \> Périodique \> Documents électroniques \> Journal d’envoi de documents électroniques**.
2. Dans le champ **Type de document**, sélectionnez le type de document pour le filtre.

    ![Sélection du type de document pour lequel afficher les journaux d’envoi](media/e-invoicing-services-get-started-select-document-type-for-viewing-submission-log.png)

    > [!IMPORTANT]
    > La valeur affichée dans la colonne **Statut d’envoi** représente le statut associé à l’exécution du processus d’envoi proprement dit. Elle indique si le flux d’actions configuré dans RCS a été exécuté jusqu’à la fin, que le document électronique ait été approuvé ou rejeté. La valeur de la colonne **Statut d’envoi** ne représente pas le statut du document envoyé. Vous pouvez afficher le statut du document envoyé (c’est-à-dire, si le document a été approuvé ou rejeté) dans le raccourci **Journal des actions de traitement** des détails du journal d’envoi, comme décrit ci-après.

3. Dans le volet Actions, sélectionnez **Recherches \> Détails de l’envoi**.
4. Affichez les détails du journal d’envoi.

    ![Détails du journal d’envoi](media/e-invoicing-services-get-started-view-submission-log-form.png)

Les résultats affichés dans le journal d’envoi dépendent du paramétrage de la fonctionnalité de facturation électronique dans RCS. Cependant, quelle que soit le paramétrage, le journal d’envoi comporte toujours trois raccourcis :

- **Actions de traitement** : ce raccourci affiche le journal d’exécution des actions configurées dans la version de fonctionnalité paramétrée dans RCS. La colonne **Statut** indique si l’exécution de l’action a réussi.
- **Fichiers d’action** : ce raccourci affiche les fichiers intermédiaires générés lors de l’exécution des actions. Vous pouvez sélectionner **Afficher** pour télécharger le fichier et afficher son contenu.
- **Journal des actions de traitement** : ce raccourci affiche les résultats de la communication entre le module complémentaire de facturation électronique et le service web cible. Il indique également ce qui a été renvoyé par le traitement du service web.

## <a name="related-topics"></a>Rubriques connexes

- [Présentation du module complémentaire de facturation électronique](e-invoicing-service-overview.md)
- [Démarrage du module complémentaire de facturation électronique pour le Brésil](e-invoicing-bra-get-started.md)
- [Démarrage du module complémentaire de facturation électronique pour le Mexique](e-invoicing-mex-get-started.md)
- [Démarrage du module complémentaire de facturation électronique pour l’Italie](e-invoicing-ita-get-started.md)
- [Paramétrer le module complémentaire de facturation électronique](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]