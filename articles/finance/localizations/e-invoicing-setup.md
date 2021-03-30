---
title: Paramétrer le module complémentaire de facturation électronique
description: Cette rubrique explique comment paramétrer le module complémentaire de facturation électronique dans Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 5821a512b2beaf7ba2b8015355f04562f7b3b38a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209944"
---
# <a name="set-up-the-electronic-invoicing-add-on"></a>Paramétrer le module complémentaire de facturation électronique

[!include [banner](../includes/banner.md)]


Le paramétrage de la fonctionnalité complémentaire de facturation électronique consiste à créer la configuration requise via l’environnement Regulatory Configuration Services (RCS) et à publier cette configuration sur le serveur complémentaire de facturation électronique. Le paramétrage vous permet de créer les règles configurables permettant au module complémentaire de facturation électronique d’utiliser un protocole sécurisé sur Internet pour communiquer et échanger des données avec une entité tierce via des services web.

La configurabilité repose sur la configuration du format des états électroniques (ER) comme moyen de créer du contenu qui est envoyé et reçu via des fichiers numériques. Elle repose également sur l’orchestration des actions de communication pour envoyer des demandes et recevoir des réponses de services web tiers sans que vous ayez besoin d’écrire du code.

## <a name="overview"></a>Vue d’ensemble

La « fonctionnalité complémentaire de facturation électronique » est le nom générique de la ressource configurée et publiée pour utiliser le serveur complémentaire de facturation électronique. Le paramétrage de la fonctionnalité combine, entre autres, l’utilisation de formats de configuration d’états électroniques pour créer des fichiers d’exportation et d’importation configurables, et l’utilisation d’actions et de flux d’actions pour permettre la création de règles configurables pour envoyer des demandes, importer les réponses et analyser le contenu des réponses.

L’illustration suivante présente les principaux composants d’une fonctionnalité complémentaire de facturation électronique.

![Présentation de la fonctionnalité complémentaire de facturation électronique](media/e-Invoicing-services-feature-setup-Overview-e-Invoicing-feature.png)

En raison des variations de formats de facture et de flux d’actions, le paramétrage de la fonctionnalité peut varier selon le pays ou la région, ou selon les besoins de l’entreprise.

## <a name="set-up-the-electronic-invoicing-add-on-feature"></a>Paramétrer la fonctionnalité complémentaire de facturation électronique

Le processus de paramétrage doit être effectué dans votre environnement RCS. Suivez les étapes ci-après pour créer une nouvelle fonctionnalité de facturation électronique.

1. Connectez-vous à votre environnement RCS.
2. Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Fonctionnalités**, sélectionnez la vignette **Module complémentaire de facturation électronique**.
3. Sur la page **Fonctionnalités complémentaires de facturation électronique**, sélectionnez **Importer** pour importer la configuration du modèle de données ER à partir du référentiel global.
4. Sélectionnez **Ajouter** pour créer une fonctionnalité complémentaire de facturation électronique. Vous pouvez créer la fonctionnalité à partir de zéro ou la dériver d’une fonctionnalité complémentaire de facturation électronique existante.

    ![Ajout d’une fonctionnalité complémentaire de facturation électronique](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature.png)

> [!NOTE]
> Lorsque vous créez une nouvelle fonctionnalité complémentaire de facturation électronique, celle-ci a un numéro de version et son statut par défaut est défini sur **Brouillon**.

### <a name="configurations"></a>Configurations

Les configurations contiennent les configurations de format ER requises pour les transformations et pour créer les fichiers qui seront échangés lors de la communication avec des services web tiers. Une fonctionnalité complémentaire de facturation électronique peut avoir autant de configurations de format de fichier ER que nécessaire, selon la spécification technique de l’intégration fournie par le fournisseur de services web.

Suivez les étapes ci-après pour ajouter des formats ER à la fonctionnalité complémentaire de facturation électronique.

1. Sur la page **Fonctionnalités complémentaires de facturation électronique**, dans l’onglet **Configurations**, sélectionnez **Ajouter** pour ajouter des configurations de format de fichier ER pour la fonctionnalité complémentaire de facturation électronique.

    ![Ajout de configurations à la fonctionnalité complémentaire de facturation électronique](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature-Configurations.png)

    > [!NOTE]
    > Lorsque vous créez une fonctionnalité complémentaire de facturation électronique à partir de zéro, vous devez ajouter manuellement toutes les configurations de format de fichier ER. Lorsque vous dérivez une fonctionnalité complémentaire de facturation électronique d’une fonctionnalité existante, les configurations de format de fichier ER sont automatiquement créées, car elles sont héritées de la fonctionnalité complémentaire de facturation électronique d’origine.

2. Sélectionnez **Modifier** pour ouvrir la page **Concepteur de formats**, où vous pouvez modifier la configuration du format de fichier ER.

    ![Modification des configurations de la fonctionnalité complémentaire de facturation électronique](media/e-Invoicing-services-feature-setup-Select-Edit-e-Invoicing-feature-Configurations.png)

    > [!NOTE]
    > Lorsque vous modifiez le format, le statut de la version de configuration est défini sur **Brouillon**.

3. Utilisez la page **Concepteur de formats** pour modifier la configuration du format de fichier. Pour plus d’informations, voir [Créer des configurations de document électronique](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration).

    ![Page Concepteur de formats](media/e-Invoicing-services-feature-setup-ER-Format-designer.png)

### <a name="feature-setups"></a>Paramétrages de fonctionnalité

Les paramétrages de fonctionnalité encapsulent les règles de communication et de sécurité avec un service web tiers. Une fonctionnalité complémentaire de facturation électronique peut avoir autant de paramétrages de fonctionnalité que nécessaire, selon la règle métier que vous souhaitez appliquer.

Suivez les étapes ci-après pour ajouter des paramétrages de fonctionnalité à la fonctionnalité complémentaire de facturation électronique.

1. Sur la page **Fonctionnalités complémentaires de facturation électronique**, dans l’onglet **Paramétrages**, sélectionnez **Ajouter** pour ajouter des paramétrages de fonctionnalité à la fonctionnalité complémentaire de facturation électronique.

    ![Ajout de paramétrages à la fonctionnalité complémentaire de facturation électronique](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature-Setups.png)

    > [!NOTE]
    > Lorsque vous créez une fonctionnalité complémentaire de facturation électronique à partir de zéro, vous devez ajouter manuellement tous les paramétrages de fonctionnalité nécessaires. Lorsque vous dérivez une fonctionnalité complémentaire de facturation électronique d’une fonctionnalité existante, tous les paramétrages de fonctionnalité sont automatiquement créées, car ils sont hérités de la fonctionnalité complémentaire de facturation électronique d’origine.

2. Sélectionnez **Modifier** pour modifier le paramétrage de la version de la fonctionnalité.

    ![Modification des paramétrages de la fonctionnalité complémentaire de facturation électronique](media/e-Invoicing-services-feature-setup-Select-Edit-e-Invoicing-feature-Setups.png)

3. Utilisez la page **Paramétrage de version de fonctionnalité** pour configurer les actions, les règles d’applicabilité et les variables.

    ![Actions, règles d’applicabilité et variables](media/e-Invoicing-services-feature-setup-View-Actions-Applicability-Rules-Variables.png)

### <a name="actions"></a>Actions

Les actions sont une liste prédéfinie d’opérations exécutées dans un ordre séquentiel. Cette liste représente les différentes étapes nécessaires à l’exécution complète de la fonctionnalité complémentaire de facturation électronique. Les actions peuvent encapsuler, dans la même fonctionnalité complémentaire de facturation électronique, la communication dans les deux sens : l’envoi d’une demande à une destination et la réception d’une réponse et l’analyse de son contenu.

Chaque action contient une liste prédéfinie de paramètres nécessaires à la réalisation de son objectif. Des paramètres supplémentaires peuvent éventuellement être fournis.

#### <a name="actions-fasttab"></a>Raccourci Actions

Sur la page **Paramétrage de version de fonctionnalité**, dans l’onglet **Actions**, dans le raccourci **Actions**, suivez l’une de ces étapes ou les deux pour gérer les actions :

- Sélectionnez **Nouveau** ou **Supprimer** pour ajouter de nouvelles actions ou supprimer des actions existantes.
- Sélectionnez **Haut** ou **Bas** pour déplacer les actions sélectionnées vers le haut ou vers le bas de la grille et modifier ainsi leur ordre d’exécution. Les actions sont exécutées dans leur ordre d’affichage dans la grille, de haut en bas.

![Gestion des actions](media/e-Invoicing-services-feature-setup-Manage-Actions.png)

Le tableau suivant décrit les champs disponibles dans le raccourci **Actions**.

| Champ        | Description |
|--------------|-------------|
| Action       | Il existe huit actions prédéfinies :<ul><li><strong>Signer le document</strong></li><li><strong>FileStoreActionName</strong></li><li><strong>Transformer le document</strong></li><li><strong>Réponse du processus</strong></li><li><strong>Appeler le service web REST</strong></li><li><strong>Appeler le service PAC mexicain</strong></li><li><strong>Appeler le service SEFAZ brésilien</strong></li><li><strong>Appeler le service SDI italien</strong></li></ul> |
| Nom de l’action  | Nom de l’action et son ordre d’exécution. |
| Description  | Description de l’action. |
| Activer la nouvelle tentative | Une case cochée indique que l’action peut être réexécutée si la tentative précédente a échoué. |
| Réessayer l’action | En cas de nouvelle tentative, action à partir de laquelle la nouvelle tentative est lancée. La nouvelle tentative se termine sur l’action actuelle (nouvelle tentative inclusive). Pour les actions applicables, les paramétres **Interruption minimale** et **Interruption maximale** spécifient le nombre minimal et le nombre maximal de nouvelles tentatives. |

#### <a name="parameters-fasttab"></a>Raccourci Paramètres

Le raccourci **Paramètres** répertorie les paramètres de l’action sélectionnée dans le raccourci **Actions**.

![Raccourci Paramètres](media/e-Invoicing-services-feature-setup-View-Actions-Parameters.png)

Le tableau suivant décrit les champs disponibles dans le raccourci **Paramètres**.

| Champ       | Description |
|-------------|-------------|
| Nom        | Liste prédéfinie de paramètres. Pour plus d’informations, consultez la section [Liste des paramètres par action](#list-of-parameters-by-action). |
| Description | Description du paramètre. |
| Valeur       | Valeur du paramètre. |

#### <a name="list-of-parameters-by-action"></a>Liste des paramètres par action

Les paramètres disponibles varient selon l’action sélectionnée dans le raccourci **Actions**.

###### <a name="action-sign-document"></a>Action : Signer le document

| Paramètre                             | Description |
|---------------------------------------|-------------|
| Fichier d’entrée                            | Fichier document XML d’entrée devant être signé à l’aide d’une signature électronique. |
| Nom du certificat                      | Nom du certificat stocké. |
| Type de signature                        | Type de signature à utiliser. |
| Nom de la méthode de signature                 | Nom de la méthode de signature utilisée pour générer une signature électronique. |
| Nom de la méthode de résumé                    | Méthode de résumé utilisée pour générer une chaîne de résumé dans la signature numérique. |
| Nom de la méthode de canonicalisation          | Méthode de canonicalisation utilisée pour calculer le hachage de signature. |
| Nom de l’attribut de référence              | Nom d’attribut indiquant où l’ID de référence doit être inséré dans l’élément de signature. |
| Nom de l’élément à signer               | Nom de l’élément XML du document devant être signé à l’aide d’une signature électronique. Si aucun élément n’est spécifié, la racine du document est signée. |
| Nom de l’élément d’insertion d’une signature   | Nom de l’élément XML dans lequel une signature numérique générée doit être insérée. Si aucun élément n’est spécifié, la signature est insérée à la racine du document. |
| Fichier XLST avec transformation du résumé       | Fichier XSLT (Extensible Stylesheet Language Transformations) contenant les règles de transformation de résumé pour générer la chaîne de résumé d’une signature électronique. |
| Chemin d’insertion de la chaîne de résumé          | Chemin d’accès, au format **\<elementName\>.\<Attribute.Path\>**, de l’emplacement où la chaîne de résumé générée doit être insérée. |
| Emplacement du numéro de certificat           | Nom de l’élément et de l’attribut où le numéro de certificat doit être inséré. |
| Emplacement des données de certificat          | Nom de l’élément et de l’attribut où les données de certificat (base64) doivent être insérées. |
| Le numéro de certificat est au format ASCII | Valeur spécifiant si le numéro du certificat est codé au format ASCII. |

###### <a name="action-filestoreactionname"></a>Action : FileStoreActionName

| Paramètre  | Description |
|------------|-------------|
| Fichier d’entrée | Fichier d’entrée à stocker. |

###### <a name="action-transform-document"></a>Action : Transformer le document

| Paramètre                       | Description |
|---------------------------------|-------------|
| Fichier d’entrée                      | Fichier source qui fournit les données devant être exécutées pour l’action. |
| Direction                       | Valeur indiquant si le format d’importation ou le format d’exportation doit être utilisé. |
| ID configuration                | Format à exécuter. |
| Version de la configuration           | Si aucune version de configuration n’est spécifiée, la version la plus récente sera utilisée. |
| Point d’intégration de la configuration | Fichier source qui fournit des données pour l’exécution de rapports. |

###### <a name="action-process-response"></a>Action : Réponse du processus

| Paramètre                    | Description |
|------------------------------|-------------|
| Fichier d’entrée                   | Réponse à analyser. |
| Liste de configuration des rapports | Liste de configurations utilisée pour analyser les réponses. |

###### <a name="action-call-rest-web-service"></a>Action : Appeler le service web REST

| Paramètre                   | Description |
|-----------------------------|-------------|
| URL de service Web             | URL vers laquelle envoyer des requêtes. |
| Délai d’expiration de la requête web         | Durée maximale (en millisecondes) d’attente d’une réponse du service web. |
| Type d’opération de requête      | Type d’opération de requête HTTP (par exemple, **GET**, **POST** ou **DELETE**). |
| Noms de certificat           | Noms de certificat. |
| Codage du corps de la réponse      | Codage attendu du corps de la réponse HTTP, afin qu’il puisse être décodé correctement. |
| Type de contenu de la requête HTTP   | Entrée d’en-tête du type de contenu de la requête HTTP. |
| Corps du contenu de la requête HTTP   | Corps de la requête HTTP. (Le corps peut être vide.) |
| Valeurs de requête de paramètre HTTP | Valeurs de requête de paramètre utilisées pour remplir l’URL avec des paramètres variables. |
| Gamme de la requête               | Chemin de gamme de la requête HTTP. Les paramètres variables peuvent être écrits en notation **\{paramName\}**. Voici un exemple : **"api/{id}/submit"**. |
| Liste des paramètres de gamme        | Paramètres de gamme, en notation clé-valeur, utilisés pour insérer des variables dans la gamme. |
| En-têtes HTTP personnalisés         | En-têtes HTTP personnalisés à insérer dans la requête. |
| Cookies de requête HTTP        | Liste de cookies, en notation clé-valeur, à insérer dans la requête d’en-tête de cookies HTTP. |
| Protocole de sécurité           | Protocole de sécurité à utiliser pour les requêtes HTTP pour communiquer avec le serveur. (Par défaut, Transport Layer Security \[TLS\] 1.2 est utilisé.) |

###### <a name="action-call-mexican-pac-service"></a>Action : Appeler le service PAC mexicain

| Paramètre                | Description |
|--------------------------|-------------|
| Fichier d’entrée               | Fichier contenant les données XML qui seront envoyées au service web en tant que paramètre d’entrée de la méthode. |
| Adresse URL              | Adresse du service web (point de terminaison). |
| Nom de la méthode web (action) | Nom de la méthode web (action) à exécuter. |
| Certificats             | Chaîne de certificats requise pour l’authentification du client par le service web. Le certificat client doit être le dernier certificat de la chaîne. Les certificats racine et intermédiaire doivent être les premiers. |
| Délai d’expiration de la requête web      | Durée maximale (en millisecondes) d’attente d’une réponse du service web. |
| Intervalle de nouvelle tentative           | Intervalle entre les tentatives d’appel et de réception d’une réponse du service web. Si aucun intervalle n’est spécifié, aucune nouvelle tentative ne sera effectuée après l’échec du premier appel. |
| Nombre de nouvelles tentatives              | Nombre maximal de nouvelles tentatives d’appel et de récupération d’une réponse du service web. |
| Réessayer jusqu’à               | Durée maximale (en millisecondes) pendant laquelle les nouvelles tentatives d’appels peuvent continuer. |
| Interruption minimale         | Taux d’interruption minimale pour le calcul exponentiel des intervalles de nouvelle tentative. |
| Interruption maximale         | Taux d’interruption maximale pour le calcul exponentiel des intervalles de nouvelle tentative. |
| Protocole de sécurité        | Protocole de sécurité à utiliser pour les requêtes HTTP pour communiquer avec le serveur. (Par défaut, TLS 1.2 est utilisé.) |

###### <a name="action-call-brazilian-sefaz-service"></a>Action : Appeler le service SEFAZ brésilien

| Paramètre                | Description |
|--------------------------|-------------|
| Fichier d’entrée               | Fichier contenant les données XML qui seront envoyées au service web en tant que paramètre d’entrée de la méthode. |
| Adresse URL              | Adresse du service web (point de terminaison). |
| Nom de la méthode web (action) | Nom de la méthode web (action) à exécuter. |
| Certificats             | Chaîne de certificats requise pour l’authentification du client par le service web. Le certificat client doit être le dernier certificat de la chaîne. Les certificats racine et intermédiaire doivent être les premiers. |
| Délai d’expiration de la requête web      | Durée maximale (en millisecondes) d’attente d’une réponse du service web. |
| Intervalle de nouvelle tentative           | Intervalle entre les tentatives d’appel et de réception d’une réponse du service web. Si aucun intervalle n’est spécifié, aucune nouvelle tentative ne sera effectuée après l’échec du premier appel. |
| Nombre de nouvelles tentatives              | Nombre maximal de nouvelles tentatives d’appel et de récupération d’une réponse du service web. |
| Réessayer jusqu’à               | Durée maximale (en millisecondes) pendant laquelle les nouvelles tentatives d’appels peuvent continuer. |
| Interruption minimale         | Taux d’interruption minimale pour le calcul exponentiel des intervalles de nouvelle tentative. |
| Interruption maximale         | Taux d’interruption maximale pour le calcul exponentiel des intervalles de nouvelle tentative. |
| Protocole de sécurité        | Protocole de sécurité à utiliser pour les requêtes HTTP pour communiquer avec le serveur. (Par défaut, TLS 1.2 est utilisé.) |

###### <a name="action-call-italian-sdi-service"></a>Action : Appeler le service SDI italien

| Paramètre                | Description |
|--------------------------|-------------|
| Fichier d’entrée               | Fichier contenant les données XML qui seront envoyées au service web en tant que paramètre d’entrée de la méthode. |
| Adresse URL              | Adresse du service web (point de terminaison). |
| Nom de la méthode web (action) | Nom de la méthode web (action) à exécuter. |
| Certificats             | Chaîne de certificats requise pour l’authentification du client par le service web. Le certificat client doit être le dernier certificat de la chaîne. Les certificats racine et intermédiaire doivent être les premiers. |
| Délai d’expiration de la requête web      | Durée maximale (en millisecondes) d’attente d’une réponse du service web. |
| Intervalle de nouvelle tentative           | Intervalle entre les tentatives d’appel et de réception d’une réponse du service web. Si aucun intervalle n’est spécifié, aucune nouvelle tentative ne sera effectuée après l’échec du premier appel. |
| Nombre de nouvelles tentatives              | Nombre maximal de nouvelles tentatives d’appel et de récupération d’une réponse du service web. |
| Réessayer jusqu’à               | Durée maximale (en millisecondes) pendant laquelle les nouvelles tentatives d’appels peuvent continuer. |
| Interruption minimale         | Taux d’interruption minimale pour le calcul exponentiel des intervalles de nouvelle tentative. |
| Interruption maximale         | Taux d’interruption maximale pour le calcul exponentiel des intervalles de nouvelle tentative. |
| Protocole de sécurité        | Protocole de sécurité à utiliser pour les requêtes HTTP pour communiquer avec le serveur. (Par défaut, TLS 1.2 est utilisé.) |

### <a name="applicability-rules"></a>Règles d’applicabilité

Les règles d’applicabilité vous permettent de créer des règles logiques qui déterminent le contexte d’utilisation pour le paramétrage de la fonctionnalité. Ainsi, la correspondance entre le contexte fourni par le document commercial envoyé pour traitement, ainsi que les critères de la règle d’applicabilité, déterminent quelle fonctionnalité complémentaire de facturation électronique est utilisée pour traiter cet envoi.

#### <a name="set-up-applicability-rules"></a>Paramétrer les règles d’applicabilité

1. Sur la page **Paramétrage de version de fonctionnalité**, dans l’onglet **Règles d’applicabilité**, sélectionnez **Nouveau** pour ajouter une règle d’applicabilité.

    ![Gestion des règles d’applicabilité](media/e-Invoicing-services-feature-setup-Manage-Actions-Applicability-rules.png)

2. Dans la grille, sélectionnez les clauses à regrouper.
3. Sélectionnez **Regrouper les clauses**.

    ![Regroupement de clauses](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-Group-clause.png)

    Lorsque les clauses sont regroupées, une nouvelle colonne est ajoutée à la grille. Cette colonne spécifie l’opérateur logique pour les clauses regroupées.

    ![Opérateur logique pour les clauses regroupées](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-Group-criterias.png)

Pour dissocier des clauses, sélectionnez les clauses regroupées à dissocier, puis sélectionnez **Dissocier les clauses**.

![Dissociation de clauses](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-UnGroup-criterias.png)

> [!NOTE]
> Lorsque vous dissociez une clause, commencez toujours par le niveau de regroupement le plus interne.

Le tableau suivant décrit les champs disponibles dans l’onglet **Règles d’applicabilité**.

| Champ         | Description |
|---------------|-------------|
| Et/ou        | Opérateur logique. |
| Champ         | Champ à utiliser pour construire la règle. |
| Type d’opérateur | Type d’opérateur :<ul><li>Egal</li><li>Différent</li><li>Supérieur à/Inférieur à</li><li>Supérieur ou égal à/Inférieur ou égal à</li><li>Contient</li><li>Commence par</li></ul> |
| Valeur         | Critère de la règle. |

### <a name="variables"></a>Variables

Vous pouvez créer des variables, puis les utiliser comme valeur d’entrée pour un paramètre d’une action spécifique. Vous pouvez également les utiliser pour échanger, entre les services complémentaires de facturation électronique et le client, des informations résultant de l’exécution d’une action spécifique dans le cadre du flux d’envois.

#### <a name="set-up-variables"></a>Configurer des variables

- Sur la page **Paramétrage de version de fonctionnalité**, dans l’onglet **Variables**, sélectionnez **Nouveau** ou **Supprimer** pour gérer les variables.

    ![Gestion des variables](media/e-Invoicing-services-feature-setup-Manage-Variables.png)

Le tableau suivant décrit les champs disponibles dans l’onglet **Variables**.

| Champ       | Description |
|-------------|-------------|
| Nom        | Nom de la variable. |
| Description | Courte description de la variable. |
| Type        | Type de variable :<ul><li><strong>Constant</strong> : le contenu de la variable est fixe.</li><li><strong>À partir du client</strong> : le contenu de la variable est acquis à partir du client Microsoft Dynamics 365 pendant l’exécution du processus d’envoi.</li><li><strong>Vers le client</strong> : le contenu de la variable est disponible pour importation par le client Microsoft Dynamics 365 pendant l’exécution du processus d’envoi.</li></ul> |
| Type de données   | Type de données de la variable :<ul><li>Booléen</li><li>Date</li><li>Nombre</li><li>UUID</li><li>Chaîne</li><li>Fichier</li></ul> |
| Valeur       | Valeur de la variable ou nom de l’action qui définit la valeur de la variable. |

### <a name="validate-the-feature-setup"></a>Valider le paramétrage de la fonctionnalité

- Sur la page **Paramétrage de version de fonctionnalité**, dans le volet Actions, sélectionnez **Valider** pour valider le paramétrage de la version de la fonctionnalité.

   ![Sélection du bouton Valider](media/e-Invoicing-services-feature-setup-Select-Validate-Button.png)

La validation vérifie la cohérence de l’ensemble de la configuration. Par exemple, si un paramètre spécifique pour une action est obligatoire mais que sa valeur reste vide, la validation détecte cette incohérence et vous recevez un avertissement.

## <a name="environments"></a>Environnements

Un environnement complémentaire de facturation électronique doit être associé à la fonctionnalité complémentaire de facturation électronique et activé pour celle-ci. Les environnements complémentaires de facturation électronique doivent être créés et publiés à l’avance, via la configuration des fonctionnalités de globalisation dans le compte RCS de votre organisation.

Suivez les étapes ci-après pour activer un environnement complémentaire de facturation électronique pour la fonctionnalité complémentaire de facturation électronique.

1. Sur la page **Fonctionnalités complémentaires de facturation électronique**, dans l’onglet **Environnements**, sélectionnez **Activer** pour ajouter un environnement complémentaire de facturation électronique.
2. Dans le champ **Date d’effet**, entrez la date à laquelle le nouvel environnement prend effet.

![Activation d’un environnement complémentaire de facturation électronique](media/e-Invoicing-services-feature-setup-Select-Enable-e-Invoicing-feature-Environment.png)

## <a name="organizations"></a>Organisations

La fonctionnalité complémentaire de facturation électronique peut être partagée entre plusieurs organisations.

- Sur la page **Fonctionnalités complémentaires de facturation électronique**, dans l’onglet **Organisations**, sélectionnez **Partager avec** pour ajouter l’organisation avec laquelle vous souhaitez partager la fonctionnalité complémentaire de facturation électronique.

Pour arrêter le partage de la fonctionnalité complémentaire de facturation électronique avec l’organisation, sélectionnez **Annuler le partage**.

## <a name="versions"></a>Versions

Les versions aident à contrôler le cycle de vie de la fonctionnalité complémentaire de facturation électronique en gérant son statut. Vous pouvez créer une nouvelle version d’une fonctionnalité complémentaire de facturation électronique existante ou, lorsque toutes les configurations de la fonctionnalité complémentaire de facturation électronique sont terminées, vous pouvez modifier le statut de la fonctionnalité en **Terminer**, puis **Publier**.

### <a name="create-a-new-version-of-an-existing-electronic-invoicing-add-on-feature"></a>Créer une nouvelle version d’une fonctionnalité complémentaire de facturation électronique existante

1. Sur la page **Fonctionnalités complémentaires de facturation électronique**, dans la grille à gauche, sélectionnez la fonctionnalité complémentaire de facturation électronique.
2. Dans l’onglet **Versions**, sélectionnez **Nouveau** pour ajouter une nouvelle version de la fonctionnalité complémentaire de facturation électronique.

### <a name="change-the-status-of-the-electronic-invoicing-add-on-feature"></a>Modifier le statut de la fonctionnalité complémentaire de facturation électronique

Suivez les étapes ci-après pour gérer le cycle de vie de la fonctionnalité complémentaire de facturation électronique.

1. Sur la page **Fonctionnalités complémentaires de facturation électronique**, dans la grille à gauche, sélectionnez la fonctionnalité complémentaire de facturation électronique.
2. Dans l’onglet **Versions**, sélectionnez **Modifier le statut**, puis modifiez le statut de **Brouillon** à **Terminer**.
3. Vous êtes invité à confirmer que vous souhaitez terminer la fonctionnalité complémentaire de facturation électronique et tous ses composants. Sélectionnez **Oui** pour confirmer l’action ou **Non** pour l’annuler.

    > [!NOTE]
    > Lorsque vous sélectionnez **Oui**, le statut des versions de configuration, qui sont des composants de la fonctionnalité complémentaire de facturation électronique, est automatiquement modifié de **Brouillon** à **Terminé**.

4. Sélectionnez **Modifier le statut**, puis modifiez le statut de **Terminer** à **Publier**.
5. Vous êtes invité à confirmer que vous souhaitez publier la fonctionnalité complémentaire de facturation électronique et tous ses composants dans le référentiel global. Sélectionnez **Oui** pour confirmer l’action ou **Non** pour l’annuler.

    > [!NOTE]
    > Lorsque vous sélectionnez **Oui**, le statut des versions de configuration est automatiquement modifié de **Terminé** à **Partagé**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]