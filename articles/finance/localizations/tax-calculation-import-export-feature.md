---
title: Calculs des taxes d’importation et d’exportation
description: Cet article fournit des informations sur la fonctionnalité d’importation et d’exportation du service de calcul des taxes.
author: Kai-Cloud
ms.date: 10/17/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-11-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 8666d4971e36279ebd2b1396de7cab37680980e6
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690231"
---
# <a name="import-and-export-tax-calculations"></a>Calculs des taxes d’importation et d’exportation

Cet article fournit des informations sur la fonctionnalité d’importation et d’exportation du service de calcul des taxes. Cette fonctionnalité permet de garantir une expérience de configuration flexible et efficace.

## <a name="import-and-export-tax-codes"></a>Codes fiscaux d’importation et d’exportation

### <a name="export-templates"></a>Modèles d’exportation

1. Connectez-vous à votre compte [Regulatory Configuration Service (RCS)](https://marketing.configure.global.dynamics.com/).
2. Dans l’espace de travail **Fonctionnalités de globalisation**, sélectionnez **Fonctionnalités**, puis la vignette **Calcul des taxes**.
3. Sélectionnez une fonctionnalité existante ou [créez une nouvelle fonctionnalité](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
4. Dans la grille **Versions**, sélectionnez **Modifier**.
5. Sur la page de fonctionnalité **Calcul de la taxe**, définissez la [version de configuration](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
6. Dans l’onglet **Codes fiscaux**, sélectionnez **Importer**.
7. Sélectionnez **Exporter un modèle de code fiscal** pour télécharger le fichier **TaxCodesTemplate.zip**.
8. Décompressez **TaxCodesTemplate.zip**. Les modèles de code fiscal sont compressés séparément selon la valeur **Origine du calcul**.
9. Décompressez **Par montant net.zip** pour obtenir les fichiers de valeurs séparées par des virgules (CSV) suivants :

    - **TaxCode.csv** : pour entrer les codes fiscaux.
    - **TaxLimit.csv** : pour entrer les limites de taxe pour chaque code fiscal.
    - **TaxRate.csv** : pour entrer les taux d’imposition pour chaque code fiscal.

> [!NOTE]
> Par défaut, les entrées pour le code fiscal **Exemple** sont disponibles dans les modèles. Si le code fiscal **Exemple** n’est pas supprimé des fichiers CSV, il sera importé dans la fonctionnalité.

### <a name="import-tax-codes"></a>Importer les codes fiscaux

Suivez ces étapes pour importer le code fiscal **Exemple** dans le modèle dans votre fonctionnalité de calcul des taxes.

1. Dans RCS, sur la page de la fonctionnalité **Calcul des taxes**, sur l’onglet **Codes fiscaux**, sélectionnez **Importer**.
2. Sélectionnez **Parcourir**, recherchez et sélectionnez le fichier **TaxCode.csv**, puis, dans le champ **Table cible**, sélectionnez **Code fiscal**.
3. Sélectionnez **OK** pour importer le code fiscal.
4. Recherchez et sélectionnez le fichier **TaxRate.csv**, puis dans le champ **Table cible**, sélectionnez **Taux d’imposition**.
5. Sélectionnez **OK** pour importer le taux d’imposition.
6. Recherchez et sélectionnez le fichier **TaxLimit.csv**, puis dans le champ **Table cible**, sélectionnez **Limite de taxe**.
7. Sélectionnez **OK** pour importer la limite de taxe.

Vous pouvez également importer directement le fichier zip qui comprend les trois fichiers CSV. De cette façon, vous pouvez terminer rapidement et facilement l’importation.

1. Dans RCS, sur la page de la fonctionnalité **Calcul des taxes**, sur l’onglet **Codes fiscaux**, sélectionnez **Importer**.
2. Sélectionnez **Parcourir**, recherchez et sélectionnez le fichier **Par montant net.zip**, puis sélectionnez **OK**.

### <a name="export-tax-codes"></a>Exporter les codes fiscaux

1. Dans RCS, sur la page de fonctionnalité **Calcul de la taxe**, sur l’onglet **Codes fiscaux**, sélectionnez **Exporter**.

    Le bouton **Exporter** est disponible lorsqu’il y a au moins un code TVA dans la grille **Codes fiscaux**.

2. Cliquez sur **OK** pour exporter tous les codes fiscaux de la fonctionnalité dans un fichier zip.

> [!NOTE]
> Utilisez le fichier exporté comme modèle pour importer des codes fiscaux dans la fonctionnalité correspondante.

## <a name="import-and-export-applicability-rules"></a>Règles d’applicabilité d’importation et d’exportation

### <a name="export-applicability-rules"></a>Exporter les règles d’applicabilité

1. Connectez-vous à [RCS](https://marketing.configure.global.dynamics.com/).
2. Dans l’espace de travail **Fonctionnalités de globalisation**, sélectionnez **Fonctionnalités**, puis la vignette **Calcul des taxes**.
3. Sélectionnez une fonctionnalité existante ou [créez une nouvelle fonctionnalité](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
4. Dans la grille **Versions**, sélectionnez **Modifier**.
5. Sur la page de fonctionnalité **Calcul de la taxe**, définissez la [version de configuration](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs).
6. Sur l’onglet **Applicabilité au groupe de taxe**, sélectionnez les lignes de la grille **Configurer l’applicabilité au groupe de taxes**.
7. Cliquez sur le bouton **Ouvrir dans Microsoft Office**, puis sélectionnez **Matrice d’applicabilité dynamique des services fiscaux**.

    [![Exportation des règles d’applicabilité vers Microsoft Excel sur la page de la fonctionnalité de Calcul des taxes.](./media/tax-cal-import-export-1.png)](./media/tax-cal-import-export-1.png)

8. Sélectionnez **Télécharger** pour exporter les lignes sélectionnées vers une feuille de calcul Microsoft Excel.

### <a name="import-applicability-rules"></a>Importer des règles d’applicabilité

La feuille de calcul Excel que vous avez téléchargée contient la structure de la grille **Configurer l’applicabilité au groupe de taxes**. Vous pouvez ajouter de nouvelles règles directement dans la feuille de calcul. Lorsque vous avez terminé, suivez ces étapes pour réimporter les nouvelles règles dans la grille **Configurer l’applicabilité au groupe de taxes**.

1. Dans la feuille de calcul Excel, sélectionnez et copiez les lignes à importer.
2. Dans RCS, sur la page de la fonctionnalité **Calcul des taxes**, sur l’onglet **Applicabilité au groupe de taxes**, sélectionnez **Ajouter** pour insérer un enregistrement vide au bas de la grille **Configurer l’applicabilité au groupe de taxes**.
3. Faites **Ctrl+V** pour coller les lignes copiées dans la grille.
4. Cliquez sur **Enregistrer**.

## <a name="import-feature-demo-data"></a>Importer des données de démonstration de fonctionnalités

Suivez ces étapes pour importer les données de démonstration des fonctionnalités.

1. Connectez-vous à [RCS](https://marketing.configure.global.dynamics.com/).
2. Dans l’espace de travail **Fonctionnalités de globalisation**, sélectionnez **Fonctionnalités**, puis la vignette **Calcul des taxes**.
3. Sélectionnez **Importer**, puis, sur la page **Importer la fonctionnalité depuis le référentiel global**, sélectionnez **Synchroniser**. 
4. Dans le tableau, sélectionnez la fonctionnalité **tax-calculation-feature-demo-data**, puis sélectionnez **Importer**.
5. Sélectionnez **Voir** pour réviser les codes de taxe, les groupes et les règles d’applicabilité définis dans la fonction importée.
6. Dans Finance, basculez sur l’entité juridique **DEMF**, puis accédez à **Taxe** \> **Paramétrage** \> **Configuration de taxe** \> **Paramètres de calcul de taxe**.
7. Sur l’onglet **Général**, sélectionnez **Activer le service de calcul des taxes**.
8. Dans le champ **Nom du paramétrage de fonctionnalité**, sélectionnez **tax-calculation-feature-demo-data**.
9. Sélectionnez une **Période de règlement** et un **Groupe de validations dans la comptabilité** pour les nouveaux codes de taxe de démonstration, puis sélectionnez **Confirmer**.
10. Cliquez sur **Enregistrer**.

> [!NOTE]
> La fonctionnalité de démonstration **tax-calculation-feature-demo-data** est basée sur la version de la fonctionnalité **40.54.234** et conçue pour l‘entité juridique de démonstration **DEMF**. Assurez-vous que Finance et RCS sont mis à niveau vers la version 10.0.26 ou ultérieure.
