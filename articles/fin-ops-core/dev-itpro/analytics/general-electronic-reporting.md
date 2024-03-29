---
title: Vue d’ensemble des rapports électroniques
description: Cet article fournit une vue d’ensemble de l’outil de rapport électronique. Il décrit les concepts clés, les scénarios pris en charge et les formats qui font partie de la solution.
author: kfend
ms.date: 11/02/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58941,  ""intro-internal
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.form: ERWorkspace
ms.openlocfilehash: e94846dd565abb6de2c1f07532d285e28307e9a2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269689"
---
# <a name="electronic-reporting-er-overview"></a>Vue d’ensemble des rapports électroniques

[!include [banner](../includes/banner.md)]

Cet article fournit une vue d’ensemble de l’outil de rapport électronique (ER). Il comporte des informations sur les concepts essentiels, les scénarios pris en charge par l’ER et une liste des formats conçus et lancés dans le cadre de la solution.

ER est un outil configurable qui vous aide à créer et à gérer des rapports et des paiements électroniques réglementaires. Il repose sur les trois concepts suivants :

- Configuration au lieu de codage :

    - La configuration peut être effectuée par un utilisateur professionnel et ne nécessite pas de développeur.
    - Le modèle de données est défini en termes commerciaux.
    - Des éditeurs visuels sont utilisés pour créer tous les composants de la configuration ER.
    - Le langage utilisé pour la transformation de données ressemble à celui utilisé dans Microsoft Excel.

- Une configuration pour plusieurs versions de Dynamics 365 Finance :

    - Il est possible de gérer un modèle de données spécifique à un domaine qui est défini en termes commerciaux.
    - Il est possible d’isoler les détails de la version de l’application dans les mappages de modèle de données dépendant de la version.
    - Il est possible de conserver une configuration de format pour plusieurs versions de la version actuelle, en fonction du modèle de données.

- Mise à jour facile ou automatique :

    - Le contrôle de version des configurations ER est pris en charge.
    - La bibliothèque des actifs Microsoft Dynamics Lifecycle Services (LCS) peut être utilisée comme référentiel pour les configurations ER, pour l’échange de versions.
    - Les localisations basées sur les configurations ER d’origine peuvent être introduites en tant que versions enfants.
    - Une arborescence de configuration ER est fournie en tant qu’outil permettant de contrôler les dépendances des versions.
    - Les différences de localisation, ou la configuration delta, sont enregistrées pour permettre la mise à niveau automatique vers une nouvelle version de la configuration ER d’origine.
    - Il est facile de résoudre manuellement les conflits découverts lors de la mise à niveau automatique des versions de localisation.

ER vous permet de définir des structures de format électronique, puis de décrire la manière dont ces structures doivent être remplies à l’aide des données et des algorithmes. Vous pouvez utiliser un langage de formule qui ressemble au langage Excel pour la transformation des données. Pour rendre le mappage de la base de données au format plus gérable, réutilisable et indépendant des changements de format, un concept de modèle de données intermédiaire est introduit. Ce concept permet de masquer les détails de mise en œuvre du mappage de format et de réutiliser un seul modèle de données pour des mappages de formats multiples.

Vous pouvez utiliser ER pour configurer les formats de documents électroniques entrants et sortants conformément aux exigences légales des différents pays et régions. ER vous permet de gérer ces formats au cours de leur cycle de vie. Par exemple, vous pouvez adopter de nouvelles exigences réglementaires et générer des documents commerciaux au format requis pour échanger des informations avec les organismes publics, les banques et d’autres parties par voie électronique.

Le moteur ER est destiné aux utilisateurs métier, plutôt qu’aux développeurs. Étant donné que vous configurez des formats, à la place du code, les processus de création et d’ajustement des formats pour les documents électroniques sont plus rapides et plus faciles.

ER prend actuellement en charge les formats de feuille de calcul TEXT, XML, JSON, PDF, Microsoft Word, Microsoft Excel et OPENXML.

## <a name="capabilities"></a>Capacités

Le moteur ER est doté des capacités suivantes :

- Il représente un outil commun unique partagé pour la génération d’états électronique dans différents domaines et remplace plus de 20 moteurs différents effectuant certains types de génération d’états électronique pour les applications de finances et d’opérations.
- Il isole le format d’un état de l’implémentation actuelle. En d’autres termes, le format est applicable aux différentes versions.
- Il prend en charge la création d’un format personnalisé qui est basé sur un format d’origine. Il inclut également des fonctionnalités permettant de mettre à niveau automatiquement le format personnalisé lorsque le format d’origine est modifié du fait que des spécifications de localisation/personnalisation sont introduites.
- Il devient l’outil standard principal pour prendre en charge les exigences de localisation dans les rapports électroniques, pour Microsoft ainsi que pour les partenaires de Microsoft.
- Il prend en charge la capacité à distribuer des formats aux partenaires et aux clients via Microsoft Dynamics Lifecycle Services (LCS).

## <a name="key-concepts"></a>Concepts clés

### <a name="main-data-flow"></a>Flux de données principal

[![Flux de données principal ER.](./media/ger-main-data-flow.jpg)](./media/ger-main-data-flow.jpg)

### <a name="component"></a>Composant

ER prend en charge les types de composants suivants :

- Modèle de données
- Mappage de modèles
- Format
- Métadonnées

Pour plus d’informations, voir [Composants des états électroniques](er-overview-components.md).

### <a name="configuration"></a><a name="Configuration"></a>Configuration

Une configuration ER est le wrapper d’un composant ER particulier. Ce composant peut être un composant du modèle de données ou un composant de format. Une configuration peut inclure différentes versions d’un composant ER. Chaque configuration est marquée comme possédée par un fournisseur de configuration spécifique. La version **Brouillon** d’un composant d’une configuration peut être modifiée lorsque le propriétaire de la configuration a été sélectionné comme un fournisseur actif dans les paramètres ER dans l’application.

Chaque configuration de modèle contient un composant de modèle de données. Une nouvelle configuration de format peut être dérivée d’une configuration de modèle de données spécifique. Dans l’arborescence de configuration, la configuration de format qui est créée apparaît comme un enfant de la configuration de modèle de données d’origine.

La configuration de format qui est créée contient un composant de format. Le composant de modèle de données de cette configuration de modèle d’origine est automatiquement inséré dans le composant de format de la configuration de format enfant comme source de données par défaut.

Une configuration ER est partagée pour les sociétés d’application.

### <a name="provider"></a><a name="Provider"></a>Fournisseur

Le fournisseur ER est l’identificateur de partie utilisé pour indiquer l’auteur (propriétaire) de chaque configuration ER. ER vous permet de gérer la liste des fournisseurs de configuration. Les configurations de format émises pour les documents électroniques dans le cadre de la solution de finances et d’opérations sont marquées comme détenues par le fournisseur de configuration **Microsoft**.

Pour savoir comment enregistrer un nouveau fournisseur ER, consultez le Guide de tâche, **ER Créer un fournisseur de configuration et le marquer comme actif** (qui fait partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)** ).

### <a name="repository"></a><a name="Repository"></a>Référentiel

Un référentiel ER enregistre les configurations ER. Les types de référentiels ER suivants sont actuellement pris en charge : 

- Bibliothèque LCS partagée
- Projet LCS
- Système de fichiers
- RCS
- Ressources opérationnelles
- Référentiel global

Un référentiel **Bibliothèque LCS partagée** permet d’accéder à la liste des configurations dans la bibliothèque d'actif partagé de Lifecycle Services (LCS). Ce type de référentiel ER ne peut être enregistré que pour le fournisseur Microsoft. À partir de la bibliothèque d’actif partagé LCS, vous pouvez importer les dernières versions des configurations ER dans l’instance actuelle.

Un référentiel **Projet LCS** permet d’accéder à la liste des configurations d’un projet LCS spécifique (bibliothèque d’actifs de projet LCS) sélectionné lors de l’enregistrement du référentiel. ER vous permet de télécharger des configurations partagées de l’instance actuelle vers un référentiel **Projet LCS** donné. Vous pouvez également importer des configurations depuis un référentiel **Projet LCS** vers l’instance actuelle de vos applications de finances et d’opérations.

Un référentiel **Système de fichiers** permet d’accéder à la liste des configurations situées en tant que fichiers XML dans le dossier spécifique du système de fichiers local de l’ordinateur où le service AOS est hébergé. Le dossier requis est sélectionné au stade d’inscription du référentiel. Vous pouvez importer des configurations depuis un référentiel **Système de fichiers** vers l’instance actuelle. 

Notez que ce type de référentiel est accessible dans les environnements suivants :

- Environnements hébergés dans le cloud déployés à des fins de développement (contenant des modèles de test de suites incluses)
- Environnements déployés localement (on-premises)

Pour plus d’informations, voir [Importer les configurations de génération d’états électroniques (ER)](./electronic-reporting-import-ger-configurations.md).

Un référentiel **RCS** permet d’accéder à la liste des configurations d’une instance spécifique de [Service de configuration (RCS)](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration) sélectionné au phase d'enregistrement du référentiel. ER vous permet d’importer des configurations terminées ou partagées de l’instance RCS sélectionnée dans l’instance actuelle, de manière à pouvoir les utiliser pour la génération d’états électroniques.

Pour plus d’informations, voir [Importer les configurations de génération d’états électroniques (ER) à partir de RCS](./rcs-download-configurations.md).

Un référentiel **Global** permet d’accéder à la liste des configurations dans le référentiel global dans le [Service de configuration](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration). Ce type de référentiel ER ne peut être enregistré que pour le fournisseur Microsoft. À partir du référentiel global, vous pouvez importer les dernières versions des configurations ER dans l’instance actuelle.

Pour plus d’informations, voir [Importer les configurations des états électroniques (ER) à partir du référentiel global du service de configuration](./er-download-configurations-global-repo.md).

Un référentiel **Ressources opérationnelles** permet d’accéder à la liste des configurations que Microsoft, en tant que fournisseur de configuration ER, fournit initialement dans le cadre de la solution de l’application. Ces configurations peuvent être importées dans l’instance actuelle et être utilisées pour la génération d’états électroniques ou la lecture d’exemples de guides de tâches. Elles peuvent également être utilisées pour des localisations et personnalisations. Notez que les dernières versions des configurations ER fournies par Microsoft doivent être importées à partir de la bibliothèque d'actif partagé LCS à l’aide du référentiel ER correspondant.

Les référentiels **Projet LCS**, **Système de fichiers** et **Services de configuration réglementaire (RCS)** requis peuvent être enregistrés individuellement pour chaque fournisseur de configuration de l’instance actuelle. Chaque référentiel peut être consacré à un fournisseur de configuration spécifique.

## <a name="supported-scenarios"></a>Scénarios pris en charge

### <a name="building-a-data-model"></a>Élaboration d’un modèle de données

ER propose un concepteur de modèle vous permettant de créer un modèle de données pour un domaine de l’entreprise donné. Toutes les entités commerciales spécifiques à un domaine et les relations entre elles peuvent être présentées dans un modèle de données en tant que structure hiérarchique. 

Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Concevoir un modèle de données spécifiques au domaine** (qui fait partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)** ) .

### <a name="translating-data-model-content"></a>Traduction du contenu du modèle de données

Le contenu du modèle de données (étiquettes et descriptions) peut être traduit dans d’autres langues prises en charge par les applications. Vous souhaitez peut-être traduire le contenu du modèle de données pour les raisons suivantes :

- Au moment de la conception, pour rendre le contenu plus intelligible aux concepteurs de format parlant une langue étrangère qui utilisent le modèle de données pour le mappage des données des composants de format.
- Au moment de l’exécution, pour rendre le contenu plus convivial en présentant des invites et de l’aide pour les paramètres d’exécution ainsi que des messages de validation configurés (erreurs et avertissements) dans la langue que l’utilisateur actuellement connecté préfère.

### <a name="configuring-data-model-mappings-for-outgoing-documents"></a>Configuration des mappages de modèle de données pour les documents sortants

ER fournit un concepteur de mappage de modèle qui permet aux utilisateurs de mapper des modèles de données qu’ils ont conçus aux sources de données de l’application spécifiques. Selon le mappage, les données seront importées au moment de l’exécution des sources de données sélectionnées dans le modèle de données. Le modèle de données est ensuite utilisé comme une source de données abstraite des formats ER qui créent des documents électroniques sortants. 

Pour vous familiariser avec ce scénario en détails, visionnez les guides de tâche **ER Définir le mappage de modèles et sélectionner des sources de données** et **ER Mapper le modèle de données aux sources de données sélectionnées** (qui font partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)** ).

### <a name="configuring-data-model-mappings-for-incoming-documents"></a>Configuration des mappages de modèle de données pour les documents entrants

ER fournit un concepteur de mappage de modèle qui permet aux utilisateurs de mapper des modèles de données qu’ils ont conçus à des destinations spécifiques. Par exemple, des modèles de données peuvent être mappés aux composants pouvant être mis à jour (tables, entités de données et vues). Selon le mappage, les données sont mises à jour au moment de l’exécution à l’aide des données du modèle de données. Pour un stockage abstrait du format ER, le modèle de données contient les données importées depuis un document électronique entrant. 

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>Stockage du composant de modèle conçu en tant que modèle de configuration

ER peut stocker un modèle de données conçu avec des mappages associés en tant que configuration de modèle de l’instance actuelle. L’illustration suivante montre un exemple de ce type de configuration de modèle de données (la configuration du modèle de paiement).

Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Mapper le modèle de données aux sources de données sélectionnées** (qui fait partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)** ) .

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Élaboration d’un format qui utilise un modèle de données en tant que base

ER prend en charge un concepteur de format que vous pouvez utiliser pour élaborer le format d’un document électronique pour un domaine d’entreprise sélectionné en sélectionnant le composant modèle comme base. Le même concepteur de format ER vous permet de mapper un format que vous créez à un mappage de modèle de données du domaine sélectionné comme une source de données. 

Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Concevoir un format spécifique au domaine** (qui fait partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)** ).

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Création d’une configuration pour générer des documents électroniques au format de feuille de calcul OPENXML

Le concepteur de format ER peut être utilisé pour générer un document électronique au format de feuille de calcul OPENXML. 

Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Créer une configuration pour des états au format OPENXML** (qui fait partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)** ). Dans le cadre de l’étape du guide de tâche pour importer un modèle, utilisez le fichier Excel [Modèle d’état de paiement (SampleVendPaymWsReport.xlsx)](https://download.microsoft.com/download/3/f/0/3f0658b2-042c-43cf-a776-0f4c7f7cfe4e/SampleVendPaymWsReport.xlsx) en tant que modèle.

### <a name="building-a-configuration-to-generate-electronic-documents-in-a-word-document-format"></a>Création d’une configuration pour générer des documents électroniques au format de document Word

Le concepteur de format ER peut être utilisé pour générer un document électronique particulier au format de document Word. L’illustration suivante montre un exemple de ce type de format. Notez que ce format réutilise la configuration ER existante qui a été conçue initialement pour générer la sortie d’état au format OPENXML.

Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche ER Concevoir une configuration pour générer des états au format Microsoft WORD (qui fait partie du processus d’entreprise 7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)). Dans le cadre de l’étape du guide de tâche pour importer un modèle, utilisez les fichiers Word suivants en tant que modèles pour le format ER :

- [Modèle d’état de paiement (SampleVendPaymDocReport.docx)](https://download.microsoft.com/download/0/d/e/0de5a87c-95fc-4dfa-958f-285cb28b5b2b/SampleVendPaymDocReport.docx)
- [Modèle lié d’état de paiement (SampleVendPaymDocReportBounded.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded.docx)

### <a name="building-a-configuration-to-import-data-from-incoming-electronic-documents"></a>Génération d’une configuration pour importer les données des documents électroniques entrants

Le concepteur de format ER peut servir à décrire un document électronique planifié pour l’importation de données au format XML ou texte. Le format conçu permet d’analyser un document entrant. Le concepteur de mappage des formats ER permet de définir la liaison des éléments du format conçu au modèle de données. 

Pour vous familiariser avec ce scénario en détails, consultez le guide de tâche ER Créer des configurations pour importer des données d’un fichier externe (qui fait partie du processus d’entreprise 7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)). Utilisez les fichiers suivants pour lire le présent guide :

- [Configuration du modèle de données ER (1099model.xml)](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml)
- [Configuration du format ER (1099format.xml)](https://download.microsoft.com/download/e/8/7/e87154b0-b53f-431f-8e1e-0b7f7c9805a9/1099format.xml)
- [Exemple du document entrant au format XML (1099entries.xml)](https://download.microsoft.com/download/4/0/3/403a4958-df24-476a-b8b0-6843a9fa7f89/1099entries.xml)
- [Exemple du classeur pour gérer les données du document entrant (1099entries.xlsx)](https://download.microsoft.com/download/6/0/0/6001abab-a331-48db-a939-41851fb0f5d0/1099entries.xlsx)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Stockage d’un composant de format conçu dans une configuration de format

ER peut stocker un format conçu avec des mises en correspondance de données configurées en tant que configuration de format de l’instance actuelle. L’illustration ci-dessus montre un exemple de ce type de configuration de format (**BACS (Royaume-Uni)**, qui est un enfant de la configuration **Modèle de paiement** ). Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Concevoir un format spécifique au domaine** (qui fait partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)** ).

### <a name="configuring-finance-to-start-to-use-a-created-format-internally"></a>Configuration de Finance pour utiliser le format créé en interne

Vous pouvez configurer l’application pour utiliser un format créé pour générer des états électroniques. La référence à la configuration de format créé doit être définie dans les paramètres d’un domaine particulier. Par exemple, pour commencer à utiliser une configuration de format ER pour les paiements fournisseur électroniques au format BACS, la configuration de format doit être référencée dans des modes de paiement spécifiques.

Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Utiliser le format pour générer un document électronique pour les paiements** (qui fait partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)** ).

## <a name="handling-er-components"></a>Gestion des composants ER

### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>Publication d’un composant ER dans LCS pour l’offrir en externe (localisation)

Le propriétaire d’un composant (modèle ou format) qui a été créé peut utiliser ER pour publier la version terminée du composant vers LCS. Un référentiel de type **Projet LCS** pour le fournisseur de configuration ER actuel est requis. Lorsque le statut de la version terminée d’un composant est modifié pour passer de **TERMINÉE** à **PARTAGÉE**, cette version est publiée dans LCS. Lorsqu’un composant a été publié vers LCS, le propriétaire de ce composant devient un fournisseur du service permettant de prendre en charge ce composant. Par exemple, si le composant de format est conçu pour générer un document électronique légalement requis (par exemple, conformément au scénario de localisation), ce service suppose que ce format reste conforme aux modifications législatives et le fournisseur émet de nouvelles versions du composant dès que de nouvelles exigences législatives doivent être prises en charge. Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Charger une configuration dans Lifecycle Services** (qui fait partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)** ).

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>Importation du composant ER depuis LCS pour l’utiliser en interne

ER vous permet d’importer des composants ER à partir de LCS vers l’instance actuelle. Un référentiel de type **Projet LCS** est requis. Lorsqu’un composant ER a été importé de LCS vers l’instance actuelle, le propriétaire de l’instance devient un consommateur du service fourni par le propriétaire (auteur) du composant importé. Par exemple, si un composant de format est conçu pour générer à partir de l’application un document électronique donné dans un format spécifique à un pays/région particulier (scénario de localisation), cette consommation de service suppose la possibilité d’obtenir les mises à jour de ce format afin qu’il demeure conforme aux exigences législatives. Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Charger une configuration à partir de Lifecycle Services** (qui fait partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)** ).

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Élaboration d’un format en sélectionnant un autre format en tant que base (personnalisation)

ER vous permet de créer (dériver) un nouveau composant à partir de la version actuelle d’un composant (base) qui a été importé à partir de LCS. Par exemple, un utilisateur souhaite dériver un nouveau format pour mettre en œuvre des exigences spéciales pour un document électronique (par exemple, un champ supplémentaire ou une description complète) pour prendre en charge un scénario de personnalisation. Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Mettre à niveau le format par adoption d’une nouvelle version de base** (qui fait partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)** ).

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Mise à niveau d’un format en sélectionnant une nouvelle version du format de base (redéfinir)

ER vous permet d’adopter automatiquement les modifications de la version la plus récente du composant de base dans la version brouillon actuelle du composant dérivé. Ce processus est appelé *redéfinition de la base*. Par exemple, une nouvelle modification réglementaire (introduite dans la version la plus récente du composant de format importé depuis LCS) peut être automatiquement fusionnée dans la propre version personnalisée de ce format de document électronique. Toutes les modifications qui ne peuvent pas être fusionnées automatiquement sont considérées comme des conflits. Ces conflits sont présentés pour une résolution manuelle dans l’outil de concepteur pour le composant approprié. Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Mettre à niveau le format par adoption d’une nouvelle version de base de ce format** (qui fait partie du processus d’entreprise **7.5.5.3 Acquérir/Développer un composant de services/solutions informatiques modifié (10683)** ).

## <a name="list-of-er-configurations-that-have-been-released-in-finance"></a><a name="list-of-configurations"></a>Liste des configurations ER qui ont été publiées dans Finance

La liste des configurations ER pour Finance est constamment mise à jour. Ouvrez le [référentiel global](er-download-configurations-global-repo.md) pour consulter la liste des configurations ER actuellement prises en charge. Sur l’organisateur **Détails de l’abandon**, vous pouvez consulter les informations sur les configurations qui ont été abandonnées ou qui ne sont plus gérées. 

![Contenu du référentiel global sur la page Référentiel de configuration.](./media/er-overview-03.gif)

## <a name="additional-resources"></a>Ressources supplémentaires

- [Composants des états électroniques](er-overview-components.md)
- [Créer des configurations de gestion des états électroniques (ER)](electronic-reporting-configuration.md)
- [Gérer le cycle de vie de la configuration des états électroniques (ER)](general-electronic-reporting-manage-configuration-lifecycle.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

