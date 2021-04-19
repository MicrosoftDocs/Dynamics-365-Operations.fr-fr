---
title: Génération du fichier d’audit standard pour la France (FEC)
description: Cette rubrique décrit le processus de génération du fichier d’audit standard pour la France (FEC) dans Microsoft Dynamics 365 Finance.
author: anasyash
ms.date: 01/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: France
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cb2324ad158b548c4a35e6a74e110058e0326c32
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826080"
---
# <a name="generate-the-standard-audit-file-for-france-fec"></a>Génération du fichier d’audit standard pour la France (FEC)

[!include [banner](../includes/banner.md)]

Cette procédure vous montre comment générer le fichier d’audit standard (FEC) pour la France dans le format de fichier électronique. L’administration fiscale française a besoin de fichiers d’audit générés au format FEC.

Avant de générer un fichier d’audit FEC, vous devez :

1. Définir les souches des N° documents. Chaque souche de N° de justificatif doit contenir une partie du texte considérée comme une valeur pour **JournalCode** dans l’état **Audit FEC**. Par exemple, configurez une souche de N° de justificatif pour les journaux de facture fournisseur comme **FRSIFACF-########** pour obtenir la valeur « FRSIFACF » dans **JournalCode** dans le fichier FEC.txt.
2. Importer la dernière version du **Fichier d’audit FEC français** de la configuration de génération d’états électroniques. Pour plus d’informations, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
3. Sur la page **Configurations**, développez **Modèle d’exportation des données**, sélectionnez **Mise en correspondance de modèle FEC français**, et paramétrez **Valeur par défaut de la mise en correspondance des modèles** sur **Oui**.

## <a name="generate-the-standard-audit-file-for-france"></a>Générer le fichier d’audit standard pour la France
1. Accédez à **Comptabilité générale** > **Tâches périodiques** > **Exportation de données** pour ouvrir la page **Exportation de données**.
2. Dans le champ **Mise en correspondance des formats**, sélectionnez **Fichier d’audit FEC français**.
3. Cliquez sur **OK**.
4. Dans la page **Paramètres de génération d’états électroniques**, entrez les dates de début et de fin pour la période dans les champs **Période – date de début** et **Période – Date de fin**. Cliquez sur **OK**.
5. Examinez le fichier généré.

## <a name="review-the-standard-audit-file"></a>Consultez le fichier d’audit standard
Lorsque le fichier d’audit standard est généré, un fichier d’archive avec les cinq rapports suivants est également généré.

- FEC.txt
- Fournisseur Stock en entrée.txt
- Client Stock en entrée.txt
- Solde fournisseur.txt
- Solde client.txt

Envisagez les informations suivantes pour certains champs suivants dans les états :

- **JournalCode** : contient la partie texte du N° document. Si la souche de N° documents n’a pas de partie texte, la valeur sera vide. Assurez-vous de configurer correctement la souche de N° documents afin d’avoir la valeur correcte dans ce champ.
- **JournalLib** : 

   - Dans les états **Solde fournisseur.txt** et **Solde client.txt**, cela doit être la valeur constante **Système**.
   - Dans les états **Fournisseur Stock en entrée.txt** et **Client Stock en entrée.txt**, c’est la valeur du champ **Type de transaction des états** à partir de la transaction fournisseur ou transaction client rapportée. Par exemple, les valeurs possibles peuvent être **Commande fournisseur** ou **Paiement**.
   - Dans l’état **FEC.txt**, c’est la valeur du champ **Type de transaction** de l’état Transaction de documents. Si le **Type de transaction** équivaut à **Feuille comptabilité**, c’est la valeur dans le champ **Description** du journal comptable qui est la source de la transaction de documents. Vérifiez en consultant la valeur sur la page **Noms de journal**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]