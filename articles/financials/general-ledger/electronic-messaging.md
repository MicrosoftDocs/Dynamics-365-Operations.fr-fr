---
title: Messagerie électronique
description: Cette rubrique fournit des informations générales et de configuration pour la messagerie électronique dans Microsoft Dynamics 365 for Finance and Operations.
author: ShylaThompson
manager: AnnBe
ms.date: 11/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2018-10-28
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 082ad886f40a52457900523f44158da3ed939458
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "357931"
---
# <a name="electronic-messaging"></a>Messages électroniques

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations générales et de configuration pour la messagerie électronique dans Microsoft Dynamics 365 for Finance and Operations.

Récemment, les gouvernements et autorités législatives de différents pays/régions du monde entier ont implémenté l'obligation de génération d'états pour les sociétés qui sont enregistrées dans ces pays ou régions. L'objectif de ces obligations vise à permettre d'obtenir des données de ces sociétés au format électronique, directement depuis les systèmes auxquelles elles ont été comptabilisées, enregistrées, et traitées.

La fonctionnalité de messagerie électronique dans Finance and Operations prend en charge différents processus d'interopérabilité électronique entre Finance and Operations et les systèmes que les gouvernements et les autorités législatives offrent pour la génération d'états, la soumission, et la réception d'informations officielle.

La fonctionnalité de messagerie électronique est intégrée au module **États électroniques** (ER). Par conséquent, vous pouvez paramétrer des formats d'ER pour les messageries électroniques. Pour plus d'informations, voir [États électroniques (ER)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting).

La messagerie électronique est basée sur les entités suivantes :

- **Message électronique** : État ou déclaration qui doit être déclaré et/ou transmis en interne. Par exemple, un état transmis à un centre des impôts.
- **Éléments de messagerie électronique** : Enregistrements à inclure dans le message qui est déclaré.
- **Traitement de message électronique** : Chaîne d'actions, liées ou non, qui doivent être effectuées pour collecter les données nécessaires, générer des états, stocker des données dans le stockage d'objet blob Microsoft Azure, transmettre des états en dehors du système, obtenir des réponses en dehors du système, et mettre à jour la base de données, selon les informations reçues.

L'illustration suivante présente le flux des données pour la messagerie électronique.

![Flux de données de la messagerie électronique](media/electronic-messaging-data-flow.png)

La fonctionnalité de message électronique prend en charge les scénarios suivants :

- Créez des messages et générez des états manuellement qui sont basées sur des formats d'exportation d'ER de différents types : Microsoft Excel, XML, JSON (JavaScript Object Notation), PDF, Texte et Microsoft Word.
- Créez et traitez automatiquement les messages qui sont basées sur les informations demandées et obtenues depuis une autorité via un format d'ER d'importation associé.
- Collectez et traitez les informations d'une source de données (table Finance and Operations) comme des éléments du message.
- Stockez des informations supplémentaires, et évaluez différentes valeurs en appelant des classes exécutables définies spécifiquement concernant les messages ou les éléments du message.
- Regroupez les informations collectées dans les éléments de message, répartissez les informations par message, et générez des états dans des formats d'ER d'exportation associés.
- Transmettez les états générés à un service Web à l'aide des informations de sécurité stockées dans Azure Key Vault.
- Obtenez une réponse d'un service Web, interprétez la réponse, et mettez à jour les données dans Finance and Operations au besoin.
- Stockez et vérifiez tous les états générés.
- Stockez et vérifiez toutes les informations de journal associées aux actions exécutées pour un message ou un élément du message.
- Contrôlez le traitement par l'intermédiaire de différents statuts de message et statuts d'élément du message.

## <a name="set-up-electronic-messaging"></a>Paramétrage d'une messagerie électronique

La messagerie électronique peut vous aider à gérer différents processus de génération d'états électroniques pour chaque type de document. Dans certains scénarios complexes, la messagerie électronique est paramétrée pour avoir une combinaison de nombreux statuts de message, de statuts d'éléments de message, d'actions, de champs supplémentaires, et de classes exécutables. Pour ces scénarios, les packages d'entités de données sont disponibles pour l'importation. Si vous utilisez ces packages d'entité de données, vous devez les importer dans une entité juridique à l'aide de l'outil de gestion des données. Pour plus d'informations sur l'utilisation de l'outil de gestion de données, voir [Gestion des données](../../dev-itpro/data-entities/data-entities-data-packages.md).

Si vous n'importez pas un packages d'entité de données, vous pouvez paramétrer manuellement la fonctionnalité de messages électroniques. Dans ce cas, vous devez paramétrer les éléments suivants : 

- [Souches de numéros](#number-sequences)
- [Types et statuts d'élément du message](#message-item-types-and-statuses)
- [Statuts du message](#message-statuses)
- [Champs supplémentaires](#additional-fields)
- [Paramètres de la classe exécutable](#executable-class-settings)
- [Actions Renseignement des enregistrements](#populate-records-actions)
- [Paramètres du service Web](#web-service-settings)
- [Actions de traitement des messages](#message-processing-actions)
- [Traitement du message électronique](#electronic-message-processing)

Les sections suivantes fournissent des informations supplémentaires sur chacun de ces éléments.

### <a name="number-sequences"></a>Souches de numéros

Paramétrez les souches de numéros pour les messages et les éléments de message. Les souches de numéros sont utilisées pour compter automatiquement les messages et les éléments de message, et les numéros affectés sont utilisés comme identificateurs uniques pour les messages et éléments de message dans le système. Vous pouvez paramétrer des souches de numéros pour la messagerie électronique sur la page **Paramètres de comptabilité** (**Comptabilité générale** \> **Paramétrage de la comptabilité** \> **Paramètres de comptabilité**).

### <a name="message-item-types-and-statuses"></a>Types et statuts d'élément du message

Les types d'éléments du message identifient les types d'enregistrements utilisés dans les messageries électroniques. Vous pouvez paramétrer les types d'éléments de message sur la page **Types d'éléments de message** (**Taxe** \> **Paramétrage** \> **Messageries électroniques** \> **Types d'élément de message**).

Les statuts d'élément de message identifient les statuts qui s'appliquent aux éléments du message dans le traitement que vous paramétrez. Vous pouvez paramétrer les types d'éléments de message sur la page **Statuts d'éléments de message** (**Taxe** \> **Paramétrage** \> **Messageries électroniques** \> **Statuts d'élément de message**).

### <a name="message-statuses"></a>Statuts du message

Paramétrez les statuts du message qui doivent être disponibles dans le traitement des messages. Vous pouvez paramétrer les statuts d'éléments de message sur la page **Statuts du message** (**Taxe** \> **Paramétrage** \> **Messageries électroniques** \> **Statuts du message**).

### <a name="additional-fields"></a>Champs supplémentaires

La fonctionnalité de messages électroniques permet de renseigner les enregistrements à partir d'une table de transactions. De cette manière, vous pouvez préparer les enregistrements pour la gestion des états électroniques puis les générer. Parfois, les informations sont insuffisantes dans la table de transactions pour déclarer un enregistrement selon les besoins d'état. Vous pouvez renseigner toutes les informations à déclarer pour un enregistrement en paramétrant des champs supplémentaires. Les champs supplémentaires peuvent être associés à des messages et des éléments de message. Vous pouvez paramétrer des champs supplémentaires sur la page **Champs supplémentaires** (**Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Champs supplémentaires**).

Le tableau suivant décrit les champs de la page **Champs supplémentaires**.

| Champ                | Description |
|----------------------|-------------|
| Nom du champ           | Entrez le nom d'un attribut supplémentaire des éléments de message qui sont liés au processus. Ce nom est affiché dans l'interface utilisateur lorsque vous utilisez le processus. Il peut également être utilisé dans les configurations d'ER liées au processus. |
| Description          | Entrez une description de l'attribut supplémentaire des éléments de message qui sont liés au processus. |
| Valeur de champ          | Entrez la valeur du champ à utiliser pour un élément de message lors de la génération d'états. |
| Description du champ    | Entrez une description de la valeur du champ à utiliser pour un élément de message lors de la génération d'états. |
| Type de compte         | Certaines valeurs de champs supplémentaires peuvent être limitées à des types de comptes spécifiques. Sélectionner l'une des valeurs suivantes : **Tous**, **Client** et **Fournisseur**. |
| Compte - valide pour         | Si vous avez sélectionné **Client** ou **Fournisseur** dans le champ **Type de compte**, vous pouvez limiter davantage l'utilisation des valeurs de champ à un groupe ou à une table spécifique. |
| Numéro de compte/groupe | Si vous avez sélectionné **Client** ou **Fournisseur** dans le champ **Type de compte**, et si vous avez entré un groupe ou une table dans le champ **Code du compte**, vous pouvez entrer un groupe ou un contragent spécifique dans ce champ. |
| Date d'effet            | Spécifiez la date à laquelle la valeur doit commencer à être prise en compte. |
| Expiration           | Spécifiez la date à laquelle la valeur doit arrêter d'être prise en compte. |

### <a name="executable-class-settings"></a>Paramètres de la classe exécutable

Une classe exécutable est une méthode ou une classe X++ que le traitement de message électronique peut appeler en relation à une action si une certaine évaluation est nécessaire pour le processus.

Vous pouvez paramétrer manuellement une classe exécutable sur la page **Paramètres de classe exécutable** (**Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Paramètres de classe exécutable**). Créez une ligne, puis définissez les champs suivants.

| Champ                 | Description |
|-----------------------|-------------|
| Classe exécutable      | Entrez le nom qui sera utilisé lors du paramétrage d'une action de traitement de message en lien avec la classe appelée. |
| Description           | Entrez une description de la classe exécutable. |
| Nom de la classe exécutable | Sélectionnez une classe exécutable X++. |
| Niveau d'exécution       | Ce champ est défini automatiquement, car la valeur doit être prédéfinie pour la classe exécutable sélectionnée. Ce champ limite le niveau auquel on exécute l'évaluation associée. |
| Description de la classe     | Ce champ est défini automatiquement, car la valeur doit être prédéfinie pour la classe exécutable sélectionnée. |

### <a name="populate-records-actions"></a>Actions Renseignement des enregistrements

Vous utilisez les actions de renseignement des enregistrements pour paramétrer des actions qui ajoutent des enregistrements à la table Éléments de message de sorte qu'ils puissent être ajoutés à un message électronique. Par exemple, si votre message électronique doit déclarer des factures client, vous devez paramétrer une action **Renseigner les enregistrements** qui est liée à la table **Journal des factures client** (dans le champ **Source de données** ). Vous pouvez paramétrer des actions de renseignements d'enregistrements sur la page **Action de renseignement d'enregistrements** (**Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Action de renseignement d'enregistrements**). Créez un enregistrement pour chaque action qui doit ajouter des enregistrements à la table, puis définissez les champs suivants.

| Champ       | Description                                                               |
|-------------|---------------------------------------------------------------------------|
| Nom        | Entrez un nom pour l'action qui renseigne les enregistrements dans votre processus.       |
| Description | Entrez une description de l'action qui renseigne les enregistrements dans votre processus. |

Dans l'organisateur **Paramétrage des sources de données**, ajoutez une ligne pour chaque source de données utilisée pour le processus, puis définissez les champs suivants.

| Champ                  | Description |
|------------------------|-------------|
| Nom                   | Entrez un nom pour la source de données. |
| Type d'élément de message      | Sélectionnez le type d'élément de message qui doit être utilisé lorsque des enregistrements sont créés pour la source de données. |
| Type de compte           | Sélectionnez le type de compte qui doit être associé à des enregistrements de la source de données. |
| Nom de la table principale      | Sélectionnez la table dans Finance and Operations qui doit être une source de données. |
| Champ Numéro du document  | Sélectionnez le champ dans lequel le numéro de document doit être extrait dans la table sélectionnée. |
| Champ Date du document    | Sélectionnez le champ dans lequel la date de document doit être extraite dans la table sélectionnée. |
| Champ Compte du document | Sélectionnez le champ dans lequel le compte du document doit être extrait dans la table sélectionnée. |
| Requête utilisateur             | Si cette case à cocher est activée, vous pouvez paramétrer une requête en sélectionnant **Modifier la requête** au-dessus de la grille. Sinon, tous les enregistrements seront renseignés à partir de la source de données. |

### <a name="web-service-settings"></a>Paramètres du service Web

Vous utilisez des paramètres de service Web pour paramétrer la transmission de données directe à un service Web. Vous pouvez définir les paramètres de service Web sur la page **Paramètres des services Web** (**Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Paramètres des services Web**).

Le tableau suivant décrit les champs de la page **Paramètres de service Web**.

| Champ                   | Description |
|-------------------------|-------------|
| Service Web             | Entrez un nom pour le service Web. |
| Description             | Permet d'entrer une description du service Web. |
| Adresse Internet        | Entrez l'adresse Internet du service Web. |
| Certificat             | Sélectionnez un certificat de coffre de clés précédemment paramétré. |
| Type de réponse – XML | Définissez cette option sur **Oui** si le type de réponse est XML. |
| Méthode de la demande          | Spécifiez la méthode de demande. HTTP définit un ensemble de méthodes de demande qui indiquent l'action à effectuer pour une ressource donnée. La méthode peut être **GET**, **POST**, ou une autre méthode HTTP. |
| En-tête de la demande         | Spécifiez les en-têtes de la demande. Un en-tête de demande est un en-tête HTTP pouvant être utilisée dans une demande HTTP, et qui n'est pas lié au contenu du message. |
| Accepter le codage         | Spécifiez Accepter le codage. L'en-tête HTTP de demande Accepter le codage publie l'encodage du contenu que le client peut comprendre. Cet encodage de contenu est généralement un algorithme de compression. |
| Type de contenu            | Spécifiez le type de contenu. L'en-tête d'entité Type de contenu indique le type de support de la ressource. |

### <a name="message-processing-actions"></a>Actions de traitement des messages

Vous utilisez des actions de traitement des messages pour créer des actions pour vos processus et définir leurs paramètres. Vous pouvez paramétrer des actions de traitement sur la page **Actions de traitement des messages** (**Taxe** \> **Paramétrage** \> **Messageries électroniques** \> **Actions de traitement des messages**).

Les tableaux suivants décrivent les champs de la page **Actions de traitement des messages**.

#### <a name="general-fasttab"></a>Organisateur Général

| Champ                   | Description |
|-------------------------|-------------|
| Type d'action             | Permet de sélectionner le type de l'action. Pour plus d'informations sur les options disponibles, voir la section [Types d'actions de traitement des messages](#message-processing-action-types). |
| Mise en correspondance des formats          | Sélectionnez le format d'ER qui doit être appelé pour l'action. Ce champ n'est disponible que pour les actions de types **Exportation de la gestion des états électroniques**, **Importation de la gestion des états électroniques** et **Message d'exportation pour la gestion des états électroniques**. |
| Type d'élément de message       | Sélectionnez le type d'enregistrements pour lequel l'action doit être évaluée. Ce champ est disponible pour les actions de types **Niveau d'exécution de l'élément de message**, **Exportation de la gestion des états électroniques** et **Importation de la gestion des états électroniques**, ainsi que d'autres types. Si vous laissez ce champ vide, tous les types d'éléments de message définis pour le traitement des messages sont évalués. |
| Classe exécutable        | Sélectionnez les paramètres de classe exécutable créés précédemment. Ce champ n'est disponible que pour les actions **Niveau d'exécution de l'élément de message** et **Niveau d'exécution de l'élément de message**. |
| Action Renseigner des enregistrements | Sélectionnez une action de renseignement des enregistrements paramétrée auparavant. Ce champ n'est disponible que pour les actions du type **Renseigner les enregistrements**. |

##### <a name="message-processing-action-types"></a>Types d'actions de traitement des messages

Les options suivantes sont disponibles dans le champ **Type d'action** :

- **Renseigner les enregistrements** : Une action **Renseigner les enregistrements** doit déjà être paramétrée. Associez-la à une action de type **Renseigner les enregistrements** pour activer sont inclusion lors de traitement. On suppose que ce type d'action est utilisé pour la première action dans le traitement des messages. Par conséquent, seul un statut de résultat peut être paramétré pour une action de ce type. Un statut initial ne peut pas être paramétré.
- **Créer un message** : Utilisez ce type pour permettre aux utilisateurs de créer manuellement des messages sur la page **Message électronique**. Un statut initial ne peut pas être paramétré pour une action de ce type.
- **Niveau d'exécution du message** : Utilisez ce type pour paramétrer une classe exécutable à évaluer au niveau du message.
- **Niveau d'exécution de l'élément de message** : Utilisez ce type pour paramétrer une classe exécutable à évaluer au niveau de l'élément de message.
- **Exportation de la gestion des états électroniques** : Utilisez ce type pour les actions devant générer un état basé sur une configuration d'exportation de la gestion des ER au niveau de l'élément de message.
- **Message d'exportation pour la gestion des états électroniques** : Utilisez ce type pour les actions devant générer un état basé sur une configuration d'exportation de la gestion des ER au niveau du message (par exemple, lorsqu'un message ne contient pas d'éléments de message).
- **Importation de la gestion des états électroniques** : Utilisez ce type pour les actions devant générer un état basé sur une configuration d'importation de la gestion des ER.
- **Traitement utilisateur au niveau du message** : Utilisez ce type pour les actions qui assument certaines actions manuelles par l'utilisateur. Par exemple, l'utilisateur peut mettre à jour le statut des messages.
- **Traitement utilisateur** : Utilisez ce type pour les actions qui assument certaines actions manuelles par l'utilisateur. Par exemple, l'utilisateur peut mettre à jour le statut des éléments de messages.
- **Service Web** : Utilisez ce type pour les actions devant transmettre l'état généré à un service Web. Ce type d'action n'est pas utilisé pour la génération d'états de communication de factures d'achat et client italiens.
- **Vérification de la demande** : Utilisez ce type pour demander une vérification d'un serveur.

#### <a name="initial-statuses-fasttab"></a>Organisateur Statuts initiaux

> [!NOTE]
> L'organisateur **Statuts initiaux** n'est pas disponible pour les actions avec un type initial de **Renseigner les enregistrements** ou **Créer un message**.

| Champ               | Description                                                                                         |
|---------------------|-----------------------------------------------------------------------------------------------------|
| Statut de l'élément de message | Sélectionnez le statut de l'élément de message indiquant que l'action de traitement du message sélectionné doit être évaluée. |
| Description         | Description du statut de l'élément de message sélectionné.                                                  |

#### <a name="result-statuses-fasttab"></a>Organisateur Statuts de résultat

| Champ               | Description |
|---------------------|-------------|
| Statut du message      | Sélectionnez les statuts de message indiquant que l'action de traitement du message sélectionné doit être évaluée. Ce champ est disponible uniquement pour les actions de traitement de message qui sont évaluées au niveau de message. Par exemple, il est disponible pour les actions des types **Exportation de la gestion des états électroniques** et **Importation de la gestion des états électroniques**. Il n'est pas disponible pour les actions des types **Traitement utilisateur** et **Niveau d'exécution de l'élément de message**. |
| Description         | Description du statut de message sélectionné. |
| Type de réponse       | Type de réponse du statut de message sélectionné. |
| Statut de l'élément de message | Sélectionnez les statuts résultants devant être disponibles une fois l'action de traitement du message sélectionné évaluée. Ce champ est disponible uniquement pour les actions de traitement de message qui sont évaluées au niveau de l'élément de message. Par exemple, il est disponible pour les actions des types **Traitement utilisateur** et **Niveau d'exécution de l'élément de message**. Pour les actions de traitement de messages évaluées au niveau du message, ce champ affiche le statut de l'élément de message paramétré pour le statut de message sélectionné. |

### <a name="electronic-message-processing"></a>Traitement du message électronique

Le traitement de message électronique est un concept de base de la fonctionnalité de messages électroniques. Il regroupe les actions à évaluer pour les messages électroniques. Les actions peuvent être liées via un statut initial et un statut de résultat. Sinon, les actions de type **Traitement utilisateur** peuvent être démarrées individuellement. Sur la page **Traitement du message électronique** (**Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Traitement du message électronique**), vous pouvez également sélectionner des champs supplémentaires à prendre en charge pour le traitement.

L'organisateur **Action** vous permet d'ajouter des actions prédéfinies au traitement. Vous pouvez spécifier si une action doit être exécutée séparément, ou si elle peut être lancée par le traitement. (Les actions utilisateur doivent être exécutées séparément.)

L'organisateur **Champs supplémentaires de l'élément du message** vous permet d'ajouter des champs supplémentaires prédéfinis liés aux éléments de message. Vous devez ajouter des champs supplémentaires pour chaque type d'élément de message auquel les champs sont liés.

L'organisateur **Champs supplémentaires du message** vous permet d'ajouter des champs supplémentaires prédéfinis liés aux messages.

L'organisateur **Rôles de sécurité** vous permet de paramétrer les rôles de sécurité prédéfinis dans le système pour un traitement spécifique. Les utilisateurs disposant d'un rôle spécifique verront uniquement le traitement qui est défini pour ce rôle.

L'organisateur **Traitement par lot** vous permet de paramétrer le traitement pour fonctionner à un régime de lots.

## <a name="work-with-electronic-messages-functionality"></a>Utiliser la fonctionnalité de messages électroniques

Si vous travaillez au niveau du message, la page **Messages électroniques** (**Taxe** \> **Recherches et états** \> **Messages électroniques** \> **Messages électroniques**) est plus utile. Si vous travaillez au niveau de la collecte de données (élément de message), la page **Éléments du message électronique** (**Taxe** \> **Recherches et états** \> **Messages électroniques** \> **Éléments du message électronique**) est plus utile.

### <a name="electronic-messages"></a>Messages électroniques

La page **Messages électroniques** présente le traitement disponible pour vous, en fonction de votre rôle. Les rôles de sécurité sont associés au traitement dans le paramétrage de celui-ci. Pour chaque traitement disponible pour vous, la page affiche les messages électroniques et les informations connexes.

L'organisateur **Messages** affiche les messages électroniques du traitement sélectionné. Selon le statut du message sélectionné et le traitement prédéfini, vous pouvez exécuter certaines actions en sélectionnant les boutons au-dessus de la grille :

- **Nouveau** : Ce bouton est associé aux actions du type **Créer un message**.
- **Supprimer** : Ce bouton est disponible si la case à cocher **Autoriser la suppression** est activée pour le statut actuel du message sélectionné.
- **Générer un état** : Ce bouton est associé aux actions du type **Message d'exportation pour la gestion des états électroniques**.
- **Envoyer un état** : Ce bouton est associé aux actions du type **Service Web**.
- **Mettre à jour le statut** : Ce bouton est associé aux actions du type **Traitement utilisateur au niveau du message**.
- **Éléments du message** : Ouvre la page **Éléments du message électronique**.

L'organisateur **Journal des actions** présente des informations sur toutes les actions exécutées pour le message sélectionné.

L'organisateur **Champs supplémentaires du message** affiche tous les champs supplémentaires définis pour les messages dans le paramétrage du traitement. Il affiche également les valeurs de ces champs supplémentaires.

L'organisateur **Éléments du message** affiche tous les éléments du message liés au message sélectionné.

Vous pouvez réviser toutes les pièces jointes du message sélectionné. Ces pièces jointes sont des états déjà générés et reçus. Sélectionnez le message pour réviser les pièces jointes, puis sélectionnez le bouton **Pièce jointe** sur le volet Actions.

![Bouton Pièce jointe](media/attachment-icon.png)

La page **Pièces jointes** affiche toutes les pièces jointes associées au message. Pour afficher un fichier, sélectionnez-le dans la liste à gauche, puis sélectionnez **Ouvrir** sur le volet Actions.

![Bouton Ouvrir](media/open-button.png)

Pour réviser une pièce jointe liée à une action spécifique précédemment exécutée pour un message, sélectionnez le message sur la page **Messages électroniques**, puis, dans l'organisateur **Journal des actions**, sélectionnez l'action. Ensuite, sélectionnez le bouton **Pièce jointe** sur le volet Action.

Vous pouvez également exécuter l'ensemble du traitement ou seulement une action spécifique en sélectionnant **Exécuter le traitement** sur le volet Action.

### <a name="electronic-message-items"></a>Éléments du message électronique

La page **Éléments du message électronique** présente tous les éléments du message et un journal des actions exécutées pour chaque élément du message. Elle affiche également les champs supplémentaires définis pour les éléments du message, et les valeurs de ces champs supplémentaires.

Le tableau suivant décrit les champs de la page **Éléments du message**.

<table>
<thead>
<tr>
<th>Champ</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>Traitement</td>
<td>Nom du traitement utilisé pour créer l'élément du message.</td>
</tr>
<tr>
<td>Élément du message</td>
<td>ID de l'élément du message. Cet ID est affecté automatiquement, selon la souche de numéros <strong>Élément du message</strong> définie sur la page <strong>Paramètres de comptabilité</strong>.</td>
</tr>
<tr>
<td>Date de l'élément de message</td>
<td>Date de création de l'élément du message.</td>
</tr>
<tr>
<td>Type d'élément de message</td>
<td>Type de l'élément du message. Plusieurs types d'éléments de messages peuvent être paramétrés pour le même traitement (par exemple, <strong>Factures entrantes</strong> et <strong>Factures sortantes</strong>). Ce champ peut être renseigné automatiquement uniquement si une facture est ajoutée à la table Éléments du message.</td>
</tr>
<tr>
<td>Statut de l'élément de message</td>
<td>Statut actuel de l'élément du message. Les statuts disponibles varient, en fonction du type de l'élément du message. Voici quelques exemples :
<ul>
<li><strong>Renseigné</strong> : Un enregistrement a été ajouté à la table Éléments du message.</li>
<li><strong>Évalué</strong> : Des attributs supplémentaires ont été calculés pour l'élément du message.</li>
<li><strong>Déclaré</strong> : L'élément du message a bien été ajouté à un état.</li>
<li><strong>Exclu</strong> : Ce statut peut être utile si vous devez exclure des éléments du message d'un état avant qu'il soit exporté.</li>
</ul>
</td>
</tr>
<tr>
<td>Date de transmission</td>
<td>Pour le traitement qui transmet automatiquement un état généré en dehors du système, date à laquelle l'élément du message a été transmis.</td>
</tr>
<tr>
<td>Numéro du document</td>
<td>Ce champ est automatiquement renseigné en fonction du paramétrage de l'action de renseignement des enregistrements. Ce champ peut être renseigné automatiquement uniquement si une facture est ajoutée à la table Éléments du message.</td>
</tr>
<tr>
<td>Numéro de compte</td>
<td>Numéro de compte d'un client ou d'un fournisseur (ou autre valeur de champ, selon le champ défini dans l'action <strong>Renseigner les enregistrements</strong>). Ce champ peut être renseigné automatiquement uniquement si une facture est ajoutée à la table Éléments du message.</td>
</tr>
<tr>
<td>Message</td>
<td>Numéro du message. Ce numéro est affecté automatiquement, selon la souche de numéros <strong>Message</strong> définie sur la page <strong>Paramètres de comptabilité</strong>.</td>
</tr>
<tr>
<td>Statut du message</td>
<td>Statut actuel du message électronique.</td>
</tr>
<tr>
<td>Action suivante</td>
<td>Actions suivantes pouvant être initiées pour le statut actuel de l'élément du message.</td>
</tr>
</tbody>
</table>

L'onglet **Champs supplémentaires** affiche les champs supplémentaires de l'élément du message sélectionné, et leurs valeurs.

#### <a name="run-processing"></a>Exécuter le traitement

Sélectionnez **Exécuter le traitement** sur le volet Actions pour exécuter le traitement des éléments du message. Pour exécuter une action spécifique, dans la boîte de dialogue **Exécuter le traitement**, définissez l'option **Sélectionner l'action** sur **Oui**, puis sélectionnez une action. Pour exécuter le traitement complet, laissez l'option **Sélectionner l'action** définie sur **Non**.

#### <a name="generate-report"></a>Générer un état

Sélectionnez **Générer un état** sur le volet Actions pour générer un état. Ce bouton est associé aux actions du type **Exportation pour la gestion des états électroniques**.

#### <a name="update-status"></a>Mise à jour du statut

Sélectionnez **Mettre à jour le statut** sur le volet Actions pour mettre à jour le statut d'un ou de plusieurs éléments du message. Dans la boîte de dialogue **Mettre à jour le statut**, utilisez l'organisateur **Enregistrements à inclure** pour sélectionner les éléments du message pour la mise à jour. Assurez-vous de définir correctement les critères de sélection, car les statuts d'élément du message sont mis à jour selon ces critères, le statut initial de l'action sélectionnée, et la valeur **Nouveau statut** définie. Une fois la mise à jour du statut terminée, il sera difficile de déterminer les éléments mis à jour. Par conséquent, il sera difficile d'annuler les mises à jour de statut.

#### <a name="electronic-messages"></a>Messages électroniques

Sélectionnez **Message électronique** sur le volet Actions pour réviser une message électronique associé à l'élément du message sélectionné.

Vous pouvez également réviser tous les fichiers correspondant à l'élément du message. Sélectionnez le champ **Message** de l'élément du message, ou sélectionnez **Message électronique** sur le volet Actions. Sur la page **Message électronique**, sélectionnez le message pour lequel réviser un état, puis sélectionnez le bouton **Pièce jointe** sur le volet Actions.

![Bouton Pièce jointe](media/attachment-icon.png)

La page **Pièces jointes** affiche toutes les pièces jointes associées au message. Pour afficher un fichier, sélectionnez-le dans la liste à gauche, puis sélectionnez **Ouvrir** sur le volet Actions.

![Bouton Ouvrir](media/open-button.png)

#### <a name="original-document"></a>Document d'origine

Sélectionnez **Document d'origine** sur le volet Actions pour ouvrir le document d'origine de l'élément du message sélectionné.

## <a name="example"></a>Exemple

Après avoir créé votre format d'ER, l'avoir mappé à des sources de données, et l'avoir terminé, vous pouvez l'exécuter à l'aide de l'espace de travail **Gestion des états électroniques**. Un état est généré que vous pouvez enregistrer localement.

Pour contrôler les aspects suivants du processus de gestion d'états, vous devez paramétrer le traitement par messagerie électronique :

- Enregistrez les informations sur l'utilisateur ayant généré l'état.
- Enregistrez la date et l'heure auxquelles l'état a été généré.
- Enregistrez les états générés pour les périodes précédentes.

Cette section fournit un exemple qui indique comment vous pouvez paramétrer la fonctionnalité de messages électroniques pour établir un processus de génération d'états.

### <a name="set-up-and-run-processing-to-call-a-simple-er-exporting-format-to-generate-an-excel-report"></a>Paramétrez et exécutez le traitement pour appeler format d'exportation d'ER pour générer un état d'Excel

Cette section fournit un exemple qui indique comment paramétrer la messagerie électronique pour générer un état basé sur un format d'exportation ER pour Excel. Pour suivre cet exemple, le format d'exportation Excel d'ER doit déjà être créé, mappé à des sources de données, et être terminé. Une souche de numéros doit déjà être paramétrée pour les messages électroniques.

Lorsque vous créez le traitement, il est utile de commencer par définir les actions et les statuts de traitement à paramétrer. L'illustration suivante présente à quoi ce traitement ressemble pour cet exemple.

![Schéma du traitement](media/processing-scheme.png)

#### <a name="create-message-statuses"></a>Créer des statuts de message

1. Accédez à **Taxe \> Paramétrage \> Messages électroniques \> Statuts de message**.
2. Créez les statuts de message suivants :

    - Nouveau
    - Préparé
    - Généré

    ![Statuts du message](media/message-statuses.png)

3. Sur la ligne du statut **Nouveau**, activez la case à cocher **Autoriser la suppression** pour permettre aux utilisateurs de supprimer les messages avec ce statut.

#### <a name="create-additional-fields"></a>Créer des champs supplémentaires

1. Accédez à **Taxe \> Paramétrage \> Messages électroniques \> Champs supplémentaires**.
2. Ajouter un champ supplémentaire et ses valeurs. Voici un exemple :

    ![Champs supplémentaires](media/additional-fields.png)

3. Définissez l'option **Modification utilisateur** sur **Oui** de permettre aux utilisateurs de modifier le champ.

#### <a name="create-message-processing-actions"></a>Créer des actions de traitement des messages

Pour cet exemple, vous allez créer les actions suivantes :

- **Créer un message**
- **Mettre à jour sur Préparé**
- **Générer un état**
- **Mettre à jour sur le statut initial** (facultatif)

1. Accédez à **Taxe \> Paramétrage \> Messages électroniques \> Actions de traitement du message**.
2. Créez une action nommée **Créer un message**. Sur l'organisateur **Général**, dans le champ **Type d'action**, sélectionnez **Créer un message**.
3. Créez une action nommée **Mettre à jour sur Préparé**, puis définissez les champs suivants :

    - Sur l'organisateur **Général**, dans le champ **Type d'action**, sélectionnez **Traitement utilisateur au niveau du message**.
    - Sur l'organisateur **Statuts initiaux**, dans le champ **Statut du message**, sélectionnez **Nouveau**.
    - Sur l'organisateur **Statuts de résultat**, dans le champ **Statut du message**, sélectionnez **Préparé**. Dans le champ **Type de réponse**, entrez **Exécution réussie**.

4. Créez une action nommée **Générer un état**, puis définissez les champs suivants :

    - Sur l'organisateur **Général**, dans le champ **Type d'action**, sélectionnez **Exportation de la gestion des états électroniques**. Dans le champ **Mise en correspondance des formats**, sélectionnez le format d'exportation ER. Les options sont **Excel**, **XML**, **JSON**, **Texte**, et **Autre**.
    - Sur l'organisateur **Statuts initiaux**, dans le champ **Statut du message**, sélectionnez **Préparé**.
    - Sur l'organisateur **Statuts de résultat**, dans le champ **Statut du message**, sélectionnez **Généré**. Dans le champ **Type de réponse**, entrez **Exécution réussie**.

    ![Générer une action d'état](media/generate-report-action.png)

5. Facultatif : Pour permettre aux utilisateurs de regénérer un état plusieurs fois, vous pouvez créer une action **Mettre à jour sur le statut initial** et définir les champs suivants :

    - Sur l'organisateur **Général**, dans le champ **Type d'action**, sélectionnez **Traitement utilisateur au niveau du message**.
    - Sur l'organisateur **Statuts initiaux**, dans le champ **Statut du message**, sélectionnez **Généré**.
    - Sur l'organisateur **Statuts de résultat**, dans le champ **Statut du message**, sélectionnez **Préparé** ou (et) **Nouveau**. Dans le champ **Type de réponse**, entrez **Exécution réussie**.

#### <a name="electronic-message-processing"></a>Traitement du message électronique

Dans cet exemple, toutes les actions doivent être paramétrées de manière à ce que elles s'exécutent séparément. On suppose que chaque action est lancée par l'utilisateur.

1. Accédez à **Taxe \> Paramétrage \> Messages électroniques \> Traitement du message électronique**.
2. Ajoutez un enregistrement pour votre traitement, puis ajoutez toutes les actions définies précédemment et un champ supplémentaire.
3. Facultatif : Sur l'organisateur **Rôles de sécurité**, définissez des rôles de sécurité pour votre traitement afin de restreindre l'accès à l'état spécifique.
4. Accédez à **Taxe \> Recherches et états \> Messages électroniques \> Messages électroniques**.
5. Sélectionnez **Nouveau** pour créer un message. À ce stade, vous pouvez ajouter des dates et une description. Vous pouvez également mettre à jour la valeur du champ supplémentaire au besoin.

    ![Créer un message électronique](media/create-electronic-message.png)

La grille sur l'organisateur **Journal des actions** est renseignée automatiquement avec un journal de toutes les actions effectuées sur le message.

Vous pouvez désormais supprimer ou mettre à jour le statut du message. Pour mettre à jour le statut du message, sélectionnez **Mettre à jour le statut**, puis, dans le champ **Nouveau statut**, sélectionnez **Préparé**. Puis sélectionnez **OK**.

![Mettre à jour le statut du message](media/update-status.png)

Le statut du message est mis jour sur **Préparé**, et vous pouvez désormais générer l'état en sélectionnant **Générer l'état**. L'état est généré, et le statut du message et le journal des actions sont mis à jour. Pour afficher l'état généré, sélectionnez le bouton **Pièce jointe** sur le volet Actions.
