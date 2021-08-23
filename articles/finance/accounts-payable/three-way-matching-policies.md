---
title: Stratégies de rapprochement à trois facteurs
description: Cette rubrique fournit des exemples de rapprochement à trois facteurs.
author: abruer
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendInvoicePostingHistory
audience: Application User
ms.reviewer: roschlom
ms.custom: 2761
ms.assetid: 70f3cb1a-18b7-4474-95ec-28b2410dd8f8
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d33a8cb001f1cd2f79c2a174710af90af423b9b3abc66eb80aa4811953ea4a14
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722837"
---
# <a name="three-way-matching-policies"></a>Stratégies de rapprochement à trois facteurs

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des exemples de rapprochement à trois facteurs.

## <a name="example-three-way-matching-for-items"></a>Exemple : Rapprochement à trois facteurs pour les articles

**Synthèse :** Ken est contrôleur au siège de l’entité juridique Fabrikam. Il décide que toutes les factures fournisseur basées sur des commandes fournisseur doivent être mises en correspondance avec les lignes de commande fournisseur (rapprochement à deux facteurs). Pour les achats des articles qui seront utilisés comme immobilisations, les factures doivent être mises en correspondance avec les lignes de commande fournisseur et les lignes d’accusé de réception de marchandises (rapprochement à trois facteurs).

Fabrikam est constitué de plusieurs entités juridiques et emploie des milliers de salariés dans le monde entier. À mesure que le volume de transactions augmente, les différences entre les accusés de réception et les factures augmentent également. Ceci se traduit par l’annulation d’immobilisations. Les factures des fournisseurs sont payées, mais le processus n’inclut pas l’identification des écarts lorsque le nombre d’articles reçus est inférieur au nombre d’articles commandés ou lorsque les articles ne sont pas reçus du tout. Les dépenses augmentent également car les employés ont toujours besoin d’outils et d’autres matériaux pour travailler. Ken souhaite que les fournisseurs expédient les produits commandés et que les articles soient reçus par les employés de Fabrikam. Par conséquent, Ken a besoin d’un rapprochement à deux et à trois facteurs pour toutes les entités juridiques de l’organisation. Le rapprochement de factures permet de s’assurer que les problèmes avec des articles disparus ou non reçus peuvent être suivis et résolus. 

Les stratégies de rapprochement de factures de cet exemple aident les personnes ayant les rôles suivants à atteindre ces objectifs :

-   Ken est contrôleur pour l’entreprise Fabrikam. Ken peut aider les personnes de l’organisation à identifier et corriger les problèmes liés à la commande, la réception et le paiement des articles (biens et services) et concernant les fournisseurs.
-   Phyllis et April sont les chefs comptables du département des Achats pour la division États-Unis de Fabrikam. Elles peuvent appliquer la stratégie d’entreprise et s’assurer que les factures ne sont payées qu’après avoir été mises en correspondance avec la commande fournisseur et les accusés de réception des biens et services, le cas échéant.
-   Tony est le responsable de production de la division États-Unis de Fabrikam. Tony et d’autres employés du département Production peuvent s’assurer que les articles reçus sont conformes à la commande passée auprès des fournisseurs et sont pris en compte afin que le personnel ait ce dont il a besoin pour travailler.

### <a name="prerequisites"></a>Conditions préalables

-   Ken définit la stratégie de rapprochement au niveau de l’entité juridique sur Rapprochement à trois facteurs.
-   Ken définit l’option Mettre à jour automatiquement le statut de rapprochement des en-têtes de l’entité juridique sur Oui.
-   Ken définit le champ Mettre en correspondance les prix totaux de l’entité juridique sur Pourcentage et entre 15 % comme pourcentage de tolérance.
-   Ken définit la stratégie de rapprochement au niveau de l’article 1500 – CNC Milicron Machine sur Rapprochement à trois facteurs. Cet article est un élément d’immobilisation utilisé pour la production chez Fabrikam. Les factures correspondant à cet article sont mises en correspondance avec les lignes de commande fournisseur pour ce qui concerne les prix et avec les accusés de réception de marchandises pour ce qui concerne les quantités.
-   Tony entre un bon de commande pour cinq machines CNC Milicron Machine. Alicia, employée chargée des commandes fournisseur chez Fabrikam, émet une commande fournisseur vers une entité juridique nommée Contoso pour la fourniture des articles.

    | Numéro d’article                 | Quantité | Prix unitaire | Montant HT | Code frais        | Valeur des frais |
    |-----------------------------|----------|------------|------------|---------------------|---------------|
    | 1500 – CNC Milicron Machine | 5        | 8 000,00   | 40 000,00  | Expédition et gestion | 3,000.00      |

-   Arnie, employé chargé des ventes chez Contoso, vérifie les expéditions pour la semaine. Il sélectionne les transactions d’expédition de manière à facturer Fabrikam pour la livraison des machines CNC Milicron Machine. Il inclut des frais d’expédition et de gestion. Fabrikam considère les frais comme faisant partie du coût de l’immobilisation.

### <a name="scenario"></a>Scénario

1.  Sammy, travailleur dans le département Réception de Fabrikam, reçoit la quantité totale de machines qui sont expédiées par Contoso. Sammy entre la quantité 5 sur un accusé de réception de marchandises. Étant donné que la commande fournisseur a été entièrement reçue, le statut de la commande fournisseur passe à Reçu.
2.  April, coordinatrice des Achats chez Fabrikam, entre et vérifie la facture envoyée par Contoso. Elle vérifie les informations suivantes :
    -   Pour les articles nécessitant un rapprochement à trois facteurs, la quantité de la ligne de facture correspond à la quantité reçue. La quantité reçue est indiquée sur l’accusé de réception de marchandises mis en correspondance avec la facture.
    -   Pour les articles nécessitant un rapprochement à deux ou trois facteurs, les prix figurant sur la ligne de facture sont compris dans les tolérances définies dans Microsoft Dynamics 365 Finance. Cela inclut les types de rapprochement de prix suivants :
        -   Rapprochement des prix unitaires nets – Le prix unitaire net de la ligne de facture correspond au prix unitaire net de la ligne de commande fournisseur et est compris dans le pourcentage de tolérance. Dans cet exemple, la tolérance de prix unitaire net est de 8 %.
        -   Rapprochement des prix totaux – Le montant net de la ligne de facture correspond au montant net de la ligne de commande fournisseur et est compris dans le pourcentage et/ou le montant de tolérance. Dans cet exemple, la tolérance de rapprochement des prix totaux est de +15 %.

La facture papier de Contoso contient les informations suivantes.

| Article                        | Quantité | Prix unitaire | Montant net |
|-----------------------------|----------|------------|------------|
| 1500 – CNC Milicron Machine | 5        | 8 100,00   | 40,500.00  |
| Expédition et traitement       |          |            | 4,000.00   |
| Taxes                         |          |            | 0,00       |
| Total                       |          |            | 44,500.00  |

La ligne de facture inclut les informations suivantes.

| numéro d’article                 | Quantité | Prix unitaire | Montant net de ligne | Stratégie de rapprochement    | Correspondance de quantités des accusés de réception de marchandises | Correspondance de prix | Correspondance de prix total |
|-----------------------------|----------|------------|-----------------|--------------------|--------------------------------|-------------|-------------------|
| 1500 – CNC Milicron Machine | 5        | 8 100,00   | 40 500,00       | Rapprochement à trois facteurs | Transmis(e)                         | Transmis(e)      | Transmis(e)            |

Étant donné que cette ligne réussit le processus de rapprochement de factures, la facture peut être validée.

## <a name="example-three-way-matching-for-item-and-vendor-combinations"></a>Exemple : Rapprochement à trois facteurs pour les combinaisons article/fournisseur
Synthèse : Ken est contrôleur au siège de l’entité juridique Fabrikam. Ken décide que toutes les factures basées sur des commandes fournisseur doivent être mises en correspondance avec les lignes de commande fournisseur (rapprochement à deux facteurs). Cassie est comptable dans la division Malaisie de Fabrikam. Elle spécifie que les articles sélectionnés commandés auprès de certains fournisseurs en Malaisie doivent être mis en correspondance avec les lignes de commande fournisseur et les lignes d’accusé de réception de marchandises (rapprochement à trois facteurs). Elle peut également remplacer la stratégie de rapprochement à un niveau de rapprochement plus élevé pour les commandes fournisseur spécifiques. 

Le volume et les montants sont faibles et il y a eu des problèmes de livraison avec certains fournisseurs en Malaisie. Pour ces motifs, Cassie définit le niveau de contrôle pour certaines combinaisons article/fournisseur en Malaisie sur un rapprochement à trois facteurs. 

Les stratégies de rapprochement de factures de cet exemple aident les personnes ayant les rôles suivants à atteindre ces objectifs :
-   Ken est contrôleur pour l’entreprise Fabrikam. Ken peut aider les personnes de l’organisation à identifier et corriger les problèmes liés à la commande, la réception et le paiement des articles (biens et services) et concernant les fournisseurs.
-   Cassie est comptable dans la division Malaisie de Fabrikam. Elle peut appliquer la stratégie d’entreprise et s’assurer que les factures ne sont payées qu’après avoir été mises en correspondance avec les lignes de commande fournisseur et les accusés de réception des biens et services. Elle peut également augmenter le niveau de contrôle en choisissant un rapprochement à trois facteurs pour des articles spécifiques afin de contrôler les coûts d’exploitation.

### <a name="prerequisites"></a>Conditions préalables

-   Ken définit la stratégie de rapprochement au niveau de l’entité juridique sur Rapprochement à deux facteurs.
-   Ken définit le champ Mettre en correspondance les prix totaux de l’entité juridique sur Pourcentage et entre 10 % comme pourcentage de tolérance.
-   Ken définit la tolérance de prix unitaire pour tous les articles sur 2 %.
-   Cassie définit la stratégie de rapprochement au niveau de la combinaison article/fournisseur pour l’article PH2500 – Ordinateur et le fournisseur Contoso sur Rapprochement à trois facteurs.
-   Alicia, employée chargée des commandes fournisseur dans la division Malaisie de Fabrikam, émet des commandes fournisseur à Contoso pour fournir trois articles, comme indiqué dans le tableau suivant. Lorsqu’elle crée la commande fournisseur, elle remplace la stratégie de rapprochement pour la souris sans fil sur un rapprochement à trois facteurs au lieu d’un rapprochement à deux facteurs.

    | Numéro d’article           | Quantité | Prix unitaire | Montant net | Stratégie de rapprochement (entrée par défaut) | Stratégie de rapprochement (sur la ligne de commande fournisseur) |
    |-----------------------|----------|------------|------------|---------------------------------|----------------------------------------------|
    | PH2500 – Ordinateur     | 2        | 2 500,00   | 5 000,00   | Rapprochement à trois facteurs              | Rapprochement à trois facteurs                           |
    | MM01 – Souris sans fil | 2        | 40,00      | 80,00      | Rapprochement à deux facteurs                | Rapprochement à trois facteurs                           |
    | Lecteur USB             | 200      | 10,00      | 2 000,00   | Rapprochement à deux facteurs                | Rapprochement à deux facteurs                             |

### <a name="scenario"></a>Scénario

1.  Les articles arrivent. Sammy, travailleur dans le département Réception de la division Malaisie de Fabrikam, est interrompu et ne valide pas l’accusé de réception de marchandises immédiatement.
2.  April, coordinatrice des Achats chez Fabrikam, entre et vérifie la facture envoyée par Contoso. Elle vérifie les informations suivantes :
    -   Pour les articles nécessitant un rapprochement à trois facteurs, la quantité de la ligne de facture correspond à la quantité reçue. La quantité reçue est indiquée sur l’accusé de réception de marchandises mis en correspondance avec la facture.
    -   Pour les articles nécessitant un rapprochement à deux ou trois facteurs, les prix figurant sur la ligne de facture sont compris dans les tolérances définies dans l’application. Cela inclut les types de rapprochement de prix suivants :
        -   Rapprochement des prix unitaires nets – Le prix unitaire net de la ligne de facture correspond au prix unitaire net de la ligne de commande fournisseur et est compris dans le pourcentage de tolérance. Dans cet exemple, la tolérance de prix unitaire net est de 2 %.
        -   Rapprochement des prix totaux – Le montant net de la ligne de facture correspond au montant net de la ligne de commande fournisseur et est compris dans le pourcentage et/ou le montant de tolérance. Dans cet exemple, la tolérance de rapprochement des prix totaux est de +10 %.

La facture papier de Contoso contient les informations suivantes.

| Article                  | Quantité | Prix unitaire | Montant net |
|-----------------------|----------|------------|------------|
| PH2500 – Ordinateur     | 2        | 2 500,00   | 5 000,00   |
| MM01 – Souris sans fil | 2        | 41.00      | 82.00      |
| Lecteur USB             | 200      | 10.05      | 2,010.00   |
| Facture totale         |          |            | 7,092.00   |

La ligne de facture inclut les informations suivantes.

| numéro d’article           | Quantité | Prix unitaire | Montant net de ligne | Stratégie de rapprochement    | Correspondance de quantités des accusés de réception de marchandises | Correspondance de prix | Correspondance de prix total |
|-----------------------|----------|------------|-----------------|--------------------|--------------------------------|-------------|-------------------|
| PH2500 – Ordinateur     | 2        | 2 500,00   | 5 000,00        | Rapprochement à trois facteurs | Échec                         | Transmis(e)      | Transmis(e)            |
| MM01 – Souris sans fil | 2        | 41,00      | 82,00           | Rapprochement à trois facteurs | Échec                         | Échec      | Transmis(e)            |
| Lecteur USB             | 200      | 10,05      | 2 010,00         | Rapprochement à deux facteurs   |                                | Transmis(e)      | Transmis(e)            |

Notez les éléments suivants :
-   Pour la ligne PH2500 – Ordinateur, la colonne Correspondance de quantités des accusés de réception de marchandises a une icône d’avertissement car la ligne de facture n’est pas mise en correspondance avec un accusé de réception de marchandises.
-   Pour la ligne MM01 – Souris sans fil, la colonne Correspondance de quantités des accusés de réception de marchandises a une icône d’avertissement car la ligne de facture n’est pas mise en correspondance avec un accusé de réception de marchandises. La colonne Rapprochement des prix unitaires a une icône d’avertissement car la tolérance de prix unitaires de 2 % est dépassée.
-   Pour la ligne Lecteur USB, la colonne Correspondance de quantités des accusés de réception de marchandises est vide car le rapprochement à deux facteurs ne correspond pas aux quantités de la ligne de facture et des lignes d’accusé de réception de marchandises.

Si une approbation est requise pour que les factures soient validées avec des écarts de rapprochement de factures, la case à cocher Approuver les validations avec écarts de rapprochement de l’écran Détails de rapprochement de factures doit être activée avant que la facture puisse être validée avec les erreurs de correspondance de prix et de quantités. Si l’approbation n’est pas nécessaire, le traitement de la facture peut continuer s’il n’existe aucune autre erreur de validation.


Pour plus d’informations, voir [Vue d’ensemble du rapprochement de factures du module Achats](accounts-payable-invoice-matching.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]