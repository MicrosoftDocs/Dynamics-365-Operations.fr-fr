---
title: Exemples et logique de l’état de valeur des stocks
description: Cette rubrique fournit quelques exemples de résultats qui sont présentés sur chaque type de rapport de valeur de stock. Les rapports sur la valeur du stock fournissent des détails sur les quantités et les montants physiques et financiers de votre stock.
author: JennySong-SH
ms.date: 10/19/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-10-19
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 0d594fc18a104c434a334a5b6d1d249330a6be9a
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675317"
---
# <a name="inventory-value-report-examples-and-logic"></a>Exemples et logique de l’état de valeur des stocks

[!include [banner](../includes/banner.md)]

Les rapports sur la valeur du stock fournissent des détails sur les quantités et les montants physiques et financiers de votre stock. Cette rubrique fournit quelques exemples de résultats qui sont présentés sur chaque type de rapport de valeur de stock.

Pour plus d’informations sur la façon de générer et d’utiliser chaque type de rapport de valeur d’inventaire, voir [Rapports de valeur de stock](inventory-value-report-storage.md).

## <a name="sample-data-that-is-used-in-these-examples"></a>Exemples de données utilisées

Les exemples de cette rubrique sont basés sur les exemples de données de transaction de stock décrits dans cette section.

### <a name="storage-dimension-setup"></a>Configuration de la dimension de stockage

L’exemple de système contient la configuration suivante des dimensions de stockage.

| Nom | Actifs | Stock physique | Stock financier |
|---|---|---|---|
| Site | Oui | Oui | Oui |
| Entrepôt | Oui | Oui | Non |

### <a name="inventory-model"></a>Modèle de stock

Pour l’exemple de système, le modèle de stock pour les produits lancés est *FIFO*, et le champ **Prix de revient** du modèle de stock est défini sur *Inclure une valeur physique*.

### <a name="inventory-transactions"></a>Mouvements de stock

L’exemple de système contient les transactions de stock suivantes pour un produit lancé portant le numéro d’article *B0001*.

| Référence | Site | Entrepôt | Récépissé | Problème | Date physique | Date financière | Quantité | Coût | Montant du coût physique |
|---|---|---|---|---|---|---|---|---|---|
| Commande fournisseur | 1 | 11 | Acheté | | 15 mars | 15 mars | 10 | 1 000 | 1 000 |
| Commande fournisseur | 2 | 21 | Acheté | | 15 mars | 15 mars | 10 | 2,000 | 2,000 |
| Commande fournisseur | 1 | 11 | Reçu(e) | | 15 avril | | 5 | | 375 |
| Ordre de transfert | 1 | 11 | | Vendu | mai 2 | mai 2 | -5 | -458,33 | -458,33 |
| Ordre de transfert | 1 | 12 | Acheté | | mai 2 | mai 2 | 5 | 458.33 | 458.33 |
| Commande de vente | 1 | 12 | | Vendu | mai 3 | mai 3 | -1 | -91,67 | -91,67 |

### <a name="inventory-value-report-configuration"></a>Configuration de l’état de valeur de stock

L’exemple de système comprend une configuration de rapport de valeur de stock qui a les paramètres suivants :

- **Plage :** *Date de validation*
- **Stock :** *Oui*
- **Calculer le coût unitaire moyen :** *Oui*
- **Quantité et valeur totales :** *Oui*
- **Site, vue :** *Sélectionné*
- **ID de ressource, vue :** *Oui*
- **Niveau :** *Totaux*

## <a name="inventory-value-report-example-1"></a>Exemple de l’état de valeur de stock 1

Le tableau et les illustrations suivants montrent les résultats lorsque vous utilisez les exemples de configuration de données et de rapport décrits plus haut dans cette rubrique.

| Type de ressource | Ressource | Site | Référence | Stock : quantité financière | Stock : montant financier | Stock : quantité physique validée | Stock : montant physique validé | Stock : quantité | Stock : montant | Coût unitaire moyen |
|---|---|---|---|---|---|---|---|---|---|---|
| Matière | B0001 | 1 | Solde de fin | 9.00 | 908.33 | 5.00 | 375.00 | 14,00 | 1,283.33 | 91.67 |
| Matière | B0001 | 2 | Solde de fin | 10.00 | 2,000.00 | 0,00 | 0,00 | 10.00 | 2,000.00 | 200.00 |

### <a name="standard-inventory-value-report-for-example-1"></a>Rapport de valeur de stock standard pour l’exemple 1

L’illustration suivante montre le rapport **Valeur de stock** standard pour l’exemple 1. (Sélectionnez l’illustration pour ouvrir une version plus grande.)

[![Rapport de valeur de stock pour l’exemple 1.](media/inventory-value-report-ex1-small.png "Rapport de valeur de stock pour l’exemple 1")](media/inventory-value-report-ex1.png)

### <a name="inventory-value-report-storage-report-for-example-1"></a>Rapport de stockage de rapport de valeur de stock pour l’exemple 1

L’illustration suivante montre le rapport **Stockage du rapport de valeur de stock** pour l’exemple 1. (Sélectionnez l’illustration pour ouvrir une version plus grande.)

[![Rapport de stockage de rapport de valeur de stock pour l’exemple 1.](media/inventory-value-report-storage-ex1-small.png "Rapport de stockage de rapport de valeur de stock pour l’exemple 1")](media/inventory-value-report-storage-ex1.png)

## <a name="inventory-value-report-example-2"></a>Exemple de l’état de valeur de stock 2

Le tableau et les illustrations suivants montrent les résultats lorsque vous utilisez les exemples de données décrits plus haut dans cette rubrique, mais que vous modifiez la valeur du champ **Niveau** sur *Transactions* dans la configuration du rapport, et le champ **Date de début** sur *15 mars* lorsque vous exécutez le rapport.

| Type de ressource | Ressource | Site | Date | Nombre | Référence | Stock : quantité financière | Stock : montant financier | Stock : quantité physique validée | Stock : montant physique validé | Stock : quantité | Stock : montant |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Matière | B0001 | 1 | 15/03/2021 | 00000126 | Commande fournisseur | 0,00 | 0,00 | 10.00 | 1,000.00 | **10.00** | **1 000,00** |
| Matière | B0001 | 1 | 15/03/2021 | 00000126 | Commande fournisseur | 10.00 | 1,000.00 | -10,00 | -1 000,00 | **0.00** | **0.00** |
| Matière | B0001 | 1 | 15/04/2021 | 00000128 | Commande fournisseur | 0,00 | 0,00 | 5.00 | 375.00 | **5.00** | **375.00** |
| Matière | B0001 | 1 | 02/05/2021 | 000003 | Expédition de l’ordre de transfert | -5,00 | -458,33 | 0,00 | 0,00 | **-5.00** | **-458.33** |
| Matière | B0001 | 1 | 02/05/2021 | 000003 | Réception de l’ordre de transfert | 5.00 | 458.33 | 0,00 | 0,00 | **5.00** | **458.33** |
| Matière | B0001 | 1 | 03/05/2021 | 000835 | Commande de vente | 0,00 | 0,00 | -1,00 | -91,67 | **-1.00** | **-91.67** |
| Matière | B0001 | 1 | 03/05/2021 | 000835 | Commande de vente | -1,00 | -91,67 | 1.00 | 91.67 | **0.00** | **0.00** |
| Matière | B0001 | 2 | 15/03/2021 | 00000127 | Commande fournisseur | 0,00 | 0,00 | 10.00 | 2,000.00 | **10.00** | **2,000.00** |
| Matière | B0001 | 2 | 15/03/2021 | 00000127 | Commande fournisseur | 10.00 | 2,000.00 | -10,00 | -2 000,00 | **0.00** | **0.00** |
| Matière | B0001 | 2 | 02/05/2021 | 000003 | Expédition de l’ordre de transfert | 5.00 | 458.33 | 0,00 | 0,00 | **5.00** | **458.33** |
| Matière | B0001 | 2 | 02/05/2021 | 000003 | Réception de l’ordre de transfert | -5,00 | -458,33 | 0,00 | 0,00 | **-5.00** | **-458.33** |

### <a name="standard-inventory-value-report-for-example-2"></a>Rapport de valeur de stock standard pour l’exemple 2

L’illustration suivante montre le rapport **Valeur de stock** standard pour l’exemple 2. (Sélectionnez l’illustration pour ouvrir une version plus grande.)

[![Rapport de valeur de stock pour l’exemple 2.](media/inventory-value-report-ex2-small.png "Rapport de valeur de stock pour l’exemple 2")](media/inventory-value-report-ex2.png)

### <a name="inventory-value-report-storage-report-for-example-2"></a>Rapport de stockage de rapport de valeur de stock pour l’exemple 2

L’illustration suivante montre le rapport **Stockage du rapport de valeur de stock** pour l’exemple 2. (Sélectionnez l’illustration pour ouvrir une version plus grande.)

[![Rapport de stockage de rapport de valeur de stock pour l’exemple 2.](media/inventory-value-report-storage-ex2-small.png "Rapport de stockage de rapport de valeur de stock pour l’exemple 2")](media/inventory-value-report-storage-ex2.png)

## <a name="inventory-value-report-example-3"></a>Exemple de l’état de valeur de stock 3

Nous vous recommandons d’exécuter des rapports sur la valeur du stock après le recalcul ou la clôture du stock, afin que vous disposiez des transactions et des montants qui sont affectés par le recalcul ou la clôture du stock.

Les sous-sections suivantes présentent les rapports sur la valeur de stock générés après la clôture de l’inventaire jusqu’au 30 mai.

### <a name="example-3-when-the-totals-level-is-used"></a>Exemple 3 lorsque le niveau Totaux est utilisé

Le tableau suivant montre les résultats lorsque vous utilisez les exemples de configuration de données et de rapport décrits plus haut dans cette rubrique. (Dans cette configuration de rapport, le champ **Niveau** est défini sur *Totaux*.)

| Type de ressource | Ressource | Site | Référence | Stock : quantité financière | Stock : montant financier | Stock : quantité physique validée | Stock : montant physique validé | Stock : quantité | Stock : montant | Coût unitaire moyen |
|---|---|---|---|---|---|---|---|---|---|---|
| Matière | B0001 | 1 | Solde de fin | 9.00 | 900.00 | 5.00 | 375.00 | 14,00 | 1,275.00 | 91.07 |
| Matière | B0001 | 2 | Solde de fin | 10.00 | 2,000.00 | 0,00 | 0,00 | 10.00 | 2,000.00 | 200.00 |

### <a name="example-3-when-the-transactions-level-is-used"></a>Exemple 3 lorsque le niveau Transactions est utilisé

Le tableau suivant montre les résultats lorsque vous utilisez les exemples de données décrits plus haut dans cette rubrique, mais que vous modifiez la valeur du champ **Niveau** sur *Transactions* dans la configuration du rapport.

| Type de ressource | Ressource | Site | Date | Nombre | Référence | Stock : quantité financière | Stock : montant financier | Stock : quantité physique validée | Stock : montant physique validé | Stock : quantité | Stock : montant |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Matière | B0001 | 1 | 15/03/2021 | 00000126 | Commande fournisseur | 0,00 | 0,00 | 10.00 | 1,000.00 | 10.00 | 1,000.00 |
| Matière | B0001 | 1 | 15/03/2021 | 00000126 | Commande fournisseur | 10.00 | 1,000.00 | -10,00 | -1 000,00 | 0,00 | 0,00 |
| Matière | B0001 | 1 | 15/04/2021 | 00000128 | Commande fournisseur | 0,00 | 0,00 | 5.00 | 375.00 | 5.00 | 375.00 |
| Matière | B0001 | 1 | 02/05/2021 | 000003 | Expédition de l’ordre de transfert | -5,00 | -458,33 | 0,00 | 0,00 | -5,00 | -458,33 |
| Matière | B0001 | 1 | 02/05/2021 | 000003 | Réception de l’ordre de transfert | 5.00 | 458.33 | 0,00 | 0,00 | 5.00 | 458.33 |
| Matière | B0001 | 1 | 03/05/2021 | 000835 | Commande de vente | 0,00 | 0,00 | -1,00 | -91,67 | -1,00 | -91,67 |
| Matière | B0001 | 1 | 03/05/2021 | 000835 | Commande de vente | -1,00 | -91,67 | 1.00 | 91.67 | 0,00 | 0,00 |
| Matière | B0001 | 1 | 31/05/2021 | 000835 | Commande de vente | 0,00 | -8,33 | 0,00 | 0,00 | 0,00 | -8,33 |
| Matière | B0001 | 1 | 31/05/2021 | 000003 | Expédition de l’ordre de transfert | 0,00 | -41,67 | 0,00 | 0,00 | 0,00 | -41,67 |
| Matière | B0001 | 1 | 31/05/2021 | 000003 | Réception de l’ordre de transfert | 0,00 | 41.67 | 0,00 | 0,00 | 0,00 | 41.67 |
| Matière | B0001 | 2 | 15/03/2021 | 00000127 | Commande fournisseur | 0,00 | 0,00 | 10.00 | 2,000.00 | 10.00 | 2,000.00 |
| Matière | B0001 | 2 | 15/03/2021 | 00000127 | Commande fournisseur | 10.00 | 2,000.00 | -10,00 | -2 000,00 | 0,00 | 0,00 |
| Matière | B0001 | 2 | 02/05/2021 | 000003 | Expédition de l’ordre de transfert | 5.00 | 458.33 | 0,00 | 0,00 | 5.00 | 458.33 |
| Matière | B0001 | 2 | 02/05/2021 | 000003 | Réception de l’ordre de transfert | -5,00 | -458,33 | 0,00 | 0,00 | -5,00 | -458,33 |
| Matière | B0001 | 2 | 31/05/2021 | 000003 | Expédition de l’ordre de transfert | 0,00 | 41.67 | 0,00 | 0,00 | 0,00 | 41.67 |
| Matière | B0001 | 2 | 31/05/2021 | 000003 | Réception de l’ordre de transfert | 0,00 | -41,67 | 0,00 | 0,00 | 0,00 | -41,67 |
