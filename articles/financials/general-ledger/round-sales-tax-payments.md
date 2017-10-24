---
title: "Règles d'arrondissement et de paiements de taxe"
description: "Cet article explique le fonctionnement du paramétrage de la règle d'arrondi sur les administrations fiscales et de l'arrondi du solde de taxe au cours de la tâche Régler et valider la taxe."
author: twheeloc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8de01b77fcbeb65321e60614b6a11d264460208f
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="sales-tax-payments-and-rounding-rules"></a>Règles d'arrondissement et de paiements de taxe

[!include[banner](../includes/banner.md)]


Cet article explique le fonctionnement du paramétrage de la règle d'arrondi sur les administrations fiscales et de l'arrondi du solde de taxe au cours de la tâche Régler et valider la taxe.

Régulièrement, la taxe doit être déclarée et payée à l'administration fiscale. Pour ce faire, exécutez le processus de règlement et de validation de la taxe sur la page Taxe. La taxe pour une période sera réglée pour des comptes de taxe et le solde de taxe sera validé dans le compte de règlement de la taxe. Le solde de la taxe, qui est validé sur le compte de règlement de la taxe, peut être arrondi comme requis par l'administration fiscale en définissant une règle d'arrondissement sur la page Taxe. 

La différence d'arrondissement est validée sur le compte d'arrondissement de la taxe qui est sélectionné dans le champ Comptes pour transactions automatiques dans la comptabilité.

L'exemple ci-dessous illustre la manière dont la règle d'arrondissement fonctionne dans l'administration fiscale.

### <a name="example"></a>Exemple :

La taxe totale pour une période indique un solde de -98 765,43. L'entité juridique a collecté plus de taxes qu'elle n'en a payé. C'est pourquoi, l'entité juridique doit de l'argent à l'administration fiscale. 

L'entité juridique veut utiliser une méthode d'arrondi qui arrondit le solde à l'entier le plus proche. L'utilisateur responsable de la comptabilité des taxes procède comme suit.

1.  Cliquez sur &gt; Taxes indirectes &gt; Taxe &gt; Administrations fiscales
2.  Sur l'organisateur Général, sélectionnez Normal dans le champ Type d'arrondi.
3.  Entrez un nombre dans le champ Arrondi, saisissez 1,00.
4.  Au moment de payer les taxes à l'administration fiscale, ouvrez la page Régler et valider la taxe. (Cliquez sur &gt; Déclarations &gt; Taxe &gt; Régler et valider la taxe.)
5.  Dans le compte de règlement de la taxe, le montant de l'impôt à payer de 98 765,43 est arrondi à 98 765.

Le tableau suivant montre comment un montant de 98 765,43 est arrondi à l'aide de chaque méthode d'arrondi disponible dans le champ Type d'arrondi de la page Administrations fiscales.

| Option du type d'arrondi                | Valeur d'arrondi = 0,01 | Valeur d'arrondi = 0,10 | Valeur d'arrondi = 1,00 | Valeur d'arrondi = 100,00 |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| Standard                              | 98 765,43              | 98 765,40              | 98 765,00              | 98 800,00                |
| Inférieur                            | 98 765,43              | 98 765,40              | 98 765,00              | 98 700,00                |
| Supérieur                         | 98 765,43              | 98 765,50              | 98 766,00              | 98 800,00                |
| Avantage, pour un solde créditeur | 98 765,43              | 98 765,40              | 98 765,00              | 98 700,00                |
| Avantage, pour un solde débiteur  | 98 765,43              | 98 765,50              | 98 766,00              | 98 800,00                |

> [!NOTE]                                                                                  
> Si vous sélectionnez Avantage, l'arrondi est toujours à l'avantage de l'entité juridique. 

Pour plus d'informations, voir les rubriques suivantes :
- [Vue d'ensemble des taxes](indirect-taxes-overview.md)
- [Créer un paiement de taxe](tasks/create-sales-tax-payment.md)
- [Créer des transactions de taxe sur les documents](tasks/create-sales-tax-transactions-documents.md)
- [Afficher les transactions de taxe validées](tasks/view-posted-sales-tax-transactions.md)



