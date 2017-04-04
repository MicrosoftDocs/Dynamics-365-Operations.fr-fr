---
title: Publier des lignes de journal et les documents d&quot;Excel
description: "Cette rubrique explique comment entrer et publier des lignes des journaux des opérations diverses Microsoft Excel. Elle inclut des informations sur les différents modèles que vous pouvez utiliser, en fonction de le type de transactions que vous entrez."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62213
ms.assetid: 211874a7-4bf0-4a0c-96c2-fa05042777d3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 087339cb3002b42bcb985c2ccfc2d97c752a817c
ms.lasthandoff: 03/31/2017


---

# <a name="publish-journal-lines-and-documents-from-excel"></a>Publier des lignes de journal et les documents d'Excel

Cette rubrique explique comment entrer et publier des lignes des journaux des opérations diverses Microsoft Excel. Elle inclut des informations sur les différents modèles que vous pouvez utiliser, en fonction de le type de transactions que vous entrez.

Les utilisateurs peuvent entrer et publier des lignes pour les journaux financiers Microsoft Excel. Une fois qu'un utilisateur crée un journal, ** les lignes en cours dans Excel ** le bouton indique les modèles disponibles. Les modèles sont conçus pour prendre en charge les scénarios spécifiques, mais non chaque combinaison Type de compte est prise en charge dans le journal. Le tableau suivant indique les modèles disponibles et les types de comptes qu'ils prennent en charge.
|                          |                                                                                                                         |                                                                                         |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| **Template**             | ** Types de compte pris en charge **                                                                                             | ** Procédure d'accéder au modèle **                                                          |
| Lignes de journal comptable     | Compte : Comptabilité, client, fournisseur, le compte de contrepartie bancaire : Compte général, client, fournisseur, des intersociétés bancaires est prise en charge.       | Journal des opérations diverses                                                                         |
| Registre des factures         | Compte : Compte de contrepartie de fournisseur : Les de comptabilité intersociétés ne sont pas prises en charge.                                                    | Registre des factures d'Achats                                                                     |
| Journal des factures          | Comptes : Compte de contrepartie de fournisseur : Les de comptabilité intersociétés sont prises en charge.                                                      | Journal des factures de Comptabilité fournisseur                                                                      |
| Facture fournisseur           |                                                                                                                         | Facture fournisseur                                                                          |
| Journal des factures client | Compte : Compte de contrepartie de client : Les de comptabilité intersociétés sont prises en charge.                                                     | Journal des opérations diverses                                                                         |
| Facture financière        |                                                                                                                         | Sous ** facture financière ** la page, cliquez sur ** cours dans Excel ** (l'icône de Microsoft Office). |
| Journal des immobilisations     | Immobilisation à la comptabilité, à la banque, au client, ou au fournisseur. L'intersociétés ne sont pas prises en charge.                                               | Journal des immobilisations                                                                     |
| Journal des paiements fournisseur   | Compte : Compte de contrepartie de fournisseur : La comptabilité, les intersociétés bancaires est prise en charge.                                                 | Journal des paiements fournisseur                                                                  |
| Journal des paiements client | Compte : Compte de contrepartie de client : La comptabilité, les intersociétés bancaires est prise en charge.                                               | Journal des paiements client                                                                |
| Journal des dépenses de projet  | Compte : Projet, Comptabilité, client, compte de contrepartie du fournisseur : Le projet, Comptabilité, client intersociétés, de fournisseur est pris en charge. | Dépenses de journal des opérations diverses (dans la Gestion de projets et comptabilité)                       |

Lorsque les lignes sont émises, elles sont validées pour s'assurer qu'elles sont conformes aux règles paramétrées dans les journaux financiers. Une fois les lignes sont émises, les utilisateurs peuvent modifier ou valider les documents Microsoft Dynamics 365 pour les opérations. 

Pour ajouter des dimensions financières à un modèle, les modifications supplémentaires sont requises. Pour plus d'informations, voir [ajoutez les dimensions dans le modèle Microsoft Excel] (\ DEV -itpro - itpro\dimensions financières\ajouter-dimension-Excel- modèles). Une fois les dimensions soient ajoutées à l'entité, elles sont disponibles dans le concepteur de calcul Excel et peuvent être ajoutées au modèle.




