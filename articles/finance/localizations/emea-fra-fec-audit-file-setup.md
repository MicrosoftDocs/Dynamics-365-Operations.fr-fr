---
title: Préparer votre environnement pour générer un FEC
description: Cet article explique comment préparer votre environnement Microsoft Dynamics 365 Finance pour générer un fichier d’audit Fichier des écritures comptables (FEC).
author: AdamTrukawka
ms.date: 06/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: France
ms.author: atrukawk
ms.openlocfilehash: cbcc4fc57ee6bceb343c3b020548308c653de12f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267723"
---
# <a name="prepare-your-environment-to-generate-an-fec"></a>Préparer votre environnement pour générer un FEC

Avant de pouvoir générer un fichier d’audit du Fichier des écritures comptables (FEC), vous devez importer les dernières versions des configurations de reporting électronique (ER) suivantes.

| Configuration ER         | Type          | Description |
|--------------------------|---------------|-------------|
| Modèle d’exportation des données        | Modèle         | Le modèle de données unifié pour l’exportation de données. |
| Cartographie du modèle FEC français | Mappage de modèles | La configuration qui collecte les données de différentes sources de données pour les préparer à la création de rapports FEC. |
| Fichier d’audit FEC (FR)      | Format        | Le format d’exportation dans la structure FEC. |

> [!NOTE]
> Une fois que vous importez toutes les configurations ER du tableau précédent importées, sur la page **Configurations**, définissez l’option **Valeur par défaut pour le mappage de modèle** sur **Oui** pour la configuration **Cartographie du modèle FEC français**.

Pour plus d’informations sur le téléchargement des configurations ER à partir du référentiel global Microsoft, consultez [Télécharger les configurations ER à partir du référentiel global](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

À partir de la version 10.0.20, pour utiliser le format **Fichier d’audit FEC (FR)**, vous devez définir le nom de la configuration ER dans un nouveau paramètre de comptabilité. 

1. Accédez à **Comptabilité** \> **Paramétrage de la comptabilité** \> **Paramètres de comptabilité**.
2. Dans l’onglet **Registre**, dans le raccourci **Rapports électroniques**, dans la section **Exportation des écritures comptables**, dans le champ **Exportation des écritures comptables**, sélectionnez le format **Fichier d’audit FEC (FR)**.
3. Enregistrez la nouvelle configuration.

> [!NOTE]
> Si vous introduisez une personnalisation dans les configurations FEC ER et que vous n’utilisez pas le champ **Exportation des transactions du grand livre** sur la page **Paramètres du grand livre** pour prédéfinir le format à utiliser pour générer le FEC, nous vous conseillons d’utiliser la fonction *derive* pour créer un format ER personnalisé à partir du format **Dossier d’audit FEC** dans l’espace de travail **Rapports électroniques**. De cette manière, le nouveau format personnalisé sera une configuration enfant de **Dossier d’audit FEC**. Pour plus d’informations sur la création et la gestion d’applications , consultez [Créer un format personnalisé](../../fin-ops-core/dev-itpro/analytics/er-quick-start2-customize-report.md).
