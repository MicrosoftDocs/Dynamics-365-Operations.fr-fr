---
title: "Vue d&quot;ensemble des États électroniques"
description: "Cet article fournit une vue d&quot;ensemble de l&quot;outil de gestion des états électroniques (ER). Il comporte des informations sur les concepts essentiels, les scénarios pris en charge par l&quot;ER et une liste des formats conçus et lancés dans le cadre de la solution."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: b3e8174d07c9b9fd4210486c369c640fe07c49eb
ms.lasthandoff: 03/31/2017


---

# <a name="electronic-reporting-overview"></a>Vue d'ensemble des États électroniques

Cet article fournit une vue d'ensemble de l'outil de gestion des états électroniques (ER). Il comporte des informations sur les concepts essentiels, les scénarios pris en charge par l'ER et une liste des formats conçus et lancés dans le cadre de la solution.

États électroniques est un outil que vous pouvez utiliser pour configurer les formats de documents électroniques conformément aux exigences légales des différents pays/régions. Il vous permet de gérer ces formats au cours de leur cycle de vie. Par exemple, vous pouvez adopter de nouvelles exigences réglementaires et vous pouvez générer des documents commerciaux au format requis pour échanger des informations avec les organismes publics, les banques et d'autres parties par voie électronique. Le moteur d'états électroniques est destiné aux utilisateurs professionnels, plutôt qu'aux développeurs. Étant donné que vous configurez des formats, pas du code, les processus de création et d’ajustement des formats pour les documents électroniques sont plus rapides et plus faciles. Les états électroniques prennent actuellement en charge les formats de feuille de calcul texte, XML et OPENXML. Toutefois, une interface d’extension prend en charge plus de formats.

## <a name="capabilities"></a>Capacités
Le moteur d'états électroniques est doté des fonctionnalités suivantes :

-   Il est un outil commun unique pour la génération d'états électronique dans différents domaines, et remplace plus de 20 moteurs différents qui effectuent un certain type de déclaration électronique pour Microsoft Dynamics 365 pour les opérations.
-   Il fait le format d'un rapport isolé actuel de Dynamics 365 pour l'implémentation d'opérations. (Autrement dit, le format s'applique pour différentes versions de Dynamics 365 pour les opérations.)
-   Il prend en charge la création d’un format personnalisé qui est basé sur un format d’origine. Il inclut des fonctionnalités permettant de mettre à niveau automatiquement le format personnalisé lorsque des modifications sont apportées au format d’origine du fait que des spécifications de localisation/personnalisation sont introduites.
-   Il devient l'outil standard principal pour prendre en charge les exigences de localisation dans les états électroniques, pour Microsoft ainsi que pour les partenaires de Microsoft.
-   Il prend en charge la capacité à distribuer des formats aux partenaires et aux clients via Microsoft Dynamics Lifecycle Services (LCS).

## <a name="concepts"></a>Concepts
### <a name="components"></a>Composants

Les états électroniques prennent en charge deux types de composants : **Modèle de données **et **Format**.

#### <a name="data-model-components"></a>Composants de modèle de données

Un composant de modèle de données est une représentation abstraite de la structure de données à utiliser pour décrire un domaine de l'entreprise donné avec suffisamment de détails pour répondre aux exigences de génération d'états dans ce domaine. Un composant de modèle de données se compose des éléments suivants :

-   un modèle de données en tant qu'ensemble d'entités commerciales spécifiques au domaine, ainsi qu'une définition hiérarchiquement structurée des relations entre elles ;
-   Une mise en correspondance modèle qui relie la a sélectionné Dynamics 365 pour les sources de données d'opérations à différents éléments d'un modèle de données qui spécifie, au moment de l'exécution, le flux de données et les règles de la population de données commerciales à un composant de modèle de données.

Une entité commerciale de modèle de données est représentée comme un conteneur (enregistrement). Les propriétés d'entité commerciale sont représentées comme des articles de données (champs). Chaque article de données est doté d'un nom, d'un libellé, d'une description et d'une valeur uniques. La valeur de chaque élément de données peut être conçu de sorte qu’il soit reconnu comme une chaîne, entier, réel, date, type enumerate, booléen et ainsi de suite. En outre, il peut s'agir d'un autre enregistrement ou d'une liste d'enregistrements. Un composant de modèle de données unique peut contenir plusieurs hiérarchies d'entités commerciales spécifiques à un domaine, ainsi que des mises en correspondance de modèles pour prendre en charge un flux de données particulier à un état spécifique au moment de l'exécution. Les hiérarchies sont différenciées par un enregistrement unique sélectionné comme racine de la mise en correspondance de modèle. Par exemple, le modèle de données du domaine du paiement peut prendre en charge les mises en correspondance suivantes :

-   Société -&gt; transactions&gt; de paiement fournisseur du domaine d'Achats
-   Client -&gt; société -&gt; transactions de paiement du domaine de Ventes

Notez que les entités commerciales (par exemple, les transactions de paiement et la société) sont conçues en une fois. Différents mappages permettent de les réutiliser. Un mappage de modèle possède les fonctionnalités suivantes :

-   Il peut utiliser Dynamics autre 365 pour les types de données d'opérations comme source de données pour un modèle de données. Par exemple, il peut utiliser des enums, des entités de données, des méthodes ou des tables.
-   Il prend en charge les paramètres d'entrée utilisateur qui peuvent être définies comme sources de données pour un modèle de données lorsque certaines données doivent être spécifiées au moment de l'exécution.
-   Il prend en charge la transformation de Dynamics 365 pour les données d'opérations en groupes requis, le filtrage, tri, et la somme des données, ainsi que l'ajout avec les champs calculés logiques qui sont conçus via les formules comme Excel Microsoft (pour plus de détails, voir [Concepteur de formule de génération d'états électronique] (general-electronic-reporting-formula-designer.md)).

[éditeur comme Excel de formule![] (. /media/pic-formula-1024x615.png)](. Le composant de modèle de données /media/pic-formula.png) A est conçu pour chaque domaine d'entreprise à utiliser comme source de données unifiée pour déclarer cette des isolats génération d'états de l'implémentation physique de Dynamics 365 pour les sources de données d'opérations, et représente des concepts et de la fonctionnalité domaine- spécifiques d'entreprise dans un écran qui rend la conception d'origine et autre maintenance d'un format de génération d'états plus de rendement.

#### <a name="format-components"></a>Composants des formats

Un composant de format est le modèle utilisé pour la sortie générée au moment de l'exécution. Un modèle se compose des éléments suivants :

-   un format qui définit la structure et le contenu d'un document d'état électronique généré au moment de l'exécution ;
-   des sources de données en tant qu'ensemble de paramètres d'entrée utilisateur et de modèle de données spécifique au domaine avec la mise en correspondance du modèle sélectionnée ;
-   une mise en correspondance de format en tant qu'ensemble de liaisons des sources de données de format avec des éléments individuels de format qui spécifient au moment de l'exécution le flux de données et les règles de génération de sortie de format ;
-   une validation de format en tant qu'ensemble de règles configurables qui contrôlent la génération d'états au moment de l’exécution, en fonction du contexte de l’exécution (par exemple, une règle qui arrête la génération de la sortie des paiements d’un fournisseur et renvoie une exception lorsque des attributs spécifiques du fournisseur sélectionné sont manquantes, comme le numéro de compte bancaire).

Un composant de format prend en charge les fonctions suivantes :

-   Création de rapports de sortie en tant que fichiers individuels dans différents formats : texte, XML ou feuille de calcul
-   Création de plusieurs fichiers séparément et également encapsulation de ces fichiers dans des fichiers zip

Un composant de format donne la possibilité de joindre certains fichiers pouvant être utilisés dans la sortie d'états :

-   des classeurs Excel qui contiennent une feuille de calcul qui peut être utilisée comme modèle pour les sorties au format de feuille de calcul OPENXML ;
-   d'autres fichiers pouvant être incorporés à la sortie du format en tant que fichiers prédéfinis.

#### <a name="component-versioning"></a>Contrôle de versions du composant

Le contrôle de versions est pris en charge pour les composants d'états électroniques. Le workflow suivant est fourni pour gérer et sauvegarder les modifications dans les composants d'états électroniques :

-   La version qui est créée est marquée comme étant une version en mode **BROUILLON**. Cette version peut être modifiée et est disponible pour des séries de tests.
-   La version **BROUILLON** peut être convertie en une version **TERMINÉE**. Cette version peut être utilisée dans les processus de création d'états locaux.
-   ** TERMINÉ ** la version peut être convertie dans a ** PARTAGÉ ** version. Cette version est publiée sur des lettres de crédit et peut être utilisée dans les processus globaux de génération d'états.
-   La version **PARTAGÉE** peut être convertie en une version **INTERROMPUE**. Cette version peut ensuite être supprimée.

Les versions qui ont ** TERMINÉ ** ou ** PARTAGÉ ** statut sont disponibles pour l'autre échange de données. Un composant possédant ces statuts peut avoir ces actions effectuées sur ceux-ci :

-   Elles peuvent être sérialisées au format XML et être exportées de Dynamics 365 pour les opérations comme un fichier au format XML.
-   Elles peuvent reserialized d'un fichier XML et être importées dans Dynamics 365 pour les opérations comme une nouvelle version d'un composant d'ER.

#### <a name="component-date-effectivity"></a>Validité de date du composant

Les versions du composant d'état électronique est soumis à une date d'effet. La date** Prend effet le **peut être défini pour un composant d'état électronique afin de spécifier la date à partir de laquelle ce composant devient valide pour les processus de génération d'états. Dynamics 365 pour la date de la session d'opérations permet de définir si un composant est valide pour l'exécution. Lorsque plusieurs versions sont valides pour une date spécifique, la version la plus récente est utilisée pour le processus de génération d'états.

#### <a name="component-access"></a>Accès au composant

L'accès aux composants de format d'états électroniques dépend du paramètre du code de pays/région ISO. Lorsque ce paramètre est vide pour une version sélectionnée d'une configuration de format, un composant de format peut être consulté de tout Dynamics 365 pour la société d'opérations au moment de l'exécution. Lorsque ce paramètre contient les codes pays/région ISO, un composant de format est disponible que dans Dynamics 365 pour les sociétés d'opérations qui ont une adresse principale définie pour un des codes pays/région ISO d'un composant de format. Différentes versions d'un composant de format de données peuvent avoir différents paramètres de codes pays/région ISO.

#### <a name="configuration"></a>Configuration

Une configuration d'état électronique est le wrapper d'un composant d'état électronique spécifique : **Modèle de données **ou **Format**. Une configuration peut inclure différentes versions d'un composant d'état électronique particulier. Chaque configuration est marquée comme possédée par un fournisseur de configuration spécifique. ** BROUILLON ** la version d'un composant d'une configuration peut être modifiée lorsque le propriétaire de la configuration a été sélectionné comme fournisseur actif dans les paramètres d'ER dans Dynamics 365 pour les opérations. Chaque configuration de modèle contient un composant **Modèle de données**. Une nouvelle configuration de format peut être émise (dérivée) d'une configuration de modèle de données spécifique. La configuration de format créée s’affiche dans l’arborescence de configuration en tant qu’enfant de la configuration de modèle de données d’origine. La configuration de format qui est créée contient un composant **Format**. Le composant **Modèle de données** de cette configuration de modèle d'origine est automatiquement inséré dans le composant **Format** de la configuration de format enfant comme source de données par défaut. Configuration d'ER est partagée pour Dynamics 365 pour les sociétés d'opérations.

#### <a name="provider"></a>Fournisseur

Le fournisseur d'états électroniques est l'identificateur de partie utilisé pour indiquer l'auteur (propriétaire) de chaque configuration d'état électronique. L'état électronique vous permet de gérer la liste des fournisseurs de configuration. Formatez de configurations qui sont lancées pour les documents électroniques dans le cadre de Dynamics 365 pour les opérations que la solution sont marquées comme du sexe ** Microsoft ** le fournisseur de configuration.

#### <a name="repository"></a>Référentiel

Un référentiel d'états électroniques enregistre les configurations d'états électroniques. Les types de référentiel d'ER actuellement pris en charge : ** Ressources opérationnelles ** et ** projet lettres de crédit **. ** Ressources opérationnelles ** un référentiel permet d'accéder à la liste des configurations qui sont lancées dans le cadre de Dynamics 365 pour la solution d'opérations par Microsoft comme fournisseur de configuration d'ER. Ces configurations peuvent être importées dans Dynamics actuel 365 pour les opérations Services et les utilisés pour la génération d'états électronique. Elles peuvent également être utilisées pour des localisations/personnalisations. Un référentiel de **projet LCS** permet d'accéder à la liste des configurations d'un projet LCS spécifique (bibliothèque d'actifs de projet LCS) sélectionné à l'enregistrement du référentiel. L'ER permet de télécharger des configurations partagées de Dynamics actuel 365 pour l'instance d'opérations à un spécifique ** projet lettres de crédit ** référentiel. Vous pouvez également importer des configurations d'un détail ** projet lettres de crédit ** référentiel dans Dynamics actuel 365 pour l'instance d'opérations. ** Projet lettres de crédit ** de référentiel obligatoires peuvent être enregistrés individuellement pour chaque fournisseur de configuration de Dynamics actuel 365 pour l'instance d'opérations. Chaque référentiel peut être consacré à un fournisseur de configuration spécifique.

## <a name="supported-scenarios"></a>Scénarios pris en charge
### <a name="building-a-data-model"></a>Élaboration d'un modèle de données

L'état électronique propose un concepteur de modèle vous permettant de créer un modèle de données pour un domaine de l'entreprise donné. Toutes les entités commerciales spécifiques à un domaine et les relations entre elles peuvent être présentées dans un modèle de données en tant que structure hiérarchique. L’illustration suivante montre un exemple de ce type de modèle de données (le modèle de données du domaine de paiement). [exemple de![d'un modèle de données] (. /media/pic-data-model-1024x550.png)](. /media/pic-data-model.png) À vous familiariser avec les détails de ce scénario, jouent ** modèle de données spécifique de domaine de conception d'ER ** le Guide de tâche (une partie ** 7.5.4.3 acquièrent/développez les composants de services/solution informatique (10677) ** du processus entreprise).

### <a name="translating-data-model-content"></a>Traduction du contenu du modèle de données

Le contenu du modèle de données (des étiquettes et les descriptions) peut être traduit en d'autres langues que Dynamics 365 pour les opérations prend en charge. Vous souhaitez peut-être traduire le contenu du modèle de données pour les raisons suivantes :

-   au moment de la conception, pour rendre le contenu plus intelligible aux concepteurs de format parlant une langue étrangère qui utilisent un modèle de données pour la mise en correspondance des données des composants de format ;
-   Avec l'exécution, pour rendre le contenu plus conviviaux en présentant des invites et aide pour les paramètres d'exécution, et les messages également configurés de contrôle (erreurs et avertissements), dans la langue que Dynamics actuellement connecté 365 pour l'utilisateur d'opérations préfère

L’illustration suivante montre un exemple de la traduction du contenu du modèle de données de l’anglais vers le japonais. [contenu du modèle de données![en anglais (]. /media/pic-translate-en-1024x495.png)](. /media/pic-translate-en.png) [contenu du modèle de données![traduit Japonais (]. /media/pic-translate-ja-1024x495.png)](. /media/pic-translate-ja.png)

### <a name="configuring-data-model-mappings"></a>Configuration des mises en correspondance de modèles de données

L'ER fournit un modèle concepteur de mise en correspondance qui permet aux utilisateurs de mettre en correspondance les modèles de données qu'ils ont conçus à Dynamics spécifique 365 pour les sources de données d'opérations. L'illustration suivante présente un exemple de ce type de mise en correspondance de modèle de données (mise en correspondance du modèle **Virement SEPA** avec le modèle de données du domaine de paiement). [exemple de![d'une mise en correspondance de modèle de données] (. /media/pic-model-mapping-1024x551.png)](. /media/pic-model-mapping.png) À vous familiariser avec les détails de ce scénario, jouer ** l'ER définissent la mise en correspondance modèle et sélectionnez des sources de données ** et ** modèle de données de carte d'ER aux sources de données sélectionnées ** guides de tâche (une partie ** 7.5.4.3 acquièrent/développez les composants de services/solution informatique (10677) ** du processus entreprise).

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>Stockage du composant de modèle conçu en tant que modèle de configuration

L'ER peut enregistrer un modèle de données conçu avec les mappages des données associés comme configuration modèle de Dynamics actuel 365 pour l'instance d'opérations. L’illustration suivante montre un exemple de ce type de configuration de modèle de données (la configuration du modèle de paiement). [exemple de![d'une configuration du modèle de données] (. /media/pic-model-configuration-1024x585.png)](. /media/pic-model-configuration.png) À vous familiariser avec les détails de ce scénario, jouent ** modèle de données de carte d'ER aux sources de données sélectionnées ** le Guide de tâche (une partie ** 7.5.4.3 acquièrent/développez les composants de services/solution informatique (10677) ** du processus entreprise).

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Élaboration d'un format qui utilise un modèle de données en tant que base

ER prend en charge un concepteur de format que vous pouvez utiliser pour élaborer le format d'un document électronique particulier pour le domaine d'entreprise en sélectionné d'affaires en sélectionnant le composant modèle comme base. Le même concepteur de format ER vous permet de mettre en correspondance un format créé et la mise en correspondance du modèle de données du domaine sélectionné comme source de données. L’illustration suivante montre un exemple de ce type de format (la configuration du format qui prend en charge le format de paiement **BACS** pour le Royaume-Uni). [exemple de![d'un format avec un modèle de données comme base (]. /media/pic-format-1024x690.png)](. /media/pic-format.png) À vous familiariser avec les détails de ce scénario, jouent ** format spécifique du domaine de conception d'ER ** le Guide de tâche (une partie ** 7.5.4.3 acquièrent/développez les composants de services/solution informatique (10677) ** du processus entreprise).

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Création d'une configuration pour générer des documents électroniques au format de feuille de calcul OPENXML

Le concepteur de format ER peut être utilisé pour générer un document électronique au format de feuille de calcul OPENXML. L'illustration suivante présente un exemple de ce type de format (une configuration de format pour générer la feuille de calcul d'OPENXML avec les détails d'un journal des paiements sélectionné) : [![PIC-ER-FORMAT- Excel (]. /media/pic-er-format-excel.jpg)](. /media/pic-er-format-excel.jpg) À vous familiariser avec les détails de ce scénario, jouent ** l'ER créer une configuration pour les états dans le format d'OPENXML ** le Guide de tâche (une partie ** 7.5.4.3 acquièrent/développez les composants de services/solution informatique (10677) ** du processus entreprise). Utilisez consulté sous le fichier Excel comme modèle du format dans la conception d'ER pour effectuer l'étape de l'importation d'un modèle de format dans ce guide de tâche : [Modèle d'état de paiement (SampleVendPaymWsReport.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Stockage d'un composant de format conçu dans une configuration de format

L'ER peut enregistrer un format défini avec les mappages des données configurés comme configuration du format de Dynamics actuel 365 pour l'instance d'opérations. L’illustration ci-dessus montre un exemple de ce type de configuration de format (**BACS (Royaume-Uni)**, qui est un enfant de la configuration **Modèle de paiement **). Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Concevoir un format spécifique au domaine** (qui fait partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)** .

### <a name="configuring-dynamics-365-for-operations-to-start-to-use-a-created-format-internally"></a>Configuration Dynamics 365 pour les opérations commencent à utiliser un format créé en interne

Dynamics 365 pour les opérations peut être configuré pour commencer à utiliser un format créé pour générer les états électroniques. La référence à la configuration de format créé doit être définie dans les paramètres d'un domaine particulier. Par exemple, pour commencer à utiliser une configuration de format d'ER pour les paiements fournisseur électroniques au format de le système BACS, la configuration du format doit être référencée dans les modes de paiement spécifiques, comme le montrent des illustrations suivantes : 

[![Configuration du format de le système BACS (UK)](media/ger-bacs-uk-format-configuration.png) 

[![Référencer le format de le système BACS (UK) dans un mode de paiement](media/ger-bacs-uk-format-method.png) 

Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Utiliser le format pour générer un document électronique pour les paiements** (qui fait partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**).

## <a name="handling-er-components"></a>Gestion des composants ER
### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>Publication d'un composant ER dans LCS pour l'offrir en externe (localisation)

Le propriétaire d'un composant (modèle ou format) qui a été créé peut utiliser ER pour publier la version terminée du composant vers LCS. Un référentiel de type **Projet LCS **pour le fournisseur de configuration ER actuel est requis. Lorsque le statut de la version terminée d'un composant est modifié pour passer de **TERMINÉE** à **PARTAGÉE**, cette version est publiée dans LCS. Lorsqu'un composant a été publié vers LCS, le propriétaire de ce composant devient un fournisseur du service permettant de prendre en charge ce composant. Par exemple, si le composant de format est conçu pour générer un document électronique légalement requis (par exemple, conformément au scénario de localisation), ce service suppose que ce format reste conforme aux modifications législatives et le fournisseur émet de nouvelles versions du composant dès que de nouvelles exigences législatives doivent être prises en charge. Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Charger une configuration dans Lifecycle Services **(qui fait partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**).

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>Importation du composant ER depuis LCS pour l'utiliser en interne

L'ER permet d'importer des composants d'ER de lettres de crédit à Dynamics actuel 365 pour l'instance d'opérations. Un référentiel de type **Projet LCS **est requis. Lorsqu'un composant d'ER a été importé de crédit à Dynamics actuel 365 pour les opérations citez, le propriétaire de l'instance devient un client du service fourni par le propriétaire (auteur) du composant importé. Par exemple, si un composant de format est conçu pour générer un document électronique spécifique de Dynamics 365 pour les opérations d'un pays/format spécifique (scénario de localisation), il est impossible de le client de service peut obtenir toutes les mises à jour effectuées à ce format, permet de tenir à jour compatible avec les besoins législatifs. Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Charger une configuration à partir de Lifecycle Services** (qui fait partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**).

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Élaboration d'un format en sélectionnant un autre format en tant que base (personnalisation)

ER vous permet de que créer (dériver) un nouveau composant à partir de la version actuelle d’un composant (base) qui a été importé à partir de LCS. Par exemple, un utilisateur souhaite dériver un nouveau format pour mettre en œuvre une configuration spécifique pour un document électronique (par exemple, un champ supplémentaire ou une description complète) pour prendre en charge un scénario de personnalisation. Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Mettre à niveau le format par adoption d'une nouvelle version de base** (qui fait partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**).

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Mise à niveau d'un format en sélectionnant une nouvelle version du format de base (redéfinir)

ER vous permet d'adopter automatiquement les modifications de la version la plus récente du composant de base dans la version brouillon actuelle du composant dérivé. Ce processus est appelé *redéfinition de la base*. Par exemple, une nouvelle modification réglementaire (introduite dans la version la plus récente du composant de format importé depuis LCS) peut être automatiquement fusionnée dans la propre version personnalisée de ce format de document électronique. Toutes les modifications qui ne peuvent pas être fusionnées automatiquement sont considérées comme des conflits. Ces conflits sont présentés pour une résolution manuelle dans l’outil de concepteur pour le composant approprié. Pour vous familiariser avec ce scénario en détails, visionnez le guide de tâche **ER Mettre à niveau le format par adoption d'une nouvelle version de base** (qui fait partie du processus d'entreprise **7.5.4.3 Acquérir/Développer des composants de services/solutions informatiques (10677)**).

## <a name="list-of-er-configurations-that-are-delivered-in-the-dynamics-365-for-operations-solution"></a>Liste des configurations d'ER fournies dans Dynamics 365 pour la solution d'opérations
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


