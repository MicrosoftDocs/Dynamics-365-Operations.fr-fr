---
title: Configurer des groupes de taxes d’article
description: Cet article explique comment configurer des groupes de taxes d’article dans le service de calcul des taxes.
author: wangchen
ms.date: 11/30/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 3bc705bc8173ad2bc8ef883e6dc80b0a187314ad
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846461"
---
# <a name="set-up-item-tax-groups"></a>Configurer des groupes de taxes d’article

[!include [banner](../includes/banner.md)]

Cet article explique comment configurer des groupes de taxes d’article dans le service de calcul des taxes. Elle explique également comment paramétrer la matrice de règles d’applicabilité du groupe de taxes d’article et configurer les lignes dans la matrice.

Le concept de groupes de taxes d’article dans le service de calcul des taxes ressemble au concept de groupes de taxes de vente d’article dans Microsoft Dynamics 365 Finance. Il s’agit de groupes de codes fiscaux. Le service de calcul des taxes utilise l’intersection d’un groupe de taxes et d’un groupe de taxes d’article pour déterminer les codes fiscaux.

> [!IMPORTANT]
> La configuration des groupes de taxes d’article dans le service de calcul des taxes est indépendante de l’entité juridique. Vous ne pouvez effectuer cette configuration dans Regulatory Configuration Service (RCS) qu’une seule fois. Lorsque vous activez le service de calcul des taxes dans Finance, les groupes de taxes d’article sont automatiquement synchronisés pour l’entité juridique sélectionnée.

## <a name="set-up-an-item-tax-group"></a>Paramétrer un groupe de taxes d’article 

Suivez ces étapes pour configurer un groupe de taxes d’article.

1. Connectez-vous à [Regulatory Configuration Service (RCS)](https://marketing.configure.global.dynamics.com/).
2. Accédez à **Espaces de travail** \> **Fonctionnalités de globalisation** \> **Calcul de la taxe**.
3. Sélectionnez la fonctionnalité et la version à configurer, puis sélectionnez **Modifier**.
4. Sur l’onglet **Général**, sélectionnez **Version de la configuration**.
5. Sur l’onglet **Groupe de taxes d’article**, sélectionnez **Gérer les colonnes**. Si vous configurez un groupe de taxes d’article pour la première fois, les champs de la boîte de dialogue **Gérer la colonne** sont automatiquement définis.
6. Dans la liste de gauche, développez le nœud **Lignes** et cochez la case en regard de **Groupe de taxes d’article**.

    ![Groupe de taxes d’article sélectionné sous le nœud Lignes dans la boîte de dialogue Gérer les colonnes.](media/select-item-tax-group.png)

7. Sélectionnez le bouton Flèche droite pour ajouter **Groupe de taxes d’article** à la liste **Colonnes sélectionnées** sur la droite.

    ![Groupe de taxes d’article ajouté à la liste Colonnes sélectionnées.](media/add-item-tax-group.png)

8. Cliquez sur **OK**.

## <a name="configure-an-item-tax-group"></a>Configurer un groupe de taxes d’article

Après avoir configuré un groupe de taxes d’article, la matrice de règles d’applicabilité est créée. Vous pouvez ajouter des lignes à la matrice pour configurer le groupe de taxes d’article.

1. Sur l’onglet **Groupe de taxes d’article**, sélectionnez **Ajouter**.
2. Dans le champ **Groupe de taxes d’article**, entrez le nom du groupe de taxes d’article.

    > [!IMPORTANT]
    > Nous vous recommandons de limiter le nom du groupe de taxes d’article à 10 caractères. Ce nom est synchronisé avec Finance, qui a une limite de 10 caractères pour les noms des groupes de taxes d’article.

3. Dans le champ **Codes fiscaux**, cochez la case en regard de chaque code fiscal que vous souhaitez inclure dans le groupe de taxes d’article. Vous pouvez inclure plusieurs codes fiscaux dans un groupe de taxes d’article.

    ![Plusieurs codes fiscaux sélectionnés dans le champ Codes fiscaux.](media/multiple-tax-codes-selection.png)

4. Répétez les étapes 1 à 3 pour ajouter plusieurs groupes de taxes d’article.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
