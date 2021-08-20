---
title: Paramétrer un entrepôt à l’aide d’un modèle de configuration d’entrepôt
description: Cette rubrique explique comment paramétrer un entrepôt à l’aide d’un modèle de configuration d’entrepôt.
author: perlynne
ms.date: 11/16/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DataManagementWorkspace, DMFQuickImportExportEnhanced, DMFDefinitionGroupTemplate, DMFEntityTemplateDefinitionLoadDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: adb14507ad26879ee4811c6eb984ce3888b1913a0e6f0664a99079ba49f1a4c5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751911"
---
# <a name="set-up-a-warehouse-by-using-a-warehouse-configuration-template"></a>Paramétrer un entrepôt à l’aide d’un modèle de configuration d’entrepôt

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment paramétrer un entrepôt à l’aide d’un modèle de configuration d’entrepôt. Il existe plusieurs modèles de configuration prédéfinis que vous pouvez utiliser. Pour plus d’informations sur l’utilisation de ces modèles, voir [Modèles de données de configuration](../../fin-ops-core/dev-itpro/data-entities/configuration-data-templates.md).

## <a name="scenarios-where-configuration-templates-can-be-helpful"></a>Scénarios où les modèles de configuration peuvent être utiles

Les modèles de configuration peuvent être utiles dans de nombreux scénarios. Voici quelques exemples :

- Vous avez exécuté et testé un paramétrage de configuration dans un environnement de test, et vous souhaitez maintenant copier le paramétrage dans un environnement de production.
- Vous souhaitez utiliser le paramétrage d’entrepôt sur plusieurs entités juridiques ou créer un entrepôt dans la même entité juridique.
- Vous souhaitez préparer rapidement une démonstration de la fonctionnalité d’entrepôt.
- Vous souhaitez que les articles et entrepôts existants utilisent la fonctionnalité du module Gestion des entrepôts au lieu de la fonctionnalité du module Gestion des stocks.

Cette rubrique porte sur le premier de ces scénarios. Elle indique comment utiliser un modèle de configuration pour copier un paramétrage de configuration d’un environnement de test vers un environnement de production.

## <a name="copy-a-configuration-setup-from-a-test-environment-to-a-production-environment"></a>Copier un paramétrage de configuration d’un environnement de test vers un environnement de production

Pour ce scénario, le paramétrage de la configuration d’un entrepôt et de certains processus de transactions existe déjà dans un environnement de test. Vous souhaitez maintenant copier le paramétrage de la configuration de l’entrepôt de l’environnement de test vers un environnement de production.

> [!NOTE]
> Il est important d’inclure d’autres données de paramétrage associées lorsque vous copiez un paramétrage de configuration. Par exemple, vous pouvez paramétrer des produits en copiant le paramétrage à partir d’un environnement de test. Toutefois, vous ne pouvez pas paramétrer un emplacement de prélèvement fixe pour un produit avant que celui-ci soit créé. Bien que les modèles de configuration individuels ne prennent pas en charge ce type de dépendance, il existe des modèles de données par défaut qui le prennent en charge. Vous pouvez facilement inclure ces modèles de données par défaut dans un processus de configuration.

### <a name="export-a-default-warehouse-template"></a>Exporter un modèle d’entrepôt par défaut 

1. Ouvrez l’espace de travail **Gestion des données**.

    > [!NOTE]
    > Si vous utilisez cet espace de travail pour la première fois, vous devez charger toutes les entités de données avant de continuer.

2. Sélectionnez la vignette **Modèles**, puis sélectionnez **Charger les modèles par défaut** pour charger les modèles par défaut.

    > [!NOTE]
    > L’option **Charger les modèles par défaut** est disponible uniquement dans la vue **Améliorée**. Sélectionnez **Paramètres de l’environnement**, puis dans le champ **Afficher les valeurs par défaut**, sélectionnez **Vue améliorée**.

3. Une fois que les modèles par défaut sont chargés, vous pouvez les modifier afin qu’ils répondent aux besoins de votre entreprise.

    > [!NOTE]
    > Pour charger les modèles par défaut et les modèles d’importation, vous devez disposer d’un accès de type Administrateur système. Cela permet de garantir que toutes les entités sont correctement chargées dans le modèle.

4. Vérifiez que vous êtes dans l’entité juridique à partir de laquelle vous souhaitez exporter les données spécifiques à la société.
5. Dans l’espace de travail, sélectionnez **Exporter**.
6. Créez un projet d’exportation.
7. Sélectionnez **+ Ajouter un modèle**, puis recherchez le modèle d’entrepôt par défaut **400 - WMS**. Ce modèle ajoute des entités de données pour la configuration d’entrepôt.

    > [!NOTE]
    > Si les données que vous exportez doivent être filtrées (par exemple, vous souhaitez exporter uniquement les données associées à un entrepôt spécifique), vous devez évaluer chaque entité de données et ajouter un filtrage via une requête. Vous pouvez également exporter toutes les données puis supprimer les enregistrements qui ne sont pas nécessaires dans les fichiers de destination.

8. Sélectionnez **Exporter**. Les données associées à toutes les entités de données du projet sont exportées.

Vous pouvez télécharger un fichier zip pour le package de données. Ce fichier contient toutes les données au format sélectionné (par exemple, le format Excel). Comme il a été mentionné, certains enregistrements des fichiers de package de données doivent être mis à jour avant de pouvoir les importer dans l’environnement de production. Si vous mettez à jour un enregistrement, veillez à ne pas modifier le nom de fichier.

### <a name="import-a-warehouse-configuration-setup"></a>Importer un paramétrage de configuration d’entrepôt

1. Dans l’environnement de destination, vérifiez que vous êtes dans la société dans laquelle vous souhaitez importer les données d’entrepôt.

    > [!NOTE]
    > Avant de procéder à l’importation, vous devez identifier les dépendances de données. Par exemple, le modèle **Gestion des entrepôts** inclut une entité de données intitulée **Codes disposition d’entrepôt**. Cette entité contient les données associées à la page de paramétrage **Codes disposition** (**Gestion des entrepôts** > **Paramétrage** > **Appareil mobile** > **Codes disposition**). Si un paramétrage existant gère déjà le processus de retour pour les commandes client, le champ **Code disposition de retour** contient une valeur. Le code disposition de ce champ est associé à l’entité de données **Code disposition**, qui fait partie du modèle **Ventes et marketing**. Si les données de l’entité de données **Code disposition** ne sont pas importées avant les données du champ **Codes disposition d’entrepôt**, l’importation échoue.

2. Dans l’espace de travail **Gestion des données**, sélectionnez **Importer**.
3. Créez un projet d’importation.
4. Sélectionnez **+ Ajouter un fichier** et téléchargez le fichier zip pour le package de données.
5. Sélectionnez **Importer**. Dans la vue **Améliorée**, vous pouvez utiliser l’option **Filtrer** pour obtenir un aperçu rapide des problèmes qui peuvent se produire pendant l’importation.

L’option **Afficher le journal des exécutions** fournit des informations détaillées sur chaque entité de données importée. Vous pouvez utiliser la vue des données intermédiaires pour accéder rapidement aux données cibles. Vous pouvez ainsi voir l’apparence des données importées sur les pages associées de l’application. Lorsque vous utilisez les modèles de données par défaut, la séquence d’importation pour chaque entité de données fonctionne de la manière prédéfinie, afin de garantir que toutes les données dépendantes sont importées en premier. Si les entités de données personnalisées font partie du projet, vous devez vérifier que la séquence correcte est définie. Pour plus d’informations, voir [Modèles de données de configuration](../../fin-ops-core/dev-itpro/data-entities/configuration-data-templates.md).

Pour en savoir plus sur l’utilisation du modèle d’entrepôt pour copier la configuration d’un entrepôt d’une entreprise à une nouvelle entreprise dans la même instance, consultez cette vidéo de 3 minutes sur YouTube : [Utiliser le modèle d’entrepôt pour copier la configuration dans Finance and Operations](https://www.youtube.com/watch?v=K2WIfFlqJYs).

## <a name="related-topic"></a>Rubrique connexe

[Modèles de données de configuration](../../fin-ops-core/dev-itpro/data-entities/configuration-data-templates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]