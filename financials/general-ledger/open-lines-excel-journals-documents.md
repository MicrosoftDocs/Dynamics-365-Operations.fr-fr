---
title: Publier des lignes de journal et les documents d'Excel
description: "Cette rubrique explique comment entrer et publier des lignes de journaux d'opérations diverses issues de Microsoft Excel. Elle inclut des informations sur les différents modèles que vous pouvez utiliser, en fonction du type de transactions que vous entrez."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62213
ms.assetid: 211874a7-4bf0-4a0c-96c2-fa05042777d3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 1fed8d162a37736883365fa765a059e5beff06be
ms.contentlocale: fr-fr
ms.lasthandoff: 06/13/2017

---

# <a name="publish-journal-lines-and-documents-from-excel"></a>Publier des lignes de journal et les documents d'Excel

[!include[banner](../includes/banner.md)]


Cette rubrique explique comment entrer et publier des lignes de journaux d'opérations diverses issues de Microsoft Excel. Elle inclut des informations sur les différents modèles que vous pouvez utiliser, en fonction du type de transactions que vous entrez.

Les utilisateurs peuvent entrer et publier des lignes pour les journaux financiers provenant de Microsoft Excel. Une fois qu'un utilisateur crée un journal, le bouton **Ouvrir les lignes dans Excel** indique les modèles disponibles. Les modèles sont conçus pour prendre en charge des scénarios spécifiques, mais toutes les combinaisons de type de compte ne sont pas prises en charge dans le journal. Le tableau suivant indique les modèles disponibles et les types de comptes pris en charge.
|                          |                                                                                                                         |                                                                                         |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| **Modèle**             | **Types de compte pris en charge**                                                                                             | **Procédure d'accès au modèle**                                                          |
| Lignes de journal comptable     | Compte : Comptabilité, Client, Fournisseur, Compte de contrepartie bancaire : Comptabilité, Client, Fournisseur, Intersociétés bancaires est pris en charge.       | Journal des opérations diverses                                                                         |
| Registre des factures         | Compte : Compte de contrepartie fournisseur : Comptabilité Intersociétés n'est pas pris en charge.                                                    | Registre des factures AP                                                                     |
| Journal des factures          | Comptes : Compte de contrepartie fournisseur : Comptabilité intersociétés est pris en charge.                                                      | Journal des factures de Comptabilité fournisseur                                                                      |
| Facture fournisseur           |                                                                                                                         | Facture fournisseur                                                                          |
| Journal des factures client | Compte : Compte de contrepartie client : Comptabilité intersociétés est pris en charge.                                                     | Journal des opérations diverses                                                                         |
| Facture financière        |                                                                                                                         | Sur la page **Facture financière**, cliquez sur **Ouvrir dans Excel** (icône de Microsoft Office). |
| Journal des immobilisations     | Transfert d'immobilisation vers la comptabilité, la banque, le client ou le fournisseur. Intersociétés n'est pas pris en charge.                                               | Journal des immobilisations                                                                     |
| Journal des paiements fournisseur   | Compte : Compte de contrepartie fournisseur : Intersociétés banque est pris en charge.                                                 | Journal des paiements fournisseur                                                                  |
| Journal des paiements client | Compte : Compte de contrepartie client : Comptabilité, Intersociétés banque est pris en charge.                                               | Journal des paiements client                                                                |
| Journal des dépenses de projet  | Compte : Projet, Comptabilité, Client, Fournisseur, Compte de contrepartie fournisseur : Projet, Comptabilité, Client, Fournisseur, Intersociétés fournisseurs est pris en charge. | Dépenses de journal d'opérations diverses (sous Gestion de projets et comptabilité)                       |

Lorsque les lignes sont émises, elles sont validées pour s'assurer qu'elles sont conformes aux règles paramétrées dans les journaux financiers. Une fois que les lignes sont émises, les utilisateurs peuvent modifier ou valider les documents Microsoft Dynamics 365 for Finance and Operations, Enterprise edition. 

Pour ajouter des dimensions financières à un modèle, des modifications supplémentaires sont requises. Pour plus d'informations, voir [Ajouter des dimensions au modèle Microsoft Excel](/dynamics365/unified-operations/dev-itpro/financial/add-dimensions-excel-templates). Une fois que les dimensions sont ajoutées à l'entité, elles sont disponibles dans le concepteur Excel et peuvent être ajoutées au modèle.






