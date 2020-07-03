---
title: État DAS-2
description: Cette rubrique décrit le processus de génération du fichier d'audit standard pour la France (FEC) dans Microsoft Dynamics 365 Finance.
author: sndray
manager: AnnBe
ms.date: 06/01/2020
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
ms.openlocfilehash: 3226b0e672714f63706389826793f9cb16aa9dd1
ms.sourcegitcommit: a9dffa475d243e42bd0b64943418c81540d88ba1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2020
ms.locfileid: "3414069"
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
3. Sélectionnez **Configurations** \> **Exchange** et chargez les configurations à partir des fichiers XML pour importer le modèle Statistics, le mappage de modèle, l'état DAS-2 et le fichier de format de formulaire DAS-2.
4. Sélectionnez le format **État DAS-2**.
5. Dans l'espace de travail **Gestion des états électroniques**, sélectionnez **Configurations** \> **Paramétrage**.
6. Sur l'onglet **Conditions**, sélectionnez la version **32.14** et créez la configuration qui vous permettra de configurer le mappage entre les comptes principaux configurés dans votre entreprise et la classification des autorités fiscales associée de l'état DAS-2.

    1. Dans le champ **Résultat de la recherche**, sélectionnez la classification associée.
    2. Dans le champ **Compte principal**, sélectionnez le compte principal utilisé pour valider les transactions associées qui appartiennent à la classification sélectionnée.
    3. Définissez le champ **Statut** sur **Terminé**.

### <a name="example"></a>Exemple

[![Exemple de configuration](./media/emea-fra-das2-report-configuration.png)](./media/emea-fra-das2-report-configuration.png)

Sur la ligne 1 de la configuration précédente, le compte principal **622000**, qui est utilisé pour valider les transactions de dépenses de frais, est configuré sur classification **C** (**Commissions**), ce qui est établi par l'autorité fiscale.

La ligne 5 inclut la configuration qui a la classification **ZZ** et est mappée sur ***Pas de blancs***. Elle est utilisée lorsque le journal des factures contient d'autres transactions de dépenses qui ne seront pas détaillées dans l'état DAS-2. Cette ligne doit toujours être la dernière ligne. Si vous devez introduire des classifications supplémentaires, supprimez cette ligne et introduisez les nouvelles.

> [!NOTE]
> Créez la même configuration pour le format de formulaire DAS-2.


## <a name="vendor-configuration"></a>Configuration du fournisseur

Étant donné que l'état inclut l'enregistrement SIRET (Système d'identification du répertoire des établissements), procédez comme suit pour ajouter les informations associées.

1. Accédez à **Comptabilité fournisseur > Fournisseurs > Tous les fournisseurs**.
2. Cliquez sur l'enregistrement fournisseur à mettre à jour.
3. Développez la section **Démographie des achats**.
4. Sélectionnez **Modifier**.
5. Tapez une valeur dans le champ **N° de Siret**.
6. Dans le champ **Activité**, saisissez une valeur pour identifier la profession.

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
