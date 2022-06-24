---
title: Configurer des codes fiscaux
description: Cet article explique comment configurer des codes fiscaux dans le service de calcul des taxes.
author: wangchen
ms.date: 11/30/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 1bc250716763ce9d8e25c8850c8a3676bf65fb0c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862926"
---
# <a name="set-up-tax-codes"></a>Configurer des codes fiscaux

[!include [banner](../includes/banner.md)]

Cet article explique comment configurer des codes fiscaux dans le service de calcul des taxes. Elle comprend la configuration d’un scénario simple pour faire fonctionner le code fiscal et des informations sur certaines fonctionnalités avancées du code fiscal pour des scénarios complexes.

> [!IMPORTANT]
> La configuration des codes fiscaux dans le service de calcul des taxes est indépendante de l’entité juridique. Vous ne pouvez effectuer cette configuration dans Regulatory Configuration Service (RCS) qu’une seule fois. Les codes fiscaux sont automatiquement synchronisés dans Microsoft Dynamics 365 finance lorsque vous activez le service de calcul des taxes dans Finance.

## <a name="simple-setup"></a>Configuration simple

Suivez ces étapes pour utiliser un code fiscal dans un scénario simple, tel qu’un scénario où il n’y a qu’un seul taux d’imposition.

1. Connectez-vous à [Regulatory Configuration Service (RCS)](https://marketing.configure.global.dynamics.com/).
2. Accédez à **Espaces de travail** \> **Fonctionnalités de globalisation** \> **Calcul de la taxe**.
3. Sélectionnez la fonctionnalité et la version à configurer, puis sélectionnez **Modifier**.
4. Sur l’onglet **Général**, sélectionnez **Version de la configuration**.
5. Sur l’onglet **Codes taxe**, sélectionnez **Ajouter**, puis entrez le code taxe et une description.
6. Sélectionnez **Origine du calcul**. Une origine du calcul est un groupe de méthodes de calcul qui sont définies dans la version de la configuration de taxe sélectionnée. Pour ce scénario simple, sélectionnez **Par montant net**.
7. Cliquez sur **Enregistrer**. D’autres champs deviennent disponibles, en fonction de l’origine du calcul que vous avez sélectionnée.
8. Sur le raccourci **Taux**, sélectionnez **Ajouter** pour ajouter un taux d’imposition pour ce code fiscal.
9. Cliquez sur **Enregistrer**.

## <a name="calculation-origin"></a>Origine du calcul

L’origine du calcul définit la manière dont le montant de la base d’imposition et le montant de la taxe sont calculés. Elle est configurée par la configuration de taxe de l’espace de travail **États électroniques**. Les valeurs suivantes sont disponibles dans le champ **Origine du calcul** :

- Par montant net
- Par montant brut
- Par quantité
- Par marge
- Taxe sur la taxe

### <a name="by-net-amount"></a>Par montant net

Si vous sélectionnez **Par montant net** dans le champ **Origine du calcul**, le montant de la taxe est calculé comme un pourcentage du montant d’achat ou de vente, à l’exclusion de toute autre codes de taxe.

Par exemple, si le taux d’imposition est de 25 % et que la ligne de facture affiche une quantité de 10 articles à 1,00 €, alors le client peut prétendre à 10 % de remise ligne. Dans ce cas, les montants sont calculés comme suit :

- **Montant net :** (10 × 1,00) – 10 % = 9,00 
- **Taxe de vente :** 9,00 × 25 % = 2,25 
- **Montant total de la facture :** 9,00 + 2,25 = 11,25

### <a name="by-gross-amount"></a>Par montant brut

Si vous sélectionnez **Par montant brut** dans le champ **Origine du calcul**, le montant de la taxe est calculé comme un pourcentage du chiffre d’affaires brut. Le montant brut est le montant net de la ligne plus l’ensemble des taxes et frais pour la ligne à l’exception de la taxe où le champ **Origine du calcul** est défini sur **Par montant brut**.

Par exemple, l’administration fiscale impose des droits de douanes spéciaux sur un article. Le montant des droits de douanes est ajouté au montant net avant le calcul de la taxe. Les codes fiscaux suivants sont utilisés :

- **Droits de douane 1** : Le taux est de 10 %, et la méthode de calcul **Par montant net** est utilisée.
- **Droits de douane 2** : Le taux est de 20 %, et la méthode de calcul **Par montant net** est utilisée.
- **Taux d’imposition** : Le taux est de 25 %, et la méthode de calcul **Par montant brut** est utilisée.

Si le montant net est de 10,00 €, le montant du champ des droits de douane 1 est de 1,00 € (10,00 × 10 %) et le montant des droits de douanes 2 est de 2,00 € (10,00 × 20 %). Dans ce cas, les montants sont calculés comme suit : 

- **Montant TTC :** montant net + montant des droits de douane 1 + montant des droits de douane 2 = 10,00 + 1,00 +2,00 = 13,00 
- **Montant de la taxe :** 13,00 × 25 % = 3,25 
- **Total droits de douanes et taxe :** 1,00 + 2,00 + 3,25 = 6,25 
- **Montant total de la facture :** 10,00 + 6,25 = 16,25

### <a name="by-quantity"></a>Par quantité

Si vous sélectionnez **Par quantité** dans le champ **Origine du calcul**, le montant de la taxe est calculé comme un montant fixe par unité et multiplié par la quantité entrée dans la ligne de document. Le montant unitaire est indiqué sur le raccourci **Taux**.

Par exemple, le code fiscal est défini sur 1,20 par unité. Sur une ligne de facture client, 25 unités d’un article sont vendues. Dans ce cas, le montant de la taxe est calculé comme suit : 25 × 1,20 = 30,00.

### <a name="by-margin"></a>Par marge

Si vous sélectionnez **Par marge** dans le champ **Origine du calcul**, le montant de la taxe est calculé comme un pourcentage de la marge commerciale. La marge commerciale est le montant des ventes moins le montant des coûts. Cette méthode de calcul s’applique uniquement aux transactions de vente.

Par exemple, si le taux d’imposition est de 25 % et que la ligne de facture affiche une quantité de 10 articles à 10,00 €, alors le coût par article est de 6 €. Dans ce cas, les montants sont calculés comme suit :

- **Marge commerciale :** 10 × (10,00 – 6,00) = 40,00
- **Montant de la taxe :** 40,00 × 25 % = 10,00
- **Montant total de la facture :** 100,00 + 10,00 = 110,00

### <a name="tax-on-tax"></a>Taxe sur la taxe

Si vous sélectionnez **Taxe sur la taxe** dans le champ **Origine du calcul**, la taxe est calculée sous forme de pourcentage de tous les autres montants de taxe sur la même ligne de document.

Par exemple, les codes fiscaux suivants sont utilisés :

- **Droits de douane 1** : Le taux est de 10 %, et la méthode de calcul **Par montant net** est utilisée.
- **Droits de douane 2** : Le taux est de 20 %, et la méthode de calcul **Par montant net** est utilisée.
- **Taux de douane** : Le taux est de 25 %, et la méthode de calcul **Taxe sur la taxe** est utilisée.

Dans ce cas, les montants sont calculés comme suit :

- **Montant net :** 10,00 
- **Droits de douane 1 :** 10,00 × 10 % = 1,00 
- **Droits de douane 2 :** 10,00 × 20 % = 2,00 
- **Taxe de douane :** 3,00 × 25 % = 0,75
- **Total des taxes :** 1,00 + 2,00 + 0,75 = 3,75 
- **Montant total de la facture :** 10,00 + 3,75 = 13,75

## <a name="advanced-functionality"></a>Fonctionnalité avancée

Cette section explique certaines fonctionnalités avancées de la configuration du code fiscal pour des scénarios complexes.

### <a name="tax-exemption"></a>Exonération de taxe

Si vous définissez l’option **Est exonéré** sur **Oui** sur le raccourci **Général**, le montant de la taxe sera toujours remplacé par 0 (zéro), quel que soit le taux d’imposition réel.

Vous pouvez définir le champ **Code d’exonération** pour préciser le motif de l’exonération. 

Vous pouvez activer la recherche des données de base pour le champ **Code d’exonération**. De cette façon, vous pouvez sélectionner parmi les valeurs de code d’exonération définies dans Finance. Pour plus d’informations sur l’activation de la recherche des données de référence, consultez [Activer la recherche des données de base pour la configuration du calcul des taxes](tax-service-set-up-environment-master-data-lookup.md).

Par exemple, le taux d’imposition est de 25 %, et l’option **Est exonéré** est définie sur **Oui** sur le code fiscal. La ligne de facture affiche une quantité de 10 articles à 1 € pièce et le client peut prétendre à 10 % de remise ligne. Dans ce cas, les montants sont calculés comme suit :

- **Montant net :** (10 × 1,00) – 10 % = 9,00 
- **Taxe de vente :** 0,00 
- **Montant total de la facture :** 9,00 + 0,00 = 9,00

### <a name="use-tax"></a>Taxe d’utilisation

Si vous définissez l’option **Est une taxe d’utilisation** sur **Oui** sur le raccourci **Général**, le montant de la taxe sera publié dans le compte **Taxe d’utilisation due** au lieu du compte **Écriture collective fournisseur**.

Par exemple, le taux d’imposition est de 25 %, et l’option **Est une taxe d’utilisation** est définie sur **Oui** sur le code fiscal. La ligne de facture affiche une quantité de 10 articles à 1 € pièce et le client peut prétendre à 10 % de remise ligne. Dans ce cas, les montants sont calculés comme suit :

- **Montant net :** (10 × 1,00) – 10 % = 9,00 
- **Taxe d’utilisation :** 9,00 × 25 % = 2,25
- **Montant total de la facture :** 9,00 + 0,00 = 9,00

> [!IMPORTANT]
> Si l’option **Est exonéré** et l’option **Est une taxe d’utilisation** sont définies sur **Oui** sur un code fiscal, le code sera reconnu comme exonéré pour les transactions de vente et utilisera la taxe pour les transactions d’achat.

### <a name="reverse-charges"></a>Taxe au preneur

Si vous définissez l’option **Est une taxe au preneur** sur **Oui** sur le raccourci **Général**, le taux d’imposition peut être configuré comme négatif. Pour un scénario de taxe au preneur, nous vous recommandons de configurer deux codes fiscaux, l’un ayant un taux d’imposition positif et l’autre négatif. Les deux codes fiscaux doivent avoir la même valeur et l’option **Est une taxe au preneur** doit être définie sur **Oui** sur le code fiscal ayant un taux d’imposition négatif. Pour plus d’informations sur la solution de taxe au preneur dans Finance, voir [Mécanisme de Taxe au preneur pour le régime TVA/TPS](emea-reverse-charge.md).

Par exemple, deux codes fiscaux sont déterminés sur une ligne de facture. Un taux d’imposition est de 25 %. L’autre taux d’imposition est de -25 %, et l’option **Taxe au preneur** est définie sur **Oui** sur le deuxième code fiscal. La ligne de facture indique une quantité de 10 articles à 1,00 € chacun. Dans ce cas, les montants des écarts sont calculés comme suit :

- **Montant net :** (10 × 1,00) = 10,00 
- **Code fiscal 1 :** 10,00 × 25 % = 2,50
- **Code fiscal 2 :** 10 × -25 % = 2,50
- **Montant total de la facture :** 10,00 + 2,50 -2,50 = 10,00

### <a name="exclusion-from-base-amount-calculations"></a>Exclusion des calculs du montant de base

Si vous définissez l’option **Exclure du calcul du montant de base** sur **Oui** sur le raccourci **Général**, le montant calculé dans le code fiscal est exclu du montant de base pour les autres calculs de code fiscal dans le scénario incluant le prix.

Pour plus d’informations, voir [Calculer la taxe sur les prix lorsque Les prix incluent les taxes est activé](global-exclude-from-tax-base-amount-calculation.md).

### <a name="rates"></a>Taux

Sur le raccourci **Taux**, vous pouvez définir différents taux d’imposition pour différentes plages de montants de la base d’imposition. Pour calculer le montant de la taxe, le service Calcul de la taxe utilise toujours le taux qui correspond au montant de la base d’imposition.

Par exemple, les taux d’imposition peuvent être configurés comme indiqué dans le tableau suivant.

| Montant minimum | Montant maximal | Taux de taxe   |
| -------------- | -------------- | ---------- |
| 0              | 1 000          | 10 pourcent |
| 1 000          | 5 000          | 15 pourcent |
| 5 000          | 10,000         | 20 % |
| 10,000         | 0              | 30 pourcent |

Dans ce cas, le montant de la taxe est calculé comme suit :

- Si le montant de base de la taxe est de 300,00 €, le taux d’imposition est de 10 % et le montant de la taxe est de 300,00 × 10 % = 30,00.
- Si le montant de base de la taxe est de 3 000,00 €, le taux d’imposition est de 15 % et le montant de la taxe est de 3 000,00 × 15 % = 450,00.
- Si le montant de base de la taxe est de 6 000,00 €, le taux d’imposition est de 20 % et le montant de la taxe est de 6 000,00 × 10 % = 1.200,00.
- Si le montant de base de la taxe est de 20 000,00 €, le taux d’imposition est de 30 % et le montant de la taxe est de 20 000,00 × 30 % = 6 000,00.

> [!NOTE]
> Si le montant de base de la taxe peut correspondre à la fois au montant maximum sur une ligne et au montant minimum sur l’autre ligne, la base utilisera le taux d’imposition qui correspond au montant de base minimum. Par exemple, si le montant de base de la taxe est de 1000,00 €, le taux d’imposition est de 15 % et le montant de la taxe est de 1 000,00 × 15 % = 150,00.

### <a name="limits"></a>Limites

Sur le raccourci **Limites**, vous pouvez définir des limites de taxe pour remplacer le montant de taxe calculé si le montant de taxe tombe dans la plage minimum/maximum.

- Si le montant de taxe calculé est supérieur ou égal au montant de taxe maximum configuré sur le raccourci **Limites**, le montant final de la taxe est égal au montant maximum de la taxe.
- Si le montant de taxe calculé est inférieur au montant de taxe minimum configuré sur le raccourci **Limites**, le montant final de la taxe est de 0 (zéro).

Par exemple, les limites de taxes sont configurées de la manière suivante :

- **Montant minimum de la taxe :** 100 
- **Montant maximum de la taxe :** 1 000

Si le montant de taxe calculé est de 2 000, le montant de taxe final est de 1 000.

Si le montant de taxe calculé est de 500, le montant de taxe final est de 500.

Si le montant de taxe calculé est de 80, le montant de taxe final est de 0 (zéro).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
