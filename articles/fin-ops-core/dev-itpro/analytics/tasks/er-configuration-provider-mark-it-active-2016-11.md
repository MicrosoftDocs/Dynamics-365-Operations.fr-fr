---
title: Créer des fournisseurs de configuration et les marquer comme actif
description: Cette rubrique explique comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut créer un fournisseur de configuration.
author: NickSelin
ms.date: 07/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 27e1275199d098fffb56db61ed6bfd2fc3cdb790
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755128"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a>Créer des fournisseurs de configuration et les marquer comme actif

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment un utilisateur affecté au rôle d’administrateur système ou de développeur d’états électroniques peut créer un fournisseur de configuration pour la génération d’états électroniques (ER). Chaque configuration ER fait référence au fournisseur en tant que l’auteur de la configuration. Dans cet exemple, vous allez créer un fournisseur de configuration pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans n’importe quelle société car les fournisseurs de configurations ER sont partagés entre toutes les sociétés.

## <a name="create-a-provider"></a>Créer un fournisseur
1. Accédez au **volet de navigation** dans le coin supérieur gauche et sélectionnez **Administration d’organisation**.
2. Accédez à **Espaces de travail > États électroniques**.
3. Accédez à **Liens connexes > Fournisseurs de configuration**.
4. Sélectionnez **Nouveau**.
    - Un enregistrement fournisseur a un nom et une URL uniques. Examinez le contenu de cette page et ignorez cette procédure si un enregistrement pour Litware, Inc. (https://www.litware.com) existe déjà.  
5. Dans le champ Nom, saisissez `Litware, Inc.`.
6. Dans le champ Adresse Internet, tapez « `https://www.litware.com` ».
7. Sélectionnez **Enregistrer**.
8. Fermez la page.

## <a name="select-as-an-active-provider"></a>Sélectionner en tant que fournisseur actif
1. Sélectionnez le fournisseur Litware, Inc. .
2. Sélectionnez **Activer**.

![Page de l’espace de travail des états électroniques](../media/GER-Task-ActiveProvider-1.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]