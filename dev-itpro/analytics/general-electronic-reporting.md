---
title: "Vue d'ensemble des États électroniques"
description: "Cet article fournit une vue d'ensemble de l'outil de gestion des états électroniques (ER). Il comporte des informations sur les concepts essentiels, les scénarios pris en charge par l'ER et une liste des formats conçus et lancés dans le cadre de la solution."
author: kfend
manager: AnnBe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: cebd1b6f041e18c2e016142aba7447bf813f570b
ms.openlocfilehash: f6327b339441f2f1f6d4e557e45d085685245a08
ms.contentlocale: fr-fr
ms.lasthandoff: 06/19/2017


---

# <a name="electronic-reporting-overview"></a>Vue d'ensemble des états électroniques

[!include[banner](../includes/banner.md)]


Cette rubrique fournit une vue d'ensemble de l'outil de gestion des états électroniques (ER). Il comporte des informations sur les concepts essentiels, les scénarios pris en charge par l'ER et une liste des formats conçus et lancés dans le cadre de la solution.

États électroniques est un outil que vous pouvez utiliser pour configurer les formats de documents électroniques entrants et sortants conformément aux exigences légales des différents pays/régions. Il vous permet de gérer ces formats au cours de leur cycle de vie. Par exemple, vous pouvez adopter de nouvelles exigences réglementaires et générer des documents commerciaux au format requis pour échanger des informations avec les organismes publics, les banques et d'autres parties par voie électronique.

Le moteur d'états électroniques est destiné aux utilisateurs professionnels, plutôt qu'aux développeurs. Étant donné que vous configurez des formats, à la place du code, les processus de création et d’ajustement des formats pour les documents électroniques sont plus rapides et plus faciles.

La génération d'états électroniques prend en charge les formats TEXT, XML, Document Microsoft Word et OPENXML. Toutefois, une interface d’extension prend en charge d'autres formats.

## <a name="capabilities"></a>Capacités
Le moteur d'états électroniques est doté des fonctionnalités suivantes :

- il représente un outil partagé unique pour la génération d'états électronique dans différents domaines et remplace plus de 20 moteurs différents effectuant certains types de génération d'états électronique Microsoft Dynamics 365 for Operations.
- Il isole le format d’un état de l’implémentation actuelle de Dynamics 365 for Operations. En d’autres termes, le format est applicable aux différentes versions de Dynamics 365 for Operations.
- Il prend en charge la création d’un format personnalisé qui est basé sur un format d’origine. Il inclut également des fonctionnalités permettant de mettre à niveau automatiquement le format personnalisé lorsque le format d’origine est modifié du fait que des spécifications de localisation/personnalisation sont introduites.
- Il devient l'outil standard principal pour prendre en charge les exigences de localisation dans les états électroniques, pour Microsoft ainsi que pour les partenaires de Microsoft.
- Il prend en charge la capacité à distribuer des formats aux partenaires et aux clients via Microsoft Dynamics Lifecycle Services (LCS).

## <a name="key-concepts"></a>Concepts clés
### <a name="components"></a>Composants

Les états électroniques prennent en charge deux types de composants : **Modèle de données** et **Format**.

#### <a name="data-model-components"></a>Composants de modèle de données

Un composant de modèle de données est une représentation abstraite d'une structure de données. Il décrivait un domaine de l'entreprise spécifique avec suffisamment de détail pour satisfaire aux conditions de génération d'états pour ce domaine. Un composant de modèle de données se compose des éléments suivants :

- un modèle de données, en tant qu'ensemble d'entités commerciales spécifiques au domaine, ainsi qu'une définition hiérarchiquement structurée des relations entre elles.
- une mise en correspondance de modèle en tant qu'ensemble de sources de données Dynamics 365 for Operations avec des éléments individuels de ce modèle de données qui spécifie au moment de l'exécution le flux de données et les règles de population de données commerciales dans le composant de modèle de données.
Une entité commerciale de modèle de données est représentée comme un conteneur (enregistrement). Les propriétés d'entité commerciale sont représentées comme des articles de données (champs). Chaque article de données est doté d'un nom, d'un libellé, d'une description et d'une valeur uniques. La valeur de chaque élément de données peut être conçu de sorte qu’il soit reconnu comme une chaîne, entier, réel, date, énumération, booléen, etc. En outre, il peut s'agir d'un autre enregistrement ou d'une liste d'enregistrements.

Un composant de modèle de données unique peut contenir plusieurs hiérarchies des entités commerciales spécifiques à un domaine. Il contient également les mappages de modèles qui prennent en charge le flux de données spécifiques aux états au moment de l'exécution. Les hiérarchies sont différenciées par un enregistrement unique sélectionné comme racine de la mise en correspondance de modèle. Par exemple, le modèle de données du domaine du paiement peut prendre en charge les mises en correspondance suivantes :

- Société > Fournisseur > Transactions de paiement du domaine comptabilité fournisseur
- Client > Société > Transactions de paiement du domaine comptabilité client

Notez que les entités commerciales (par exemple, les transactions de paiement et la société) sont conçues en une fois. Différents mappages permettent de les réutiliser.

Un mappage de modèle qui prend en charge les documents électroniques sortants a les fonctionnalités suivantes :

- Il peut utiliser les différents types de données Dynamics 365 for Operations comme sources de données pour un modèle de données. Par exemple, il peut utiliser des enums, des entités de données, des méthodes ou des tables.
- Il prend en charge les paramètres d'entrée utilisateur qui peuvent être définies comme sources de données pour un modèle de données lorsque certaines données doivent être spécifiées au moment de l'exécution.
- Il prend en charge la transformation des données Dynamics 365 Operations en groupes requis. Il permet également de filtrer, de trier et d'ajouter des données, ainsi que des champs calculés logiques qui sont conçus via les formules qui sont semblables aux formules de Microsoft Excel, comme le montre l'illustration suivante. Pour plus d'informations, voir [Concepteur de formule dans les états électroniques](general-electronic-reporting-formula-designer.md).

[![Concepteur de formule](./media/ER-overview-01.png)](./media/ER-overview-01.png) 

Un mappage de modèle qui prend en charge les documents électroniques entrants a les fonctionnalités suivantes :

- Il peut utiliser les objets de données Dynamics 365 for Operations pouvant être mis à jour en tant que cibles. Ces éléments de données incluent des tables, des entités de données et des vues. Les données peuvent être mises à jour à l'aide des données issues de documents électroniques entrants. Plusieurs cibles peuvent être utilisées dans un mappage de modèle unique.
- Il prend en charge les paramètres d'entrée utilisateur qui peuvent être définies comme sources de données pour un modèle de données lorsque certaines données doivent être spécifiées au moment de l'exécution.
Un composant de modèle de données est conçu pour chaque domaine d'activité qui devrait être utilisé comme une source de données unifiée pour les rapports qui isolent les rapports de l'implémentation physique des sources de données Dynamics 365 for Operations. Il représente des concepts et des fonctionnalités d'entreprise spécifiques au domaine sous une forme qui rend la conception d'origine du format de rapport et toute autre maintenance plus efficaces.

#### <a name="format-components-for-outgoing-electronic-documents"></a>Composants de format pour les documents électroniques sortants

Un composant de format est le modèle utilisé pour la sortie générée au moment de l'exécution. Un modèle se compose des éléments suivants :

- un format qui définit la structure et le contenu d'un document électronique sortant généré au moment de l'exécution ;
- des sources de données, en tant qu'ensemble de paramètres d'entrée utilisateur et de modèle de données spécifique au domaine avec la mise en correspondance du modèle sélectionnée ;
- une mise en correspondance de format, en tant qu'ensemble de liaisons des sources de données de format avec des éléments individuels de format qui spécifient au moment de l'exécution le flux de données et les règles de génération de sortie de format ;
- une validation de format en tant qu'ensemble de règles configurables qui contrôlent la génération d'états au moment de l'exécution en fonction du contexte d'exécution. Par exemple, il peut y avoir une règle qui arrête la génération de sortie des paiements d'un fournisseur et lance une exception lorsque des attributs spécifiques du fournisseur sélectionné sont manquants, comme le numéro de compte bancaire.

Un composant de format prend en charge les fonctions suivantes :

- La création de sortie de rapports en tant que fichiers individuels dans différents formats, tels que texte, XML, document Microsoft Word ou feuille de calcul.
- Création de plusieurs fichiers séparément et encapsulation de ces fichiers dans des fichiers zip.

Un composant de format vous permet de joindre certains fichiers pouvant être utilisés dans la sortie d'états :

- des classeurs Excel qui contiennent une feuille de calcul qui peut être utilisée comme modèle pour les sorties au format de feuille de calcul OPENXML ;
- des fichiers Word qui contiennent un document qui peut être utilisé comme modèle pour les sorties au format de document Microsoft Word
- d'autres fichiers pouvant être incorporés à la sortie du format en tant que fichiers prédéfinis.

L'illustration ci-dessous indique les flux de données pour ces formats.

[![Flux de données des composants de format sortants](./media/ER-overview-02.png)](./media/ER-overview-02.png)

Pour exécuter une configuration de format de génération d'états électroniques unique et générer un document électronique sortant, vous devez identifier le mappage de la configuration de format.

#### <a name="format-components-for-incoming-electronic-documents"></a>Composants de format pour les documents électroniques entrants
Un composant de format est le modèle de document entrant qui est importé au moment de l'exécution. Un modèle se compose des éléments suivants :

- Un format qui définit la structure et le contenu d'un document électronique entrant contenant des données qui sont importées au moment de l'exécution. Un composant de format est utilisé pour analyser un document entrant dans différents formats : texte et XML.
- Un mappage des formats qui lie les éléments de format individuels aux éléments d'un modèle de données spécifique au domaine. Au moment de l'exécution, les éléments du modèle de données spécifient le flux de données et les règles pour importer les données d'un document entrant, puis stockent les données dans un modèle de données.
- Une validation de format en tant qu'ensemble de règles configurables qui contrôlent l'importation de données au moment de l'exécution en fonction du contexte d'exécution. Par exemple, il peut y avoir une règle qui empêche l'importation de données d'un relevé bancaire contenant des paiements d'un fournisseur et lance une exception lorsque les attributs d'un fournisseur spécifique sont manquants, comme le code d'identification du fournisseur.

L'illustration ci-dessous indique les flux de données pour ces formats.

[![Flux de données des composants de format entrants](./media/ER-overview-03.png)](./media/ER-overview-03.png)

Pour exécuter une configuration simple de format de génération d'états électroniques pour importer les données d'un document électronique entrant, vous devez identifier le mappage souhaité d'une configuration de format, ainsi que le point d'intégration d'un mappage de modèle. Vous pouvez utiliser les mêmes mappages et destinations de modèles avec différents formats pour différents types de documents entrants.

#### <a name="component-versioning"></a>Contrôle de versions du composant

Le contrôle de versions est pris en charge pour les composants d'états électroniques. Le workflow suivant est fourni pour gérer et sauvegarder les modifications dans les composants d'états électroniques :

1. La version qui est créée est marquée comme étant une version en mode **Brouillon**. Cette version peut être modifiée et est disponible pour des séries de tests.
2. La version **Brouillon** peut être convertie en une version **Terminée**. Cette version peut être utilisée dans les processus de création d'états locaux.
3. La version **Terminée** peut être convertie en une version **Partagée**. Cette version est publiée sur LCS et peut être utilisée dans le processus de création de rapports globaux.
4. La version **Partagée** peut être convertie en une version **Interrompue**. Cette version peut ensuite être supprimée.

Les versions dotées du statut **Terminée** ou **Partagée** sont disponibles pour un autre échange de données. Les actions suivantes peuvent être exécutées sur un composant possédant ces statuts :

- Le composant peut être sérialisé au format XML et exporté vers un fichier au format XML à partir de Dynamics 365 for Operations.
- Le composant peut être resérialisé à partir d’un fichier XML et importé dans Dynamics 365 for Operations sous la forme d’une nouvelle version d’un composant d'état électronique.

#### <a name="component-date-effectivity"></a>Validité de date du composant

Les versions du composant d'état électronique est soumis à une date d'effet. Vous pouvez définir la date **Prend effet le** pour un composant d'état électronique afin de spécifier la date à partir de laquelle ce composant devient valide pour les processus de génération d'états. La date de session de Microsoft Dynamics 365 for Operations permet de définir si un composant est valide pour l'exécution. Lorsque plusieurs versions sont valides pour une date spécifique, la version la plus récente est utilisée pour le processus de génération d'états.

#### <a name="component-access"></a>Accès au composant

L'accès aux composants de format d'états électroniques dépend du paramètre du code de pays/région ISO. Lorsque ce paramètre est vide pour une version sélectionnée d’une configuration de format, un composant de format est accessible à partir de n’importe quelle société Dynamics 365 for Operations au moment de l’exécution. Lorsqu'il contient des codes pays/région ISO, un composant de format est disponible uniquement à partir des sociétés Dynamics 365 for Operations dont l'adresse principale est défini pour l'un des codes pays/régions ISO du composant de format.

Différentes versions d'un composant de format de données peuvent avoir différents paramètres de codes pays/région ISO.

#### <a name="configuration"></a>Configuration

Une configuration de la génération d'états électroniques est le wrapper d'un composant de génération d'états électroniques particulier. Ce composant peut être un composant du modèle de données ou un composant de format. Une configuration peut inclure différentes versions d'un composant d'état électronique. Chaque configuration est marquée comme possédée par un fournisseur de configuration spécifique. La version **Brouillon** d'un composant d'une configuration peut être modifiée lorsque le propriétaire d'une configuration a été sélectionné comme fournisseur actif dans les paramètres d'états électroniques de Dynamics 365 for Operations.

Chaque configuration de modèle contient un composant de modèle de données. Une nouvelle configuration de format peut être dérivée d'une configuration de modèle de données spécifique. Dans l'arborescence de configuration, la configuration de format qui est créée apparaît en tant qu’enfant de la configuration de modèle de données d’origine.

La configuration de format qui est créée contient un composant de format. Le composant de modèle de données de cette configuration de modèle d'origine est automatiquement inséré dans le composant de format de la configuration de format enfant comme source de données par défaut.

Une configuration d'état électronique est partagée pour les sociétés de Dynamics 365 for Operations.

#### <a name="provider"></a>Fournisseur

Le fournisseur d'états électroniques est l'identificateur de partie utilisé pour indiquer l'auteur (propriétaire) de chaque configuration d'état électronique. L'état électronique vous permet de gérer la liste des fournisseurs de configuration. Les configurations de format émises pour les documents électroniques dans le cadre de la solution Dynamics 365 for Operations sont marquées comme détenues par le fournisseur de configuration **Microsoft**.

Pour savoir comment enregistrer un nouveau fournisseur d'états électroniques, consultez le Guide de tâche, **Génération d'états électroniques - Créer un fournisseur de configuration et le marquer comme actif** (qui fait partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**).

#### <a name="repository"></a>Référentiel

Un référentiel d'états électroniques enregistre les configurations d'états électroniques. Deux types de référentiels d'états électroniques suivants sont actuellement pris en charge : **Ressources opérationnelles** et **Projet LCS**.

Un référentiel **Ressources opérationnelles** permet d'accéder à la liste des configurations que Microsoft, en tant que fournisseur de configurations d'états électroniques, livre dans le cadre de la solution Dynamics 365 for Operations. Ces configurations peuvent être importées dans l’instance actuelle de Dynamics 365 for Operations et utilisées pour l'état électronique. Elles peuvent également être utilisées pour des localisations et personnalisations.

Un référentiel de **projet LCS** permet d'accéder à la liste des configurations d'un projet LCS spécifique (bibliothèque d'actifs de projet LCS) sélectionné à l'enregistrement du référentiel. Les états électroniques vous permettent de télécharger des configurations partagées de l'instance Dynamics 365 for Operations actuelle vers un référentiel **Projet LCS** donné. Vous pouvez également importer des configurations depuis un référentiel **Projet LCS** vers l'instance Dynamics 365 for Operations actuelle.

Les référentiels **Projet LCS** requis peuvent être enregistrés individuellement pour chaque fournisseur de configuration de l'instance Dynamics 365 for Operations actuelle. Chaque référentiel peut être consacré à un fournisseur de configuration spécifique.

## <a name="supported-scenarios"></a>Scénarios pris en charge
### <a name="building-a-data-model"></a>Élaboration d'un modèle de données

L'état électronique propose un concepteur de modèle vous permettant de créer un modèle de données pour un domaine de l'entreprise donné. Toutes les entités commerciales spécifiques à un domaine et les relations entre elles peuvent être présentées dans un modèle de données en tant que structure hiérarchique. L’illustration suivante montre un exemple de ce type de modèle de données (le modèle de données du domaine de paiement). 

[![Modèle de données de domaine de paiement](./media/ER-overview-04.png)](./media/ER-overview-04.png)

Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Concevoir un modèle de données spécifiques au domaine** (qui fait partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)** .

### <a name="translating-data-model-content"></a>Traduction du contenu du modèle de données

Le contenu du modèle de données (étiquettes et descriptions) peut être traduit dans d'autres langues prises en charge par Finance and Operations. Vous souhaitez peut-être traduire le contenu du modèle de données pour les raisons suivantes :

-   Au moment de la conception, pour rendre le contenu plus intelligible aux concepteurs de format parlant une langue étrangère qui utilisent le modèle de données pour la mise en correspondance des données des composants de format.
-   Au moment de l'exécution, pour rendre le contenu plus convivial pour la présentation des invites et de l'aide pour les paramètres d'exécution ainsi que des messages de validation configurés (erreurs et avertissements) dans la langue que l'utilisateur actuellement connecté préfère.

L’illustration suivante montre un exemple de la traduction du contenu du modèle de données de l’anglais vers le japonais. 

[![Contenu du modèle de données en anglais](./media/ER-overview-05.png)](./media/ER-overview-05.png)

[![Contenu du modèle de données traduit en japonais](./media/ER-overview-06.png)](./media/ER-overview-06.png)


### <a name="configuring-data-model-mappings-for-outgoing-documents"></a>Configuration des mappages de modèle de données pour les documents sortants

L'état électronique fournit un concepteur de mise en correspondance de modèle qui permet aux utilisateurs de mapper des modèles de données qu'ils ont conçus pour des sources de données Finance and Operations spécifiques. Selon le mappage, les données seront importées au moment de l'exécution des sources de données sélectionnées dans le modèle de données. Le modèle de données est ensuite utilisé comme une source de données abstraite des formats de génération d'états électroniques qui créent les documents électroniques sortants. L'illustration suivante présente un exemple de ce type de mise en correspondance de modèle de données (mise en correspondance du modèle **Virement SEPA** avec le modèle de données du domaine de paiement). 

[![Exemple de mise en correspondance de modèle de données](./media/ER-overview-07.png)](./media/ER-overview-07.png)

Pour vous familiariser avec ce scénario en détails, visionnez les guides de tâche **ER Définir le mappage de modèles et sélectionner des sources de données** et **ER Mapper le modèle de données aux sources de données sélectionnées** (qui font partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**).

### <a name="configuring-data-model-mappings-for-incoming-documents"></a>Configuration des mappages de modèle de données pour les documents entrants
L'état électronique fournit un concepteur de mise en correspondance de modèle qui permet aux utilisateurs de mapper des modèles de données qu'ils ont conçus pour des destinations spécifiques. Par exemple, des modèles de données peuvent être mappés aux composants Dynamics 365 for Operations pouvant être mis à jour (tables, entités de données et vues). Selon le mappage, les données Dynamics 365 for Operations sont mises à jour au moment de l'exécution à l'aide des données du modèle de données. Pour un stockage abstrait du format de génération d'états électroniques, le modèle de données contient les données importées depuis un document électronique entrant. L’illustration suivante montre un exemple de ce type de mappage de modèle de données. Dans cet exemple, le mappage de modèle **Mappage d'importation pour NETS** du domaine de paiement est utilisé pour prendre en charge l'importation des relevés bancaires au format de banque NETS de la Norvège.

[![Exemple de modèle de données de mappage d'importation pour NETS](./media/ER-overview-08.png)](./media/ER-overview-08.png)

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>Stockage du composant de modèle conçu en tant que modèle de configuration

ER peut stocker un modèle de données conçu avec des mises en correspondance de données associées en tant que configuration de modèle de l'instance actuelle Finance and Operations. L’illustration suivante montre un exemple de ce type de configuration de modèle de données (la configuration du modèle de paiement). 

Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Mapper le modèle de données aux sources de données sélectionnées** (qui fait partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)** .

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Élaboration d'un format qui utilise un modèle de données en tant que base

ER prend en charge un concepteur de format que vous pouvez utiliser pour élaborer le format d'un document électronique pour le domaine d'entreprise en sélectionné d'affaires en sélectionnant le composant modèle comme base. Le même concepteur de format ER vous permet de mettre en correspondance un format créé et la mise en correspondance du modèle de données du domaine sélectionné comme source de données. L’illustration suivante montre un exemple de ce type de format (la configuration du format qui prend en charge le format de paiement **BACS** pour le Royaume-Uni). 

[![Exemple d'un format qui utilise un modèle de données en tant que base](./media/ER-overview-09.png)](./media/ER-overview-09.png)

Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Concevoir un format spécifique au domaine** (qui fait partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)** .

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Création d'une configuration pour générer des documents électroniques au format de feuille de calcul OPENXML

Le concepteur de format ER peut être utilisé pour générer un document électronique particulier au format de feuille de calcul OPENXML. L’illustration suivante montre un exemple de ce type de format (configuration de format permettant de générer une feuille de calcul OPENXML avec les détails d’un journal des paiements sélectionné).

[![Pic-ER-format-Excel](./media/ER-overview-10.png)](./media/ER-overview-10.png)

Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Créer une configuration pour des états au format OPENXML** (qui fait partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**). Dans le cadre de l'étape du guide de tâche pour importer un modèle, utilisez le fichier Excel [Modèle d'état de paiement (SampleVendPaymWsReport.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202) en tant que modèle.

### <a name="building-a-configuration-to-generate-electronic-documents-in-a-word-document-format"></a>Création d'une configuration pour générer des documents électroniques au format de document Word
Le concepteur de format ER peut être utilisé pour générer un document électronique particulier au format de document Word. L’illustration suivante montre un exemple de ce type de format. Notez que ce format réutilise la configuration ER existante qui a été conçue initialement pour générer la sortie d'état au format OPENXML.

[![Pic-ER-format-Word](./media/ER-overview-11.png)](./media/ER-overview-11.png)

Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche ER Concevoir une configuration pour générer des états au format Microsoft WORD (qui fait partie du processus d'entreprise 7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)). Dans le cadre de l'étape du guide de tâche pour importer un modèle, utilisez les fichiers Word suivants en tant que modèles pour le format ER :

- [Modèle d'état de paiement (SampleVendPaymDocReport.docx)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Modèle lié d'état de paiement (SampleVendPaymDocReportBounded.docx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="building-a-configuration-to-import-data-from-incoming-electronic-documents"></a>Génération d'une configuration pour importer les données des documents électroniques entrants  
Le concepteur de format ER peut servir à décrire un document électronique planifié pour l'importation de données au format XML ou texte. Le format conçu permet d'analyser un document entrant. Le concepteur de mappage des formats ER permet de définir la liaison des éléments du format conçu au modèle de données. Les illustrations suivantes montrent un exemple de ce type de format et de mappage de format. Dans cet exemple, des relevés bancaires NETS qui incluent des informations de paiement fournisseur au format texte sont importés.

[![ER-format-designer](./media/ER-overview-12.png)](./media/ER-overview-12.png)

[![ER-model-mapping-designer](./media/ER-overview-13.png)](./media/ER-overview-13.png)

Pour vous familiariser avec ce scénario en détails, consultez le guide de tâche ER Créer des configurations pour importer des données d'un fichier externe (qui fait partie du processus d'entreprise 7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)). Les fichiers suivants pour lire le présent guide :

- [Configuration du modèle de données ER (1099model.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Configuration du format ER (1099format.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Exemple du document entrant au format XML (1099entries.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Exemple du classeur pour gérer les données du document entrant (1099entries.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Stockage d'un composant de format conçu dans une configuration de format

ER peut stocker un format conçu avec des mises en correspondance de données configurées en tant que configuration de format de l'instance actuelle Finance and Operations. L’illustration ci-dessus montre un exemple de ce type de configuration de format (**BACS (Royaume-Uni)**, qui est un enfant de la configuration **Modèle de paiement**). Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Concevoir un format spécifique au domaine** (qui fait partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)** .

### <a name="configuring-finance-and-operations-to-start-to-use-a-created-format-internally"></a>Configuration de Finance and Operations pour utiliser le format créé en interne

Vous pouvez configurer Finance and Operations pour utiliser le format créé pour générer des états électroniques. La référence à la configuration de format créé doit être définie dans les paramètres d'un domaine particulier. Par exemple, pour commencer à utiliser une configuration de format ER pour les paiements fournisseur électroniques au format BACS, la configuration de format doit être référencée dans des modes de paiement spécifiques, comme indiqué dans les illustrations suivantes : 

[![Format de la configuration BACS (Royaume-Uni)](./media/ER-overview-14.png)](./media/ER-overview-14.png)

[![Référencement du format BACS (Royaume-Uni) dans un mode de paiement](./media/ER-overview-15.png)](./media/ER-overview-15.png)

Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Utiliser le format pour générer un document électronique pour les paiements** (qui fait partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**).

## <a name="handling-er-components"></a>Gestion des composants ER
### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>Publication d'un composant ER dans LCS pour l'offrir en externe (localisation)

Le propriétaire d'un composant (modèle ou format) qui a été créé peut utiliser ER pour publier la version terminée du composant vers LCS. Un référentiel de type **Projet LCS** pour le fournisseur de configuration ER actuel est requis. Lorsque le statut de la version terminée d'un composant est modifié pour passer de **TERMINÉE** à **PARTAGÉE**, cette version est publiée dans LCS. Lorsqu'un composant a été publié vers LCS, le propriétaire de ce composant devient un fournisseur du service permettant de prendre en charge ce composant. Par exemple, si le composant de format est conçu pour générer un document électronique légalement requis (par exemple, conformément au scénario de localisation), ce service suppose que ce format reste conforme aux modifications législatives et le fournisseur émet de nouvelles versions du composant dès que de nouvelles exigences législatives doivent être prises en charge. Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Charger une configuration dans Lifecycle Services**(qui fait partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**).

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>Importation du composant ER depuis LCS pour l'utiliser en interne

ER vous permet d’importer des composants ER à partir de LCS vers l’instance actuelle de Finance and Operations. Un référentiel de type **Projet LCS** est requis. Lorsqu'un composant ER a été importé de LCS vers l'instance actuelle Finance and Operations, le propriétaire de l'instance Dynamics AX devient un consommateur du service fourni par le propriétaire (auteur) du composant importé. Par exemple, si un composant de format est conçu pour générer à partir de Finance and Operations un document électronique donné dans un format spécifique à un pays/région particulier (scénario de localisation), cette consommation de service suppose la possibilité d'obtenir les mises à jour de ce format afin qu'il demeure conforme aux exigences législatives. Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Charger une configuration à partir de Lifecycle Services** (qui fait partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**).

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Élaboration d'un format en sélectionnant un autre format en tant que base (personnalisation)

ER vous permet de que créer (dériver) un nouveau composant à partir de la version actuelle d’un composant (base) qui a été importé à partir de LCS. Par exemple, un utilisateur souhaite dériver un nouveau format pour mettre en œuvre une configuration spécifique pour un document électronique (par exemple, un champ supplémentaire ou une description complète) pour prendre en charge un scénario de personnalisation. Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Mettre à niveau le format par adoption d'une nouvelle version de base** (qui fait partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**).

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Mise à niveau d'un format en sélectionnant une nouvelle version du format de base (redéfinir)

ER vous permet d'adopter automatiquement les modifications de la version la plus récente du composant de base dans la version brouillon actuelle du composant dérivé. Ce processus est appelé *redéfinition de la base*. Par exemple, une nouvelle modification réglementaire (introduite dans la version la plus récente du composant de format importé depuis LCS) peut être automatiquement fusionnée dans la propre version personnalisée de ce format de document électronique. Toutes les modifications qui ne peuvent pas être fusionnées automatiquement sont considérées comme des conflits. Ces conflits sont présentés pour une résolution manuelle dans l’outil de concepteur pour le composant approprié. Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Mettre à niveau le format par adoption d'une nouvelle version de base** (qui fait partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**).

## <a name="list-of-er-configurations-that-are-delivered-in-the-finance-and-operations-solution"></a>Liste de configurations ER qui sont fournies dans la solution de Finance and Operations
| Configurations de modèles de données spécifiques au domaine : titre | Domaine                | Configurations de format en fonction du modèle de données : titre | Description                                                        |
|--------------------------------------------------|-----------------------|---------------------------------------------------|--------------------------------------------------------------------|
| Modèle de fichier d'audit                                 | Audit financier       |                                                   |                                                                    |
|                                                  |                       | Fichier d'audit (P.-B.)                                   | Format de fichier d'audit pour les Pays-Bas                                  |
| Modèle BAS                                        | Déclaration de taxe         |                                                   |                                                                    |
|                                                  |                       | BAS (AU)                                          | Format BAS pour l'Australie                                           |
| Modèle de l'industrie de la construction               | Déclaration de taxe         |                                                   |                                                                    |
|                                                  |                       | Retour mensuel CIS (Royaume-Uni)                           | Format de retour mensuel CIS pour le Royaume-Uni                   |
| Modèle de lettre de relance                          | Factures électroniques  |                                                   |                                                                    |
|                                                  |                       | Lettre de relance OIOUBL (Danemark)                     | Format de lettre de relance OIOUBL pour le Danemark                        |
| Modèle de comptabilité électronique (Mexique)          | Déclaration de taxe         |                                                   |                                                                    |
|                                                  |                       | XML de comptabilité auxiliaire (Mexique)                         | Transactions de grand livre auxiliaire par format d'état de compte pour le Mexique |
|                                                  |                       | XML de plan de comptes (Mexique)                         | Graphique du format d'état de compte pour le Mexique                          |
|                                                  |                       | XML de journaux (Mexique)                                 | Format d'états de transactions de journal pour le Mexique                      |
|                                                  |                       | XML de balance comptable (Mexique)                            | Format d'état de balance comptable pour le Mexique                             |
| Modèle Elster                                     | Déclaration de taxe         |                                                   |                                                                    |
|                                                  |                       | Elster (Allemagne)                                       | Format ELSTER pour l’Allemagne                                          |
| Modèle de liste des ventes intracommunautaires                              | États commerciaux       |                                                   |                                                                    |
|                                                  |                       | Liste des ventes intracommunautaires (Allemagne)                                | Format TXT de liste des ventes intracommunautaires pour l'Allemagne                               |
|                                                  |                       | Liste des ventes intracommunautaires (Danemark)                                | Format TXT de liste des ventes intracommunautaires pour le Danemark                               |
|                                                  |                       | Liste des ventes intracommunautaires (France)                                | Format XML de liste des ventes intracommunautaires pour la France                                |
|                                                  |                       | Liste des ventes intracommunautaires (P.-B.)                                | Format XML pour la liste des ventes intracommunautaires pour les Pays-Bas                           |
|                                                  |                       | TXT pour la liste des ventes intracommunautaires (R.-U.)                            | Format TXT de liste de ventes intracommunautaires pour le Royaume-Uni                    |
|                                                  |                       | XML pour la liste des ventes intracommunautaires (R.-U.)                            | Format XML de liste de ventes intracommunautaires pour le Royaume-Uni                    |
|                                                  |                       | État Liste des ventes intracommunautaires par colonnes                   | État Liste des ventes intracommunautaires par colonnes                                    |
|                                                  |                       | État Liste des ventes intracommunautaires par lignes                      | État Liste des ventes intracommunautaires par lignes                                       |
| Modèle de comptabilité FEC (FR)                        | Déclaration de taxe         |                                                   |                                                                    |
|                                                  |                       | XML de données comptables FEC (France)                      | Format XML d’exportation des données comptables FEC pour la France                   |
| Fichier d'audit allemand                                | Audit financier       |                                                   |                                                                    |
|                                                  |                       | Sortie du fichier d'audit allemand                          | Sortie du fichier d'audit pour l’Allemagne et l’Autriche                          |
| Modèle de déclaration d'échanges de biens                                  | États commerciaux       |                                                   |                                                                    |
|                                                  |                       | Déclaration d'échanges de biens (Allemagne)                                    | Format de déclaration d'échanges de biens pour l’Allemagne                                       |
|                                                  |                       | Déclaration d'échanges de biens (Danemark)                                    | Format de déclaration d'échanges de biens pour le Danemark                                       |
|                                                  |                       | Format INTRACOM pour la déclaration d'échanges de biens (FR)                           | Format INTRACOM pour la déclaration d'échanges de biens pour la France                               |
|                                                  |                       | Format SAISUNIC pour la déclaration d'échanges de biens (FR)                           | Format SAISUNIC pour la déclaration d'échanges de biens pour la France                               |
|                                                  |                       | Déclaration d'échanges de biens (P.-B.)                                    | Format de déclaration d'échanges de biens pour les Pays-Bas                               |
|                                                  |                       | Déclaration d'échanges de biens (R.-U.)                                    | Format de déclaration d'échanges de biens pour le Royaume-Uni                            |
|                                                  |                       | État de déclaration d'échanges de biens                                  | État de contrôle Excel pour la déclaration d'échanges de biens                                     |
| Modèle de facture client                           | Factures électroniques  |                                                   |                                                                    |
|                                                  |                       | Avoir de projet OIOUBL (Danemark)                   | Format d'avoir de projet OIOUBL pour le Danemark                      |
|                                                  |                       | Facture de projet OIOUBL (Danemark)                       | Format de facture de projet OIOUBL pour le Danemark                          |
|                                                  |                       | Avoir sur vente OIOUBL (Danemark)                     | Format d'avoir sur vente OIOUBL pour le Danemark                        |
|                                                  |                       | Facture de vente OIOUBL (Danemark)                         | Format de facture de vente de OIOUBL pour le Danemark                            |
| Modèle de déclaration OB                             | Déclaration de taxe         |                                                   |                                                                    |
|                                                  |                       | Déclaration OB (P.-B.)                               | Format de déclaration OB pour les Pays-Bas.                          |
| Modèle de paiement                                    | Paiements              |                                                   |                                                                    |
|                                                  |                       | Betalingsservice (DK)                             | Format de paiement Betalingsservice pour le Danemark                        |
|                                                  |                       | Remise d'une lettre de change (France)                  | Format de remise de lettre de change pour la France                      |
|                                                  |                       | BTL91 (P.-B.)                                        | Format de paiement fournisseur BTL91 pour les Pays-Bas                    |
|                                                  |                       | Prélèvements CFONB (FR)                           | Format de paiement de débit direct CFONB pour la France                       |
|                                                  |                       | Virements CFONB (FR)                              | Format de paiement de fournisseur local CFONB pour la France                    |
|                                                  |                       | Fournisseur Nordea (Danemark)                                | Format de paiement de fournisseur Nordea Corporate Netbank pour le Danemark         |
|                                                  |                       | Service de crédit direct ANZ (Australie)                    | Format de service de crédit direct ANZ pour l’Australie                 |
|                                                  |                       | Service de crédit direct CBA (Australie)                    | Format de service de crédit direct CBA pour l’Australie                 |
|                                                  |                       | Service de crédit direct NAB (Australie)                    | Format de service de crédit direct NAB pour l’Australie                 |
|                                                  |                       | Service de crédit direct STG (Australie)                    | Format de service de crédit direct STG pour l’Australie                 |
|                                                  |                       | Système de saisie directe WBC (Australie)                      | Format de système de saisie directe WBC pour l’Australie                   |
|                                                  |                       | DirectLink (Nouvelle-Zélande)                                   | Format DirectLink pour la Nouvelle-Zélande                              |
|                                                  |                       | Fichier de paiement JBA (Japon)                             | Format de paiement de JBA pour le Japon                                       |
|                                                  |                       | Virement ISO20022                          | Format de virement SEPA pour l’Europe                             |
|                                                  |                       | Virement ISO20022 (France)                     | Format de virement SEPA pour la France                             |
|                                                  |                       | Virement ISO20022 (Allemagne)                     | Format de virement SEPA pour l'Allemagne                            |
|                                                  |                       | Virement ISO20022 (P.-B.)                     | Format de virement SEPA pour les Pays-Bas                    |
|                                                  |                       | Débit direct ISO20022                             | Format de débit Direct SEPA pour l’Europe                                |
|                                                  |                       | Débit direct ISO20022 (France)                        | Format de débit direct SEPA pour la France                                |
|                                                  |                       | Débit direct ISO20022 (Allemagne)                        | Format de débit Direct SEPA pour l’Allemagne                               |
|                                                  |                       | Débit direct ISO20022 (P.-B.)                        | Format de débit direct SEPA pour les Pays-Bas                       |
|                                                  |                       | BACS (ROYAUME-UNI)                                         | Format de paiement fournisseur BACS pour le Royaume-Uni                  |
| Taxe au preneur                                   | Déclaration de taxe         |                                                   |                                                                    |
|                                                  |                       | Liste des ventes soumises à la taxe au preneur                         | Format de liste des ventes soumises à la taxe au preneur                                   |
| Modèle d'intégration XBRL néerlandais                     | Déclaration XBRL        |                                                   |                                                                    |
|                                                  |                       | Semansys XBRL (P.-B.)                                | Format d’exportation Semansys XBRL pour les Pays-Bas                    |
| Modèle GAF (Malaisie)                                   | Audit financier       |                                                   |                                                                    |
|                                                  |                       | Fichier GAF (Malaisie)                                     | Format de GAF pour la Malaisie                                         |
| Balance âgée des fournisseurs (Chine)                         | Analyse de données de fournisseurs |                                                   |                                                                    |
|                                                  |                       | Format de balance âgée des fournisseurs (Chine)                   | Format de balance âgée des fournisseurs pour la Chine                               |
| Modèle de déclaration de facture fournisseur                 | Analyse de données de fournisseurs |                                                   |                                                                    |
|                                                  |                       | Déclaration de facture fournisseur (Islande)                   | Format de déclaration de facture fournisseur pour l'Islande                      |
|                                                  |                       | État des déclarations de facture fournisseur (Islande)            | État de déclaration de facture fournisseur pour l'Islande                      |



<a name="see-also"></a>Voir également :
--------

[Exigences de localisation – créer une configuration de génération d’états électroniques](electronic-reporting-configuration.md)

[Gérer le cycle de vie de la configuration des états électroniques](general-electronic-reporting-manage-configuration-lifecycle.md)




