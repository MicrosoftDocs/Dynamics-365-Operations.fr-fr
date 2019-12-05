---
title: Règles d'arrondissement et de paiements de taxe
description: Cet article explique le fonctionnement du paramétrage de la règle d'arrondi sur les administrations fiscales et de l'arrondi du solde de taxe au cours de la tâche Régler et valider la taxe.
author: ShylaThompson
manager: AnnBe
ms.date: 05/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: yijialuan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4e66a62007025964b3d58ff0620ebecd6d9769f9
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771750"
---
# <a name="sales-tax-payments-and-rounding-rules"></a>Règles d'arrondissement et de paiements de taxe

[!include [banner](../includes/banner.md)]

Cet article explique le fonctionnement du paramétrage de la règle d'arrondi sur les administrations fiscales et de l'arrondi du solde de taxe au cours de la tâche Régler et valider la taxe.

Régulièrement, la taxe doit être déclarée et payée à l'administration fiscale. Pour ce faire, exécutez le processus de règlement et de validation de la taxe sur la page Taxe. La taxe pour une période sera réglée pour des comptes de taxe et le solde de taxe sera validé dans le compte de règlement de la taxe. Le solde de la taxe, qui est validé sur le compte de règlement de la taxe, peut être arrondi comme requis par l'administration fiscale en définissant une règle d'arrondissement sur la page Taxe. 

La différence d'arrondissement est validée sur le compte d'arrondissement de la taxe qui est sélectionné dans le champ Comptes pour transactions automatiques dans la comptabilité.

L'exemple ci-dessous illustre la manière dont la règle d'arrondissement fonctionne dans l'administration fiscale.

## <a name="examples"></a>Exemples

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
| Avantage, pour un solde débiteur  | 98,765.43              | 98,765.50              | 98,766.00              | 98,800.00                |


### <a name="no-rounding-at-all-since-the-round-off-is-000"></a>Aucun arrondi du tout, car la précision d'arrondi est 0,00

round(1,0151, 0,00) = 1,0151 round(1,0149, 0,00) = 1,0149

### <a name="normal-round-and-round-precision-is-001"></a>Arrondi normal, et précision d'arrondi 0,01

<table>
  <tr>
    <td>Arrondi
    </td>
    <td>Processus de calcul
    </td>
  </tr>
    <tr>
    <td>round(1,015, 0,01) = 1,02
    </td>
    <td>
      <ol>
        <li>round(1,015 / 0,01, 0) = round(101,5, 0) = 102
        </li>
        <li>102 * 0,01 = 1,02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1,014, 0,01) = 1,01
    </td>
    <td> <ol>
        <li>round(1,014 / 0,01, 0) = round(101,4, 0) = 101
        </li>
        <li>101 * 0,01 = 1,01
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1,011, 0,02) = 1,02
    </td>
    <td> <ol>
        <li>round(1,011 / 0,02, 0) = round(50,55, 0) = 51
        </li>
        <li>51 * 0,02 = 1,02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1,009, 0,02) = 1,00
    </td>
    <td> <ol>
        <li>round(1,009 / 0,02, 0) = round(50,45, 0) = 50
        </li>
        <li>50 * 0,02 = 1,00
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> Si vous sélectionnez Avantage, l'arrondi est toujours à l'avantage de l'entité juridique. 

Pour plus d'informations, voir les rubriques suivantes :
- [Vue d'ensemble des taxes](indirect-taxes-overview.md)
- [Créer un paiement de taxe](tasks/create-sales-tax-payment.md)
- [Créer des transactions de taxe sur les documents](tasks/create-sales-tax-transactions-documents.md)
- [Afficher les transactions de taxe validées](tasks/view-posted-sales-tax-transactions.md)
- [Fonction round](https://msdn.microsoft.com/library/aa850656.aspx)


