---
title: Vue d’ensemble des états électroniques (ER)
description: Cette rubrique fournit une vue d’ensemble de l’outil de gestion des états électroniques. Elle décrit les concepts clés, les scénarios pris en charge et les formats qui font partie de la solution.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom:
- "58941"
- intro-internal
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 05c77b913c1c2281ca45a3dea8fef2223a1dcfbb
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6345688"
---
# <a name="electronic-reporting-er-overview"></a>Vue d’ensemble des états électroniques

[!include [banner](../includes/banner.md)]

Cette rubrique fournit une vue d’ensemble de l’outil de gestion des états électroniques (ER). Il comporte des informations sur les concepts essentiels, les scénarios pris en charge par l’ER et une liste des formats conçus et lancés dans le cadre de la solution.

États électroniques est un outil que vous pouvez utiliser pour configurer les formats de documents électroniques entrants et sortants conformément aux exigences légales des différents pays/régions. Il vous permet de gérer ces formats au cours de leur cycle de vie. Par exemple, vous pouvez adopter de nouvelles exigences réglementaires et générer des documents commerciaux au format requis pour échanger des informations avec les organismes publics, les banques et d’autres parties par voie électronique.

Le moteur d’états électroniques est destiné aux utilisateurs professionnels, plutôt qu’aux développeurs. Étant donné que vous configurez des formats, à la place du code, les processus de création et d’ajustement des formats pour les documents électroniques sont plus rapides et plus faciles.

Les états électroniques prennent actuellement en charge les formats de feuille de calcul texte, XML, Microsoft Word et OPENXML. Toutefois, une interface d’extension prend en charge d’autres formats.

## <a name="capabilities"></a>Capacités

Le moteur d’états électroniques est doté des fonctionnalités suivantes :

- il représente un outil commun unique partagé pour la génération d’états électronique dans différents domaines et remplace plus de 20 moteurs différents effectuant certains types de génération d’états électronique Finance and Operations.
- Il isole le format d’un état de l’implémentation actuelle. En d’autres termes, le format est applicable aux différentes versions.
- Il prend en charge la création d’un format personnalisé qui est basé sur un format d’origine. Il inclut également des fonctionnalités permettant de mettre à niveau automatiquement le format personnalisé lorsque le format d’origine est modifié du fait que des spécifications de localisation/personnalisation sont introduites.
- Il devient l’outil standard principal pour prendre en charge les exigences de localisation dans les états électroniques, pour Microsoft ainsi que pour les partenaires de Microsoft.
- Il prend en charge la capacité à distribuer des formats aux partenaires et aux clients via Microsoft Dynamics Lifecycle Services (LCS).

## <a name="key-concepts"></a>Concepts clés

### <a name="components"></a>Composants

Les états électroniques prennent en charge deux types de composants : **Modèle de données** et **Format**.

#### <a name="data-model-and-model-mapping-components"></a>Composants de modèle de données et de mappage de modèle

Un composant de modèle de données est une représentation abstraite d’une structure de données. Il décrivait un domaine de l’entreprise spécifique avec suffisamment de détail pour satisfaire aux conditions de génération d’états pour ce domaine. Un composant de modèle de données se compose des éléments suivants :

- <a name="DataModelComponent"></a>un modèle de données, en tant qu’ensemble d’entités commerciales spécifiques au domaine, ainsi qu’une définition hiérarchiquement structurée des relations entre elles.
- <a name="ModelMappingComponent"></a>une mise en correspondance de modèle en tant qu’ensemble de sources de données de l’application avec des éléments individuels de ce modèle de données qui spécifie au moment de l’exécution le flux de données et les règles de population de données commerciales dans le composant de modèle de données.

Une entité commerciale de modèle de données est représentée comme un conteneur (enregistrement). Les propriétés d’entité commerciale sont représentées comme des articles de données (champs). Chaque article de données est doté d’un nom, d’un libellé, d’une description et d’une valeur uniques. La valeur de chaque élément de données peut être conçu de sorte qu’il soit reconnu comme une chaîne, entier, réel, date, énumération, booléen, etc. En outre, il peut s’agir d’un autre enregistrement ou d’une liste d’enregistrements.

Un composant de modèle de données unique peut contenir plusieurs hiérarchies des entités commerciales spécifiques à un domaine. Il contient également les mappages de modèles qui prennent en charge le flux de données spécifiques aux états au moment de l’exécution. Les hiérarchies sont différenciées par un enregistrement unique sélectionné comme racine de la mise en correspondance de modèle. Par exemple, le modèle de données du domaine du paiement peut prendre en charge les mises en correspondance suivantes :

- Société \> Fournisseur \> Transactions de paiement du domaine comptabilité fournisseur
- Client \> Société \> Transactions de paiement du domaine comptabilité client

Notez que les entités commerciales (par exemple, les transactions de paiement et la société) sont conçues en une fois. Différents mappages permettent de les réutiliser.

Un mappage de modèle qui prend en charge les documents électroniques sortants a les fonctionnalités suivantes :

- Il peut utiliser les différents types de données comme sources de données pour un modèle de données. Par exemple, il peut utiliser des enums, des entités de données, des méthodes ou des tables.
- Il prend en charge les paramètres d’entrée utilisateur qui peuvent être définies comme sources de données pour un modèle de données lorsque certaines données doivent être spécifiées au moment de l’exécution.
- Il prend en charge la transformation des données en groupes requis. Il permet également de filtrer, de trier et d’ajouter des données, ainsi que des champs calculés logiques qui sont conçus via les formules qui sont semblables aux formules de Microsoft Excel. Pour plus d’informations, voir [Concepteur de formule dans la gestion des états électroniques](general-electronic-reporting-formula-designer.md)).

Un mappage de modèle qui prend en charge les documents électroniques entrants a les fonctionnalités suivantes :

- Il peut utiliser différents éléments de données pouvant être mis à jour comme cibles. Ces éléments de données incluent des tables, des entités de données et des vues. Les données peuvent être mises à jour à l’aide des données issues de documents électroniques entrants. Plusieurs cibles peuvent être utilisées dans un mappage de modèle unique.
- Il prend en charge les paramètres d’entrée utilisateur qui peuvent être définies comme sources de données pour un modèle de données lorsque certaines données doivent être spécifiées au moment de l’exécution.

Un composant de modèle de données est conçu pour chaque domaine d’activité qui devrait être utilisé comme une source de données unifiée pour les rapports qui isolent les rapports de l’implémentation physique des sources de données Finance and Operations. Il représente des concepts et des fonctionnalités d’entreprise spécifiques au domaine sous une forme qui rend la conception d’origine du format de rapport et toute autre maintenance plus efficaces.

#### <a name="format-components-for-outgoing-electronic-documents"></a><a name="FormatComponentOutbound"></a>Composants de format pour les documents électroniques sortants

Un composant de format est le modèle utilisé pour la sortie générée au moment de l’exécution. Un modèle se compose des éléments suivants :

- un format qui définit la structure et le contenu d’un document électronique sortant généré au moment de l’exécution ;
- des sources de données, en tant qu’ensemble de paramètres d’entrée utilisateur et de modèle de données spécifique au domaine avec la mise en correspondance du modèle sélectionnée ;
- une mise en correspondance de format, en tant qu’ensemble de liaisons des sources de données de format avec des éléments individuels de format qui spécifient au moment de l’exécution le flux de données et les règles de génération de sortie de format ;
- une validation de format en tant qu’ensemble de règles configurables qui contrôlent la génération d’états au moment de l’exécution en fonction du contexte d’exécution. Par exemple, il peut y avoir une règle qui arrête la génération de sortie des paiements d’un fournisseur et lance une exception lorsque des attributs spécifiques du fournisseur sélectionné sont manquants, comme le numéro de compte bancaire.

Un composant de format prend en charge les fonctions suivantes :

- La création de sortie de rapports en tant que fichiers individuels dans différents formats, tels que texte, XML, document Microsoft Word ou feuille de calcul.
- Création de plusieurs fichiers séparément et encapsulation de ces fichiers dans des fichiers zip.

Un composant de format vous permet de joindre certains fichiers pouvant être utilisés dans la sortie d’états :

- des classeurs Excel qui contiennent une feuille de calcul qui peut être utilisée comme modèle pour les sorties au format de feuille de calcul OPENXML ;
- des fichiers Word qui contiennent un document qui peut être utilisé comme modèle pour les sorties au format de document Microsoft Word
- d’autres fichiers pouvant être incorporés à la sortie du format en tant que fichiers prédéfinis.

L’illustration ci-dessous indique les flux de données pour ces formats.

[![Flux de données des composants de format sortants.](./media/ER-overview-02.png)](./media/ER-overview-02.png)

Pour exécuter une configuration de format de génération d’états électroniques unique et générer un document électronique sortant, vous devez identifier le mappage de la configuration de format.

#### <a name="format-components-for-incoming-electronic-documents"></a><a name="FormatComponentInbound"></a>Composants de format pour les documents électroniques entrants

Un composant de format est le modèle de document entrant qui est importé au moment de l’exécution. Un modèle se compose des éléments suivants :

- Un format qui définit la structure et le contenu d’un document électronique entrant contenant des données qui sont importées au moment de l’exécution. Un composant de format est utilisé pour analyser un document entrant dans différents formats : texte et XML.
- Un mappage des formats qui lie les éléments de format individuels aux éléments d’un modèle de données spécifique au domaine. Au moment de l’exécution, les éléments du modèle de données spécifient le flux de données et les règles pour importer les données d’un document entrant, puis stockent les données dans un modèle de données.
- Une validation de format en tant qu’ensemble de règles configurables qui contrôlent l’importation de données au moment de l’exécution en fonction du contexte d’exécution. Par exemple, il peut y avoir une règle qui empêche l’importation de données d’un relevé bancaire contenant des paiements d’un fournisseur et lance une exception lorsque les attributs d’un fournisseur spécifique sont manquants, comme le code d’identification du fournisseur.

L’illustration ci-dessous indique les flux de données pour ces formats.

[![Flux de données des composants de format entrants.](./media/ER-overview-03.png)](./media/ER-overview-03.png)

Pour exécuter une configuration simple de format de génération d’états électroniques pour importer les données d’un document électronique entrant, vous devez identifier le mappage souhaité d’une configuration de format, ainsi que le point d’intégration d’un mappage de modèle. Vous pouvez utiliser les mêmes mappages et destinations de modèles avec différents formats pour différents types de documents entrants.

#### <a name="component-versioning"></a>Contrôle de versions du composant

Le contrôle de versions est pris en charge pour les composants d’états électroniques. Le workflow suivant est fourni pour gérer et sauvegarder les modifications dans les composants d’états électroniques :

1. La version qui est créée est marquée comme étant une version en mode **Brouillon**. Cette version peut être modifiée et est disponible pour des séries de tests.
2. La version **Brouillon** peut être convertie en une version **Terminée**. Cette version peut être utilisée dans les processus de création d’états locaux.
3. La version **Terminée** peut être convertie en une version **Partagée**. Cette version est publiée sur LCS et peut être utilisée dans le processus de création de rapports globaux.
4. La version **Partagée** peut être convertie en une version **Interrompue**. Cette version peut ensuite être supprimée.

Les versions dotées du statut **Terminée** ou **Partagée** sont disponibles pour un autre échange de données. Les actions suivantes peuvent être exécutées sur un composant possédant ces statuts :

- Le composant peut être sérialisé au format XML et exporté vers un fichier au format XML.
- Le composant peut être resérialisé à partir d’un fichier XML et importé dans l’application sous la forme d’une nouvelle version d’un composant d’état électronique.

#### <a name="component-date-effectivity"></a>Validité de date du composant

Les versions du composant d’état électronique est soumis à une date d’effet. Vous pouvez définir la date **Prend effet le** pour un composant d’état électronique afin de spécifier la date à partir de laquelle ce composant devient valide pour les processus de génération d’états. La date de session de l’application permet de définir si un composant est valide pour l’exécution. Lorsque plusieurs versions sont valides pour une date spécifique, la version la plus récente est utilisée pour le processus de génération d’états.

#### <a name="component-access"></a>Accès au composant

L’accès aux composants de format d’états électroniques dépend du paramètre du code de pays/région ISO. Lorsque ce paramètre est vide pour une version sélectionnée d’une configuration de format, un composant de format est accessible à partir de n’importe quelle société au moment de l’exécution. Lorsqu’il contient des codes pays/région ISO, un composant de format est disponible uniquement à partir des sociétés dont l’adresse principale est défini pour l’un des codes pays/régions ISO du composant de format.

Différentes versions d’un composant de format de données peuvent avoir différents paramètres de codes pays/région ISO.

#### <a name="configuration"></a><a name="Configuration"></a>Configuration

Une configuration de la génération d’états électroniques est le wrapper d’un composant de génération d’états électroniques particulier. Ce composant peut être un composant du modèle de données ou un composant de format. Une configuration peut inclure différentes versions d’un composant d’état électronique. Chaque configuration est marquée comme possédée par un fournisseur de configuration spécifique. La version **Brouillon** d’un composant d’une configuration peut être modifiée lorsque le propriétaire d’une configuration a été sélectionné comme fournisseur actif dans les paramètres d’états électroniques dans l’application.

Chaque configuration de modèle contient un composant de modèle de données. Une nouvelle configuration de format peut être dérivée d’une configuration de modèle de données spécifique. Dans l’arborescence de configuration, la configuration de format qui est créée apparaît en tant qu’enfant de la configuration de modèle de données d’origine.

La configuration de format qui est créée contient un composant de format. Le composant de modèle de données de cette configuration de modèle d’origine est automatiquement inséré dans le composant de format de la configuration de format enfant comme source de données par défaut.

Une configuration d’état électronique est partagée pour les sociétés de l’application.

#### <a name="provider"></a><a name="Provider"></a>Fournisseur

Le fournisseur d’états électroniques est l’identificateur de partie utilisé pour indiquer l’auteur (propriétaire) de chaque configuration d’état électronique. L’état électronique vous permet de gérer la liste des fournisseurs de configuration. Les configurations de format émises pour les documents électroniques dans le cadre de la solution Finance and Operations sont marquées comme détenues par le fournisseur de configuration **Microsoft**.

Pour savoir comment enregistrer un nouveau fournisseur d’états électroniques, consultez le Guide de tâche, **Génération d’états électroniques – Créer un fournisseur de configuration et le marquer comme actif** (qui fait partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**).

#### <a name="repository"></a><a name="Repository"></a>Référentiel

Un référentiel d’états électroniques enregistre les configurations d’états électroniques. Les types de référentiels ER suivants sont actuellement pris en charge : 

- Bibliothèque LCS partagée
- Projet LCS
- Système de fichiers
- RCS
- Ressources Operations
- Référentiel global

Un référentiel **Bibliothèque LCS partagée** permet d’accéder à la liste des configurations dans la bibliothèque des actifs partagés de Lifecycle Services (LCS). Ce type de référentiel ER ne peut être enregistré que pour le fournisseur Microsoft. À partir de la bibliothèque d’actifs LCS partagés, vous pouvez importer les dernières versions des configurations ER dans l’instance actuelle.

Un référentiel **Projet LCS** permet d’accéder à la liste des configurations d’un projet LCS spécifique (bibliothèque d’actifs de projet LCS) sélectionné lors de l’enregistrement du référentiel. Les états électroniques vous permettent de télécharger des configurations partagées de l’instance actuelle vers un référentiel **Projet LCS** donné. Vous pouvez également importer des configurations depuis un référentiel **Projet LCS** vers votre instance Finance and Operations actuelle.

Un référentiel **Système de fichiers** permet d’accéder à la liste des configurations situées en tant que fichiers xml dans le dossier spécifique du système de fichiers local de l’ordinateur où le service AOS est hébergé. Le dossier requis est sélectionné au stade d’enregistrement du référentiel. Vous pouvez importer des configurations depuis un référentiel **Système de fichiers** vers l’instance actuelle. 

Notez que ce type de référentiel est accessible dans les environnements suivants :

- environnements hébergés dans le cloud déployés à des fins de développement (contenant des modèles de test de suites incluses)
- environnements déployés localement (sur site)

Pour plus d’informations, voir [Importer les configurations de génération d’états électroniques (ER)](./electronic-reporting-import-ger-configurations.md).

Un référentiel **RCS** permet d’accéder à la liste des configurations d’une instance spécifique de [Configuration Service (RCS)](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration) sélectionnée à l’enregistrement du référentiel. La génération d’états électroniques permet d’importer des configurations terminées ou partagées de l’instance RCS sélectionnée dans l’instance actuelle, de manière à pouvoir les utiliser pour la génération d’états électroniques.

Pour plus d’informations, voir [Importer les configurations de génération d’états électroniques (ER) à partir de RCS](./rcs-download-configurations.md).

Un référentiel **Global** permet d’accéder à la liste des configurations dans le référentiel global dans le [Configuration Service](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration). Ce type de référentiel ER ne peut être enregistré que pour le fournisseur Microsoft. À partir du référentiel global, vous pouvez importer les dernières versions des configurations ER dans l’instance actuelle.

Pour plus d’informations, voir [Importer les configurations des états électroniques (ER) à partir du référentiel global de Configuration Service](./er-download-configurations-global-repo.md).

Un référentiel **Ressources opérationnelles** permet d’accéder à la liste des configurations que Microsoft, en tant que fournisseur de configurations d’états électroniques, fournit à l’origine dans le cadre de la solution de l’application. Ces configurations peuvent être importées dans l’instance actuelle et être utilisées pour la génération d’états électroniques ou la lecture d’exemples de guides de tâches. Elles peuvent également être utilisées pour des localisations et personnalisations. Notez que les dernières versions des configurations ER fournies par Microsoft doivent être importées à partir de la bibliothèque des actifs LCS partagés à l’aide du référentiel ER correspondant.

Les référentiels **Projet LCS**, **Système de fichiers** et **Services de configuration réglementaire (RCS)** requis peuvent être enregistrés individuellement pour chaque fournisseur de configuration de l’instance actuelle. Chaque référentiel peut être consacré à un fournisseur de configuration spécifique.

## <a name="supported-scenarios"></a>Scénarios pris en charge

### <a name="building-a-data-model"></a>Élaboration d’un modèle de données

L’état électronique propose un concepteur de modèle vous permettant de créer un modèle de données pour un domaine de l’entreprise donné. Toutes les entités commerciales spécifiques à un domaine et les relations entre elles peuvent être présentées dans un modèle de données en tant que structure hiérarchique. 

Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Concevoir un modèle de données spécifiques au domaine** (qui fait partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**) .

### <a name="translating-data-model-content"></a>Traduction du contenu du modèle de données

Le contenu du modèle de données (étiquettes et descriptions) peut être traduit dans d’autres langues prises en charge par les applications. Vous souhaitez peut-être traduire le contenu du modèle de données pour les raisons suivantes :

- Au moment de la conception, pour rendre le contenu plus intelligible aux concepteurs de format parlant une langue étrangère qui utilisent le modèle de données pour la mise en correspondance des données des composants de format.
- Au moment de l’exécution, pour rendre le contenu plus convivial pour la présentation des invites et de l’aide pour les paramètres d’exécution ainsi que des messages de validation configurés (erreurs et avertissements) dans la langue que l’utilisateur actuellement connecté préfère.

### <a name="configuring-data-model-mappings-for-outgoing-documents"></a>Configuration des mappages de modèle de données pour les documents sortants

L’état électronique fournit un concepteur de mise en correspondance de modèle qui permet aux utilisateurs de mapper des modèles de données qu’ils ont conçus pour des sources de données de l’application spécifiques. Selon le mappage, les données seront importées au moment de l’exécution des sources de données sélectionnées dans le modèle de données. Le modèle de données est ensuite utilisé comme une source de données abstraite des formats de génération d’états électroniques qui créent les documents électroniques sortants. 

Pour vous familiariser avec ce scénario en détails, visionnez les guides de tâche **ER Définir le mappage de modèles et sélectionner des sources de données** et **ER Mapper le modèle de données aux sources de données sélectionnées** (qui font partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**).

### <a name="configuring-data-model-mappings-for-incoming-documents"></a>Configuration des mappages de modèle de données pour les documents entrants

L’état électronique fournit un concepteur de mise en correspondance de modèle qui permet aux utilisateurs de mapper des modèles de données qu’ils ont conçus pour des destinations spécifiques. Par exemple, des modèles de données peuvent être mappés aux composants pouvant être mis à jour (tables, entités de données et vues). Selon le mappage, les données sont mises à jour au moment de l’exécution à l’aide des données du modèle de données. Pour un stockage abstrait du format de génération d’états électroniques, le modèle de données contient les données importées depuis un document électronique entrant. 

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>Stockage du composant de modèle conçu en tant que modèle de configuration

ER peut stocker un modèle de données conçu avec des mises en correspondance de données associées en tant que configuration de modèle de l’instance actuelle. L’illustration suivante montre un exemple de ce type de configuration de modèle de données (la configuration du modèle de paiement).

Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Mapper le modèle de données aux sources de données sélectionnées** (qui fait partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**) .

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Élaboration d’un format qui utilise un modèle de données en tant que base

ER prend en charge un concepteur de format que vous pouvez utiliser pour élaborer le format d’un document électronique pour le domaine d’entreprise en sélectionné d’affaires en sélectionnant le composant modèle comme base. Le même concepteur de format ER vous permet de mettre en correspondance un format créé et la mise en correspondance du modèle de données du domaine sélectionné comme source de données. 

Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Concevoir un format spécifique au domaine** (qui fait partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)** ).

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Création d’une configuration pour générer des documents électroniques au format de feuille de calcul OPENXML

Le concepteur de format ER peut être utilisé pour générer un document électronique particulier au format de feuille de calcul OPENXML. 

Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Créer une configuration pour des états au format OPENXML** (qui fait partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**). Dans le cadre de l’étape du guide de tâche pour importer un modèle, utilisez le fichier Excel [Modèle d’état de paiement (SampleVendPaymWsReport.xlsx)](https://download.microsoft.com/download/3/f/0/3f0658b2-042c-43cf-a776-0f4c7f7cfe4e/SampleVendPaymWsReport.xlsx) en tant que modèle.

### <a name="building-a-configuration-to-generate-electronic-documents-in-a-word-document-format"></a>Création d’une configuration pour générer des documents électroniques au format de document Word

Le concepteur de format ER peut être utilisé pour générer un document électronique particulier au format de document Word. L’illustration suivante montre un exemple de ce type de format. Notez que ce format réutilise la configuration ER existante qui a été conçue initialement pour générer la sortie d’état au format OPENXML.

Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche ER Concevoir une configuration pour générer des états au format Microsoft WORD (qui fait partie du processus d’entreprise 7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)). Dans le cadre de l’étape du guide de tâche pour importer un modèle, utilisez les fichiers Word suivants en tant que modèles pour le format ER :

- [Modèle d’état de paiement (SampleVendPaymDocReport.docx)](https://download.microsoft.com/download/0/d/e/0de5a87c-95fc-4dfa-958f-285cb28b5b2b/SampleVendPaymDocReport.docx)
- [Modèle lié d’état de paiement (SampleVendPaymDocReportBounded.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded.docx)

### <a name="building-a-configuration-to-import-data-from-incoming-electronic-documents"></a>Génération d’une configuration pour importer les données des documents électroniques entrants

Le concepteur de format ER peut servir à décrire un document électronique planifié pour l’importation de données au format XML ou texte. Le format conçu permet d’analyser un document entrant. Le concepteur de mappage des formats ER permet de définir la liaison des éléments du format conçu au modèle de données. 

Pour vous familiariser avec ce scénario en détails, consultez le guide de tâche ER Créer des configurations pour importer des données d’un fichier externe (qui fait partie du processus d’entreprise 7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)). Les fichiers suivants pour lire le présent guide :

- [Configuration du modèle de données ER (1099model.xml)](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml)
- [Configuration du format ER (1099format.xml)](https://download.microsoft.com/download/e/8/7/e87154b0-b53f-431f-8e1e-0b7f7c9805a9/1099format.xml)
- [Exemple du document entrant au format XML (1099entries.xml)](https://download.microsoft.com/download/4/0/3/403a4958-df24-476a-b8b0-6843a9fa7f89/1099entries.xml)
- [Exemple du classeur pour gérer les données du document entrant (1099entries.xlsx)](https://download.microsoft.com/download/6/0/0/6001abab-a331-48db-a939-41851fb0f5d0/1099entries.xlsx)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Stockage d’un composant de format conçu dans une configuration de format

ER peut stocker un format conçu avec des mises en correspondance de données configurées en tant que configuration de format de l’instance actuelle. L’illustration ci-dessus montre un exemple de ce type de configuration de format (**BACS (Royaume-Uni)**, qui est un enfant de la configuration **Modèle de paiement**). Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Concevoir un format spécifique au domaine** (qui fait partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**).

### <a name="configuring-finance-to-start-to-use-a-created-format-internally"></a>Configuration de Finance pour utiliser le format créé en interne

Vous pouvez configurer l’application pour utiliser le format créé pour générer des états électroniques. La référence à la configuration de format créé doit être définie dans les paramètres d’un domaine particulier. Par exemple, pour commencer à utiliser une configuration de format ER pour les paiements fournisseur électroniques au format BACS, la configuration de format doit être référencée dans des modes de paiement spécifiques.

Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Utiliser le format pour générer un document électronique pour les paiements** (qui fait partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**).

## <a name="handling-er-components"></a>Gestion des composants ER

### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>Publication d’un composant ER dans LCS pour l’offrir en externe (localisation)

Le propriétaire d’un composant (modèle ou format) qui a été créé peut utiliser ER pour publier la version terminée du composant vers LCS. Un référentiel de type **Projet LCS** pour le fournisseur de configuration ER actuel est requis. Lorsque le statut de la version terminée d’un composant est modifié pour passer de **TERMINÉE** à **PARTAGÉE**, cette version est publiée dans LCS. Lorsqu’un composant a été publié vers LCS, le propriétaire de ce composant devient un fournisseur du service permettant de prendre en charge ce composant. Par exemple, si le composant de format est conçu pour générer un document électronique légalement requis (par exemple, conformément au scénario de localisation), ce service suppose que ce format reste conforme aux modifications législatives et le fournisseur émet de nouvelles versions du composant dès que de nouvelles exigences législatives doivent être prises en charge. Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Charger une configuration dans Lifecycle Services**(qui fait partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**).

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>Importation du composant ER depuis LCS pour l’utiliser en interne

ER vous permet d’importer des composants ER à partir de LCS vers l’instance actuelle. Un référentiel de type **Projet LCS** est requis. Lorsqu’un composant ER a été importé de LCS vers l’instance actuelle, le propriétaire de l’instance devient un consommateur du service fourni par le propriétaire (auteur) du composant importé. Par exemple, si un composant de format est conçu pour générer à partir de l’application un document électronique donné dans un format spécifique à un pays/région particulier (scénario de localisation), cette consommation de service suppose la possibilité d’obtenir les mises à jour de ce format afin qu’il demeure conforme aux exigences législatives. Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Charger une configuration à partir de Lifecycle Services** (qui fait partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**).

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Élaboration d’un format en sélectionnant un autre format en tant que base (personnalisation)

ER vous permet de que créer (dériver) un nouveau composant à partir de la version actuelle d’un composant (base) qui a été importé à partir de LCS. Par exemple, un utilisateur souhaite dériver un nouveau format pour mettre en œuvre une configuration spécifique pour un document électronique (par exemple, un champ supplémentaire ou une description complète) pour prendre en charge un scénario de personnalisation. Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Mettre à niveau le format par adoption d’une nouvelle version de base** (qui fait partie du processus d’entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**).

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Mise à niveau d’un format en sélectionnant une nouvelle version du format de base (redéfinir)

ER vous permet d’adopter automatiquement les modifications de la version la plus récente du composant de base dans la version brouillon actuelle du composant dérivé. Ce processus est appelé *redéfinition de la base*. Par exemple, une nouvelle modification réglementaire (introduite dans la version la plus récente du composant de format importé depuis LCS) peut être automatiquement fusionnée dans la propre version personnalisée de ce format de document électronique. Toutes les modifications qui ne peuvent pas être fusionnées automatiquement sont considérées comme des conflits. Ces conflits sont présentés pour une résolution manuelle dans l’outil de concepteur pour le composant approprié. Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Mettre à niveau le format par adoption d’une nouvelle version de base de ce format** (qui fait partie du processus d’entreprise **7.5.5.3 Acquérir/Développer un composant de services/solutions informatiques modifié (10683)**).

## <a name="list-of-er-configurations-that-have-been-released-in-finance"></a><a name="list-of-configurations"></a>Liste des configurations de la gestion des états électroniques qui ont été publiées dans Finance

La liste des configurations de gestion des états électroniques pour Finance est constamment mis à jour. Ouvrez le [référentiel global](er-download-configurations-global-repo.md) pour consulter la liste des configurations de gestion des états électroniques actuellement prises en charge. Sur l’organisateur **Détails de l’abandon**, vous pouvez consulter les informations sur les configurations qui ont été abandonnées ou qui ne sont plus gérées. 

![Contendu du référentiel global sur la page Référentiel de configuration.](./media/er-overview-03.gif)

## <a name="additional-resources"></a>Ressources supplémentaires

- [Créer des configurations de gestion des états électroniques](electronic-reporting-configuration.md)
- [Gérer le cycle de vie de la configuration des états électroniques (ER)](general-electronic-reporting-manage-configuration-lifecycle.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
