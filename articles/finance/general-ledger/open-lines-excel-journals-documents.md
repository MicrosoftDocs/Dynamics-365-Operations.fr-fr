---
title: Publier des lignes de journal et les documents d’Excel
description: Cette rubrique explique comment entrer et publier des lignes de journaux d’opérations diverses issues de Microsoft Excel. Elle inclut des informations sur les différents modèles que vous pouvez utiliser, en fonction du type de transactions que vous entrez.
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 62213
ms.assetid: 211874a7-4bf0-4a0c-96c2-fa05042777d3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f87ce1dcbae779f875abcbffd1781bbf076b1b7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230248"
---
# <a name="publish-journal-lines-and-documents-from-excel"></a>Publier des lignes de journal et les documents d’Excel

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment entrer et publier des lignes de journaux d’opérations diverses issues de Microsoft Excel. Elle inclut des informations sur les différents modèles que vous pouvez utiliser, en fonction du type de transactions que vous entrez.

Les utilisateurs peuvent entrer et publier des lignes pour les journaux financiers provenant de Microsoft Excel. Une fois qu’un utilisateur crée un journal, le bouton **Ouvrir les lignes dans Excel** indique les modèles disponibles. Les modèles sont conçus pour prendre en charge des scénarios spécifiques, mais toutes les combinaisons de type de compte ne sont pas prises en charge dans le journal. Le tableau suivant indique les modèles disponibles et les types de comptes pris en charge.

|                          |                                                                                                                         |                                                                                         |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| **Modèle**             | **Types de compte pris en charge**                                                                                             | **Procédure d’accès au modèle**                                                          |
| Lignes de journal comptable     | Compte : Comptabilité, Client, Fournisseur, Compte de contrepartie bancaire : Comptabilité, Client, Fournisseur, Intersociétés bancaires est pris en charge.       | Journal des opérations diverses                                                                         |
| Registre des factures         | Compte : Compte de contrepartie fournisseur : Comptabilité Intersociétés n’est pas pris en charge.                                                    | Registre des factures AP                                                                     |
| Journal des factures          | Comptes : Compte de contrepartie fournisseur : Comptabilité intersociétés est pris en charge.                                                      | Journal des factures de Comptabilité fournisseur                                                                      |
| Facture fournisseur           |                                                                                                                         | Facture fournisseur                                                                          |
| Journal des factures client | Compte : Compte de contrepartie client : Comptabilité intersociétés est pris en charge.                                                     | Journal des opérations diverses                                                                         |
| Facture financière        |                                                                                                                         | Sur la page **Facture financière**, cliquez sur **Ouvrir dans Excel** (icône de Microsoft Office). |
| Journal des immobilisations     | Transfert d’immobilisation vers la comptabilité, la banque, le client ou le fournisseur. Intersociétés n’est pas pris en charge.                                               | Journal des immobilisations                                                                     |
| Journal des paiements fournisseur   | Compte : Compte de contrepartie fournisseur : Intersociétés banque est pris en charge.                                                 | Journal des paiements fournisseur                                                                  |
| Journal des paiements client | Compte : Compte de contrepartie client : Comptabilité, Intersociétés banque est pris en charge.                                               | Journal des paiements client                                                                |
| Journal des dépenses de projet  | Compte : Projet, Comptabilité, Client, Fournisseur, Compte de contrepartie fournisseur : Projet, Comptabilité, Client, Fournisseur, Intersociétés fournisseurs est pris en charge. | Dépenses de journal d’opérations diverses (sous Gestion de projets et comptabilité)                       |

Lorsque les lignes sont émises, elles sont validées pour s’assurer qu’elles sont conformes aux règles paramétrées dans les journaux financiers. Une fois que les lignes sont émises, les utilisateurs peuvent modifier ou valider les documents Dynamics 365 Finance. 

Pour ajouter des dimensions financières à un modèle, des modifications supplémentaires sont requises. Pour plus d’informations, voir [Ajouter des dimensions au modèle Microsoft Excel](../../dev-itpro/financial/add-dimensions-excel-templates.md). Une fois que les dimensions sont ajoutées à l’entité, elles sont disponibles dans le concepteur Excel et peuvent être ajoutées au modèle.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]