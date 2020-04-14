---
title: État DAS-2
description: Cette rubrique décrit le processus de génération du fichier d'audit standard pour la France (FEC) dans Microsoft Dynamics 365 Finance.
author: sndray
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: France
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 109527612407fc6854d90ce1cf01ef2e2dab516a
ms.sourcegitcommit: e543350faaa3ff1217d21c8fd50cf90110df3ef2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/17/2020
ms.locfileid: "3137684"
---
# <a name="das-2-report"></a>État DAS-2

[!include [banner](../includes/banner.md)]

Les entités juridiques françaises qui font affaire avec des professionnels indépendants doivent fournir un état de déclaration DAS-2 à l'administration fiscale. L'état DAS-2 représente une déclaration fiscale annuelle qui comprend tous les paiements aux fournisseurs de ce type qui dépassent 1 200 euros (EUR). Il doit être généré au format Microsoft Excel. Une fois l'état généré, vous enregistrez le fichier dans l'environnement **ETAFI (CEGID)**. Le fichier sera ensuite validé, converti dans la structure d'échange électronique de données (EDI) et transmis.

L'état DAS-2 sous Excel est généré à l'aide de l'outil de gestion des états électroniques (ER). Il comprend les feuilles de calcul suivantes :

- **Détails** - Toutes les factures fournisseurs qui ont été payées à la période sélectionnée et à l'aide d'un profil de fournisseur qui a une classification DAS-2.
- **Résumé par fournisseur** - La déclaration DAS-2 groupée par fournisseur. Chaque colonne représente les montants par classification DAS-2.
- **Formulaire DAS-2** - Un résumé de la déclaration pour chaque fournisseur. Il existe un formulaire pour chaque fournisseur.

Avant de générer l'état pour la première fois, vous devez télécharger les modèles et formats suivants à partir de Microsoft Dynamics Lifecycle Services (LCS) :

- Statistiques sur factures.version.32.xml ou versions ultérieures
- Statistiques sur mise en correspondance de modèle des factures.version.32.xml ou versions ultérieures
- État DAS-2.version.32.14 (FR) ou versions ultérieures
- Formulaire DAS-2.version.32.14.6 (FR) ou versions ultérieures 

> [!NOTE]
> Pour plus d'informations sur la manière de télécharger les formats d'états électroniques, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Après avoir téléchargé les configurations des états électroniques à partir de LCS, procédez comme suit.

1. Dans Microsoft Dynamics 365 Finance, sélectionnez la société française liée.
2. Accédez à **Espaces de travail** \> **Gestion des états électroniques** et définissez le fournisseur **Microsoft** sur **Actif**.
3. Sélectionnez **Configurations** \> **Échange** et chargez la configuration à partir du fichier XML pour importer le modèle de déclaration de taxe et le fichier de format d'état Taxe sur les Produits et Services (GST).
4. Dans l'espace de travail **Gestion des états électroniques**, sélectionnez **Configurations** \> **Paramétrage**.
5. Sur l'onglet **Conditions**, sélectionnez la version **32.14** et créez la configuration qui vous permettra de configurer le mappage entre les comptes principaux configurés dans votre entreprise et la classification des autorités fiscales associée de l'état DAS-2.

    1. Dans le champ **Résultat de la recherche**, sélectionnez la classification associée.
    2. Dans le champ **Compte principal**, sélectionnez le compte principal utilisé pour valider les transactions associées qui appartiennent à la classification sélectionnée.
    3. Définissez le champ **Statut** sur **Terminé**.

### <a name="example"></a>Exemple

[![Exemple de configuration](./media/emea-fra-das2-report-configuration.png)](./media/emea-fra-das2-report-configuration.png)

Sur la ligne 2 de la configuration précédente, le compte principal **622600**, qui est utilisé pour valider les transactions de dépenses de frais, est configuré sur classification **H** (**Frais et congés**), ce qui est établi par l'autorité fiscale.

La ligne 1 inclut la configuration avec la classification **ZZ**. Elle est utilisée lorsque le journal des factures contient d'autres transactions de dépenses qui ne seront pas détaillées dans l'état DAS-2. Pour chaque compte principal TVA et classification DAS-2, créez une ligne supplémentaire qui sera utilisée lorsque la facture contient des montants de taxe qui sont inclus dans les transactions.

> [!NOTE]
> Créez la même configuration pour la page DAS-2.

## <a name="assign-a-tax-registration-id-to-a-vendor-record"></a>Attribuer un ID d'enregistrement fiscal à un enregistrement fournisseur

Étant donné que l'état inclut l'enregistrement SIRET (Système d'identification du répertoire des établissements), l'ID d'enregistrement fiscal qui représente le SIRET utilise la catégorie d'enregistrement **ID de TVA**. Suivez ces étapes pour ajouter un ID d'enregistrement de taxe à un enregistrement fournisseur.

1. Accédez à **Administration d'organisation** \> **Carnet d'adresses global** \> **Types d'enregistrement** \> **Types d'enregistrement** et créez le type d'enregistrement **SIRET**.
2. Accédez à **Administration d'organisation** \> **Carnet d'adresses global** \> **Types d'enregistrement** \> **Catégories d'enregistrement** pour attribuer le type d'enregistrement **SIRET** à la catégorie **ID de TVA**.
3. Accédez à **Comptabilité fournisseur** \> **Fournisseurs** \> **Tous les fournisseurs**.
4. Recherchez et ouvrez l'enregistrement du fournisseur pour lequel vous souhaitez saisir l'ID d'enregistrement.
5. Sur la page **Fournisseur**, sélectionnez **ID d'enregistrement** pour ouvrir la page **Gérer les adresses**.
6. Sur l'onglet **Inscription fiscale**, sélectionnez **Ajouter**, puis, dans le champ **ID d'enregistrement**, sélectionnez **SIRET**.

## <a name="generate-the-das-2-report"></a>Générer l'état DAS-2

Suivez les étapes pour générer l'état de déclaration fiscale.

1. Accédez à **Comptabilité fournisseur** \> **Recherches et états** \> **État DAS-2**.
2. Sélectionnez le format de l'état :

    - **État DAS-2 (FR)**  - Générez un état détaillé qui inclut toutes les transactions.
    - **Formulaire DAS-2 (FR)**  - Générez un état distinct pour chaque fournisseur.

3. Sélectionnez les dates « Du » et « Au ».
4. Sélectionnez le profil de validation fournisseur. Les profils de validation des fournisseurs vous permettent d'inclure facilement les transactions des fournisseurs pour tous les fournisseurs, un groupe de fournisseurs ou un seul fournisseur dans l'état généré. Vous pouvez créer un profil de publication de fournisseur utilisé spécifiquement pour les états DAS-2.

> [!NOTE]
> L'état DAS-2 inclut toutes les factures d'achat qui sont entièrement réglées pendant la période sélectionnée et pour le profil de fournisseur. Les factures partiellement réglées ne sont pas incluses dans cet état.
