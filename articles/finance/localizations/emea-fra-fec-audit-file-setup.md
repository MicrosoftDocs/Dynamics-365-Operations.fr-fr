---
title: Préparer votre environnement pour générer un FEC
description: Cette rubrique explique comment préparer votre environnement Microsoft Dynamics 365 Finance pour générer un fichier d'audit Fichier des écritures comptables (FEC).
author: liza-golub
ms.date: 05/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.author: elgolu
ms.reviewer: kfend
ms.search.region: France
ms.openlocfilehash: 33a90863b89b866f63d943a2083ec9a5a9b3d158
ms.sourcegitcommit: 51cad1ce3ed44ebf7eb9bdf553ee2df4c1f03135
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016198"
---
# <a name="prepare-your-environment-to-generate-an-fec"></a>Préparer votre environnement pour générer un FEC

Avant de pouvoir générer un fichier d'audit du Fichier des écritures comptables (FEC), vous devez importer les dernières versions des configurations de reporting électronique (ER) suivantes.

| Configuration ER         | Type          | Description  |
|--------------------------|---------------|-------------|
| Modèle d'exportation des données        | Modèle         | Le modèle de données unifié pour l'exportation de données. |
| Cartographie du modèle FEC français | Mappage de modèles | La configuration qui collecte les données de différentes sources de données pour les préparer à la création de rapports FEC. |
| Fichier d’audit FEC (FR)      | Format        | Le format d'exportation dans la structure FEC. |

> [!NOTE]
> Une fois que vous importez toutes les configurations ER du tableau précédent importées, sur la page **Configurations**, définissez l’option **Valeur par défaut pour le mappage de modèle** sur **Oui** pour la configuration **Cartographie du modèle FEC français**.

Pour plus d'informations sur le téléchargement des configurations ER à partir du référentiel global Microsoft, consultez [Télécharger les configurations ER à partir du référentiel global](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

À partir de la version 10.0.20, pour utiliser le format **Fichier d'audit FEC (FR)**, vous devez définir le nom de la configuration ER dans un nouveau paramètre de comptabilité. 

1. Accédez à **Comptabilité** \> **Paramétrage de la comptabilité** \> **Paramètres de comptabilité**.
2. Dans l'onglet **Registre**, dans le raccourci **Rapports électroniques**, dans la section **Exportation des écritures comptables**, dans le champ **Exportation des écritures comptables**, sélectionnez le format **Fichier d'audit FEC (FR)**.
3. Enregistrez la nouvelle configuration.
