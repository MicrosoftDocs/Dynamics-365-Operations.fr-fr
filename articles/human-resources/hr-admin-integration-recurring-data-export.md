---
title: Créer une application d'exportation de données récurrentes
description: Cet article montre comment créer une application logique Microsoft Azure qui exporte des données de Microsoft Dynamics 365 Human Resources sur un calendrier récurrent.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 97972d2179c42e9d2d672cbebb75643ef0a02a62
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112496"
---
# <a name="create-a-recurring-data-export-app"></a>Créer une application d'exportation de données récurrentes

Cet article montre comment créer une application logique Microsoft Azure qui exporte des données de Microsoft Dynamics 365 Human Resources sur un calendrier récurrent. Le didacticiel tire parti de l'interface de programmation d'application (API) du package DMF Human Resources pour exporter les données. Une fois les données exportées, l'application logique enregistre le package de données exporté dans un dossier Microsoft OneDrive for Business.

## <a name="business-scenario"></a>Scénario d'entreprise

Dans un scénario d'entreprise typique pour les intégrations Microsoft Dynamics 365, les données doivent être exportées vers un système en aval selon un calendrier récurrent. Ce didacticiel montre comment exporter tous les enregistrements de travail de Microsoft Dynamics 365 Human Resources et enregistrer la liste des collaborateurs dans un dossier OneDrive for Business.

> [!TIP]
> Les données spécifiques qui sont exportées dans ce didacticiel et la destination des données exportées ne sont que des exemples. Vous pouvez facilement les modifier pour répondre à vos besoins professionnels.

## <a name="technologies-used"></a>Technologies utilisées

Ce didacticiel utilise les technologies suivantes :

- **[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)**- La source de données principales pour les collaborateurs qui seront exportés.
- **[Azure Logic Apps](https://azure.microsoft.com/services/logic-apps/)** - La technologie qui fournit l'orchestration et la planification de l'exportation récurrente.

    - **[Connecteurs](https://docs.microsoft.com/azure/connectors/apis-list)** - La technologie utilisée pour connecter l'application logique aux points de terminaison requis.

        - Connecteur [HTTP with Azure AD](https://docs.microsoft.com/connectors/webcontents/)
        - Connecteur [OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness)

- **[API REST du package DMF](../dev-itpro/data-entities/data-management-api.md)** - La technologie utilisée pour déclencher l'exportation et suivre sa progression.
- **[OneDrive for Business](https://onedrive.live.com/about/business/)** - La destination des collaborateurs exportés.

## <a name="prerequisites"></a>Conditions préalables

Avant de commencer l'exercice de ce didacticiel, vous devez disposer des éléments suivants :

- Un environnement de ressources humaines doté d'autorisations de niveau administrateur dans l'environnement
- Un [Abonnement Azure](https://azure.microsoft.com/free/) pour héberger l'application logique

## <a name="the-exercise"></a>Exercice

À la fin de cet exercice, vous disposerez d'une application logique connectée à votre environnement de ressources humaines et à votre compte OneDrive for Business. L'application logique exportera un package de données à partir des ressources humaines, attendra la fin de l'exportation, téléchargera le package de données exporté et enregistrera le package de données dans le dossier OneDrive for Business que vous avez spécifié.

L'application logique terminée ressemblera à l'illustration suivante.

![Présentation de l'application logique](media/integration-logic-app-overview.png)

### <a name="step-1-create-a-data-export-project-in-human-resources"></a>Étape 1 : créer un projet d'exportation de données dans Human Resources

Dans Human Resources, créezun projet d'exportation de données qui exporte des collaborateurs. Nommez le projet **Exportation de collaborateurs** et assurez-vous que l'option **Générer le package de données** est définie sur **Oui**. Ajoutez une seule entité (**Collaborateur**) au projet et sélectionnez le format dans lequel exporter. (Le format Microsoft Excel est utilisé dans ce didacticiel.)

![Projet de données Exportation de collaborateurs](media/integration-logic-app-export-workers-project.png)

> [!IMPORTANT]
> Notez le nom du projet d'exportation de données. Vous en aurez besoin lorsque vous créerez l'application logique à l'étape suivante.

### <a name="step-2-create-the-logic-app"></a>Étape 2 : créer l'application logique

La majeure partie de l'exercice consiste à créer l'application logique.

1. Dans le portail Azure, créez une application logique.

    ![Page de création d'application logique](media/integration-logic-app-creation-1.png)

2. Dans Logic Apps Designer, commencez par une application logique vide.
3. Ajoutez un [Déclencheur de calendrier de récurrence ](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence)pour exécuter l'application logique toutes les 24 heures (ou selon un horaire de votre choix).

    ![Boîte de dialogue de récurrence](media/integration-logic-app-recurrence-step.png)

4. Appelez l'API REST DMF [ExportToPackage](../dev-itpro/data-entities/data-management-api.md#exporttopackage)pour planifier l'exportation de votre package de données.

    1. Utilisez l'action **Appeler une requête HTTP** depuis le connecteur HTTP with Azure AD.

        - **URL de la ressource de base :** l'URL de votre environnement Human Resources (n'incluez pas les informations de chemin / espace de noms.)
        - **URI ressource Azure AD :** `http://hr.talent.dynamics.com`

        > [!NOTE]
        > Le service Human Resources ne fournit pas encore de connecteur qui expose toutes les API qui composent l'API REST du package DMF, telles que **ExportToPackage**. Au lieu de cela, vous devez appeler les API en utilisant des requêtes HTTPS brutes via le connecteur HTTP with Azure AD. Ce connecteur utilise Azure Active Directory (Azure AD) pour l'authentification et l'autorisation des ressources humaines.

        ![Connecteur HTTP with Azure AD](media/integration-logic-app-http-aad-connector-step.png)

    2. Connectez-vous à votre environnement Human Resources via le connecteur HTTP with Azure AD.
    3. Configurez une requête HTTP **POST** pour appeler l'API REST DMF **ExportToPackage**.

        - **Méthode :** POST
        - **URL de la demande :** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage
        - **Corps de la requête :**

            ```JSON
            {
                "definitionGroupId":"Export Workers",
                "packageName":"talent_package.zip",
                "executionId":"",
                "reExecute":false,
                "legalEntityId":"USMF"
            }
            ```

        ![Appeler une action de requête HTTP](media/integration-logic-app-export-to-package-step.png)

    > [!TIP]
    > Vous voudrez peut-être renommer chaque étape afin qu'elle soit plus significative que le nom par défaut, **Appeler une requête HTTP**. Par exemple, vous pouvez renommer cette étape **ExporterVersPackage**.

5. [Initialisez une variable](https://docs.microsoft.com/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable)pour stocker l'état d'exécution de la requête **ExporterVersPackage**.

    ![Initialiser l'action variable](media/integration-logic-app-initialize-variable-step.png)

6. Attendez que l'état d'exécution de l'exportation de données soit **Réussi**.

    1. Ajoutez une action [Jusqu'à la boucle](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop)qui se répète jusqu'à ce que la valeur de la variable **ExecutionStatus** soit **Réussi**.
    2. Ajoutez une action **Retard** qui attend cinq secondes avant d'interroger l'état d'exécution actuel de l'exportation.

        ![Conteneur jusqu'à la boucle](media/integration-logic-app-until-loop-step.png)

        > [!NOTE]
        > Définissez le nombre limite sur **15** pour attendre un maximum de 75 secondes (15 itérations × 5 secondes) que l'exportation soit terminée. Si votre exportation prend plus de temps, ajustez la limite comme il convient.        

    3. Ajoutez une action **Appeler une requête HTTP** pour appeler l'API REST DMF [GetExecutionSummaryStatus](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus)et définissez la variable **ExecutionStatus** sur résultat de la réponse **GetExecutionSummaryStatus**.

        > Cet exemple ne vérifie pas les erreurs. L'API **GetExecutionSummaryStatus** peut renvoyer des états de terminal non réussis (c'est-à-dire des états autres que **Réussi**). Pour plus d'informations, voir la [Documentation d'API](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus).

        - **Méthode :** POST
        - **URL de la demande :** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus
        - **Corps de la demande :** body('Invoke\_an\_HTTP\_request')?['value']

            > [!NOTE]
            > Vous devrez peut-être saisir la valeur **Corps de la demande** soit en mode code, soit dans l'éditeur de fonctions du concepteur.

        ![Appeler une action de requête HTTP 2](media/integration-logic-app-get-execution-status-step.png)

        ![Définir l'action variable](media/integration-logic-app-set-variable-step.png)

        > [!IMPORTANT]
        > La valeur pour l'action **Définir la variable** (**body('Invoke\_an\_HTTP\_request\_2')?['value']**) différera de la valeur du corps **Appeler une requête HTTP 2**, même si le concepteur affichera les valeurs de la même manière.

7. Obtenez l'URL de téléchargement du package exporté.

    - Ajoutez une action **Appeler une requête HTTP** pour appeler l'API REST DMF [GetExportedPackageUrl](../dev-itpro/data-entities/data-management-api.md#getexportedpackageurl).

        - **Méthode :** POST
        - **URL de la demande :** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl
        - **Corps de la demande :** {"executionId": body('GetExportedPackageURL')?['value']}

        ![Action GetExportedPackageURL](media/integration-logic-app-get-exported-package-step.png)

8. Téléchargez le package exporté.

    - Ajoutez une requête HTTP **GET** (une fonction intégrée [HTTP connector action](https://docs.microsoft.com/azure/connectors/connectors-native-http)) pour télécharger le package à partir de l'URL renvoyée à l'étape précédente.

        - **Méthode :** GET
        - **URI :** body('Invoke\_an\_HTTP\_request\_3').value

            > [!NOTE]
            > Vous devrez peut-être saisir la valeur **URI** soit en mode code, soit dans l'éditeur de fonctions du concepteur.

        ![Action HTTP GET](media/integration-logic-app-download-file-step.png)

        > [!NOTE]
        > Cette requête ne nécessite aucune authentification supplémentaire, car l'URL retournée par l'API **GetExportedPackageUrl** inclut un jeton de signatures d'accès partagé qui autorise l'accès au téléchargement du fichier.

9. Enregistrez le package téléchargé en utilisant le connecteur [OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness).

    - Ajoutez une action OneDrive for Business [Créer un fichier ](https://docs.microsoft.com/connectors/onedriveforbusinessconnector/#create-file).
    - Connectez-vous à votre compte OneDrive for Business, selon les besoins.

        - **Chemin du dossier :** un dossier de votre choix
        - **Nom de fichier :** worker\_package.zip
        - **Contenu du fichier :** le corps de l'étape précédente (contenu dynamique)

        ![Créer une action de fichier](media/integration-logic-app-create-file-step.png)

### <a name="step-3-test-the-logic-app"></a>Étape 3 : tester l'application logique

Pour tester votre application logique, sélectionnez le bouton **Exécuter** dans le concepteur. Vous verrez que les étapes de l'application logique commencent à s'exécuter. Après 30 à 40 secondes, l'application logique devrait terminer son exécution et votre dossier OneDrive for Business devrait inclure un nouveau fichier de package contenant les collaborateurs exportés.

Si un échec est signalé pour une étape, sélectionnez l'étape ayant échoué dans le concepteur et examinez les champs **Entrées** et **Sorties** correspondants. Déboguez et ajustez l'étape au besoin pour corriger les erreurs.

L'illustration suivante montre à quoi ressemble Logic Apps Designer lorsque toutes les étapes de l'application logique s'exécutent correctement.

![Exécution de l'application logique réussie](media/integration-logic-app-successful-run.png)

## <a name="summary"></a>Synthèse

Dans ce didacticiel, vous avez appris à utiliser une application logique pour exporter des données à partir de Human Resources et enregistrer les données exportées vers un dossier OneDrive for Business. Vous pouvez modifier les étapes de ce didacticiel selon vos besoins pour répondre aux besoins de votre entreprise.


