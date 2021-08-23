---
title: Générer une feuille de distribution des dépenses (FEC) dans Dynamics 365 Finance
description: Cette rubrique explique comment générer un fichier d'audit Fichier des écritures comptables (FEC) dans Microsoft Dynamics 365 Finance.
author: liza-golub
ms.date: 05/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.author: elgolu
ms.reviewer: kfend
ms.search.region: France
ms.openlocfilehash: 7df9a9fd45a6a5fe650c98c376ab42b1d9002a87a5dd7b41515c5416652f01e8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6758786"
---
# <a name="generate-an-fec-in-dynamics-365-finance"></a>Générer une feuille de distribution des dépenses (FEC) dans Dynamics 365 Finance

Pour générer un fichier d'audit du Fichier des écritures comptables (FEC), procédez comme suit.

1. Accédez à **Comptabilité** \> **Tâches périodiques** \> **Exportation des données**. 
2. Si le format de rapport électronique (ER) n'est pas configuré dans le champ **Mappage de format** sur la page **Paramètres du compte général**, sélectionnez **Dossier d'audit FEC (FR)** dans le champ **Mappage de format** sur la page **Export de données**. Puis sélectionnez **OK**. 
3. Si le format ER est configuré dans le champ **Mappage de format** sur la page **Paramètres Comptabilité**, la page **Export de données** n'apparaît pas. Vous pouvez accéder directement à la boîte de dialogue du rapport.
4. Dans la page **Paramètres de génération d’états électroniques**, dans les champs **Période – date de début** et **Période – Date de fin**, entrez les dates de début et de fin pour la période.
5. Dans le champ **Composition du contenu du rapport FEC**, sélectionnez un ou plusieurs des fichiers de sortie suivants à générer, puis sélectionnez **Sélectionner**.

    | Nom                   | Description  | Conditions |
    |------------------------|-------------|------------|
    | FEC principal               | Fichier FEC principal pour la période spécifiée | Pour cette partie du rapport, définissez les champs **Période - date de début** et **Période - date de fin**. Dans le champ **Période - date de début**, si vous spécifiez le début de l'exercice, les transactions du type **ouverture** sont incluses au début du fichier FEC. Si la période de déclaration spécifiée n'est pas un exercice complet, le numéro de la période de l'exercice concerné est ajouté au nom du fichier (par exemple, **123456789FEC20131231\_01**). |
    | Soldes client     | Annexe sur les soldes d'ouverture de l'exercice client | Pour cette partie du rapport, définissez le champ **Période - date de début**. Le rapport est généré pour le début de l'exercice car il est lié à la date spécifiée dans le champ **Période - date de début**. Valeurs dans les colonnes **JournalCode**, **JournalLib**, **EcritureNum**, **PieceRef** et **EcritureLib** du rapport représentent les valeurs collectées à partir des transactions du compte général du type **ouverture** pour l'exercice comptable. |
    | Soldes fournisseur       | Annexe sur les soldes d'ouverture de l'exercice fournisseur | Pour cette partie du rapport, définissez le champ **Période - date de début**. Le rapport est généré pour le début de l'exercice car il est lié à la date spécifiée dans le champ **Période - date de début**. Valeurs dans les colonnes **JournalLib**, **EcritureNum**, **PieceRef** et **EcritureLib** du rapport représentent les valeurs collectées à partir des transactions du compte général du type **ouverture** pour l'exercice comptable. |
    | Transactions client | Annexe des transactions clients pour une période déterminée. | Pour cette partie du rapport, définissez les champs **Période - date de début** et **Période - date de fin**. |
    | Transactions fournisseur   | Annexe des transactions fournisseur pour une période déterminée. | Pour cette partie du rapport, définissez les champs **Période - date de début** et **Période - date de fin**. |
    | FEC principal étendu      | Fichier principal FEC qui comprend les détails du solde d'ouverture de l'exercice pour les clients et les fournisseurs. | Pour cette partie du rapport, définissez les champs **Période - date de début** et **Période - date de fin**. Assurez-vous que la période spécifiée inclut le début d'un exercice fiscal. |

6. Opérations du compte général qui sont incluses dans les types de rapport **FEC principal** et **FEC principal étendu** doivent être filtrés par couche de validation **Actuel**. Seuls les comptes principaux commençant par **1**, **2**, **3**, **4**, **5**, **6** ou **7** doivent être inclus dans le FEC. Utilisez le champ **Enregistrements à inclure** pour filtrer les enregistrements que le rapport doit inclure. Utilisez le filtre pour rapporter les données qui respectent les règles du Livre des procédures fiscales, article A47 A-1, chapitre VII : "Le numéro de compte, ne les trois premiers caractères doivent correspondre à des chiffres respectant les normes du plan comptable français. »
7. Pour générer le rapport en mode batch, sur le raccourci **Exécuter à l’arrière-plan**, spécifiez les paramètres du lot.
8. Lorsque vous avez terminé de spécifier tous les paramètres, sélectionnez **OK** pour générer le rapport.
