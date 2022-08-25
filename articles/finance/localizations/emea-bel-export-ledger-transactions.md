---
title: Exporter les écritures comptables
description: Cet article donne des informations sur l’exportation des soldes de compte général dans un fichier texte brut (ASCII) au format CED pour la Belgique.
author: AdamTrukawka
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Belgium
ms.author: atrukawk
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 273103
ms.search.form: TaxReportExtraFieldsBE
ms.openlocfilehash: ab527f52e851856d03365c1d7eedb07882f02bd7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283938"
---
# <a name="export-ledger-transactions"></a>Exporter les écritures comptables

[!include [banner](../includes/banner.md)]

La fonctionnalité décrite dans cet article permet d’exporter le solde total de chaque compte général pour une période spécifique dans un fichier texte brut (ASCII) au format CED. Vous pouvez ensuite importer le fichier généré dans un logiciel tiers pour créer un état comptable en fonction des exigences spécifiques au pays/à la région.

Cette fonctionnalité est disponible pour les entités juridiques dont l’adresse principale est en Belgique.

## <a name="prerequisites"></a>Conditions préalables

### <a name="create-posting-journals"></a>Créer des journaux de validation

1. Allez dans **Comptabilité** \> **Paramétrage du journal** \> **Journaux de validation**.
2. Sur la page **Paramétrage du journal**, sélectionnez **Créer**. Les journaux de validation et les souches de numéros correspondantes sont créés automatiquement.

## <a name="export-ledger-transactions-to-a-plain-text-file-in-ced-format"></a>Exporter les écritures comptables dans un fichier texte brut ASCII au format CED

### <a name="setup"></a>Paramétrage

1. Depuis le [référentiel global Microsoft](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md), importez les dernières versions des configurations de rapports électroniques (ER) pour le format de rapport suivant.

    | **Version Dynamics 365 Finance**          | **Nom de la configuration**                                                                                           |
    |-------------------------------------------|------------------------------------------------------------------------------------------------------------------|
    | Avant 10.0.16                            | **Format d’exportation des écritures comptables** sous **États comptables** >  **modèle Exportation des écritures comptables**. |
    | À partir de 10.0.16                     | **Exportation des données de comptabilité générale** sous le modèle **Fichier d’audit standard (SAF-T)**.                                  |

    > ![Configurations ER.](media/be-audit-er-configs.png)

2. Après l’importation, vous devez disposer des versions suivantes, ou les versions ultérieures, des configurations ER :

    | **Nom de la configuration ER**         | **Type**           | **Version** | **Description**                                                                                                             |
    |-----------------------------------|--------------------|-------------|-----------------------------------------------------------------------------------------------------------------------------|
    | Fichier d’audit standard (SAF-T)       | Modèle              | 82          | Le modèle ER commun pour les fichiers d’audit standard.                                                                               |
    | Mappage du modèle de données de la comptabilité | Mise en correspondance des modèles      | 82.13       | Le mappage de modèle qui définit les sources de données pour les données de comptabilité.                                                        |
    | Exportation des données de comptabilité (BE)   | Format (exportation) | 82.8        | Le format de texte représentant les données de comptabilité pouvant être importées dans un logiciel tiers. |

    > [!NOTE]
    > Une fois toutes les configurations ER du tableau précédent importées, définissez l’option **Valeur par défaut pour le mappage de modèle** sur **Oui** pour la configuration **Mappage du modèle de données de comptabilité** sur la page **Configurations**.

    > ![Valeur par défaut de l’option de modèle de mappage.](media/be-audit-default-mm.png)

3. À partir de la version 10.0.16, pour utiliser le format **Exportation des données du grand livre (BE)**, définissez le nom de la configuration ER dans un nouveau paramètre de comptabilité. Accédez à **Comptabilité** > **Paramétrage de la comptabilité** > **Paramètres de comptabilité**. 
4. Développer le raccourci **Rapports électroniques**, puis sélectionnez l’onglet **Comptabilité**. 
5. Dans le groupe **Exportation des écritures comptables**, dans le champ **Exportation des écritures comptables**, sélectionnez le format **Exportation des données de comptabilité**, puis enregistrez le nouveau paramètre.

    ![Paramètre de comptabilité.](media/be-audit-gl-parameter.png)

### <a name="generate-the-export-ledger-transactions-report"></a>Générer le rapport Exportation des écritures comptables

1. Dans Finance, allez dans **Comptabilité** \> **Tâches périodiques** \> **Exporter les écritures comptables**.
2. Si votre version de Finance est antérieure à 10.0.16, dans la boîte de dialogue **Exporter les écritures comptables dans un fichier ASCII au format CED**, dans le champ **Mappage de format**, sélectionnez le format **Format d’exportation des écritures comptables (BE)** que vous venez de télécharger, puis cliquez sur **OK**. À partir de la version 10.0.16, spécifiez le format ER dans les paramètres comptables. Lorsque le format ER est défini dans les paramètres comptables, le système l’utilise pour générer des états.
3. Spécifiez la période de déclaration dans les champs **Date de début** et **Date de fin** dans la boite de dialogue **Paramètres de rapport électronique**.
4. Si la devise comptable de votre entité juridique n’est pas l’EURO et que vous souhaitez générer le rapport en EURO, sélectionnez **Recalculer en Euro** dans la boîte de dialogue. Lorsque la devise comptable n’est pas l’EURO mais que la devise de reporting l’est, et que vous sélectionnez **Recalculer en Euro**, un rapport est généré avec les montants stockés dans la comptabilité dans la devise de reporting. Lorsque ni les devises de comptabilité ni de reporting ne sont l’EURO et que vous sélectionnez **Recalculer en Euro**, le rapport recalcule automatiquement les montants dans la devise comptable en EURO en utilisant le taux de change stocké dans le système à la date de chaque écriture comptable. La génération du rapport peut prendre plus de temps qu’un rapport généré sans aucun recalcul.
5. Lorsque vous générez le rapport **Exporter les écritures comptables** pour une période plus longue, exécutez-le par lots. Pour exécuter le rapport par lots, développez le raccourci **Exécuter en arrière-plan** dans la boîte de dialogue, marquez le paramètre **Traitement par lots** et spécifiez les autres paramètres du lot si nécessaire. Suivez la génération du rapport sur la page **Tâches de reporting électronique**.
6. Cliquez sur **OK** pour générer et télécharger le fichier .txt.

    Par exemple, vous validez les écritures comptables suivantes dans la société DEMF.

| **Date**        | **Type de transaction** | **Compte principal**          | **Compte de contrepartie**        | **Montant net** | **Montant de la TVA** | **Code taxe** |
|-----------------|----------------------|---------------------------|---------------------------|----------------|----------------|--------------------|
| 1 janvier 2020 | Facture client     | 110110 – Compte bancaire en USD |                           | 1 000          | 190            | TVA19              |
| 1 janvier 2020 | Facture fournisseur       |                           | 110120 – Compte bancaire en CNY | 1,095          | 76.65          | EU7                |
| 1 janvier 2020 | Facture client     | 110115 – Compte bancaire en CAD |                           | 800            | 0              | EUS                |

Dans ce cas, le fichier généré contient les données suivantes.

![Données des écritures comptables.](media/1_Export_ledger_transactions.png)

Voici une explication des colonnes de ce fichier :

- La première colonne affiche le code compte général.
- La deuxième colonne affiche le solde débiteur du compte général.
- La troisième colonne affiche le solde créditeur du compte général.
- La quatrième colonne affiche le nom du compte général.

> [!NOTE]
> Pour valider les écritures comptables pour les factures client, allez dans **Comptabilité client** \> **Factures** \> **Toutes factures financières**. Pour les factures fournisseur, allez dans **Comptabilité fournisseur** \> **Factures** \> **Journal des factures**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
