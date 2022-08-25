---
title: Utiliser des configurations
description: Cet article fournit une vue d’ensemble du scénario principal d’utilisation des configurations de gestion des états électroniques (ER) à partir de l’espace de travail des fonctionnalités de globalisation.
author: gionoder
ms.date: 01/26/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: d87559405d2490c314eb2c8b88268af0dc0dfaca
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283053"
---
# <a name="work-with-configurations"></a>Utiliser des configurations

[!include [banner](../includes/banner.md)]

Les configurations de gestion des états électroniques (ER) sont l’un des principaux ensembles de composants des fonctionnalités de facturation électronique. Une configuration de gestion des états électroniques (ER) contient la configuration de la structure de fichiers et un ensemble de règles de transformation pour transformer les données de deux manières :

- **Exporter la configuration du format ER** – Cette configuration transforme les données de la structure interne unifiée (modèle ER) au format de fichier électronique.
- **Importer la configuration du format ER** – Cette configuration transforme les données du format de fichier électronique à la structure interne unifiée (modèle ER).

En plus de générer des fichiers électroniques sortants dans le format prédéfini, les configurations ER sont largement utilisées pour analyser les messages entrants provenant de services Web externes en tant que réponses. Cette fonctionnalité permet de créer une logique configurable pour obtenir les résultats de la communication avec les canaux externes, convertir ces résultats (codes, messages et journaux) en une structure lisible par l’utilisateur, puis transmettre ces informations à l’application cliente.

Pour commencer à utiliser les configurations ER dans votre fonction de facturation électronique, vous devez les lier à la fonction et les rendre disponibles sur l’onglet **Configurations** pour la version actuelle de la fonctionnalité. Vous pouvez utiliser une configuration ER liée en sélectionnant **Ajouter**, **Supprimer**, **Modifier** ou **Afficher**.

Avant de pouvoir ajouter un lien vers une configuration ER, la configuration doit exister dans votre référentiel RCS (Regulatory Configuration Service). Pour passer en revue les configurations ER disponibles dans votre référentiel RCS, procédez comme suit.

1. Connectez-vous à votre compte RCS.
2. Dans l’espace de travail **Génération des états électroniques**, dans la section **Configurations**, sélectionnez la vignette **Configurations des états**.

Pour plus d’informations sur la création d’une nouvelle configuration ER ou l’importation d’une configuration ER existante à partir du référentiel global, voir [Déclaration électronique](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Pour ajuster une configuration ER liée, sélectionnez **Modifier** sur l’onglet **Configurations** de la fonctionnalité de facturation électronique actuelle. Le système crée automatiquement une version de la configuration ER. Si la version actuelle n’a pas été créée par le fournisseur de configuration actif, le système crée une version dérivée qui utilise votre fournisseur de configuration. Si la version actuelle a été créée par le fournisseur de configuration actif, le système crée une nouvelle version. Dans les deux cas, vous pouvez modifier la version créée, puis effectuer automatiquement toutes les mises à jour requises.
