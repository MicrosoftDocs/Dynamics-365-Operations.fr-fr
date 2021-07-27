---
title: Paramétrer un message électronique
description: Cette rubrique fournit des informations générales sur la configuration de la fonctionnalité Messages électroniques (ME).
author: liza-golub
ms.date: 07/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-23
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 947170d1db132ca5a6b7caed0e47ee814b9148cc
ms.sourcegitcommit: 73d320d2103f2b0c6ecbb2b9df746469bc544ea2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2021
ms.locfileid: "6433782"
---
# <a name="set-up-electronic-messages"></a>Paramétrer un message électronique

[!include [banner](../includes/banner.md)]

La fonctionnalité **Messages électroniques** (ME) vous aide à gérer différents processus de génération d’états électroniques pour chaque type de document. Dans certains scénarios complexes qui prennent en charge des [fonctionnalités spécifiques à un pays](electronic-messaging.md#country-specific-regulatory-features-supported-by-the-em-functionality), la fonctionnalité EM est paramétrée de manière à avoir une combinaison de nombreux statuts de message, de statuts d’éléments de message, d’actions, de champs supplémentaires, et de classes exécutables. Pour ces scénarios, les packages d’entités de données sont disponibles pour l’importation. Si vous utilisez ces packages d’entité de données, importez-lez dans une entité juridique à l’aide de l’outil de gestion des données. Pour plus d’informations sur l’utilisation de l’outil de gestion de données, voir [Gestion des données](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

Si vous n’importez pas un packages d’entité de données, vous pouvez paramétrer manuellement la fonctionnalité EM. Dans ce cas, vous devez paramétrer les éléments suivants :

- [Souches de numéros](#sequences)
- [Types d'élément de message](#types)
- [Statuts de l'élément de message](#item)
- [Statuts du message](#statuses)
- [Champs supplémentaires](#additional)
- [Paramètres de la classe exécutable](#executable)
- [Actions Renseignement des enregistrements](#populate)
- [Applications Web](#applications)
- [Paramètres du service Web](#settings)
- [Actions de traitement des messages](#actions)
- [Traitement du message électronique](#processing)

Les sections suivantes fournissent des informations supplémentaires sur chacun de ces éléments.

## <a name="number-sequences"></a><a id="sequences"></a>Souches de numéros

Paramétrez les souches de numéros pour les messages et les éléments de message. Les souches de numéros sont utilisées pour numéroter automatiquement les messages et les éléments de message. Les numéros affectés sont utilisés comme identificateurs uniques pour les messages et éléments de message dans le système. Vous pouvez paramétrer des souches de numéros pour la messagerie électronique en accédant à **Comptabilité générale** \> **Paramétrage de la comptabilité** \> **Paramètres de comptabilité**.

## <a name="message-item-types"></a><a id="types"></a>Types d'élément de message

Les types d’éléments du message identifient les types d’enregistrements utilisés dans les messageries électroniques. Vous pouvez paramétrer les types d’éléments en accédant à **Taxe** \> **Paramétrage** \> **Messageries électroniques** \> **Types d’élément de message**.

## <a name="message-item-statuses"></a><a id="item"></a>Statuts de l'élément de message

Les statuts d’élément de message identifient les statuts qui s’appliquent aux éléments du message dans le traitement que vous paramétrez. Vous pouvez paramétrer les status d’éléments en accédant à **Taxe** \> **Paramétrage** \> **Messageries électroniques** \> **Statuts d’élément de message**.

Le paramètre **Autoriser la suppression** d’un statut d’élément de message définit si vous pouvez supprimer des éléments de message ayant ce statut dans la page **Messages électroniques** ou **Éléments du message électronique**.

## <a name="message-statuses"></a><a id="statuses"></a>Statuts du message

Paramétrez les statuts du message qui doivent être disponibles dans le traitement des messages. Vous pouvez paramétrer les status de message en accédant à **Taxe** \> **Paramétrage** \> **Messageries électroniques** \> **Statuts d’élément de message**.

Le tableau suivant décrit les champs de la page **Statuts du message**.

| Nom du champ          | Description |
|---------------------|-------------|
| Statut du message      | Permet d’entrer un nom unique pour le statut du message. Les statuts de message sont utilisés pour caractériser l’état d’un message électronique à tout moment. Le nom que vous entrez s’affiche dans la page **Messages électroniques** et dans un journal associé aux messages électroniques. |
| Description         | Entrez une description du statut de message. |
| Type de réponse       | Sélectionnez le type de réponse pour le statut de message. Certaines actions d’un traitement peuvent produire plusieurs types de réponse. Par exemple, une action du type **Service Web** peuvent entraîner une réponse de type **Exécution réussie** ou **Erreur technique** selon le résultat de leur exécution. Dans ce cas, définissez des statuts de message pour les deux types de réponses. Pour en savoir plus sur les types d’action et les types de réponse qui y sont associés, consultez la section [Types d’actions de traitement des messages](#action-types) plus loin dans cette rubrique. |
| Statut de l'élément de message | Parfois, le statut d’un message électronique doit influencer le statut des éléments de message associés. Sélectionnez un statut d’élément de message dans ce champ pour l’associer au statut du message. |
| Autoriser la suppression        | Activez cette case à cocher si les utilisateurs doivent pouvoir supprimer les message électroniques ayant ce statut sur la page **Messages électroniques**. |

## <a name="additional-fields"></a><a id="additional"></a>Champs supplémentaires

La fonctionnalité EM vous permet de collecter des enregistrements à partir de tables transactionnelles dans Microsoft Dynamics 365 Finance comme éléments de message. De cette manière, vous pouvez préparer les enregistrements pour la gestion des états électroniques puis les générer. Toutefois, les tables transactionnelles n’ont parfois pas assez d’informations pour renseigner les enregistrements de manière à respecter les exigences de la génération d’états. Pour renseigner toutes les informations à déclarer pour un enregistrement, vous pouvez paramétrer des champs supplémentaires. Les champs supplémentaires peuvent être associés à des messages et des éléments de message. Vous pouvez paramétrer des champs supplémentaires en accédant à **Taxe** \> **Paramétrage** \> **Messageries électroniques** \> **Champs supplémentaires**.

Le tableau suivant décrit les champs généraux de la page **Champs supplémentaires**.

| Champ       | Description  |
|-------------|-------------|
| Nom du champ  | Entrez le nom d’un champ supplémentaire pour des messages électroniques ou des éléments de message qui sont liés au processus. Ce nom est affiché dans l’interface utilisateur (IU) lorsque vous utilisez le processus. Le nom peut également être utilisé dans les configurations États électroniques (ER) liées au processus. |
| Description  | Entrez une description des champs supplémentaires. |
| Modification utilisateur   | Définissez cette option sur **Oui** si les utilisateurs doivent pouvoir modifier la valeur du champ supplémentaire à partir de l’IU. |
| Compteur     | Définissez cette option sur **Oui** si le champ supplémentaire doit contenir une souche de numéros dans un message électronique. La valeur du champ supplémentaire sera renseignée automatiquement lors de l’exécution d’une action de type **Exportation de la gestion des états électroniques**. |
| Masqué      | Définissez cette option sur **Oui** si le champ supplémentaire doit être masqué dans l'interface utilisateur sur la page **Messages électroniques** ou la page **Éléments de message électronique**. |

Sous le raccourci **Valeurs**, vous pouvez prédéfinir les valeurs qu'un champ supplémentaire peut avoir. Ces valeurs sont ensuite disponibles pour les utilisateurs à sélectionner. Par conséquent, ils n'ont pas besoin d'être remplis manuellement pendant le traitement. Le tableau suivant décrit ces champs.

| Champ                | Description  |
|----------------------|-------------|
| Valeur de champ          | Entrez la valeur du champ à utiliser pour un message ou un élément de message lors de la génération d’états. |
| Description          | Entrez une description de la valeur du champ. |
| Type de compte         | Certaines valeurs de champs peuvent être limitées à des types de comptes spécifiques. Sélectionner l’une des valeurs suivantes : **Tous**, **Client** et **Fournisseur**. |
| Compte – valide pour         | Si vous avez sélectionné **Client** ou **Fournisseur** dans le champ **Type de compte**, vous pouvez limiter davantage l’utilisation de la valeur du champ à un groupe ou à une table spécifique. |
| Numéro de compte/groupe | Si vous avez sélectionné **Client** ou **Fournisseur** dans le champ **Type de compte**, et si vous avez entré un groupe ou une table dans le champ **Code du compte**, vous pouvez entrer un groupe ou un contragent spécifique dans ce champ. |
| Date d’effet            | Spécifiez la date à laquelle la valeur doit commencer à être prise en compte. |
| Expiration           | Spécifiez la date à laquelle la valeur doit arrêter d’être prise en compte. |

Par défaut, les combinaisons des critères définis par les champs **Numéro de compte/groupe**, **Code compte**, **Date d’effet** et **Date d’expiration** n’influencent pas la sélection des valeurs pour les champs supplémentaires. Toutefois, ces combinaisons peuvent être utilisées dans une classe exécutable pour implémenter un logique spécifique de calcul des valeurs pour les champs supplémentaires.

## <a name="executable-class-settings"></a><a id="executable"></a>Paramètres de la classe exécutable

Une classe exécutable est une méthode ou une classe X++ que le traitement de message électronique peut appeler en relation à une action si une certaine évaluation est nécessaire pour le processus.

Vous pouvez configurer manuellement une classe exécutable qui doit être appelée pendant le traitement en allant dans **Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Paramètres de la classe exécutable**. Sur la page **Paramètres de la classe exécutable**, créez une ligne et définissez les champs suivants.

| Champ                 | Description  |
|-----------------------|-------------|
| Classe exécutable      | Entrez le nom qui sera utilisé lors du paramétrage d’une action de traitement de message en lien avec la classe appelée. |
| Description           | Entrez une description de la classe exécutable. |
| Nom de la classe exécutable | Sélectionnez une classe exécutable X++. |
| Niveau d'exécution       | Ce champ est défini automatiquement, car la valeur est prédéfinie pour la classe exécutable sélectionnée. Ce champ limite le niveau auquel on exécute l’évaluation associée. |
| Description de la classe     | Ce champ est défini automatiquement, car la valeur est prédéfinie pour la classe exécutable sélectionnée. |
| Type d'action           | Ce champ est disponible lorsque la fonctionnalité **\[EM\] Type d'action de classe exécutable** est activée dans l'espace de travail **Gestion des fonctionnalités**. Utilisez ce champ pour spécifier le type d'action pour la classe exécutable. Ce champ donne un contrôle plus précis sur les prochaines actions disponibles pour le message électronique sur la page **Messages électroniques**. |

Certaines classes exécutables peuvent avoir des paramètres obligatoires qui doivent être définis avant la première exécution de la classe exécutable. Pour définir ces paramètres, dans le volet Actions, sélectionnez **Paramètres**. Dans la boîte de dialogue qui s’affiche, définissez les champs, puis sélectionnez **OK**. Il est important de sélectionner **OK**. Dans le cas contraire, les paramètres ne seront pas enregistrés dans la base de données et la classe exécutable ne sera pas appelée correctement.

## <a name="populate-records-actions"></a><a id="populate"></a>Actions Renseignement des enregistrements

Vous utilisez les actions de renseignement des enregistrements pour paramétrer des actions qui ajoutent des enregistrements à la table Éléments de message de sorte qu’ils puissent être ajoutés à un message électronique. Par exemple, si votre message électronique doit déclarer des factures client, vous devez paramétrer une action Renseigner les enregistrements qui est liée au champ **Source de données** dans la table Journal des factures client.

Vous pouvez paramétrer des actions de renseignements d’enregistrements en accédant à **Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Action de renseignement d’enregistrements**. Créez un enregistrement pour chaque action qui doit ajouter des enregistrements à la table, puis définissez les champs suivants.

| Champ       | Description |
|-------------|-------------|
| Nom        | Entrez un nom pour l’action qui renseigne les enregistrements dans votre processus. |
| Description | Entrez une description de l’action Renseigner les enregistrements. |

Dans l’organisateur **Paramétrage des sources de données**, ajoutez une ligne pour chaque source de données utilisée pour le processus, puis définissez les champs suivants.

| Champ                  | Description |
|------------------------|-------------|
| Nom                   | Entrez un nom pour la source de données. |
| Type d'élément de message      | Sélectionnez le type d’élément de message à utiliser lorsque des enregistrements sont créés pour la source de données. |
| Type de compte           | Sélectionnez le type de compte à associer à des enregistrements de la source de données. |
| Nom de la table principale      | Sélectionnez la table à utiliser comme source de données. |
| Champ Numéro du document  | Sélectionnez le champ dans lequel le numéro de document doit être extrait dans la table maître. La valeur de ce champ est utilisée comme valeur du champ **Numéro de document** pour l'élément de message. |
| Champ Date du document    | Sélectionnez le champ dans lequel la date du document doit être extrait dans la table maître. La valeur de ce champ est utilisée comme valeur du champ **Date de l’élément de message** pour l'élément de message. |
| Champ Compte du document | Sélectionnez le champ dans lequel le compte du document doit être extrait dans la table maître. La valeur de ce champ est utilisée comme valeur du champ **Numéro de compte** pour l'élément de message. |
| Société                | Ce champ est disponible lorsque la fonctionnalité **Requêtes inter-sociétés pour les actions de remplissage des enregistrements** est activée dans l'espace de travail **Gestion des fonctionnalités**. Utilisez cette fonctionnalité pour configurer des sources de données intersociétés pour les actions de remplissage des enregistrements. Les données peuvent être récupérées auprès de plusieurs entreprises. |
| Requête utilisateur             | <p>Si vous configurez une requête en sélectionnant **Modifier la requête** au-dessus de la grille et que vous spécifiez les critères qui doivent être appliqués à la table principale sélectionnée à partir de laquelle les données sont renseignées, cette case à cocher est automatiquement sélectionnée. Sinon, tous les enregistrements seront renseignés à partir de la source de la table maître.</p><p>Quand la fonctionnalité **Requêtes inter-sociétés pour les actions de remplissage des enregistrements** est activée dans l'espace de travail **Gestion des fonctionnalités**, et les enregistrements doivent être collectés auprès de plusieurs sociétés, ajoutez une ligne pour chaque entité juridique supplémentaire qui doit être incluse dans le reporting. Pour chaque nouvelle ligne, sélectionnez **Modifier la requête** et spécifiez un critère associé qui est spécifique à l'entité juridique qui est spécifiée dans le champ **Société** sur la ligne. Lorsque vous avez terminé, la grille **Configuration des sources de données** contient des lignes pour toutes les entités juridiques qui doivent être incluses dans le reporting.</p> |

## <a name="web-applications"></a><a id="applications"></a>Applications Web

Utilisez les paramètres d’application Web pour paramétrer une application Web afin qu’elle prenne en charge l’autorisation Open Authorization (OAuth) 2.0. OAuth est la norme ouverte actuelle qui permet aux utilisateurs d’« accorder l’accès sécurisé délégué » à l’application en leur nom, sans partager leurs informations d’identification d’accès. Vous pouvez également accéder au processus d’autorisation en obtenant un code d’autorisation et un jeton d’accès. Vous pouvez définir les paramètres d’application Web en accédant à **Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Applications Web**.

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
| Le jeton d'accès expirera dans  | Le temps restant avant l’expiration du jeton d’accès. Ce champ est mis à jour automatiquement. | 
| Accepter                       | Permet de spécifier la propriété **Accepter** de la requête Web. Par exemple, entrez **application/vnd.hmrc.1.0+json**. |
| Type de contenu                 | Spécifiez le type de contenu. Par exemple, entrez **application/json**. |

En outre, les boutons suivants sont disponibles dans le volet Actions de la page **Applications Web** pour prendre en charge le processus d’autorisation :

- **Obtenir le code d’autorisation** – initialise l’autorisation de l’application Web. Cette fonction utilise le format ER spécifié dans le **Mappage des formats d'autorisation** pour générer une demande d'autorisation.
- **Obtenir un jeton d’accès** – initialise le processus d’obtention d’un jeton d’accès.
- **Actualiser le jeton d’accès** – Actualise un jeton d’accès. Cette fonction utilise le format ER spécifié dans le champ **Importer le mappage du modèle de jeton** pour importer des informations sur le jeton d'accès reçu.

Lorsqu’un jeton d’accès à une application Web est enregistré dans la base de données du système dans un format chiffré, il peut être utilisé pour les requêtes vers un service Web. À des fins de sécurité, l’accès au jeton doit être limité aux rôles de sécurité qui sont autorisés à traiter ces requêtes. Si quelqu'un d'extérieur au groupe de sécurité essaie d’envoyer une requête, il reçoivent une erreur indiquant qu’ils ne sont pas autorisés à interagir à l’aide de l’application Web sélectionnée. Pour paramétrer les rôles de sécurité qui ont accès au jeton d’accès, utilisez l’organisateur **Rôles de sécurité** de la page **Applications Web**. Si les rôles de sécurité ne sont pas définis pour une application Web, seul un administrateur système est en mesure d’interagir via cette application Web.

Pour chaque action avec l'application web sélectionnée, le raccourci **Journal des actions** enregistre des informations sur l'utilisateur, ainsi que la date et l'heure.

Certains services Web peuvent nécessiter l'inclusion de différents en-têtes dans les requêtes. L'administrateur système peut configurer des en-têtes supplémentaires et leurs valeurs sous le raccourci **En-têtes supplémentaires**, puis utilisez-les lors de la génération de la demande.

## <a name="web-service-settings"></a><a id="settings"></a>Paramètres du service Web

Utilisez des paramètres de service Web pour paramétrer la transmission de données directe à un service web. Vous pouvez définir les paramètres du service web en en accédant à **Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Paramètres des applications Web**.

Le tableau suivant décrit les champs de la page **Paramètres de service Web**.

| Champ                          | Description |
|--------------------------------|-------------|
| Service Web                    | Entrez un nom pour le service Web. |
| Description                    | Permet d’entrer une description du service Web. |
| Adresse Internet               | <p>Entrez l’adresse Internet du service Web. Si une application Web est spécifiée pour un service Web et que l’adresse Internet du service Web doit être identique à celle définie pour l’application Web sélectionnée, sélectionnez **Copier l’URL de base**. L'URL de base de l'application web est ensuite copiée dans ce champ.</p><p>**Avertissement :** les services tiers ou d'autres services que vous configurez ici ne nécessitent pas de certification et peuvent ne pas répondre aux normes de confidentialité de Microsoft. Vous devez examiner la documentation de confidentialité de chaque service et travailler avec chaque fournisseur de services pour en savoir plus sur le niveau de conformité fourni par son service. Vous devez vous assurer que ces services répondent à vos normes de sécurité, de confidentialité et juridiques. Vous êtes responsable de l'utilisation des services. Microsoft n'accorde aucune garantie ni condition expresse. Nous vous recommandons fortement d'utiliser uniquement des services qui fournissent des connexions sécurisées et autorisées, telles que HTTPS.</p> |
| Certificat                    | Sélectionnez un certificat de coffre de clés Azure précédemment paramétré. |
| Application Web                | Sélectionnez une application web précédemment paramétrée. |
| Type de réponse – XML        | Définissez cette option sur **Oui** si le type de réponse est XML. |
| Méthode de la demande                 | Spécifiez la méthode de demande. HTTP définit un ensemble de méthodes de demande qui indiquent l’action à effectuer pour une ressource donnée. La méthode de requête peut être **GET**, **POST**, ou une autre méthode HTTP. |
| En-tête de la demande                | Spécifiez les en-têtes de la demande. Un en-tête de requête est un en-tête HTTP qui peut être utilisé dans une requête HTTP. Ce n'est pas lié au contenu du message. |
| Accepter                         | Permet de spécifier la propriété Accepter de la requête web. |
| Accepter le codage                | Permet de spécifier la valeur Accepter le codage. L’en-tête HTTP de demande Accepter le codage publie l’encodage du contenu que le client peut comprendre. Cet encodage de contenu est généralement un algorithme de compression. |
| Type de contenu                   | Spécifiez le type de contenu. L’en-tête HTTP d’entité Type de contenu indique le type de support de la ressource. |
| Code de réponse réussie       | Permet de spécifier le code de statut HTTP indiquant la réussite de la requête. |
| Mise en correspondance des formats pour les en-têtes de demande | Permet de sélectionner le format d’états électroniques utilisé pour générer les en-têtes de requête Web. |

## <a name="message-processing-actions"></a><a id="actions"></a>Actions de traitement des messages

Vous utilisez des actions de traitement des messages pour créer des actions pour vos processus et définir leurs paramètres. Vous pouvez paramétrer des actions de traitement des messages en accédant à **Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Actions de traitement des messages**.

Les tableaux suivants décrivent les champs de la page **Actions de traitement des messages**.

### <a name="general-fasttab"></a>Organisateur Général

| Champ                                     | Description |
|-------------------------------------------|-------------|
| Type d’action                               | Permet de sélectionner le type de l’action. Pour plus d’informations sur les options disponibles, voir la section [Types d’actions de traitement des messages](#action-types) plus loin dans cette rubrique. |
| Mise en correspondance des formats                            | Sélectionnez le format d’ER qui doit être appelé pour l’action. Ce champ n’est disponible que pour les actions de types **Exportation de la gestion des états électroniques**, **Importation de la gestion des états électroniques** et **Message d’exportation pour la gestion des états électroniques**. |
| Mise en correspondance des formats pour le chemin de l’URL               | Sélectionnez le format d’ER qui doit être appelé pour l’action. Ce format est utilisé pour composer le chemin de l’adresse URL qui sera ajoutée à l’adresse Internet de base spécifiée pour le serveur Web sélectionné. Ce champ n’est disponible que pour les actions de type **Service Web**. |
| Type d'élément de message                         | Sélectionnez le type d’enregistrements pour lequel l’action doit être évaluée. Ce champ est disponible pour les actions de types **Niveau d’exécution de l’élément de message**, **Exportation de la gestion des états électroniques** et **Importation de la gestion des états électroniques**, **Service Web** ainsi que certains autres types d’action. Si vous laissez ce champ vide, tous les types d’éléments de message définis pour le traitement des messages sont évalués. |
| Classe exécutable                          | Sélectionnez un paramètre de classe exécutable existant. Ce champ n’est disponible que pour les actions **Niveau d’exécution de l’élément de message** et **Niveau d’exécution de l’élément de message**. |
| Action Renseigner des enregistrements                   | Sélectionnez une action de remplissage des enregistrements existante. Ce champ n’est disponible que pour les actions du type **Renseigner les enregistrements**. |
| Service Web                               | Sélectionnez un service web existant. Ce champ n’est disponible que pour les actions de type **Service Web**. |
| Nom de fichier                                 | Permet de spécifier le nom du fichier qui est le résultat de l’action. Ce fichier peut être la réponse du serveur Web ou l’état généré. Ce champ n’est disponible que pour les actions de type **Service Web** et **Message d’exportation pour la gestion des états électroniques**. |
| Joindre des fichiers aux documents source          | Cochez cette case pour joindre les fichiers générés aux enregistrements dans une table principale référencée pour les éléments EM. Ce champ n’est disponible que pour les actions de type **exportation pour la gestion des états électroniques** et **Service web**. |
| Joindre les fichiers de l'archive de sortie aux éléments | Cochez cette case pour extraire des fichiers XML distincts du fichier d'archive de sortie et les joindre aux éléments de message électronique correspondants. Ce champ n’est disponible que pour les actions de type **Exportation pour la gestion des états électroniques**. |
| Nombre d'éléments de messages par exportation        | Spécifiez la limite du nombre d'éléments de message qui doivent être inclus dans un fichier (message). Ce champ n’est disponible que pour les actions de type **Exportation pour la gestion des états électroniques**. |
| Utiliser la source de gestion des états électroniques                             | Cochez cette case pour utiliser les paramètres de source ER pour l'importation. Dans le cas contraire, la pièce jointe du message électronique est utilisée. Ce champ n’est disponible que pour les actions de type **Importation pour la gestion des états électroniques**. |
| Afficher la boîte de dialogue                               | Définissez cette option sur **Oui** si une boîte de dialogue doit être présentée à l’utilisateur avant la génération des états. Ce champ n’est disponible que pour les actions de type **Message d’exportation pour la gestion des états électroniques**. |

#### <a name="message-processing-action-types"></a><a id="action-types"></a>Types d’actions de traitement des messages

Les options suivantes sont disponibles dans le champ **Type d’action** :

- **Créer un message** : utilisez ce type d’action pour permettre aux utilisateurs de créer manuellement des messages sur la page **Message électronique**. Un statut initial ne peut pas être paramétré pour une action de ce type.
- **Renseigner des enregistrements** : ce type d'action doit déjà être configuré. Associez-la à une action de renseignement des enregistrements pour activer son inclusion lors de traitement. Il est supposé que ce type d’action est utilisé pour la première action dans le traitement des messages (lorsqu’aucun message électronique n’a été créé à l’avance) ou pour une action qui ajoute des éléments de message à un message précédemment créé par le type d'action **Créer un message**. Par conséquent, pour les actions de ce type, un statut de résultats ne peut être paramétré que pour les éléments de message. Un statut initial ne peut être paramétré que pour les messages.
- **Niveau d’exécution du message** : utilisez ce type d’action pour paramétrer une classe exécutable à évaluer au niveau du message.
- **Niveau d’exécution de l’élément de message** : utilisez ce type d’action pour paramétrer une classe exécutable à évaluer au niveau de l’élément de message.
- **Exportation de la gestion des états électroniques** : Utilisez ce type d'action pour les actions devant générer un état basé sur une configuration d'exportation de la gestion des ER au niveau de l'élément de message.
- **Message d’exportation pour la gestion des états électroniques** : utilisez ce type d’action pour les actions devant générer un état basé sur une configuration d’exportation de la gestion des ER au niveau du message (par exemple, lorsqu’un message ne contient pas d’éléments de message).
- **Importation de la gestion des états électroniques** : utilisez ce type d’action pour les actions devant générer un état basé sur une configuration d’importation de la gestion des ER.
- **Traitement utilisateur au niveau du message** : utilisez ce type d’action pour les actions qui impliquent certaines actions manuelles de l’utilisateur au niveau des messages. Par exemple, l’utilisateur peut mettre à jour le statut des messages.
- **Traitement utilisateur** : utilisez ce type d’action pour les actions qui impliquent certaines actions manuelles de l’utilisateur au niveau de l’élément de message. Par exemple, l’utilisateur peut mettre à jour le statut des éléments de messages.
- **Service Web** : utilisez ce type d’action pour les actions devant transmettre l’état généré à un service Web. Ce type d’action n’est pas utilisé pour la génération d’états de communication de factures d’achat et client italiens. Pour ce type d'action, la page **Actions de traitement des messages** comprend un raccourci **Détails divers** où vous pouvez préciser un texte de confirmation. Ce texte de confirmation s’affiche aux utilisateurs avant le traitement des requêtes au service Web sélectionné.
- **Vérification de la demande** : utilisez ce type d’action pour demander une vérification à partir d’un serveur.

### <a name="initial-statuses-fasttab"></a>Organisateur Statuts initiaux

> [!NOTE]
> L’organisateur **Statuts initiaux** n’est pas disponible pour les actions dont le type d’action initial est défini sur **Créer un message**.

| Champ               | Description |
|---------------------|-------------|
| Statut de l’élément de message | Sélectionnez le statut de l’élément de message indiquant que l’action de traitement du message sélectionné doit être évaluée. |
| Description         | Description du statut de l’élément de message sélectionné. |

### <a name="result-statuses-fasttab"></a>Organisateur Statuts de résultat

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

## <a name="electronic-message-processing"></a><a id="processing"></a>Traitement du message électronique

Le traitement de message électronique est un concept de base de la fonctionnalité EM. Il regroupe les actions à évaluer pour les messages électroniques. Les actions peuvent être liées via un statut initial et un statut de résultat. Sinon, les actions de type **Traitement utilisateur** peuvent être démarrées individuellement. Pour paramétrer le traitement des messages électroniques, rendez-vous sur **Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Traitement des messages électroniques**.

L’organisateur **Action** vous permet d’ajouter des actions prédéfinies au traitement. Vous pouvez spécifier si une action doit être exécutée séparément, ou si elle peut être démarrée par le traitement. Pour spécifier qu’une action du traitement ne peut être lancée que par un utilisateur, définissez le champ **Exécuter séparément** sur **Oui** pour cette action. Si une action doit être démarrée par le traitement des messages ou des éléments de message dont le statut est celui défini dans le statut initial de l’action, définissez le champ **Exécuter séparément** sur **Non**. Les actions du type **Action utilisateur** doivent toujours être exécutées séparément.

Parfois, plusieurs actions doivent être regroupées en séquence, même si la première action est paramétrée pour être exécutée séparément. Par exemple, un utilisateur doit initialiser la génération de rapport. Immédiatement après que les états ont été générés, il doit être envoyé vers un service Web et la réponse du service Web doit être répercutée dans le système. Dans ce cas, vous pouvez créer une séquence inséparable des actions qui doivent toujours être exécutées ensemble. Sous l’organisateur **Action**, sélectionnez **Séquences inséparables** au-dessus de la grille, puis créez une séquence. Ensuite, pour toutes les actions qui doivent s’exécuter ensemble dans une séquence, sélectionnez la séquence dans le champ **Séquence inséparable**. Pour cet exemple, le champ **Exécuter séparément** peut être défini sur **Oui** pour la première action dans la séquence et sur **Non** pour toutes les autres actions.

Les actions des types **Exportation de la gestion des états électroniques** et **Message d’exportation pour la gestion des états électroniques** exécutent un format ER qui a des paramètres d'entrée. Si le traitement de votre message électronique comprend des actions de l'un ou l'autre de ces types, vous devez spécifier les valeurs des paramètres d'entrée avant la génération du rapport. De cette manière, le système peut utiliser un régime par lots pour générer le rapport. Vous pouvez sélectionner **Paramètres** au-dessus de la grille pour paramétrer le type d'action sélectionné (**Exportation de la gestion des états électroniques** ou **Message d’exportation pour la gestion des états électroniques**). Cochez la case **Utiliser les paramètres** pour l'action qui doit être exécutée avec les paramètres spécifiés dans un régime par lots.

Utilisez le raccourci **Champs supplémentaires de l’élément du message** pour ajouter des champs supplémentaires prédéfinis liés aux éléments de message. Vous devez ajouter des champs supplémentaires pour chaque type d’élément de message auquel les champs sont liés. Vous pouvez spécifier une valeur par défaut qui sera affectée au champ supplémentaire lors du traitement.

Utilisez le raccourci **Champs supplémentaires du message** pour ajouter des champs supplémentaires prédéfinis liés aux messages. Vous pouvez spécifier une valeur par défaut qui sera affectée au champ supplémentaire lors du traitement.

Utilisez le raccourci **Rôles de sécurité** pour paramétrer les rôles de sécurité prédéfinis dans le système pour un traitement spécifique. Les utilisateurs disposant d’un rôle spécifique verront uniquement le traitement qui est défini pour ce rôle.

Utilisez le raccourci **Traitement par lot** pour paramétrer le traitement pour fonctionner à un régime de lots. Nous vous recommandons de mettre en place un régime par lots pour votre traitement directement sur la page **Messages électroniques** ou **Éléments de message électronique**, lorsque vous sélectionnez **Exécuter le traitement** dans le volet Action pour lancer le traitement.
