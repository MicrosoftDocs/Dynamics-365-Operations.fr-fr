---
title: État DAS-2
description: Cette rubrique décrit le processus de génération du fichier d’audit standard pour la France (FEC) dans Microsoft Dynamics 365 Finance.
author: sndray
ms.date: 12/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: France
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3689f8408e52ec52dc3e16e4d840dbc165c190f6
ms.sourcegitcommit: f51e74ee9162fe2b63c6ce236e514840795acfe1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2021
ms.locfileid: "7943599"
---
# <a name="das-2-report"></a>État DAS-2

[!include [banner](../includes/banner.md)]

Les entités juridiques françaises qui font affaire avec des professionnels indépendants doivent fournir un état de déclaration DAS-2 à l’administration fiscale. L’état DAS-2 représente une déclaration fiscale annuelle qui comprend tous les paiements aux fournisseurs de ce type qui dépassent 1 200 euros. L’état doit être généré au format Microsoft Excel. Une fois l’état généré, vous enregistrez le fichier dans l’environnement **ETAFI (CEGID)**. Le fichier sera ensuite validé, converti dans la structure d’échange électronique de données (EDI) et transmis.

L’état DAS-2 sous Excel est généré à l’aide de l’outil de gestion des états électroniques (ER). Il comprend les feuilles de calcul suivantes :

- **Détails** – Toutes les factures fournisseurs qui ont été payées pendant la période sélectionnée et à l’aide d’un profil de fournisseur spécifique qui a une classification DAS-2
- **Résumé par fournisseur** – La déclaration DAS-2 groupée par fournisseur. Chaque colonne représente les montants par classification DAS-2.
- **Formulaire DAS-2** – Un résumé de la déclaration pour chaque fournisseur. Il existe un formulaire pour chaque fournisseur.

Avant de générer l’état pour la première fois, vous devez télécharger les modèles et formats suivants à partir de Microsoft Dynamics Lifecycle Services (LCS) :

- Statistiques sur factures.version.36.xml ou versions ultérieures.
- Statistiques sur mise en correspondance de modèle des factures.version.36.37.xml ou versions ultérieures.
- Statistiques sur mise en correspondance de modèle des factures pour DAS-2.version.36.37.8 ou versions ultérieures. Ce modèle dérivé prend en charge les paiements partiels et les montants avec taxes.
- État DAS-2.version.36.30 (FR) ou versions ultérieures.
- Formulaire DAS-2.version.36.30.15 (FR) ou versions ultérieures.

> [!NOTE]
> Pour plus d’informations sur la manière de télécharger les formats d’états électroniques, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Après avoir téléchargé les configurations des états électroniques à partir de LCS, procédez comme suit.

1. Dans Microsoft Dynamics 365 Finance, sélectionnez la société française liée.
2. Accédez à **Espaces de travail** \> **Gestion des états électroniques** et définissez le fournisseur **Microsoft** sur **Actif**.
3. Sélectionnez **Configurations** \> **Exchange** et chargez les configurations à partir des fichiers XML pour importer le modèle Statistics, le mappage de modèle, l’état DAS-2 et le fichier de format de formulaire DAS-2.
4. Sélectionnez le format **État DAS-2**.
5. Dans l’espace de travail **Gestion des états électroniques**, sélectionnez **Configurations** \> **Paramétrage**.
6. Sur l’onglet **Conditions**, sélectionnez la version **36.30** ou versions ultérieures et créez la configuration qui vous permettra de configurer le mappage entre les comptes principaux configurés dans votre entreprise et la classification des autorités fiscales associée de l’état DAS-2.

    1. Dans le champ **Résultat de la recherche**, sélectionnez la classification associée.
    2. Dans le champ **Compte principal**, sélectionnez le compte principal utilisé pour valider les transactions associées qui appartiennent à la classification sélectionnée.
    3. Définissez le champ **Statut** sur **Terminé**.

### <a name="example"></a>Exemple

[![Exemple de configuration.](./media/emea-fra-das2-report-configuration.png)](./media/emea-fra-das2-report-configuration.png)

Sur la ligne 1 de la configuration précédente, le compte principal **622000**, qui est utilisé pour valider les transactions de dépenses de frais, est configuré sur classification **C** (**Commissions**), ce qui est établi par l’autorité fiscale.

La ligne 5 inclut la configuration qui a la classification **ZZ** et est mappée sur **Pas de blancs**. Elle est utilisée lorsque le journal des factures contient d’autres transactions de dépenses qui ne seront pas détaillées dans l’état DAS-2. Cette ligne doit toujours être la dernière ligne. Si vous devez introduire des classifications supplémentaires, supprimez cette ligne et introduisez les nouvelles.


> [!NOTE]
> Créez la même configuration pour le format de formulaire DAS-2.


## <a name="vendor-configuration"></a>Configuration du fournisseur

Étant donné que l’état inclut l’enregistrement SIRET (Système d’identification du répertoire des établissements), procédez comme suit pour ajouter les informations associées.

1. Accédez à **Comptabilité fournisseur > Fournisseurs > Tous les fournisseurs**.
2. Cliquez sur l’enregistrement fournisseur à mettre à jour.
3. Développez la section **Démographie des achats**.
4. Sélectionnez **Modifier**.
5. Tapez une valeur dans le champ **N° de Siret**.
6. Dans le champ **Code NAF**, saisissez une valeur pour identifier la profession.

## <a name="statistics-on-invoices-process"></a>Statistiques sur le processus de facturation

Avant de générer l’état DAS-2, exécutez le processus **Statistiques sur les factures** pour calculer et générer toutes les transactions qui seront signalées dans la déclaration DAS-2. Vous pouvez exécuter le processus en temps réel ou le planifier à s’exécuter en arrière-plan à l’aide d’un traitement par lots.

1. Aller à **Comptabilité fournisseur** > **Tâches périodiques** > **Statistiques sur les factures**.
2. Sélectionnez **Calculer les statistiques**.
3. Sélectionnez les dates de début et de fin.
4. Sélectionnez le profil de validation fournisseur. Les profils de validation des fournisseurs vous permettent d’inclure facilement les transactions des fournisseurs pour tous les fournisseurs, un groupe de fournisseurs ou un seul fournisseur dans l’état généré. Cette option vous permet de sélectionner plusieurs profils de validation fournisseur et est obligatoire. 
5. Facultatif, sélectionnez le groupe de fournisseurs. Cette sélection vous permet d’introduire un filtre de transaction supplémentaire.  
6. Sélectionnez **OK** pour exécuter le processus.


## <a name="generate-the-das-2-report"></a>Générer l’état DAS-2

Suivez les étapes pour générer l’état de déclaration fiscale.

1. Accédez à **Comptabilité fournisseur** \> **Recherches et états** \> **État DAS-2**.
2. Sélectionnez le format de l’état :

    - **État DAS-2 (FR)** – Générez un état détaillé qui inclut toutes les transactions.
    - **Formulaire DAS-2 (FR)** – Générez un état distinct pour chaque fournisseur.

3. Sélectionnez les dates de début et de fin.
4. Sélectionnez le profil de validation fournisseur. 
5. Sélectionnez le groupe de fournisseurs.

> [!NOTE]
> L’état DAS-2 ne prend pas en charge les transactions créées et validées à partir d’une entrée de journal générale, du scénario de schéma de régularisation ou la fonctionnalité N° document. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
