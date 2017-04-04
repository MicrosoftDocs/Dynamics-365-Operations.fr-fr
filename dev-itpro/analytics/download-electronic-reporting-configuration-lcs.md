---
title: "Télécharger les configurations des états électroniques à partir de Lifecycle Services"
description: "Cette rubrique explique comment télécharger les configurations de déclarations électroniques de (ER) de Microsoft Dynamics Lifecycle Services (LCS)."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 9dca5dec846670da25926826f59d7bce0fa0dcea
ms.lasthandoff: 03/31/2017


---

# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>Télécharger les configurations des états électroniques à partir de Lifecycle Services

Cette rubrique explique comment télécharger les configurations de déclarations électroniques de (ER) de Microsoft Dynamics Lifecycle Services (LCS).

Ce didacticiel vous guide via le processus de téléchargement de la version la plus récente des configurations d'états électroniques à partir de Microsoft Dynamics Lifecycle Services (LCS).

1.  Se connecter à Dynamics 365 for Operations en utilisant l'un des rôles suivants :
    -   Développeur de gestion des états électroniques
    -   Consultant fonctionnel de gestion des états électroniques
    -   Administrateur système

2.  Allez ** Administration d'organisation ** &gt; ** à la génération d'états électronique **.
3.  Dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Microsoft**.
4.  Dans la vignette **Microsoft**, cliquez sur **Référentiels**. [mise à jour-heu-de-LCS-pour-Mme-en cours-Mme-référentiel- liste![] (. /media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](. /media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)
5.  Sur la page **Référentiels de configuration**, dans la grille, sélectionnez le référentiel existant du type **LCS**. Si ce référentiel n'apparaît pas dans la grille, procédez comme suit :
    1.  Cliquez sur **Ajouter** pour ajouter un nouveau référentiel.
    2.  Sélectionnez **LCS** comme type de référentiel.
    3.  Cliquez sur **Créer un référentiel**.
    4.  Entrez un nom et une description pour le référentiel.
    5.  Cliquez **OK** pour confirmer la nouvelle entrée de référentiel.
    6.  Dans la grille, sélectionnez le nouveau référentiel de type **LCS**.

6.  Cliquez sur **Ouvrir** pour afficher la liste des configurations ER pour le référentiel sélectionné. [mise à jour-heu-de-LCS-pour-Mme-faire-LCS-référentiel d'![] (. /media/update-er-from-lcs-for-ms-make-lcs-repository.png)](. /media/update-er-from-lcs-for-ms-make-lcs-repository.png)
7.  Dans l'arborescence de configurations du volet gauche, sélectionnez la configuration ER voulue.
8.  Dans l'organisateur **Versions**, sélectionnez la version requise de la configuration ER sélectionnée.
9.  Cliquez sur **Importer** pour télécharger la version sélectionnée de LCS vers l'instance Dynamics 365 for Operations actuelle. **Remarque :** Le bouton **Importer** n'est pas disponible pour les versions de configuration ER qui sont déjà présentes dans l'instance Dynamics 365 for Operations actuelle. [mise à jour-heu-de-LCS-pour-Mme-téléchargement- configuration de![(]. /media/update-er-from-lcs-for-ms-download-configuration.png)](. /media/update-er-from-lcs-for-ms-download-configuration.png)

**Remarque :** Selon les paramètres d'états électroniques, les configurations sont validées après leur importation. Il est possible que vous soyez averti des problèmes d'incohérences qui sont détectés. Vous devez résoudre ces problèmes avant d'utiliser la version de configuration importée. Pour plus d'informations, voir la liste d'articles associés pour cette rubrique.

<a name="see-also"></a>Voir également :
--------

[Vue d'ensemble des États électroniques](general-electronic-reporting.md)


