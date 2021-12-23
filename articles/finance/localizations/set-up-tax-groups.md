---
title: Configurer les groupes de taxes
description: Cette rubrique explique comment configurer des groupes de taxes dans le service de calcul des taxes.
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
ms.openlocfilehash: 50abafb958edfb8476434ff5842cd84cb186962f
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2021
ms.locfileid: "7883859"
---
# <a name="set-up-tax-groups"></a>Configurer les groupes de taxes

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment configurer des groupes de taxes dans le service de calcul des taxes. Elle explique également comment configurer la matrice de règles d'applicabilité du groupe de taxes et configurer les lignes dans la matrice.

Le concept de groupes de taxes dans le service de calcul des taxes ressemble au concept de groupes de taxes de vente dans Microsoft Dynamics 365 Finance. Il s'agit de groupes de codes fiscaux. Le service de calcul des taxes utilise l'intersection d'un groupe de taxes et d'un groupe de taxes d'article pour déterminer les codes fiscaux.

Cependant, les groupes de taxes dans le service de calcul des taxes diffèrent des groupes de taxes de vente dans Finance car ils ne comportent aucun paramètre supplémentaire, tels que **Taxe d’utilisation** et **Exonération de taxe**. Au lieu de cela, ces paramètres sont disponibles au niveau du code fiscal.

> [!IMPORTANT]
> La configuration des groupes de taxes dans le service de calcul des taxes est indépendante de l'entité juridique. Vous ne pouvez effectuer cette configuration dans Regulatory Configuration Service (RCS) qu'une seule fois. Lorsque vous activez le service de calcul des taxes dans Finance, les groupes de taxes sont automatiquement synchronisés pour l'entité juridique sélectionnée.

## <a name="set-up-a-tax-group"></a>Configurer un groupe de taxes

Procédez comme suit pour configurer un groupe de taxes.

1. Connectez-vous à [Regulatory Configuration Service (RCS)](https://marketing.configure.global.dynamics.com/).
2. Accédez à **Espaces de travail** \> **Fonctionnalités de globalisation** \> **Calcul de la taxe**.
3. Sélectionnez la fonctionnalité et la version à configurer, puis sélectionnez **Modifier**.
4. Sur l'onglet **Général**, sélectionnez **Version de la configuration**.
5. Sur l’onglet **Groupe de taxes**, sélectionnez **Gérer les colonnes**. Si vous configurez un groupe de taxes pour la première fois, les champs de la boîte de dialogue **Gérer la colonne** sont automatiquement définis.
6. Dans la liste de gauche, développez le nœud **Lignes** et cochez la case en regard de **Groupe de taxes**.

    ![Groupe de taxes sélectionné sous le nœud Lignes dans la boîte de dialogue Gérer les colonnes.](media/select-tax-group.png)

7. Sélectionnez le bouton Flèche droite pour ajouter **Groupe de taxes** à la liste **Colonnes sélectionnées** sur la droite.

    ![Groupe de taxes ajouté à la liste Colonnes sélectionnées.](media/add-tax-group.png)

8. Cliquez sur **OK**.

## <a name="configure-a-tax-group"></a>Configurer un groupe de taxes

Après avoir configuré un groupe de taxes, la matrice de règles d'applicabilité est créée. Vous pouvez ajouter des lignes à la matrice pour configurer le groupe de taxes.

1. Sur l’onglet **Groupe de taxes**, sélectionnez **Ajouter**.
2. Dans le champ **Groupe de taxes**, entrez le nom du groupe de taxes.

    > [!IMPORTANT]
    > Nous vous recommandons de limiter le nom du groupe de taxes à 10 caractères. Ce nom est synchronisé avec Finance, qui a une limite de 10 caractères pour les noms des groupes de taxes.

3. Dans le champ **Codes fiscaux**, cochez la case en regard de chaque code fiscal que vous souhaitez inclure dans le groupe de taxes. Vous pouvez inclure plusieurs codes fiscaux dans un groupe de taxes.

    ![Plusieurs codes fiscaux sélectionnés dans le champ Codes fiscaux.](media/multiple-tax-codes-selection.png)

4. Répétez les étapes 1 à 3 pour ajouter d’autres groupes de taxes.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
