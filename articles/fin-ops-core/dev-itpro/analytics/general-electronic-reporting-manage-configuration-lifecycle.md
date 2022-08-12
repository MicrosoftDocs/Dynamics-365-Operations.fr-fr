---
title: Gérer le cycle de vie de la configuration des états électroniques
description: Cet article décrit comment gérer le cycle de vie des configurations d’états électroniques (ER) pour Dynamics 365 Finance.
author: NickSelin
ms.date: 07/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6a64908a167c09089a95f1d3faa825dcc63f064
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2022
ms.locfileid: "9109080"
---
# <a name="manage-the-electronic-reporting-er-configuration-lifecycle"></a>Gérer le cycle de vie de la configuration des états électroniques

[!include [banner](../includes/banner.md)]

Cet article décrit comment gérer le cycle de vie des configurations d’états électroniques (ER) pour Dynamics 365 Finance.

## <a name="overview"></a>Présentation

La génération d’états électronique (ER) est un moteur qui prend en charge les documents électroniques exigés par les règlements et spécifiques aux pays. En général, l’ER suppose une capacité à effectuer les tâches suivantes pour un document électronique unique. Pour plus de détails, voir [Vue d’ensemble des États électroniques](general-electronic-reporting.md).

- Créez un modèle pour un document électronique :

    - Identifiez les sources de données exigées qui peuvent être présentées dans le document :

        - Données sous-jacentes, telles que les tables de données, entités de données et classes.
        - Propriétés spécifiques aux processus, tels que les date et heure d’exécution et fuseau horaire.
        - Paramètres d’entrée utilisateur, spécifiés par l’utilisateur final au moment de l’exécution.

    - Définissez les éléments du document nécessaires ainsi que leur topologie afin de spécifier un format de document final.
    - Configurez le flux de données souhaité à partir des sources de données sélectionnées vers les éléments du document définis (via les liaisons de sources de données aux composants de format du document) et spécifiez la logique de contrôle du processus.

- Mettez un modèle à disposition afin qu’il puisse être utilisé dans d’autres instances :

    - Transformez un modèle de document créé dans une configuration ER, et exportez la configuration de l’instance actuelle de l’application en tant que package XML pouvant être enregistré localement ou dans Lifecycle Services (LCS).
    - Transformez une configuration ER en modèle de document d’application.
    - Importez un package XML qui est enregistré localement ou dans LCS dans l’instance actuelle.

- Personnalisez le modèle d’un document électronique :

    - Importez un modèle issu de LCS dans l’instance actuelle en tant que configuration ER.
    - Créez une version personnalisée d’une configuration ER et conservez une référence à la version de base.

- Intégrez un modèle à un processus entreprise particulier, afin qu’il soit disponible dans l’application :

    - Configurez des paramètres afin que l’application commence à utiliser une configuration ER, en se rapportant à cette configuration dans un paramètre associé au processus. Par exemple, consultez la configuration ER dans un mode de paiement Achats spécifique pour générer un message de paiement électronique pour traiter les factures.

- Utilisez un modèle dans un processus d’entreprise spécifique :

    - Exécutez une configuration ER dans un processus d’entreprise spécifique. Par exemple, pour générer un message de paiement électronique pour le traitement des factures lorsqu’un mode de paiement qui référence la configuration ER est sélectionné.

## <a name="concepts"></a>Concepts
Les rôles suivants et les activités liées sont associés au cycle de vie de la configuration ER.

| Rôle                                       | Activités                                                      | description ; |
|--------------------------------------------|-----------------------------------------------------------------|-------------|
| Consultant fonctionnel de gestion des états électroniques | Créez et gérez des composants ER (modèles et formats).           | Un commercial qui conçoit des modèles de données spécifique au domaine ER, conçoit les modèles requis pour des documents électroniques et les lie en conséquence. |
| Développeur d’états électroniques             | Créez et gérez les mises en correspondance de modèle de données.                          | Un spécialiste qui sélectionne les sources de données requises de Finance et les lie aux modèles de données spécifiques au domaine ER. |
| Chef comptable                      | Configurez les paramètres liés au processus qui référencent des artefacts ER. | Par exemple, un rôle de **Chef comptable** qui autorise les paramètres d’une configuration ER à être utilisés dans un mode de paiement Achats particulier pour générer un message de paiement électronique pour traiter les factures. |
| Commis au paiement de la comptabilité fournisseur            | Utilisez des artefacts ER dans un processus d’entreprise spécifique.                | Par exemple, un rôle de **Commis au paiement de la comptabilité fournisseur** qui autorise des messages de paiement électronique à générer pour le traitement des factures, selon le format ER configuré pour un mode de paiement spécifique. |

## <a name="er-configuration-development-lifecycle"></a>Cycle de vie de développement de la configuration ER
Pour les raisons suivantes associées à ER, nous recommandons que vous conceviez des configurations ER dans l’environnement de développement en tant qu’instance distincte de finances et d’opérations :

- Les utilisateurs, qu’ils soient dans des rôles de **Développeur d’états électroniques** ou de **Consultant fonctionnel des états électroniques**, peuvent modifier des configurations et les exécuter à des fins de test. Ce scénario peut provoquer des appels de méthodes de classes et de tables qui sont potentiellement néfastes pour les données commerciales et les performances de l’instance.
- Les appels de méthodes de classes et de tables en tant que sources de données ER des configurations ER ne sont pas limités par les points d’entrée, ni par le contenu d’entreprise consigné. Par conséquent, les utilisateurs dans les rôles de **Développeur d’états électroniques** ou de **Consultant fonctionnel des états électroniques** peuvent accéder aux données commerciales importantes.

Les configurations ER conçues dans l’environnement de développement peuvent être [chargées](#data-persistence-consideration) dans l’environnement de test pour l’évaluation de la configuration (intégration correcte au processus, exactitude des résultats et des performances) et l’assurance qualité, comme l’exactitude des droits d’accès motivés par le rôle et la répartition des tâches. Les fonctions qui activent l’échange de configuration ER peuvent être utilisées à cet effet. Les configurations ER éprouvées peuvent être chargées dans LCS pour les partager avec des abonnés au service, ou être [importées](#data-persistence-consideration) dans l’environnement de production pour une utilisation interne.

![Cycle de vie de la configuration ER.](./media/ger-configuration-lifecycle.png)

## <a name="data-persistence-consideration"></a>Prise en compte de la persistance des données

Vous pouvez [importer](tasks/er-import-configuration-lifecycle-services.md) individuellement différentes [versions](general-electronic-reporting.md#component-versioning) d’une [configuration](general-electronic-reporting.md#Configuration) ER dans votre instance Finance. Lorsqu’une nouvelle version d’une configuration ER est importée, le système contrôle le contenu de la version provisoire de cette configuration :

- Lorsque la version importée est inférieure à la version la plus élevée de cette configuration dans l’instance Finance actuelle, le contenu de la version provisoire de cette configuration reste inchangé.
- Lorsque la version importée est supérieure à toute autre version de cette configuration dans l’instance Finance actuelle, le contenu de la version importée est copié dans la version provisoire de cette configuration, pour vous permettre de continuer à modifier la dernière version terminée.

Si cette configuration appartient au [fournisseur](general-electronic-reporting.md#Provider) de configurations actuellement activé, la version provisoire de cette configuration vous est visible dans le raccourci **Versions** de la page **Configurations** (**Administration de l’organisation** > **Gestion des états électroniques** > **Configurations**). Vous pouvez sélectionner la version provisoire de la configuration et [modifier](er-quick-start2-customize-report.md#ConfigureDerivedFormat) son contenu en utilisant le concepteur ER approprié. Une fois que vous avez modifié la version provisoire d’une configuration ER, son contenu ne correspond plus à celui de la version la plus élevée de cette configuration dans l’instance Finance actuelle. Pour éviter la perte de vos modifications, le système affiche une erreur indiquant que l’importation ne peut pas se poursuivre parce que la version de cette configuration est supérieure à la version la plus élevée de cette configuration dans l’instance Finance actuelle. Lorsque cela se produit, par exemple avec la configuration du format **X**, l’erreur **La version du format « X » n’est pas terminée** s’affiche.

Pour annuler les modifications que vous avez introduites dans la version provisoire, sélectionnez la version terminée ou partagée la plus élevée de votre configuration ER dans Finance dans le raccourci **Versions**, puis sélectionnez l’option **Obtenir cette version**. Le contenu de la version sélectionnée est copié dans la version provisoire.

## <a name="applicability-consideration"></a>Considération relative à l’applicabilité

Lorsque vous concevez une nouvelle version d’une configuration ER, vous pouvez définir sa [dépendance](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md) sur d’autres composants logiciels. Cette étape est considérée comme une condition préalable au contrôle du téléchargement de la version de cette configuration à partir d’un référentiel ER ou d’un fichier XML externe, et à toute utilisation ultérieure de la version. Lorsque vous essayez d’importer une nouvelle version d’une configuration ER, le système utilise les conditions préalables configurées pour contrôler si la version peut être importée.

Dans certains cas, vous pouvez exiger que le système ignore les conditions préalables configurées lorsque vous importez de nouvelles versions des configurations ER. Pour que le système ignore les conditions préalables lors de l’importation, procédez comme suit.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Dans la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.
3. Définissez l’option **Ignorer les mises à jour du produit et la vérification des conditions préalables de version lors de l’importation** sur **Oui**.

    > [!NOTE]
    > Ce paramètre est spécifique à l’utilisateur et à l’entreprise.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des états électroniques](general-electronic-reporting.md)

[Définir la dépendance des configurations ER sur d’autres composants](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

