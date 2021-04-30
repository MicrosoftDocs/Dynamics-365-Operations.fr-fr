---
title: Messagerie électronique
description: Cette rubrique fournit des informations générales et de configuration pour la messagerie électronique dans Microsoft Dynamics 365 Finance.
author: ShylaThompson
ms.date: 11/16/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-10-28
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: dd49edeb92e6a23723b1b6b6ea7800b69a81bd0f
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5897598"
---
# <a name="electronic-messaging"></a>Messages électroniques

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations générales et de configuration pour la messagerie électronique.

Récemment, les gouvernements et autorités législatives de différents pays/régions du monde entier ont implémenté l’obligation de génération d’états pour les sociétés qui sont enregistrées dans ces pays ou régions. L’objectif de ces obligations vise à permettre d’obtenir des données de ces sociétés au format électronique, directement depuis les systèmes auxquelles elles ont été comptabilisées, enregistrées, et traitées.

La fonctionnalité de messagerie électronique dans Finance prend en charge différents processus d’interopérabilité électronique entre Finance et les systèmes que les gouvernements et les autorités législatives offrent pour la génération d’états, la soumission, et la réception d’informations officielle.

La fonctionnalité de messagerie électronique est intégrée au module **États électroniques** (ER). Par conséquent, vous pouvez paramétrer des formats d’ER pour les messageries électroniques. Pour plus d’informations, voir [États électroniques (ER)](/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting).

La messagerie électronique est basée sur les entités suivantes :

- **Message électronique** : État ou déclaration qui doit être déclaré et/ou transmis en interne. Par exemple, un état transmis à un centre des impôts.
- **Éléments de messagerie électronique** : Enregistrements à inclure dans le message qui est déclaré.
- **Traitement de message électronique** : chaîne d’actions qui doivent être effectuées pour collecter les données nécessaires, générer des états, stocker des données dans le stockage d’objet blob Microsoft Azure, transmettre des états en dehors du système, recevoir des réponses extérieures au système et mettre à jour la base de données. Les actions de la chaîne peuvent être liées ou non.

L’illustration suivante présente le flux des données pour la messagerie électronique.

![Flux de données de la messagerie électronique](media/electronic-messaging-data-flow.png)

La fonctionnalité de message électronique prend en charge les scénarios suivants :

- Créez des messages et générez manuellement des états qui sont basés sur des formats d’exportation d’ER de différents types : Microsoft Excel, XML, JSON (JavaScript Object Notation), PDF, Texte et Microsoft Word.
- Créez et traitez automatiquement les messages qui sont basées sur les informations demandées et reçues depuis une autorité via un format d’ER d’importation associé.
- Collectez et traitez les informations d’une source de données comme des éléments du message. La source de données est une table Finance.
- Stockez des informations supplémentaires, et évaluez différentes valeurs en appelant des classes exécutables définies spécifiquement concernant les messages ou les éléments du message.
- Regroupez les informations collectées dans les éléments de message, répartissez les informations par message, et générez des états dans des formats d’ER d’exportation associés.
- Transmettez les états générés à un service Web à l’aide des informations de sécurité stockées dans Azure Key Vault.
- Recevez une réponse d’un service Web, interprétez la réponse, et mettez à jour les données dans Finance, au besoin.
- Stockez et vérifiez tous les états générés.
- Stockez et vérifiez toutes les informations de journal associées aux actions exécutées pour un message ou un élément du message.
- Contrôlez le traitement par l’intermédiaire de différents statuts de message et statuts d’élément du message.

## <a name="set-up-electronic-messaging"></a>Paramétrage d’une messagerie électronique

La messagerie électronique peut vous aider à gérer différents processus de génération d’états électroniques pour chaque type de document. Dans certains scénarios complexes, la messagerie électronique est paramétrée de manière à avoir une combinaison de nombreux statuts de message, de statuts d’éléments de message, d’actions, de champs supplémentaires, et de classes exécutables. Pour ces scénarios, les packages d’entités de données sont disponibles pour l’importation. Si vous utilisez ces packages d’entité de données, vous devez les importer dans une entité juridique à l’aide de l’outil de gestion des données. Pour plus d’informations sur l’utilisation de l’outil de gestion de données, voir [Gestion des données](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

Si vous n’importez pas un packages d’entité de données, vous pouvez paramétrer manuellement la fonctionnalité de messages électroniques. Dans ce cas, vous devez paramétrer les éléments suivants :

- [Souches de numéros](#number-sequences)
- [Types et statuts d’élément du message](#message-item-types-and-statuses)
- [Statuts du message](#message-statuses)
- [Champs supplémentaires](#additional-fields)
- [Paramètres de la classe exécutable](#executable-class-settings)
- [Actions Renseignement des enregistrements](#populate-records-actions)
- [Applications Web](#web-applications)
- [Paramètres du service Web](#web-service-settings)
- [Actions de traitement des messages](#message-processing-actions)
- [Traitement du message électronique](#electronic-message-processing)

Les sections suivantes fournissent des informations supplémentaires sur chacun de ces éléments.

### <a name="number-sequences"></a>Souches de numéros

Paramétrez les souches de numéros pour les messages et les éléments de message. Les souches de numéros sont utilisées pour numéroter automatiquement les messages et les éléments de message. Les numéros affectés sont utilisés comme identificateurs uniques pour les messages et éléments de message dans le système. Vous pouvez paramétrer des souches de numéros pour la messagerie électronique sur la page **Paramètres de comptabilité** (**Comptabilité générale** \> **Paramétrage de la comptabilité** \> **Paramètres de comptabilité**).

### <a name="message-item-types-and-statuses"></a>Types et statuts d’élément du message

Les types d’éléments du message identifient les types d’enregistrements utilisés dans les messageries électroniques. Vous pouvez paramétrer les types d’éléments de message sur la page **Types d’éléments de message** (**Taxe** \> **Paramétrage** \> **Messageries électroniques** \> **Types d’élément de message**).

Les statuts d’élément de message identifient les statuts qui s’appliquent aux éléments du message dans le traitement que vous paramétrez. Vous pouvez paramétrer les types d’éléments de message sur la page **Statuts d’éléments de message** (**Taxe** \> **Paramétrage** \> **Messageries électroniques** \> **Statuts d’élément de message**).

Le paramètre **Autoriser la suppression** d’un statut d’élément de message définit si les utilisateurs peuvent supprimer des éléments de message ayant ce statut dans la page **Messages électroniques** ou **Éléments du message électronique**.

### <a name="message-statuses"></a>Statuts du message

Paramétrez les statuts du message qui doivent être disponibles dans le traitement des messages. Vous pouvez paramétrer les statuts d’éléments de message sur la page **Statuts du message** (**Taxe** \> **Paramétrage** \> **Messageries électroniques** \> **Statuts du message**).

Le tableau suivant décrit les champs de la page **Statuts du message**.

| Nom du champ          | Description |
|---------------------|-------------|
| Statut du message      | Permet d’entrer un nom unique pour le statut du message. Les statuts de message sont utilisés pour caractériser l’état d’un message électronique à tout moment. Le nom que vous entrez s’affiche dans la page **Messages électroniques** et dans un journal associé aux messages électroniques. |
| Description         | Entrez une description du statut de message. |
| Type de réponse       | Sélectionnez le type de réponse pour le statut de message. Certaines actions d’un traitement peuvent produire plusieurs types de réponse. Par exemple, les actions du type **Service Web** peuvent entraîner une réponse de type **Exécution réussie** ou **Erreur technique** selon le résultat de leur exécution. Dans ce cas, il convient de définir des statuts de message pour les deux types de réponses. Pour en savoir plus sur les types d’action et les types de réponse qui y sont associés, voir [Types d’actions de traitement des messages](#message-processing-action-types). |
| Statut de l’élément de message | Parfois, le statut d’un message électronique doit influencer le statut des éléments de message associés. Sélectionnez un statut d’élément de message dans ce champ pour l’associer au statut du message. |
| Autoriser la suppression        | Activez cette case à cocher si les utilisateurs doivent pouvoir supprimer les message électroniques ayant ce statut sur la page **Messages électroniques**. |

### <a name="additional-fields"></a>Champs supplémentaires

La fonctionnalité de messages électroniques permet de renseigner les enregistrements à partir d’une table de transactions. De cette manière, vous pouvez préparer les enregistrements pour la gestion des états électroniques puis les générer. Toutefois, les tables transactionnelles n’ont parfois pas assez d’informations pour renseigner les enregistrements de manière à respecter les exigences de la génération d’états. Pour renseigner toutes les informations à déclarer pour un enregistrement, vous pouvez paramétrer des champs supplémentaires. Les champs supplémentaires peuvent être associés à des messages et des éléments de message. Vous pouvez paramétrer des champs supplémentaires sur la page **Champs supplémentaires** (**Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Champs supplémentaires**).

Le tableau suivant décrit les champs généraux de la page **Champs supplémentaires**.

| Champ       | Description |
|-------------|-------------|
| Nom du champ  | Entrez le nom d’un attribut supplémentaire des éléments de message qui sont liés au processus. Ce nom est affiché dans l’interface utilisateur (IU) lorsque vous utilisez le processus. Il peut également être utilisé dans les configurations d’ER liées au processus. |
| Description | Entrez une description des champs supplémentaires. |
| Modification utilisateur   | Définissez cette option sur **Oui** si les utilisateurs doivent pouvoir modifier la valeur du champ supplémentaire à partir de l’IU. |
| Compteur     | Définissez cette option sur **Oui** si le champ supplémentaire doit contenir une souche de numéros dans un message électronique. La valeur du champ supplémentaire sera renseignée automatiquement lors de l’exécution d’une action de type **Exportation de la gestion des états électroniques**. |
| Masqué      | Définissez cette option sur **Oui** si le champ supplémentaire est masqué dans l’IU. |

Chaque champ supplémentaire peut avoir différentes valeurs pour le traitement. Vous pouvez définir ces valeurs dans l’organisateur **Valeurs**. Le tableau suivant décrit ces champs.

| Champ                | Description |
|----------------------|-------------|
| Valeur de champ          | Entrez la valeur du champ à utiliser pour un message ou un élément de message lors de la génération d’états. |
| Description          | Entrez une description de la valeur du champ. |
| Type de compte         | Certaines valeurs de champs peuvent être limitées à des types de comptes spécifiques. Sélectionner l’une des valeurs suivantes : **Tous**, **Client** et **Fournisseur**. |
| Compte – valide pour         | Si vous avez sélectionné **Client** ou **Fournisseur** dans le champ **Type de compte**, vous pouvez limiter davantage l’utilisation de la valeur du champ à un groupe ou à une table spécifique. |
| Numéro de compte/groupe | Si vous avez sélectionné **Client** ou **Fournisseur** dans le champ **Type de compte**, et si vous avez entré un groupe ou une table dans le champ **Code du compte**, vous pouvez entrer un groupe ou un contragent spécifique dans ce champ. |
| Date d’effet            | Spécifiez la date à laquelle la valeur doit commencer à être prise en compte. |
| Expiration           | Spécifiez la date à laquelle la valeur doit arrêter d’être prise en compte. |

Par défaut, les combinaisons des critères définis par les champs **Numéro de compte/groupe**, **Code compte**, **Date d’effet** et **Date d’expiration** n’influencent pas la sélection des valeurs pour les champs supplémentaires. Toutefois, ces combinaisons peuvent être utilisées dans une classe exécutable pour implémenter un logique spécifique de calcul des valeurs pour les champs supplémentaires.

### <a name="executable-class-settings"></a>Paramètres de la classe exécutable

Une classe exécutable est une méthode ou une classe X++ que le traitement de message électronique peut appeler en relation à une action si une certaine évaluation est nécessaire pour le processus.

Vous pouvez paramétrer manuellement une classe exécutable sur la page **Paramètres de classe exécutable** (**Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Paramètres de classe exécutable**). Créez une ligne, puis définissez les champs suivants.

| Champ                 | Description |
|-----------------------|-------------|
| Classe exécutable      | Entrez le nom qui sera utilisé lors du paramétrage d’une action de traitement de message en lien avec la classe appelée. |
| Description           | Entrez une description de la classe exécutable. |
| Nom de la classe exécutable | Sélectionnez une classe exécutable X++. |
| Niveau d’exécution       | Ce champ est défini automatiquement, car la valeur doit être prédéfinie pour la classe exécutable sélectionnée. Ce champ limite le niveau auquel on exécute l’évaluation associée. |
| Description de la classe     | Ce champ est défini automatiquement, car la valeur doit être prédéfinie pour la classe exécutable sélectionnée. |

Certaines classes exécutables peuvent avoir des paramètres obligatoires qui doivent être définis avant la première exécution de la classe exécutable. Pour définir ces paramètres, sélectionnez **Paramètres** dans le volet Actions, définissez les champs de la boîte de dialogue qui s’affiche, puis sélectionnez **OK**. Il est important de sélectionner **OK**. Dans le cas contraire, les paramètres ne seront pas enregistrés dans la base de données et la classe exécutable ne sera pas appelée correctement.

### <a name="populate-records-actions"></a>Actions Renseignement des enregistrements

Vous utilisez les actions de renseignement des enregistrements pour paramétrer des actions qui ajoutent des enregistrements à la table Éléments de message de sorte qu’ils puissent être ajoutés à un message électronique. Par exemple, si votre message électronique doit déclarer des factures client, vous devez paramétrer une action Renseigner les enregistrements qui est liée au champ **Source de données** dans la table Journal des factures client. Vous pouvez paramétrer des actions de renseignements d’enregistrements sur la page **Action de renseignement d’enregistrements** (**Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Action de renseignement d’enregistrements**). Créez un enregistrement pour chaque action qui doit ajouter des enregistrements à la table, puis définissez les champs suivants.

| Champ       | Description |
|-------------|-------------|
| Nom        | Entrez un nom pour l’action qui renseigne les enregistrements dans votre processus. |
| Description | Entrez une description de l’action Renseigner les enregistrements. |

Dans l’organisateur **Paramétrage des sources de données**, ajoutez une ligne pour chaque source de données utilisée pour le processus, puis définissez les champs suivants.

| Champ                  | Description |
|------------------------|-------------|
| Nom                   | Entrez un nom pour la source de données. |
| Type d’élément de message      | Sélectionnez le type d’élément de message qui doit être utilisé lorsque des enregistrements sont créés pour la source de données. |
| Type de compte           | Sélectionnez le type de compte qui doit être associé à des enregistrements de la source de données. |
| Nom de la table principale      | Sélectionnez la table qui doit être une source de données. |
| Champ Numéro du document  | Sélectionnez le champ dans lequel le numéro de document doit être extrait dans la table sélectionnée. |
| Champ Date du document    | Sélectionnez le champ dans lequel la date de document doit être extraite dans la table sélectionnée. |
| Champ Compte du document | Sélectionnez le champ dans lequel le compte du document doit être extrait dans la table sélectionnée. |
| Requête utilisateur             | Si cette case à cocher est activée, vous pouvez paramétrer une requête en sélectionnant **Modifier la requête** au-dessus de la grille. Sinon, tous les enregistrements seront renseignés à partir de la source de données sélectionnée. |

### <a name="web-applications"></a>Applications Web

Vous utilisez les paramètres d’application Web pour paramétrer une application Web afin qu’elle prenne en charge l’autorisation Open Authorization (OAuth) 2.0. OAuth est la norme ouverte actuelle qui permet aux utilisateurs d’« accorder l’accès sécurisé délégué » à l’application en leur nom, sans partager leurs informations d’identification d’accès. Vous pouvez également accéder au processus d’autorisation en obtenant un code d’autorisation et un jeton d’accès. Vous pouvez définir les paramètres d’application Web sur la page **Applications Web** (**Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Applications Web**).

Le tableau suivant décrit les champs de la page **Applications Web**.

| Champ                        | Description |
|------------------------------|-------------|
| Nom de l’application             | Permet d’entrer un nom pour l’application Web. |
| Description                  | Permet d’entrer une description de l’application Web. |
| URL de base                     | Permet d’entrer l’adresse Internet de base de l’application Web. |
| Chemin de l’URL d’autorisation       | Permet de préciser le chemin utilisé pour constituer l’URL pour l’autorisation. |
| Chemin de l’URL du jeton               | Permet de préciser le chemin utilisé pour constituer l’URL pour le jeton. |
| URL de redirection                 | Permet de saisir l’URL de redirection. |
| ID client                    | Permet de saisir l’identifiant client de l’application Web. |
| Question secrète du client                | Permet de saisir le secret du client de l’application Web. |
| Jeton de serveur                 | Permet de saisir le jeton de serveur de l’application Web. |
| Mise en correspondance des formats d’autorisation | Permet de sélectionner le format d’états électroniques utilisé pour générer la demande d’autorisation. |
| Mise en correspondance des modèles de jeton d’importation   | Permet de sélectionner une mise en correspondance des modèles d’importation des états électroniques utilisés pour enregistrer le jeton d’accès. |
| Portée accordée                | La portée accordée pour les requêtes à l’application. Ce champ est mis à jour automatiquement. |
| Le jeton d’accès expirera dans  | Le temps restant avant l’expiration du jeton d’accès. | 
| Accepter                       | Permet de spécifier la propriété **Accepter** de la requête Web. Par exemple, entrez **application/vnd.hmrc.1.0+json**. |
| Type de contenu                 | Spécifiez le type de contenu. Par exemple, entrez **application/json**. |

En outre, les boutons suivants sont disponibles dans le volet Actions de la page **Applications Web** pour prendre en charge le processus d’autorisation :

- **Obtenir le code d’autorisation** – initialise l’autorisation de l’application Web.
- **Obtenir un jeton d’accès** – initialise le processus d’obtention d’un jeton d’accès.
- **Actualiser le jeton d’accès** – Actualise un jeton d’accès.

Lorsqu’un jeton d’accès à une application Web est enregistré dans la base de données du système dans un format chiffré, il peut être utilisé pour les requêtes vers un service Web. À des fins de sécurité, l’accès au jeton d’accès doit être limité aux rôles de sécurité qui doivent être autorisés à traiter ces requêtes. Si des utilisateurs extérieurs au groupe de sécurité essaient d’envoyer une requête, il reçoivent une erreur indiquant qu’ils ne sont pas autorisés à interagir à l’aide de l’application Web sélectionnée. Pour paramétrer les rôles de sécurité qui doivent avoir accès au jeton d’accès, utilisez l’organisateur **Rôles de sécurité** de la page **Applications Web**. Si les rôles de sécurité ne sont pas définis pour une application Web, seul un administrateur système est en mesure d’interagir via cette application Web.

### <a name="web-service-settings"></a>Paramètres du service Web

Vous utilisez des paramètres de service Web pour paramétrer la transmission de données directe à un service Web. Vous pouvez définir les paramètres de service Web sur la page **Paramètres des services Web** (**Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Paramètres des services Web**).

Le tableau suivant décrit les champs de la page **Paramètres de service Web**.

| Champ                          | Description |
|--------------------------------|-------------|
| Service Web                    | Entrez un nom pour le service Web. |
| Description                    | Permet d’entrer une description du service Web. |
| Adresse Internet               | Entrez l’adresse Internet du service Web. Si une application Web est spécifiée pour un service Web et que l’adresse Internet du service Web doit être identique à celle définie pour l’application Web sélectionnée, sélectionnez **Copier l’URL de base** pour copier l’URL de base de l’application Web dans ce champ. |
| Certificat                    | Sélectionnez un certificat de coffre de clés précédemment paramétré. |
| Application Web                | Sélectionnez un certificat de coffre de clés précédemment paramétré. |
| Type de réponse – XML        | Définissez cette option sur **Oui** si le type de réponse est XML. |
| Méthode de la demande                 | Spécifiez la méthode de demande. HTTP définit un ensemble de méthodes de demande qui indiquent l’action à effectuer pour une ressource donnée. La méthode de requête peut être **GET**, **POST**, ou une autre méthode HTTP. |
| En-tête de la demande                | Spécifiez les en-têtes de la demande. Un en-tête de demande est un en-tête HTTP pouvant être utilisée dans une demande HTTP, et qui n’est pas lié au contenu du message. |
| Accepter                         | Permet de spécifier la propriété **Accepter** de la requête Web. |
| Accepter le codage                | Permet de spécifier la valeur **Accepter le codage**. L’en-tête HTTP de demande Accepter le codage publie l’encodage du contenu que le client peut comprendre. Cet encodage de contenu est généralement un algorithme de compression. |
| Type de contenu                   | Spécifiez le type de contenu. L’en-tête HTTP d’entité Type de contenu indique le type de support de la ressource. |
| Code de réponse réussie       | Permet de spécifier le code de statut HTTP indiquant la réussite de la requête. |
| Mise en correspondance des formats pour les en-têtes de demande | Permet de sélectionner le format d’états électroniques utilisé pour générer les en-têtes de requête Web. |

### <a name="message-processing-actions"></a>Actions de traitement des messages

Vous utilisez des actions de traitement des messages pour créer des actions pour vos processus et définir leurs paramètres. Vous pouvez paramétrer des actions de traitement sur la page **Actions de traitement des messages** (**Taxe** \> **Paramétrage** \> **Messageries électroniques** \> **Actions de traitement des messages**).

Les tableaux suivants décrivent les champs de la page **Actions de traitement des messages**.

#### <a name="general-fasttab"></a>Organisateur Général

| Champ                       | Description |
|-----------------------------|-------------|
| Type d’action                 | Permet de sélectionner le type de l’action. Pour plus d’informations sur les options disponibles, voir la section [Types d’actions de traitement des messages](#message-processing-action-types). |
| Mise en correspondance des formats              | Sélectionnez le format d’ER qui doit être appelé pour l’action. Ce champ n’est disponible que pour les actions de types **Exportation de la gestion des états électroniques**, **Importation de la gestion des états électroniques** et **Message d’exportation pour la gestion des états électroniques**. |
| Mise en correspondance des formats pour le chemin de l’URL | Sélectionnez le format d’ER qui doit être appelé pour l’action. Ce champ n’est disponible que pour les actions de type **Service Web**. Il est utilisé pour composer le chemin de l’adresse URL qui sera ajoutée à l’adresse Internet de base spécifiée pour le serveur Web sélectionné. |
| Type d’élément de message           | Sélectionnez le type d’enregistrements pour lequel l’action doit être évaluée. Ce champ est disponible pour les actions de types **Niveau d’exécution de l’élément de message**, **Exportation de la gestion des états électroniques** et **Importation de la gestion des états électroniques**, **Service Web** ainsi que d’autres types d’action. Si vous laissez ce champ vide, tous les types d’éléments de message définis pour le traitement des messages sont évalués. |
| Classe exécutable            | Sélectionnez les paramètres de classe exécutable créés précédemment. Ce champ n’est disponible que pour les actions **Niveau d’exécution de l’élément de message** et **Niveau d’exécution de l’élément de message**. |
| Action Renseigner des enregistrements     | Sélectionnez une action de renseignement des enregistrements paramétrée auparavant. Ce champ n’est disponible que pour les actions du type **Renseigner les enregistrements**. |
| Service Web                 | Sélectionnez un service Web paramétré précédemment. Ce champ n’est disponible que pour les actions de type **Service Web**. |
| Nom de fichier                   | Permet de spécifier le nom du fichier qui est le résultat de l’action. Ce fichier peut être la réponse du serveur Web ou l’état généré. Ce champ n’est disponible que pour les actions de type **Service Web** et **Message d’exportation pour la gestion des états électroniques**. |
| Afficher la boîte de dialogue                 | Définissez cette option sur **Oui** si une boîte de dialogue doit être présentée à l’utilisateur avant la génération des états. Ce champ n’est disponible que pour les actions de type **Message d’exportation pour la gestion des états électroniques**. |

##### <a name="message-processing-action-types"></a>Types d’actions de traitement des messages

Les options suivantes sont disponibles dans le champ **Type d’action** :

- **Créer un message** : utilisez ce type d’action pour permettre aux utilisateurs de créer manuellement des messages sur la page **Message électronique**. Un statut initial ne peut pas être paramétré pour une action de ce type.
- **Renseigner les enregistrements** : une action du type **Renseigner les enregistrements** doit déjà être paramétrée. Associez ce type d’action à une action de type Renseigner les enregistrements pour activer son inclusion dans le traitement. Il est supposé que ce type d’action est utilisé pour la première action dans le traitement des messages (lorsqu’aucun message électronique n’a été créé à l’avance) ou pour une action qui ajoute des éléments de message à un message précédemment créé par une action du type **Créer un message**. Par conséquent, pour les actions de ce type, un statut de résultats ne peut être paramétré que pour les éléments de message. Un statut initial ne peut être paramétré que pour les messages.
- **Niveau d’exécution du message** : utilisez ce type d’action pour paramétrer une classe exécutable à évaluer au niveau du message.
- **Niveau d’exécution de l’élément de message** : utilisez ce type d’action pour paramétrer une classe exécutable à évaluer au niveau de l’élément de message.
- **Exportation de la gestion des états électroniques** : utilisez ce type d’action pour les actions devant générer un état basé sur une configuration d’exportation de la gestion des ER au niveau de l’élément de message.
- **Message d’exportation pour la gestion des états électroniques** : utilisez ce type d’action pour les actions devant générer un état basé sur une configuration d’exportation de la gestion des ER au niveau du message (par exemple, lorsqu’un message ne contient pas d’éléments de message).
- **Importation de la gestion des états électroniques** : utilisez ce type d’action pour les actions devant générer un état basé sur une configuration d’importation de la gestion des ER.
- **Traitement utilisateur au niveau du message** : utilisez ce type d’action pour les actions qui impliquent certaines actions manuelles de l’utilisateur au niveau des messages. Par exemple, l’utilisateur peut mettre à jour le statut des messages.
- **Traitement utilisateur** : utilisez ce type d’action pour les actions qui impliquent certaines actions manuelles de l’utilisateur au niveau de l’élément de message. Par exemple, l’utilisateur peut mettre à jour le statut des éléments de messages.
- **Service Web** : utilisez ce type d’action pour les actions devant transmettre l’état généré à un service Web. Ce type d’action n’est pas utilisé pour la génération d’états de communication de factures d’achat et client italiens. Pour les actions de type **Service Web**, la page **Actions de traitement des messages** comprend un organisateur **Détails divers** où vous pouvez préciser un texte de confirmation. Ce texte de confirmation s’affiche aux utilisateurs avant le traitement des requêtes au service Web sélectionné.
- **Vérification de la demande** : utilisez ce type d’action pour demander une vérification à partir d’un serveur.

#### <a name="initial-statuses-fasttab"></a>Organisateur Statuts initiaux

> [!NOTE]
> L’organisateur **Statuts initiaux** n’est pas disponible pour les actions dont le type d’action initial est défini sur **Créer un message**.

| Champ               | Description |
|---------------------|-------------|
| Statut de l’élément de message | Sélectionnez le statut de l’élément de message indiquant que l’action de traitement du message sélectionné doit être évaluée. |
| Description         | Description du statut de l’élément de message sélectionné. |

#### <a name="result-statuses-fasttab"></a>Organisateur Statuts de résultat

| Champ               | Description |
|---------------------|-------------|
| Statut du message      | Sélectionnez les statuts de message indiquant que l’action de traitement du message sélectionné doit être évaluée. Ce champ est disponible uniquement pour les actions de traitement de message qui sont évaluées au niveau de message. Par exemple, il est disponible pour les actions des types **Exportation de la gestion des états électroniques** et **Importation de la gestion des états électroniques**, mais n’est pas disponible pour les actions des types **Traitement utilisateur** et **Niveau d’exécution de l’élément de message**. |
| Description         | Description du statut de message sélectionné. |
| Type de réponse       | Type de réponse du statut de message sélectionné. |
| Statut de l’élément de message | Sélectionnez les statuts résultants devant être disponibles une fois l’action de traitement du message sélectionné évaluée. Ce champ est disponible uniquement pour les actions de traitement de message qui sont évaluées au niveau de l’élément de message. Par exemple, il est disponible pour les actions des types **Traitement utilisateur** et **Niveau d’exécution de l’élément de message**. Pour les actions de traitement de messages évaluées au niveau du message, ce champ affiche le statut de l’élément de message paramétré pour le statut de message sélectionné. |

Le tableau suivant indique les statuts de résultat à paramétrer pour différents types d’actions et types de réponses.

| Type de réponse/d’action de message électronique | Exécution réussie | Erreur commerciale | Erreur technique | Défini par l’utilisateur | Annuler |
|----------------------------------------------|-----------------------|----------------|-----------------|--------------|--------|
| Créer un message                               | O                     |                |                 |              |        |
| Exportation de la gestion des états électroniques                  | O                     |                |                 |              |        |
| Importation de la gestion des états électroniques                  |                       |                |                 |              |        |
| Service Web                                  | O                     |                | O               |              |        |
| Traitement des utilisateurs                              |                       |                |                 |              |        |
| Niveau d’exécution du message                      |                       |                |                 |              |        |
| Renseigner les enregistrements                             |                       |                |                 |              |        |
| Niveau d’exécution de l’élément de message                 |                       |                |                 |              |        |
| Vérification de la demande                         | O                     | O              | O               |              |        |
| Message d’exportation pour la gestion des états électroniques          | O                     |                |                 |              |        |
| Traitement utilisateur au niveau du message                |                       |                |                 |              |        |

### <a name="electronic-message-processing"></a>Traitement du message électronique

Le traitement de message électronique est un concept de base de la fonctionnalité de messages électroniques. Il regroupe les actions à évaluer pour les messages électroniques. Les actions peuvent être liées via un statut initial et un statut de résultat. Sinon, les actions de type **Traitement utilisateur** peuvent être démarrées individuellement. Dans la page **Traitement du message électronique** (**Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Traitement du message électronique**), vous pouvez également sélectionner des champs supplémentaires à prendre en charge pour le traitement au niveau du message ou au niveau des éléments du message.

L’organisateur **Action** vous permet d’ajouter des actions prédéfinies au traitement. Vous pouvez spécifier si une action doit être exécutée séparément, ou si elle peut être démarrée par le traitement. Pour spécifier qu’une action du traitement ne peut être lancée que par un utilisateur, définissez le champ **Exécuter séparément** sur **Oui** pour cette action. Si une action doit être démarrée par le traitement des messages ou des éléments de message dont le statut est celui défini dans le statut initial de l’action, définissez le champ **Exécuter séparément** sur **Non**. Les actions du type **Action utilisateur** doivent toujours être exécutées séparément.

Parfois, plusieurs actions doivent être regroupées en séquence, même si la première action est paramétrée de manière à être exécutée séparément. Par exemple, un utilisateur doit initialiser la génération d’états mais, immédiatement après que les états ont été générés, ils doivent être envoyés vers un service Web et la réponse du service Web doit être répercutée dans le système. Dans ce cas, vous pouvez créer une séquence inséparable des actions qui doivent toujours être exécutées ensemble. Sous l’organisateur **Action**, sélectionnez **Séquences inséparables** au-dessus de la grille, puis créez une séquence. Ensuite, pour toutes les actions qui doivent s’exécuter ensemble, sélectionnez la séquence dans le champ **Séquence inséparable**. Dans ce cas, le champ **Exécuter séparément** peut être défini sur **Oui** pour la première action dans la séquence mais sur **Non** pour toutes les autres actions.

L’organisateur **Champs supplémentaires de l’élément du message** vous permet d’ajouter des champs supplémentaires prédéfinis liés aux éléments de message. Vous devez ajouter des champs supplémentaires pour chaque type d’élément de message auquel les champs sont liés.

L’organisateur **Champs supplémentaires du message** vous permet d’ajouter des champs supplémentaires prédéfinis liés aux messages.

L’organisateur **Rôles de sécurité** vous permet de paramétrer les rôles de sécurité prédéfinis dans le système pour un traitement spécifique. Les utilisateurs disposant d’un rôle spécifique verront uniquement le traitement qui est défini pour ce rôle.

L’organisateur **Traitement par lot** vous permet de paramétrer le traitement pour fonctionner à un régime de lots.

## <a name="work-with-the-electronic-messages-functionality"></a>Utiliser la fonctionnalité de messages électroniques

Si vous travaillez au niveau du message, la page **Messages électroniques** (**Taxe** \> **Recherches et états** \> **Messages électroniques** \> **Messages électroniques**) est plus utile. Si vous travaillez au niveau de la collecte de données (élément de message), la page **Éléments du message électronique** (**Taxe** \> **Recherches et états** \> **Messages électroniques** \> **Éléments du message électronique**) est plus utile.

### <a name="electronic-messages"></a>Messages électroniques

La page **Messages électroniques** présente le traitement disponible pour vous, en fonction de votre rôle. Les rôles de sécurité sont associés au traitement dans le paramétrage de celui-ci. Pour chaque traitement disponible pour vous, la page affiche les messages électroniques et les informations connexes.

L’organisateur **Messages** affiche les messages électroniques du traitement sélectionné. Selon le statut du message sélectionné et le traitement prédéfini, vous pouvez exécuter certaines actions en sélectionnant les boutons au-dessus de la grille :

- **Nouveau** : Ce bouton est associé aux actions du type **Créer un message**.
- **Supprimer** : Ce bouton est disponible si la case à cocher **Autoriser la suppression** est activée pour le statut actuel du message sélectionné.
- **Collecte des données** – Ce bouton est associé aux actions de type **Renseigner les enregistrements**.
- **Générer un état** : Ce bouton est associé aux actions du type **Message d’exportation pour la gestion des états électroniques**.
- **Envoyer un état** : Ce bouton est associé aux actions du type **Service Web**.
- **Importer une réponse** – Ce bouton est associé aux actions de type **Importation de la gestion des états électroniques**.
- **Mettre à jour le statut** : Ce bouton est associé aux actions du type **Traitement utilisateur au niveau du message**.
- **Éléments du message** : Ouvre la page **Éléments du message électronique**.

L’organisateur **Journal des actions** présente des informations sur toutes les actions exécutées pour le message sélectionné. Si une action a causé une erreur, les informations relatives à l’erreur sont jointes à la ligne associée dans la grille. Pour vérifier les informations sur l’erreur, sélectionnez la ligne dans la grille, puis sélectionnez le bouton **Pièce jointe** (le symbole du trombone) dans le coin supérieur droit de la page.

L’organisateur **Champs supplémentaires du message** affiche tous les champs supplémentaires définis pour les messages dans le paramétrage du traitement. Il affiche également les valeurs de ces champs supplémentaires.

L’organisateur **Éléments du message** affiche tous les éléments du message liés au message sélectionné. Selon le statut du message sélectionné, vous pouvez exécuter certaines actions en sélectionnant les boutons au-dessus de la grille :

- **Supprimer** - Ce bouton est disponible si la case à cocher **Autoriser la suppression** est activée pour le statut actuel de l’élément de message sélectionné.
- **Mettre à jour le statut** – Ce bouton est associé aux actions de type **Traitement utilisateur**.
- **Document d’origine** – Ouvre une page qui affiche le document d’origine de l’élément de message sélectionné.

Tous les états qui ont déjà été générés et reçus pour un message sont liés à ce message. Pour examiner les pièces jointes associées à un message, sélectionnez le message, puis sélectionnez le bouton **Pièce jointe** (le symbole du trombone) dans le coin supérieur droit de la page.

![Bouton Pièce jointe](media/attachment-icon.png)

La page **Pièces jointes** affiche toutes les pièces jointes associées au message sélectionné. Pour afficher un fichier, sélectionnez-le dans la liste à gauche, puis sélectionnez **Ouvrir** sur le volet Actions.

![Bouton Ouvrir](media/open-button.png)

Vous pouvez également consulter les pièces jointes associées à une action spécifique qui a été précédemment exécutée pour un message. Dans la page **Messages électroniques**, sélectionnez le message dans l’organisateur **Messages**, sélectionnez l’action dans l’organisateur **Journal d’actions**, puis sélectionnez le bouton **Pièce jointe** dans le coin supérieur droit de la page.

Vous pouvez également exécuter l’ensemble du traitement ou seulement une action spécifique en sélectionnant **Exécuter le traitement** sur le volet Action.

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
<td>Nom du traitement utilisé pour créer l’élément du message.</td>
</tr>
<tr>
<td>Élément du message</td>
<td>ID de l’élément du message. Cet ID est affecté automatiquement, selon la souche de numéros <strong>Élément du message</strong> définie sur la page <strong>Paramètres de comptabilité</strong>.</td>
</tr>
<tr>
<td>Date de l’élément de message</td>
<td>Date de création de l’élément du message.</td>
</tr>
<tr>
<td>Type d’élément de message</td>
<td>Type de l’élément du message. Plusieurs types d’éléments de messages peuvent être paramétrés pour le même traitement (par exemple, <strong>Factures entrantes</strong> et <strong>Factures sortantes</strong>). Ce champ peut être renseigné automatiquement uniquement si une facture est ajoutée à la table Éléments du message.</td>
</tr>
<tr>
<td>Statut de l’élément de message</td>
<td>Statut actuel de l’élément du message. Les statuts disponibles varient, en fonction du type de l’élément du message. Voici quelques exemples :
<ul>
<li><strong>Renseigné</strong> : Un enregistrement a été ajouté à la table Éléments du message.</li>
<li><strong>Évalué</strong> : Des attributs supplémentaires ont été calculés pour l’élément du message.</li>
<li><strong>Déclaré</strong> : L’élément du message a bien été ajouté à un état.</li>
<li><strong>Exclu</strong> : Ce statut peut être utile si vous devez exclure des éléments du message d’un état avant qu’il soit exporté.</li>
</ul>
</td>
</tr>
<tr>
<td>Date de transmission</td>
<td>Pour le traitement qui transmet automatiquement un état généré en dehors du système, date à laquelle l’élément du message a été transmis.</td>
</tr>
<tr>
<td>Numéro du document</td>
<td>Ce champ est automatiquement renseigné en fonction du paramétrage de l’action de renseignement des enregistrements. Ce champ peut être renseigné automatiquement uniquement si une facture est ajoutée à la table Éléments du message.</td>
</tr>
<tr>
<td>Numéro de compte</td>
<td>Numéro de compte d’un client ou d’un fournisseur (ou autre valeur de champ, selon le champ défini dans l’action Renseigner les enregistrements). Ce champ peut être renseigné automatiquement uniquement si une facture est ajoutée à la table Éléments du message.</td>
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
<td>Actions suivantes pouvant être démarrées pour le statut actuel de l’élément du message.</td>
</tr>
</tbody>
</table>

L’onglet **Champs supplémentaires** affiche les champs supplémentaires de l’élément du message sélectionné, et leurs valeurs.

#### <a name="run-processing"></a>Exécuter le traitement

Sélectionnez **Exécuter le traitement** sur le volet Actions pour exécuter le traitement des éléments du message. Pour exécuter une action spécifique, dans la boîte de dialogue **Exécuter le traitement**, définissez l’option **Choisir l’action** sur **Oui**, puis sélectionnez une action. Pour exécuter le traitement complet, laissez l’option **Choisir l’action** définie sur **Non**.

#### <a name="generate-report"></a>Générer un état

Sélectionnez **Générer un état** sur le volet Actions pour générer un état. Ce bouton est associé aux actions du type **Exportation pour la gestion des états électroniques**.

#### <a name="update-status"></a>Mise à jour du statut

Sélectionnez **Mettre à jour le statut** sur le volet Actions pour mettre à jour le statut d’un ou de plusieurs éléments du message. Dans la boîte de dialogue **Mettre à jour le statut**, utilisez l’organisateur **Enregistrements à inclure** pour sélectionner les éléments de message à mettre à jour. Assurez-vous de définir correctement les critères de sélection, car les statuts d’élément du message sont mis à jour selon ces critères, le statut initial de l’action sélectionnée, et la valeur **Nouveau statut** spécifiée. Une fois la mise à jour du statut terminée, il sera difficile de déterminer les éléments mis à jour. Par conséquent, il sera difficile d’annuler la mise à jour de statut.

#### <a name="electronic-messages"></a>Messages électroniques

Sélectionnez **Messages électroniques** dans le volet Actions pour réviser un message électronique associé à l’élément de message sélectionné.

Vous pouvez également réviser tous les fichiers associés à un élément de message spécifique. Sélectionnez le champ **Message** pour l’élément de message, ou sélectionnez **Messages électroniques** dans le volet Actions. Ensuite, dans la page **Message électronique**, sélectionnez le message dont vous souhaitez examiner les fichiers, puis sélectionnez le bouton **Pièce jointe** (le symbole du trombone) dans le coin supérieur droit de la page.

![Bouton Pièce jointe](media/attachment-icon.png)

La page **Pièces jointes** affiche toutes les pièces jointes associées au message. Pour afficher un fichier, sélectionnez-le dans la liste à gauche, puis sélectionnez **Ouvrir** sur le volet Actions.

![Bouton Ouvrir](media/open-button.png)

#### <a name="original-document"></a>Document d’origine

Sélectionnez **Document d’origine** sur le volet Actions pour ouvrir le document d’origine de l’élément du message sélectionné.

## <a name="example-set-up-and-run-processing-to-call-a-simple-er-exporting-format-to-generate-an-excel-report"></a>Exemple : paramétrez et exécutez le traitement pour appeler un format d’exportation d’états électroniques pour générer un état Excel

Après avoir créé votre format d’ER, l’avoir mappé à des sources de données, et l’avoir terminé, vous pouvez l’exécuter à l’aide de l’espace de travail **Gestion des états électroniques**. Un état est généré que vous pouvez enregistrer localement.

Pour contrôler les aspects suivants du processus de gestion d’états, vous devez paramétrer le traitement par messagerie électronique :

- Enregistrez les informations sur l’utilisateur ayant généré l’état.
- Enregistrez les informations sur le moment de génération de l’état.
- Enregistrez les états générés pour les périodes précédentes.

Cette section fournit un exemple qui indique comment paramétrer la messagerie électronique pour générer un état basé sur un format d’exportation ER pour Excel. Si vous souhaitez suivre cet exemple, le format d’exportation Excel des états électroniques doit déjà être créé, mappé sur des sources de données, et être terminé. En outre, une souche de numéros doit déjà être paramétrée pour les messages électroniques.

Lorsque vous créez le traitement, il est utile de commencer par définir les actions et les statuts de traitement à paramétrer. L’illustration suivante présente à quoi ce traitement ressemble pour cet exemple.

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

3. Définissez l’option **Modification utilisateur** sur **Oui** de permettre aux utilisateurs de modifier le champ.

#### <a name="create-message-processing-actions"></a>Créer des actions de traitement des messages

Pour cet exemple, vous allez créer les actions suivantes :

- **Créer un message**
- **Mettre à jour sur Préparé**
- **Générer un état**
- **Mettre à jour sur le statut initial** (facultatif)

1. Accédez à **Taxe \> Paramétrage \> Messages électroniques \> Actions de traitement du message**.
2. Créez une action nommée **Créer un message**. Sur l’organisateur **Général**, dans le champ **Type d’action**, sélectionnez **Créer un message**.
3. Créez une action nommée **Mettre à jour sur Préparé**, puis définissez les champs suivants :

    - Sur l’organisateur **Général**, dans le champ **Type d’action**, sélectionnez **Traitement utilisateur au niveau du message**.
    - Sur l’organisateur **Statuts initiaux**, dans le champ **Statut du message**, sélectionnez **Nouveau**.
    - Sur l’organisateur **Statuts de résultat**, dans le champ **Statut du message**, sélectionnez **Préparé**. Dans le champ **Type de réponse**, entrez **Exécution réussie**.

4. Créez une action nommée **Générer un état**, puis définissez les champs suivants :

    - Sur l’organisateur **Général**, dans le champ **Type d’action**, sélectionnez **Exportation de la gestion des états électroniques**. Dans le champ **Mise en correspondance des formats**, sélectionnez le format d’exportation ER. Les options sont **Excel**, **XML**, **JSON**, **Texte**, et **Autre**.
    - Sur l’organisateur **Statuts initiaux**, dans le champ **Statut du message**, sélectionnez **Préparé**.
    - Sur l’organisateur **Statuts de résultat**, dans le champ **Statut du message**, sélectionnez **Généré**. Dans le champ **Type de réponse**, entrez **Exécution réussie**.

    ![Générer une action d’état](media/generate-report-action.png)

5. Facultatif : Pour permettre aux utilisateurs de regénérer un état plusieurs fois, vous pouvez créer une action **Mettre à jour sur le statut initial** et définir les champs suivants :

    - Sur l’organisateur **Général**, dans le champ **Type d’action**, sélectionnez **Traitement utilisateur au niveau du message**.
    - Sur l’organisateur **Statuts initiaux**, dans le champ **Statut du message**, sélectionnez **Généré**.
    - Dans l’organisateur **Statuts de résultat**, ajoutez une ligne distincte pour les deux statuts de message (**Préparé** et **Nouveau**). Pour les deux lignes, définissez le champ **Type de réponse** sur **Avec succès**.

#### <a name="electronic-message-processing"></a>Traitement du message électronique

Dans cet exemple, toutes les actions doivent être paramétrées de manière à ce que elles s’exécutent séparément. On suppose que chaque action est lancée par l’utilisateur.

1. Accédez à **Taxe \> Paramétrage \> Messages électroniques \> Traitement du message électronique**.
2. Ajoutez un enregistrement pour votre traitement, puis ajoutez toutes les actions définies précédemment et un champ supplémentaire.
3. Facultatif : dans l’organisateur **Rôles de sécurité**, définissez des rôles de sécurité pour votre traitement afin de limiter l’accès à l’état spécifique.
4. Accédez à **Taxe \> Recherches et états \> Messages électroniques \> Messages électroniques**.
5. Sélectionnez **Nouveau** pour créer un message. À ce stade, vous pouvez ajouter des dates et une description. Vous pouvez également mettre à jour la valeur du champ supplémentaire au besoin.

    ![Créer un message électronique](media/create-electronic-message.png)

La grille sur l’organisateur **Journal des actions** est renseignée automatiquement avec un journal de toutes les actions effectuées sur le message.

Vous pouvez désormais supprimer ou mettre à jour le statut du message. Pour mettre à jour le statut de message, sélectionnez **Mettre à jour le statut**. Dans le champ **Nouveau statut**, sélectionnez **Préparé**, puis sélectionnez **Ajouter**.

![Mettre à jour le statut du message](media/update-status.png)

Le statut du message est mis jour sur **Préparé**, et vous pouvez désormais générer l’état en sélectionnant **Générer l’état**. L’état est généré, et le statut du message et le journal des actions sont mis à jour. Pour afficher l’état généré, sélectionnez le bouton **Pièce jointe** (le symbole du trombone) dans le coin supérieur droit de la page.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]