---
title: Composants des états électroniques
description: Cet article décrit les composants Gestion des états électroniques (ER).
author: kfend
ms.date: 09/28/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.form: ERWorkspace
ms.openlocfilehash: 4851374ca4943a84d35f063e0ee65b537ec3b6cd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285029"
---
# <a name="electronic-reporting-components"></a>Composants des états électroniques

[!include [banner](../includes/banner.md)]

La Gestion des états électroniques (ER) prend en charge les types de composants suivants :

- Modèle de données
- Mappage de modèles
- Format
- Métadonnées

## <a name="data-model-component"></a>Composant Modèle de données

Un composant de modèle de données est une représentation abstraite d’une structure de données. Il décrit un domaine de l’entreprise spécifique avec suffisamment de détail pour satisfaire aux conditions de génération d’états pour ce domaine. Un composant de modèle de données se compose des éléments suivants :

- **Modèle de données** – Un ensemble d’entités commerciales spécifiques à un domaine et une définition structurée hiérarchiquement des relations entre ces entités.
- **Mappage de modèles** – Les sources de données d’application sélectionnées sont liées à des éléments individuels d’un modèle de données qui spécifie, au moment de l’exécution, le flux de données et les règles de saisie des données métier dans un composant de modèle de données.

L’entité commerciale d’un modèle de données est représentée sous la forme d’un conteneur ou d’un enregistrement. Les propriétés d’entité commerciale sont représentées comme des articles de données, ou champs. Chaque article de données est doté d’un nom, d’un libellé, d’une description et d’une valeur uniques. La valeur de chaque élément de données peut être conçu de sorte qu’il soit reconnu comme une chaîne, entier, réel, date, énumération (enum) ou valeur booléenne, etc. De plus, l’élément de données peut être un autre enregistrement ou une liste d’enregistrements.

Un composant de modèle de données unique peut contenir plusieurs hiérarchies des entités commerciales spécifiques à un domaine. Il contient également les mappages de modèles qui prennent en charge le flux de données spécifiques aux états au moment de l’exécution. Les hiérarchies sont différenciées par un enregistrement unique qui est sélectionné comme racine de la mise en correspondance de modèle. Par exemple, le modèle de données du domaine du paiement peut prendre en charge les mises en correspondance suivantes :


- Société \> Fournisseur \> Transactions de paiement du domaine comptabilité fournisseur
- Client \> Société \> Transactions de paiement du domaine comptabilité client

Les entités commerciales (par exemple, les transactions de paiement et la société) ne sont conçues qu’une fois. Différents mappages peuvent les réutiliser selon les besoins.

## <a name="model-mapping-component"></a>Composant de mise en correspondance de modèles

Le mappage de modèles lie les sources de données d’application sélectionnées sont liées à des éléments individuels d’un modèle de données qui spécifient, au moment de l’exécution, le flux de données et les règles de saisie des données métier dans un composant de modèle de données.

Un mappage de modèle qui prend en charge les documents électroniques sortants a les fonctionnalités suivantes :

- Il peut utiliser les différents types de données comme sources de données pour un modèle de données. Ces types de données incluent des tables, des entités de données, des méthodes et des énumérations.
- Il prend en charge les paramètres d’entrée utilisateur qui peuvent être définies comme sources de données pour un modèle de données lorsque certaines données doivent être spécifiées au moment de l’exécution.
- Il prend en charge la transformation des données en groupes requis. Vous pouvez également filtrer, trier et ajouter des données, ainsi que des champs calculés logiques qui sont conçus via les formules qui sont semblables aux formules de Microsoft Excel. Pour plus d’informations, voir [Concepteur de formule dans la gestion des états électroniques](general-electronic-reporting-formula-designer.md).

Un mappage de modèle qui prend en charge les documents électroniques entrants a les fonctionnalités suivantes :

- Il peut utiliser différents éléments de données pouvant être mis à jour comme cibles. Ces éléments de données incluent des tables, des entités de données et des vues. Les données peuvent être mises à jour par des données entrantes provenant de documents électroniques. Plusieurs cibles peuvent être utilisées dans un mappage de modèle unique.
- Il prend en charge les paramètres d’entrée utilisateur qui peuvent être définies comme sources de données pour un modèle de données lorsque certaines données doivent être spécifiées au moment de l’exécution.

Un composant de modèle de données est conçu pour chaque domaine métier utilisé comme source de données unifiée pour la création de rapports. La source de données unifiée isole les rapports de la mise en œuvre physique des sources de données. Le composant représente des concepts et des fonctionnalités d’entreprise spécifiques au domaine sous une forme qui rend la conception d’origine du format de rapport et toute autre maintenance plus efficaces.

## <a name="format-component"></a>Composant des formats

### <a name="format-components-for-outgoing-electronic-documents"></a>Composants de format pour les documents électroniques sortants

Un composant de format est le modèle utilisé pour la sortie générée au moment de l’exécution. Un modèle se compose des éléments suivants :

- Un format qui définit la structure et le contenu d’un document électronique sortant généré au moment de l’exécution.
- des sources de données, en tant qu’ensemble de paramètres d’entrée utilisateur et de modèle de données spécifique au domaine avec la mise en correspondance du modèle sélectionnée ;
- Une mise en correspondance de format, en tant qu’ensemble de liaisons des sources de données de format avec des éléments individuels de format qui spécifient au moment de l’exécution le flux de données et les règles de génération de sortie de format.
- Une validation de format en tant qu’ensemble de règles configurables qui contrôlent la génération d’états au moment de l’exécution en fonction du contexte d’exécution. Par exemple, il peut y avoir une règle qui arrête la génération de sortie des paiements d’un fournisseur et lance une exception lorsque des attributs spécifiques du fournisseur sélectionné sont manquants, comme le numéro de compte bancaire.

Un composant de format prend en charge les fonctions suivantes :

- Création d’une sortie de rapports en tant que fichiers individuels dans différents formats, tels que texte, XML, document Microsoft Word ou feuille de calcul
- Création de plusieurs fichiers séparément et encapsulation dans des fichiers zip

Un composant de format vous permet de joindre certains fichiers pouvant être utilisés dans la sortie d’états :

- des classeurs Excel qui contiennent une feuille de calcul qui peut être utilisée comme modèle pour les sorties au format de feuille de calcul OPENXML ;
- des fichiers Word qui contiennent un document qui peut être utilisé comme modèle pour les sorties au format de document Microsoft Word
- d’autres fichiers pouvant être incorporés à la sortie du format en tant que fichiers prédéfinis.

L’illustration ci-dessous indique les flux de données pour ces formats.

[![Flux de données des composants de format sortants](./media/ER-overview-02.png)](./media/ER-overview-02.png)

Pour exécuter une configuration de format de génération d’états électroniques unique et générer un document électronique sortant, vous devez identifier le mappage de la configuration de format.

#### <a name="format-components-for-incoming-electronic-documents"></a>Composants de format pour les documents électroniques entrants
Un composant de format est le modèle de document entrant qui est importé au moment de l’exécution. Un modèle se compose des éléments suivants :

- Un format qui définit la structure et le contenu d’un document électronique entrant contenant des données qui sont importées au moment de l’exécution. Un composant de format est utilisé pour analyser un document entrant dans différents formats : texte et XML.
- Un mappage des formats qui lie les éléments de format individuels aux éléments d’un modèle de données spécifique au domaine. Au moment de l’exécution, les éléments du modèle de données spécifient le flux de données et les règles pour importer les données d’un document entrant, puis stockent les données dans un modèle de données.
- Une validation de format en tant qu’ensemble de règles configurables qui contrôlent l’importation de données au moment de l’exécution en fonction du contexte d’exécution. Par exemple, il peut y avoir une règle qui empêche l’importation de données d’un relevé bancaire contenant des paiements d’un fournisseur et lance une exception lorsque les attributs d’un fournisseur spécifique sont manquants, comme le code d’identification du fournisseur.

L’illustration ci-dessous indique les flux de données pour ces formats.

[![Flux de données des composants de format entrants](./media/ER-overview-03.png)](./media/ER-overview-03.png)

Pour exécuter une configuration simple de format de génération d’états électroniques pour importer les données d’un document électronique entrant, vous devez identifier le mappage souhaité d’une configuration de format, ainsi que le point d’intégration d’un mappage de modèle. Vous pouvez utiliser les mêmes mappages et destinations de modèles avec différents formats pour différents types de documents entrants.


## <a name="component-versioning"></a>Contrôle de versions du composant

Le contrôle de versions est pris en charge pour les composants d’états électroniques. Le workflow suivant est fourni pour gérer et sauvegarder les modifications dans les composants d’états électroniques :

1. La version qui a été créée est marquée comme étant une version en mode **Brouillon**. Cette version peut être modifiée et est disponible pour des séries de tests.
2. La version **Brouillon** peut être convertie en une version **Terminée**. Cette version peut être utilisée dans les processus de création d’états locaux.
3. La version **Terminée** peut être convertie en une version **Partagée**. Cette version est publiée dans Microsoft Dynamics Lifecycle Services (LCS) et peut être utilisée dans le processus de création de rapports globaux.
4. La version **Partagée** peut être convertie en une version **Interrompue**. Cette version peut être supprimée.

Les versions dotées du statut **Terminée** ou **Partagée** sont disponibles pour un autre échange de données. Les actions suivantes peuvent être exécutées sur un composant possédant ces statuts :

- Le composant peut être sérialisé au format XML et exporté vers un fichier au format XML.
- Le composant peut être resérialisé à partir d’un fichier XML et importé dans l’application sous la forme d’une nouvelle version d’un composant d’état électronique.

Pour plus d’informations, voir [Importer une nouvelle configuration de modèle de données](er-quick-start1-new-solution.md#ImportDataModel) et [Exporter la version terminée d’un format dérivé](er-calculated-field-type.md#export-completed-version-of-a-derived-format).

### <a name="draft-versions-at-runtime"></a>Versions brouillon au moment de l’exécution

Dans vos paramètres utilisateur personnels pour l’infrastructure ER, vous pouvez activer l’option qui vous permet de spécifier si la version brouillon d’une configuration ER doit être utilisée lors de l’exécution. Pour savoir comment rendre l’option **Exécuter le brouillon** disponible pour vos configurations ER, voir [Marquer un format personnalisé comme exécutable](er-quick-start2-customize-report.md#MarkFormatRunnable).

> [!NOTE]
> Les paramètres d’utilisateur ER sont spécifiques à l’utilisateur et à l’entreprise.

### <a name="draft-format-versions-at-runtime"></a>Versions de format brouillon au moment de l’exécution

Par défaut, lorsque vous exécutez une solution ER, les versions brouillon de ses composants de format sont ignorées. Au lieu de cela, seule la version pertinente qui a un statut autre que **Brouillon** est utilisée. Parfois, vous souhaiterez peut-être forcer ER à utiliser la version brouillon de votre configuration de format ER lors de l’exécution. Par exemple, après avoir introduit les modifications nécessaires dans votre version brouillon, vous pouvez utiliser cette version brouillon pour effectuer le test. De cette façon, vous pouvez valider l’exactitude de vos modifications. Pour commencer à utiliser la version au format préliminaire, vous devez [définir](er-quick-start2-customize-report.md#MarkFormatRunnable) l’option **Exécuter le brouillon** de la configuration ER pertinente sur **Oui**.

### <a name="draft-model-mapping-versions-at-runtime"></a>Versions de mappage de modèle Brouillon lors de l’exécution

Par défaut, lorsque vous exécutez une solution ER, les versions brouillon de ses composants de mappage des modèles sont ignorées. Parfois, vous souhaiterez peut-être forcer ER à ignorer la version brouillon de votre configuration de mappage de modèle ER lors de l’exécution. Dans la **version 10.0.29 et ultérieures**, vous pouvez activer l’option **Tenir toujours compte de l’option « Exécuter le brouillon » pour les mappages de modèles ER** afin de contrôler la version de mappage de modèle utilisée lors de l’exécution. Lorsque cette fonctionnalité est activée, le comportement suivant se produit :

- Quand l’option **Exécuter le brouillon** est définie sur **Non** pour une configuration de mappage de modèle, la version non brouillon la plus élevée de cette configuration est utilisée lors de l’exécution. Une exception est levée si la configuration n’est pas disponible dans l’instance Finance actuelle.
- Quand l’option **Exécuter le brouillon** est définie sur **Oui** pour une configuration de mappage de modèle, la version brouillon de cette configuration est utilisée lors de l’exécution.

## <a name="component-date-effectivity"></a>Validité de date du composant

Les versions du composant de format ER ont une date d’effet. Vous pouvez définir la date "Prend effet le" pour un composant de format ER afin de spécifier la date à partir de laquelle ce composant devient valide pour les processus de génération d’états. La date de session de l’application permet de définir si un composant est valide pour l’exécution. Lorsque plusieurs versions sont valides pour une date spécifique, la version la plus récente est utilisée pour le processus de génération d’états.

## <a name="component-access"></a>Accès au composant

L’accès aux composants au format ER et à ceux de mappage des modèles lors de l’exécution dépend du réglage du code de pays/région de l’Organisation internationale de normalisation (ISO). Lorsque ce paramètre est vide pour une version sélectionnée d’une configuration de format ou de mappage de modèle, un composant de format ou de mappage de modèle est accessible à partir de n’importe quelle société au moment de l’exécution. Lorsqu’il contient des codes pays/région ISO, un composant de format ou de modèle de mappage est disponible uniquement à partir des sociétés dont l’adresse principale est défini pour l’un des codes pays/régions ISO du composant de format.

Différentes versions d’un composant de format ou de mappage de modèle peuvent avoir différents paramètres de codes pays/région ISO.

Pour en savoir plus, configurez [Configurer les mises en correspondance de modèle de gestion des états électroniques en fonction du contexte de pays](er-country-dependent-model-mapping.md).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

