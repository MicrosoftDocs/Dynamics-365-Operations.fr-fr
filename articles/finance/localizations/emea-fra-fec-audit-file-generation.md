---
title: Générer un FEC dans Dynamics 365 Finance
description: Cet article explique comment générer un fichier d’audit Fichier des écritures comptables (FEC) dans Microsoft Dynamics 365 Finance.
author: liza-golub
ms.date: 05/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.author: elgolu
ms.reviewer: kfend
ms.search.region: France
ms.openlocfilehash: 2b6e2863fb59c1043aff07496ce491bd999b52cb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902356"
---
# <a name="generate-an-fec-in-dynamics-365-finance"></a>Générer un FEC dans Dynamics 365 Finance

Pour générer un fichier d’audit du Fichier des écritures comptables (FEC), procédez comme suit.

1. Accédez à **Comptabilité** \> **Tâches périodiques** \> **Exportation des données**. 
2. Si le format de rapport électronique (ER) n’est pas configuré dans le champ **Mappage de format** sur la page **Paramètres du compte général**, sélectionnez **Dossier d’audit FEC (FR)** dans le champ **Mappage de format** sur la page **Export de données**. Puis sélectionnez **OK**. 
3. Si le format ER est configuré dans le champ **Mappage de format** sur la page **Paramètres Comptabilité**, la page **Export de données** n’apparaît pas. Vous pouvez accéder directement à la boîte de dialogue du rapport.
4. Dans la page **Paramètres de génération d’états électroniques**, dans les champs **Période – date de début** et **Période – Date de fin**, entrez les dates de début et de fin pour la période.
5. Dans le champ **Composition du contenu du rapport FEC**, sélectionnez un ou plusieurs des fichiers de sortie suivants à générer, puis sélectionnez **Sélectionner**.

    | Nom                            | Description | Conditions |
    |---------------------------------|-------------|------------|
    | 1 FEC principal                      | Fichier FEC principal pour la période spécifiée | Pour cette partie du rapport, définissez les champs **Période - date de début** et **Période - date de fin**. Dans le champ **Période - date de début**, si vous spécifiez le début de l’exercice, les transactions du type **ouverture** sont incluses au début du fichier FEC. Si la période de déclaration spécifiée n’est pas un exercice complet, le numéro de la période de l’exercice concerné est ajouté au nom du fichier (par exemple, **123456789FEC20131231\_01**). |
    | 2 Soldes client            | Annexe des soldes d’ouverture de l’exercice pour les clients | Pour cette partie du rapport, définissez le champ **Période - date de début**. Le rapport est généré pour le début de l’exercice car il est lié à la date spécifiée dans le champ **Période - date de début**. Valeurs dans les colonnes **JournalCode**, **JournalLib**, **EcritureNum**, **PieceRef** et **EcritureLib** du rapport représentent les valeurs collectées à partir des transactions du compte général du type **ouverture** pour l’exercice comptable. |
    | 3 Soldes fournisseur              | Annexe des soldes d’ouverture de l’exercice pour les fournisseurs | Pour cette partie du rapport, définissez le champ **Période - date de début**. Le rapport est généré pour le début de l’exercice car il est lié à la date spécifiée dans le champ **Période - date de début**. Valeurs dans les colonnes **JournalLib**, **EcritureNum**, **PieceRef** et **EcritureLib** du rapport représentent les valeurs collectées à partir des transactions du compte général du type **ouverture** pour l’exercice comptable. |
    | 4 Transactions client        | Annexe des transactions clients pour une période déterminée | Pour cette partie du rapport, définissez les champs **Période - date de début** et **Période - date de fin**. |
    | 5 Transactions fournisseur          | Annexe des transactions fournisseurs pour une période déterminée | Pour cette partie du rapport, définissez les champs **Période - date de début** et **Période - date de fin**. |
    | 6 FEC principal étendu             | Fichier FEC principal incluant les détails des soldes d’ouverture de l’exercice pour les clients et les fournisseurs | Pour cette partie du rapport, définissez les champs **Période - date de début** et **Période - date de fin**. Assurez-vous que la période spécifiée inclut le début d’un exercice fiscal. |
    | 7 Justification pour les numéros manquants | À partir de la version 10.0.23 de Finance, utilisez cette annexe pour déclarer les documents de la comptabilité qui manquent dans le fichier FEC principal. | Pour cette partie du rapport, définissez les champs **Période - date de début** et **Période - date de fin**. |

6. Opérations du compte général qui sont incluses dans les types de rapport **FEC principal** et **FEC principal étendu** doivent être filtrés par couche de validation **Actuel**. Seuls les comptes principaux commençant par **1**, **2**, **3**, **4**, **5**, **6** ou **7** doivent être inclus dans le FEC. Utilisez le champ **Enregistrements à inclure** pour filtrer les enregistrements que le rapport doit inclure. Utilisez le filtre pour rapporter les données qui respectent les règles du Livre des procédures fiscales, article A47 A-1, chapitre VII : "Le numéro de compte, ne les trois premiers caractères doivent correspondre à des chiffres respectant les normes du plan comptable français. »
7. Pour générer le rapport en mode batch, sur le raccourci **Exécuter à l’arrière-plan**, spécifiez les paramètres du lot.
8. Lorsque vous avez terminé de spécifier tous les paramètres, sélectionnez **OK** pour générer le rapport.
