---
title: Rapprochement des factures dans le module Achats
description: "Le rapprochement de factures du module Achats est le processus de rapprochement des informations de la facture fournisseur, de la commande fournisseur et de l'accusé de réception de marchandises."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendInvoicePostingHistory
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 27361
ms.assetid: 9f3dace7-05d8-4974-8f85-aca2e224876c
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 93017a6592a02505292075a2905303fabe89a3b0
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="accounts-payable-invoice-matching"></a>Rapprochement des factures dans le module Achats

[!include[banner](../includes/banner.md)]


Le rapprochement de factures du module Achats est le processus de rapprochement des informations de la facture fournisseur, de la commande fournisseur et de l'accusé de réception de marchandises.

Lors du rapprochement de documents, les différences sont appelées des écarts de rapprochement. Ces derniers sont comparés aux tolérances spécifiées. Si un écart de rapprochement dépasse le pourcentage ou le montant de tolérance, des icônes d'écart de rapprochement sont affichées dans les pages Facture fournisseur et Détails de correspondance et d'historique des factures. 

Par exemple, vous entrez une commande fournisseur avec une ligne pour 1 000 piles au prix unitaire de 1,00. La commande fournisseur est approuvée et soumise au fournisseur. Ce dernier expédie 1 000 piles et vous entrez un accusé de réception de marchandises pour 1 000 piles au prix unitaire de 1,00. Le coût de stock des piles est mis à jour avec ce prix. 

Une facture arrive pour 1 000 piles au prix unitaire de 1,10. La politique de votre entité juridique autorise une tolérance de prix unitaire net de 5 % pour cette catégorie d'article. 1,05 serait un prix acceptable, pas 1,10. Lorsque vous entrez ces informations de facturation, un écart de rapprochement de prix est identifié et vous pouvez enregistrer la facture en attendant que l'écart soit résolu.

Vous pouvez utiliser les types suivants de rapprochements de factures du module Achats :

-   Rapprochement des totaux des factures - Rapprochez les montants totaux de la facture avec ceux de la commande fournisseur. Ce type de rapprochement de factures inclut un minimum d'informations afin que vous puissiez utiliser cette option pour paramétrer des contrôles qui réduisent le temps de travail requis pour réviser les informations de rapprochement de factures.
-   Rapprochement à deux facteurs – Rapprochez les informations de prix de la facture avec celles de la commande fournisseur.
-   Rapprochement à trois facteurs - Rapprochez les informations de prix de la facture avec celles de la commande fournisseur. Rapprochez également les informations de quantité de la facture avec celles des accusés de réception de marchandises sélectionnés pour la facture.
-   Rapprochement des frais - Rapprochez les informations de frais (montants) de la facture avec celles de la commande fournisseur.

> [!NOTE]
> D'autres méthodes de contrôle des factures peuvent être utilisées à l'aide des stratégies de facture fournisseur. 

Les rapprochements à deux et à trois facteurs rapprochent toujours les informations relatives au prix unitaire. Vous pouvez également configurer ces stratégies de rapprochement de sorte qu'elles rapprochent les informations relatives au prix total.
-   Rapprochement des prix unitaires nets - Lors d'un rapprochement à deux ou à trois facteurs, rapprochez les informations de prix en comparant le prix unitaire net de chaque ligne de la facture avec le prix unitaire net correspondant de la commande fournisseur. Le prix unitaire net est déterminé par la formule suivante : Montant net de la ligne/Quantité de la ligne
-   Rapprochement des totaux des prix - Lors d'un rapprochement à deux ou à trois facteurs, rapprochez les informations de prix en comparant le montant net (total des prix) de chaque ligne de la facture avec le montant net correspondant de la commande fournisseur. Le montant net est déterminé par la formule suivante : (Prix unitaire \* Quantité de la ligne) + Frais de la ligne - Remises de la ligne

Les calculs de rapprochement de factures sont généralement effectués automatiquement lorsque vous modifiez les factures fournisseur dans la page Facture fournisseur. Sinon, le rapprochement de factures peut être effectué à la demande, le cas échéant. Le rapprochement de factures à la demande est contrôlé pour l'entité juridique par l'option Mettre à jour automatiquement le statut d'en-tête des factures de la page Paramètres de la comptabilité fournisseur sur l'onglet Contrôle de la facture. Le rapprochement de factures peut également être exécuté dans le cadre du processus de vérification des factures. Vous pouvez afficher les résultats du rapprochement de factures sur la page Facture fournisseur et les pages de rapprochement de factures associés.

## <a name="invoice-totals-matching"></a>Rapprochement des totaux de facture
Vous pouvez utiliser le rapprochement des totaux de facture pour vous assurer que l'écart entre les montants totaux de la facture et les montants attendus n'est pas supérieur à l'écart acceptable. Six totaux sont comparés dans la page Détails de rapprochement de factures totales, comme indiqué dans le tableau suivant. Si la tolérance autorisée pour le rapprochement des totaux de facture est de 20 %, un pourcentage d'écart de 100 % pour le montant total de la remise est considéré comme un écart de rapprochement.

| Champ Total    | Total réel de la facture | Total attendu de la facture | Pourcentage d'écart | Statut de rapprochement |
|----------------|----------------------|------------------------|---------------------|--------------|
| Solde        | 495,00               | 495,00                 | 0 %                  | Transmis(e)       |
| Remise totale | 0,00                 | 9,90                   | 100 %                | Échec       |
| Frais        | 64,90                | 64,90                  | 0 %                  | Transmis(e)       |
| Taxe      | 139,98               | 137,50                 | 2 %                  | Transmis(e)       |
| Arrondi      | 0,00                 | 0,00                   | 0 %                  | Transmis(e)       |
| Montant de la facture | 699,88               | 687,50                 | 2 %                  | Transmis(e)       |

Le rapprochement des totaux de facture est contrôlé pour l'entité juridique par le basculeur Mettre en correspondance les totaux de la facture de la page Paramètres de la comptabilité fournisseur. Le rapprochement est effectué en comparant les totaux réels et attendus de la facture. Les totaux attendus de la facture sont calculés en fonction des prix, des frais et des informations de taxe de la commande fournisseur et des quantités de la facture.

## <a name="two-way-price-totals-matching"></a>Rapprochement à deux facteurs des totaux des prix
Le rapprochement à deux facteurs permet de s'assurer que l'écart entre les informations de prix de la commande fournisseur et de la facture est compris dans les tolérances acceptables. Vous pouvez comparer les informations de prix relatives au montant net de chaque ligne de la facture et de toutes les lignes de facture en attente et précédemment validées avec le montant net de la ligne de commande fournisseur correspondante. On parle alors de rapprochement des totaux des prix. 

Le rapprochement des totaux des prix peut être basé sur un pourcentage et/ou un montant. 

Si un pourcentage de tolérance des totaux des prix d'achat est spécifié, cinq champs sont comparés, comme indiqué dans le tableau suivant. Comme le pourcentage de tolérance des totaux des prix d'achat est de 10 %, un pourcentage d'écart des prix totaux de 50 % représente un écart de rapprochement.

| Statut de rapprochement | Montant net de la facture | Montant net attendu | Total de prix d'achat qui ne correspond pas (montant d'écart) | Pourcentage total de prix d'achat qui ne correspond pas (pourcentage d'écart) | Pourcentage de tolérance du prix d'achat total |
|--------------|--------------------|---------------------|--------------------------------------------------|-----------------------------------------------------------------|----------------------------------------|
| Transmis(e)       | 105,00             | 100,00              | 5,00                                             | 5 %                                                              | 10 %                                    |
| Échec       | 150,00             | 100,00              | 50,00                                            | 50 %                                                             | 10 %                                    |

Si un montant de tolérance des totaux des prix d'achat est spécifié, cinq champs sont comparés, comme indiqué dans le tableau suivant. Comme le montant de tolérance des totaux des prix d'achat est de 100,00, le montant d'écart des prix totaux de 105,00 représente un écart de rapprochement.

| Statut de rapprochement | Montant net de la facture | Montant net attendu | Total de prix d'achat qui ne correspond pas (montant d'écart) | Total de prix d'achat qui ne correspond pas en devise comptable (montant d'écart) | Tolérance du prix d'achat total |
|--------------|--------------------|---------------------|--------------------------------------------------|-------------------------------------------------------------------------|--------------------------------|
| Transmis(e)       | 150,00             | 100,00              | 50,00                                            | 50,00                                                                   | 100,00                         |
| Échec       | 205,00             | 100,00              | 105,00                                           | 105,00                                                                  | 100,00                         |

Si le rapprochement des totaux des prix est paramétré avec une tolérance de pourcentage et un montant de tolérance (parfois appelé montant à ne pas dépasser), les deux tolérances sont prises en compte lorsque vous évaluez si une ligne inclut un écart de rapprochement. Si le pourcentage ou le montant dépasse la tolérance, comme indiqué dans les lignes 150,00 et 205,00 du tableau suivant, la ligne inclut un écart de rapprochement.

| Statut de rapprochement | Montant net de la facture | Montant net attendu | Pourcentage total de prix d'achat qui ne correspond pas (pourcentage d'écart) | Pourcentage de tolérance du prix d'achat total | Total de prix d'achat qui ne correspond pas en devise comptable (montant d'écart) | Tolérance du prix d'achat total |
|--------------|--------------------|---------------------|-----------------------------------------------------------------|----------------------------------------|-------------------------------------------------------------------------|--------------------------------|
| Transmis(e)       | 105,00             | 100,00              | 5 %                                                              | 10 %                                    | 5,00                                                                    | 100,00                         |
| Échec       | 150,00             | 100,00              | 50 %                                                             | 10 %                                    | 50,00                                                                   | 100,00                         |
| Échec       | 205,00             | 100,00              | 105 %                                                            | 10 %                                    | 105,00                                                                  | 100,00                         |

Le rapprochement à deux facteurs est contrôlé pour l'entité juridique par le champ Stratégie de rapprochement des lignes de la page Paramètres de la comptabilité fournisseur. En fonction des choix opérés dans le champ Autoriser le remplacement de la stratégie de rapprochement, vous pouvez sélectionner un rapprochement à deux facteurs pour un fournisseur, un article ou une combinaison article/fournisseur spécifique dans la page Stratégie de rapprochement et pour une commande fournisseur spécifique dans la page Commande fournisseur.

Le rapprochement des totaux des prix est contrôlé pour l'entité juridique par le champ Mettre en correspondance les prix totaux de la page Paramètres de la comptabilité fournisseur. Le pourcentage de tolérance des totaux des prix d'achat et le montant de tolérance (montant à ne pas dépasser) sont également spécifiés dans cette page.

## <a name="two-way-net-unit-price-matching"></a>Rapprochement à deux facteurs des prix unitaires nets
Le rapprochement à deux facteurs permet de s'assurer que l'écart entre les informations de prix de la commande fournisseur et de la facture est compris dans les tolérances acceptables. Vous pouvez comparer les informations de prix relatives au prix unitaire net de chaque article de la facture. On parle alors de rapprochement des prix unitaires nets. 

Neuf montants de ligne sont comparés dans la page Détails de rapprochement de factures totales, comme indiqué dans le tableau suivant. Si la tolérance de prix autorisée pour le rapprochement des prix unitaires nets est de 10 %, un écart de 22,61 % entre les prix unitaires nets est considéré comme un écart de rapprochement.

| Champ Ligne                    | Valeur de la facture | Valeur de la commande fournisseur | Pourcentage d'écart | Statut de rapprochement |
|-------------------------------|---------------|----------------------|---------------------|--------------|
| Prix unitaire                    | 55,40         | 55,38                | 0 %                  | Transmis(e)       |
| Unité de prix                    | 1,00          | 1,00                 | 0 %                  | Transmis(e)       |
| Frais sur les achats          | 50,00         | 0,00                 | 100 %                | Échec       |
| Remise                      | 0,00          | 0,00                 | 0 %                  | Transmis(e)       |
| Pourcentage de remise              | 0,00          | 0,00                 | 0 %                  | Transmis(e)       |
| Remise multiligne            | 0,00          | 0,00                 | 0 %                  | Transmis(e)       |
| Pourcentage de remise multiligne | 0,00          | 0,00                 | 0 %                  | Transmis(e)       |
| Montant net                    | 271,60        | 221,52               | 22,61 %              | Échec       |
| Prix unitaire net                | 67,9000       | 55,3800              | 22,61 %              | Échec       |

Le rapprochement à deux facteurs est contrôlé pour l'entité juridique par le champ Stratégie de rapprochement des lignes de la page Paramètres de la comptabilité fournisseur. En fonction des choix opérés dans le champ Autoriser le remplacement de la stratégie de rapprochement, vous pouvez sélectionner un rapprochement à deux facteurs pour un fournisseur, un article ou une combinaison article/fournisseur spécifique dans la page Stratégie de rapprochement et pour une commande fournisseur spécifique dans la page Commande fournisseur. 

Le rapprochement des prix unitaires nets est contrôlé pour l'entité juridique par le champ Activer le contrôle de rapprochement de factures de la page Paramètres de la comptabilité fournisseur. Les pourcentages de tolérance de prix unitaire peuvent être configurés pour des articles, des groupes d'articles, des fournisseurs, des groupes de fournisseurs, des combinaisons article/fournisseur ou une entité juridique à l'aide de la page Tolérances de prix.

## <a name="two-way-price-totals-matching-and-net-unit-price-matching"></a>Rapprochement à deux facteurs des totaux des prix et des prix unitaires nets
Vous pouvez utiliser le rapprochement des totaux des prix et des prix unitaires nets simultanément. L'exemple ci-dessous est basé sur la configuration suivante :

-   La tolérance de prix unitaire net de l'article Lecteur USB est de 10 %.
-   La tolérance de rapprochement des totaux des prix pour l'entité juridique est de 15 % ou 500,00.

La commande fournisseur contient la suivante.

| Numéro d'article | Quantité | Prix unitaire | Montant net |
|-------------|----------|------------|------------|
| Lecteur USB   | 1.000    | 10,00      | 10 000,00  |

Trois factures sont entrées, comme indiqué dans le tableau suivant. Il existe un écart de rapprochement pour la facture 3 car l'écart de 1 880,00 dépasse le montant de tolérance des totaux des prix d'achat de 500,00. Pour le rapprochement des totaux des prix, le montant net de la facture inclut toutes les factures validées précédemment, plus la facture sur laquelle vous travaillez actuellement.

| Numéro d'article          | Quantité | Prix unitaire | Montant net | Correspondance de prix | Correspondance de prix total |
|----------------------|----------|------------|------------|-------------|-------------------|
| Facture 1 : Lecteur USB | 800      | 10,80      | 8 640,00   | Transmis(e)      | Transmis(e)            |
| Facture 2 : Lecteur USB | 100      | 10,80      | 1 080,00   | Transmis(e)      | Transmis(e)            |
| Facture 3 : Lecteur USB | 200      | 10,80      | 2 160,00   | Transmis(e)      | Échec            |
| Total                |          |            | 11 880,00  |             |                   |

## <a name="three-way-matching"></a>Rapprochement à trois facteurs

Le rapprochement à trois facteurs permet de s'assurer que l'écart entre les informations de prix de la commande fournisseur et de la facture correspond aux tolérances acceptables, et que la quantité de la facture correspond à la quantité de l'accusé de réception de marchandises correspondant.

Les mêmes montants de ligne sont comparés dans la page Détails de rapprochement de factures, comme dans le cadre d'un rapprochement à deux facteurs. En outre, la quantité de la facture est rapprochée avec les quantités d'accusé de réception de marchandises reçues. Si le montant de la facture ne correspond pas à la quantité de l'accusé de réception de marchandises rapproché, une erreur de rapprochement des quantités existe.

| Champ Ligne                    | Valeur de la facture | Valeur de la commande fournisseur | Pourcentage d'écart | Statut de rapprochement |
|-------------------------------|---------------|----------------------|---------------------|--------------|
| Prix unitaire                    | 55,40         | 55,38                | 0 %                  | Transmis(e)       |
| Unité de prix                    | 1,00          | 1,00                 | 0 %                  | Transmis(e)       |
| Frais sur les achats          | 50,00         | 0,00                 | 100 %                | Échec       |
| Remise                      | 0,00          | 0,00                 | 0 %                  | Transmis(e)       |
| Pourcentage de remise              | 0,00          | 0,00                 | 0 %                  | Transmis(e)       |
| Remise multiligne            | 0,00          | 0,00                 | 0 %                  | Transmis(e)       |
| Pourcentage de remise multiligne | 0,00          | 0,00                 | 0 %                  | Transmis(e)       |
| Montant net                    | 271,60        | 221,52               | 22,61 %              | Échec       |
| Prix unitaire net                | 67,9000       | 55,3800              | 22,61 %              | Échec       |

| Champ Ligne                     | Valeur de la facture | Statut de rapprochement |
|--------------------------------|---------------|--------------|
| Quantité de la facture               | 4,00          |              |
| Total des accusés de réception de marchandises correspondants | 0,00          | Échec       |

Le rapprochement à trois facteurs est contrôlé pour l'entité juridique par le champ Stratégie de rapprochement des lignes de la page Paramètres de la comptabilité fournisseur. En fonction des choix opérés dans le champ Autoriser le remplacement de la stratégie de rapprochement, vous pouvez sélectionner un rapprochement à trois facteurs pour un fournisseur, un article ou une combinaison article/fournisseur spécifique dans la page Stratégie de rapprochement et pour une commande fournisseur spécifique dans la page Commande fournisseur.

## <a name="charges-matching"></a>Mise en correspondance des frais
Le rapprochement des frais permet de s'assurer que l'écart entre les montants des frais et les montants attendus n'est pas supérieur au pourcentage d'écart acceptable. Les montants totaux de chaque code frais qui s'applique à la facture et à la commande fournisseur sont comparés dans la page Comparer les valeurs de frais - Facture, comme indiqué dans le tableau suivant. Si la tolérance autorisée pour un code frais est de 25 %, l'écart de pourcentage 99 999 999 999,99 % pour le code frais Licence est considéré comme un écart de rapprochement.

> [!NOTE] 
> Un pourcentage d'écart de 99 999 999 999,99 % signifie que le montant attendu basé sur la commande fournisseur est nul alors que le montant réel de la facture est une valeur positive. 

| Modifier le statut de rapprochement | Code frais de la facture | Valeur totale réelle calculée | Valeur totale prévue calculée | Montant de l'écart | Pourcentage d'écart | Pourcentage de tolérance |
|----------------------|----------------------|-------------------------------|---------------------------------|-----------------|---------------------|----------------------|
| Échec               | Licence              | 25                            | 0                               | 25              | 99 999 999 999,99 %  | 25 %                  |
| Transmis(e)               | Transport              | 200                           | 200                             | 0               | 0 %                  | 25 %                  |
| Échec               | Expédition             | 4                             | 2                               | 2               | 100 %                | 25 %                  |

Le rapprochement des frais est contrôlé pour l'entité juridique par le basculeur Mettre en correspondance les frais de la page Paramètres de la comptabilité fournisseur. Vous pouvez paramétrer des pourcentages de tolérance d'écart pour les frais dans la page Tolérances en termes de frais.

> [!NOTE]
> Le rapprochement des frais est effectué uniquement sur les codes de frais pour lesquels le basculeur Comparer les valeurs de la commande fournisseur et de la facture est sélectionné sur la page Code frais.

## <a name="related-functionality"></a>Fonctionnalités associées
Les factures fournisseur sont généralement basées sur des accusés de réception de marchandises qui représentent les expéditions réelles, et non sur les commandes fournisseur. Il arrive que les montants facturés ne correspondent pas aux montants de la commande fournisseur et que les quantités expédiées diffèrent des quantités facturées. Vous pouvez gérer ces informations comme suit :
-   Créez une facture fournisseur basée sur les accusés de réception de marchandises. Ces derniers sont automatiquement suggérés pour les factures. Vous pouvez sélectionner ceux que vous souhaitez utiliser. Le cas échéant, vous pouvez également sélectionner les lignes d'accusé de réception de marchandises spécifiques de plusieurs commandes fournisseur.
-   Affichez et approuvez les différences de quantité entre la quantité facturée sur la facture et la quantité reçue sur l'accusé de réception de marchandises. En cas de différence, vous pouvez enregistrer la facture et la faire correspondre ultérieurement à un autre accusé de réception de marchandises ou modifier la quantité facturée pour la faire correspondre à la quantité reçue.
-   Entrez des montants de facture qui n'étaient pas inclus dans la commande fournisseur d'origine, afin que les informations de la facture correspondent à celles reçues du fournisseur. Vous pouvez comparer les frais des commandes fournisseur avec ceux des factures. Au besoin, vous pouvez ajouter des frais aux factures et les répartir sur les lignes de facture.
-   Affichez et approuvez les écarts de rapprochement des prix unitaires nets de la facture et de la commande fournisseur. Vous pouvez paramétrer des pourcentages de tolérance de prix pour les entités juridiques, les articles et les fournisseurs. Si le prix de la ligne de facture fournisseur n'entre pas dans la tolérance de prix acceptable, vous pouvez enregistrer la facture en attendant qu'elle soit approuvée pour validation ou que le fournisseur envoie une correction.

Pour plus d'informations, voir [Stratégies de rapprochement à trois facteurs](three-way-matching-policies.md) et [Configurer la validation du rapprochement de factures de la comptabilité fournisseur](tasks/set-up-accounts-payable-invoice-matching-validation.md). 





