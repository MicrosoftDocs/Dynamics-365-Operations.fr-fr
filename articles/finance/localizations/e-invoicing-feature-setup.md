---
title: Utiliser les configurations des fonctionnalités
description: Cet article explique comment paramétrer les fonctionnalités de facturation électronique.
author: dkalyuzh
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 23466a53bb8ba597503aaa12d41395fc82b9f14e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904323"
---
# <a name="work-with-feature-setups"></a>Utiliser les configurations des fonctionnalités

[!include [banner](../includes/banner.md)]

Pour configurer la génération de fichiers électroniques et d’autres étapes de traitement (par exemple, signer numériquement des fichiers, les soumettre au service Web du gouvernement et recevoir une réponse, ou les stocker), configurez le pipeline de traitement, les règles d’applicabilité et les variables pour les fonctionnalités de facturation.

Les informations de configuration sont combinées dans le concept de *configuration des fonctionnalités*, et peuvent être créées, supprimées, ajustées. Pour les versions terminées des fonctionnalités de facturation électronique, les informations peuvent également être consultées.

Vous pouvez créer autant d’éléments de configuration de fonctionnalités que nécessaire pour définir différents scénarios de génération, de traitement et de réception de fichiers électroniques. Bien que ces éléments de configuration de fonctionnalité aient des actions de traitement et des conditions d’exécution indépendantes, ils sont créés dans le cadre d’une seule fonctionnalité de facturation électronique et héritent de son cycle de vie et de son processus de déploiement.

## <a name="add-a-feature-setup"></a>Ajouter une configuration de fonctionnalité

1. Connectez-vous à votre compte RCS (Regulatory Configuration Service).
2. Dans l’espace de travail **Fonctionnalité de globalisation**, dans la section **Fonctionnalités**, sélectionnez la vignette **Facturation électronique**.
3. Sur la page **Fonctionnalités de facturation électronique**, sélectionnez une version de fonctionnalité de facturation électronique avec un statut défini sur **Brouillon**.
4. Dans l’onglet **Configurations**, sélectionnez **Ajouter**.
5. Dans la boîte de dialogue déroulante **Créer une configuration de fonctionnalité**, dans le groupe de champs **Nouveau**, sélectionnez les options suivantes :
 
    - **Configuration personnalisée** – Créez une configuration de fonctionnalités avec des canaux vides, une liste de pipeline de traitement vide, une section vide pour les règles d’applicabilité et un ensemble de variables par défaut, en fonction du type de configuration.
    - **Depuis la configuration des fonctionnalités** – Créez une copie d’une autre configuration de fonctionnalité dans le cadre de la fonctionnalité de facturation électronique actuelle.

6. Si vous avez sélectionné l’option **Configuration personnalisée** à la dernière étape, entrez un nom et une description de l’élément de configuration de la fonction, puis, dans le groupe de champs **Type de configuration**, sélectionnez l’une des options suivantes :

    - **Pipeline de traitement** – Sélectionnez cette option pour générer et traiter les documents électroniques sortants. Pour ce type de configuration, le système crée une liste de pipeline de traitement vide, une section vide pour les règles d’applicabilité et un ensemble de variables par défaut. Vous ne pourrez pas travailler avec les canaux pour les documents électroniques entrants.
    - **Canal de données** – Sélectionnez cette option pour configurer le processus de réception des documents électroniques entrants à partir de l’un des canaux définis et de les transmettre directement à Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management sans actions supplémentaires. Pour ce type de configuration, le système crée une liste prédéfinie de paramètres pour les canau de données, une section vide pour les règles d’applicabilité et un ensemble de variables par défaut. Vous ne pourrez pas ajouter d’actions dans le pipeline de traitement.
    - **Canal de données et pipeline de traitement** – Ce type de configuration ressemble au type de configuration **Canal de données**. Toutefois, avant qu’un document électronique entrant ne soit transmis à Finance ou Supply Chain Management, vous pouvez configurer des actions supplémentaires dans le pipeline de traitement.

7. Si vous avez sélectionné l’option **Canal de données** ou **Canal de données et pipeline de traitement** à la dernière étape, dans le champ **Sélectionner le canal de données**, vous devez sélectionner le canal à intégrer.
8. Cliquez sur **Créer**.

Une fois qu’une configuration de fonction a été créée, vous pouvez sélectionner **Modifier** pour le configurer.

## <a name="edit-a-feature-setup"></a>Modifier une configuration de fonctionnalité

Selon le type de configuration de la fonctionnalité, vous pouvez configurer le processus de génération de fichiers électroniques sortants et de les soumettre à des canaux externes, ou de recevoir des documents entrants et de les transmettre à votre application Finance ou Supply Chain Management.

### <a name="data-channel"></a>Canal de données

Un *canal de données* prend le fichier électronique et le traite ou le transmet directement à Finance ou Supply Chain Management. Cette option n’est pas disponible pour les configurations de fonctionnalités du type **Pipeline de traitement**.

Pour configurer un canal de données, entrez le nom du canal. Définissez ensuite les paramètres en fonction du type de canal sélectionné. L’identifiant du canal de données doit faire référence à la variable créée spécifiquement pour identifier le canal de données. Il servira de référence dans Finance ou Supply Chain Management.

Sur l’onglet **Filtre des pièces jointes**, vous devez définir un ensemble de filtres pour obtenir des fichiers spécifiques du canal. Vous pouvez créer plusieurs lignes si vous pensez que les fichiers auront des extensions de nom de fichier différentes ou si les fichiers doivent être traités différemment en fonction du nom de fichier. Voici les principaux paramètres :

- **Nom** – Saisissez le nom du fichier auquel le système se référera lors du traitement. Dans les applications Finance et Supply Chain Management, vous pourrez voir les fichiers dans le journal de soumission.
- **Filtre** – Définissez le filtre pour sélectionner les fichiers.
- **Optionnel** – Si cette case est décochée, le fichier est requis. Dans ce cas, le système affichera un message d’erreur si les chaînes ne contiennent pas de fichiers correspondant au filtre. Ce paramètre est applicable aux e-mails.

Si le canal est une boîte aux lettres et qu’un e-mail entrant contient plusieurs pièces jointes, vous pouvez configurer des règles pour définir la façon dont le service doit gérer les pièces jointes. Le service peut considérer chaque pièce jointe comme une facture électronique distincte, ou il peut traiter une pièce jointe comme une facture principale et toutes les autres pièces jointes comme des ajouts.

### <a name="processing-pipeline"></a>Pipeline de traitement

Un *pipeline de traitement* est un ensemble d’*actions* qui sont exécutées séquentiellement jusqu’à ce qu’elles soient terminées avec succès. Vous pouvez utiliser un pipeline de traitement pour configurer le processus de génération de fichiers électroniques et effectuer d’autres étapes (par exemple, signer numériquement des fichiers, les soumettre à des services Web externes et analyser la réponse, et recevoir et traiter des documents entrants).

La liste des actions est prédéfinie. Vous pouvez utiliser les boutons **Nouveau** et **Supprimer** pour spécifier la combinaison d’actions qui définit logiquement le processus requis pour soumettre ou recevoir des documents.

L’ordre des actions est important. Vous pouvez ajuster l’ordre avec les boutons **Vers le haut** et **Vers le bas**.

Chaque action a un ensemble de paramètres que vous pouvez configurer ou ajuster. L’ensemble spécifique de paramètres dépend du type d’action.

- **Action** – Permet de sélectionner le type de l’action.
- **Nom d’action** – Entrez le nom de l’action. Ce nom apparaîtra dans les journaux de soumission et dans les messages des applications Finance et Supply Chain Management.
- **Description** – Fournissez plus de détails sur le but de l’action dans le processus.
- **Activer la nouvelle tentative** – Si vous cochez cette case, vous pouvez sélectionner une action dans le champ **Réessayer l’action** et configurez des paramètres supplémentaires sur l’onglet **Paramètres de nouvelle tentative**.

    La fonctionnalité de nouvelle tentative vous permet de configurer le comportement du service si une action spécifique ne peut pas être exécutée. Par exemple, si le service Web externe auquel vous essayez de vous connecter ne répond pas, vous pouvez spécifier combien de fois le système doit retenter la connexion, à quel intervalle et à partir de quelle action dans le pipeline de traitement.

- **Exporter les résultats** – Vous pouvez cocher cette case pour *une* action dans le pipeline de traitement. Le fichier électronique que l’action produit dans l’application Finance ou Supply Chain Management peut ensuite être exporté depuis la page **Journal de soumission des documents électroniques**.

### <a name="applicability-rules"></a>Règles d’applicabilité

Les *règles d’applicabilité* sont des clauses configurables qui fournissent un contexte d’exécution des fonctionnalités de facturation électronique via l’ensemble de fonctionnalités de la Facturation électronique.
Les documents commerciaux qui sont envoyés de Finance ou Supply Chain Management vers la facturation électronique ne comportent pas de référence explicite permettant à l’ensemble de fonctionnalités de Facturation électronique d’appeler une version de fonctionnalité de facturation électronique particulière et un élément de configuration de la fonctionnalité spécifique pour traiter l’envoi. Néanmoins, lorsqu’un document commercial est correctement configuré, il contient les éléments nécessaires qui permettent à la facturation électronique de déterminer quelle version de la fonctionnalité de facturation électronique et pipeline de traitement doivent être sélectionnés et exécutés.

Les règles d’applicabilité permettent au service de facturation électronique de trouver les fonctionnalités de facturation électronique exactes qui doivent être utilisées pour traiter un envoi. Pour trouver les caractéristiques correctes, les champs **Contexte** du document commercial soumis sont mis en correspondance avec les clauses des règles d’applicabilité.

Vous pouvez utiliser les règles d’applicabilité de plusieurs manières :

- Sélectionnez **Nouveau** pour ajouter une nouvelle clause à un ensemble de règles d’applicabilité.
- Sélectionnez **Supprimer** pour supprimer une clause.
- Sélectionnez plusieurs enregistrements, puis utilisez le bouton **Grouper** ou **Dissocier** pour créer une combinaison d’éléments ou d’instructions logiques. Par exemple, sélectionnez les lignes que vous souhaitez regrouper, puis sélectionnez **Clause de groupe**. Lorsque les clauses sont regroupées, une nouvelle colonne est ajoutée à la grille. Cette colonne spécifie l’opérateur logique pour la clause regroupée. Les types d’opérateurs suivants sont actuellement pris en charge :

    - Equal
    - Not equal
    - Supérieur à/Inférieur à
    - Supérieur ou égal à/Inférieur ou égal à
    - Contient
    - Commence par

    > [!NOTE]
    > Lorsque vous dissociez une clause, commencez toujours par le niveau de regroupement le plus interne.

### <a name="variables"></a>Variables

Les *variables* vous offrent plus de flexibilité lorsque vous configurez un pipeline de traitement et le flux de données entre les actions. Vous pouvez faire référence à une variable dans certains paramètres d’action pour stocker temporairement des données ou des fichiers électroniques. Certaines variables sont utilisées pour transmettre des données entre les applications Finance ou Supply Chain Management et le service de facturation électronique.

Le système crée certaines variables par défaut. Par exemple, la variable **BusinessDocumentDataModel** contient des données métier dans une structure JSON (JavaScript Object Notation) qui viennent dans l’appel de l’application connectée pendant le processus de soumission.

Les types de variables suivants sont disponibles :

- **Constante** : conteneur de stockage des données temporaires utilisées dans le traitement des actions de pipeline.
- **À partir du client** : le contenu de la variable est acquis à partir du client Dynamics 365 pendant l’exécution du processus d’envoi.
- **Vers le client** : le contenu de la variable est disponible pour importation par le client Dynamics 365 pendant l’exécution du processus d’envoi.
- **Type de données** : sélectionnez le type de données des informations stockées dans la variable.

### <a name="parameters"></a>Paramètres

L’option **Désactiver la réduction des données d’entreprise** est utilisée pour optimiser la structure de la charge utile des données commerciales provenant de l’application Finance ou Supply Chain Management lors de la soumission de documents électroniques. L’optimisation permet de réduire les données qui entrent dans le service de facturation électronique pour une transformation ultérieure dans le fichier électronique requis. La valeur par défaut est **Non**.

- **Oui** –  Finance ou Supply Chain Management enverra un fichier JSON de la structure **Modèle de facture** ou **Modèle fiscal** (pour le Brésil) définie dans le module **Gestion des états électroniques**. Tous les éléments du modèle sont remplis de données commerciales côté application, quelle que soit la structure finale du fichier électronique. Les modèles contiennent généralement plus de données métier que la structure du fichier cible n’en requiert, et la génération de ces données dans l’application peut nécessiter plus de temps. Une valeur **Oui** pour cette option est requise dans les rares cas où vous souhaitez générer différents fichiers de sortie dans une fonction de facturation électronique et une configuration de fonction. Une valeur **Oui** est utile lorsque vous dépannez vos scénarios, la structure des fichiers électroniques et l’exhaustivité des données commerciales.
- **Non** – Finance ou Supply Chain Management effectuera le premier appel au service sans aucune donnée commerciale. Le but de cet appel est d’obtenir des informations sur la configuration de la gestion des états électroniques (ER) qui seront utilisés pour la transformation des fichiers électroniques dans le pipeline de traitement. Ces informations sont renvoyées à l’application, qui les utilise pour déterminer le sous-ensemble de données métier à inclure dans le fichier JSON de la structure **Modèle de facture** ou **Modèle fiscal** (pour le Brésil). Une valeur **Non** pour cette option permet de réduire le volume de données commerciales que l’application soumet au service, car l’application ne peut soumettre que les données commerciales requises pour générer avec succès un fichier électronique.

### <a name="validate-a-feature-setup"></a>Valider un paramétrage de la fonctionnalité

Vous pouvez exécuter la validation pour vérifier la cohérence de l’ensemble de la configuration. Par exemple, si un paramètre obligatoire pour une action est obligatoire, mais que sa valeur reste vide, la validation détecte cette incohérence et vous recevez un message d’avertissement.

- Sur la page **Paramétrage de version de fonctionnalité**, dans le volet Actions, sélectionnez **Valider**.

## <a name="delete-a-feature-setup"></a>Supprimer un paramétrage de la fonctionnalité

1. Sur la page **Fonctionnalités de facturation électronique**, sélectionnez une version de fonctionnalité de facturation électronique avec un statut défini sur **Brouillon**.
2. Dans l’onglet **Configurations**, sélectionnez **Supprimer**.
3. Dans la boîte de message qui s’affiche, sélectionnez **Oui** pour confirmer que vous souhaitez supprimer la configuration de la fonctionnalité.
