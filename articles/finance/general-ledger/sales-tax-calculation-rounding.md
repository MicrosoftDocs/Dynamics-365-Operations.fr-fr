---
title: Calcul et arrondi de la taxe
description: Cet article fournit une vue d’ensemble du calcul et de l’arrondi de la taxe de vente et explique les paramètres du calcul de la taxe et de la configuration de son arrondi.
author: wangchen
ms.date: 06/01/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom:
- "13111"
- intro-internal
ms.assetid: fe5fdc7f-9834-49fb-a611-1dd9c289619d
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2022-05-31
ms.dyn365.ops.version: AX 10.0.28
ms.openlocfilehash: aa3564f0fcf4a958637ba4a5cdcc497bffc50000
ms.sourcegitcommit: 8b716849707ec96d1cb4cac85b9e782dc25f5a70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/07/2022
ms.locfileid: "8939231"
---
# <a name="sales-tax-calculation-and-rounding"></a>Calcul et arrondi de la taxe

[!include [banner](../includes/banner.md)]

Cet article donne une vue d’ensemble du calcul et de l’arrondi de la taxe de vente dans Microsoft Dynamics 365 Finance. Il explique également les paramètres utilisés dans la configuration du calcul et de l’arrondi de la taxe de vente, et comment ces paramètres fonctionnent ensemble.

## <a name="parameters"></a>Paramètres

Plusieurs paramètres contrôlent le calcul et l’arrondi de la taxe de vente :

- **Méthode de calcul** : ce paramètre est défini sur la page **Paramètres de comptabilité** et définit si le montant de base de la taxe est calculé par document ou par ligne. Si le paramètre **Base marginale** pour le code de taxe de vente est défini sur **Montant net du solde de la facture**, le montant de base de la taxe est toujours calculé par document, quelle que soit la définition de ce paramètre.
- **Arrondi par**: ce paramètre est défini pour le groupe de taxe de vente et définit si le montant de la taxe est arrondi par code taxe ou par combinaison de codes taxe.
- **Origine** : ce paramètre est défini pour le code taxe et définit le mode de calcul du montant de la taxe. Pour plus d’informations, voir [Méthodes de calcul des taxes dans le champ Origine](sales-tax-calculation-methods-origin-field.md).
- **Base marginale** : ce paramètre est défini pour le code taxe et détermine le montant utilisé pour sélectionner les taux de taxe appropriés sur la page **Valeurs de code taxe**. Pour plus d’informations, voir [Taux de taxe en fonction des champs Base marginale et Modes de calcul](marginal-base-field.md).
- **Règle d’arrondi de la taxe** : ce paramètre est défini pour le code taxe et définit comment le montant de la taxe déterminé est arrondi, y compris la précision d’arrondi et la méthode d’arrondi.

Le reste de cet article présente quelques exemples typiques de calcul et d’arrondi de la taxe qui utilisent une combinaison des paramètres précédents.

## <a name="scenario-for-the-examples"></a>Scénario pour les exemples

- Il y a deux lignes dans le document fiscal et le montant de base de la taxe pour chaque ligne est de 42,42.
- Deux codes taxe sont définis pour chaque ligne : le code taxe 1 et le code taxe 2.
- Le taux de taxe du code taxe 1 et du code taxe 2 est de 10 %.
- Le prix est hors taxe.
- La précision d’arrondi est de 0,01.
- La méthode d’arrondi est définie sur **Arrondi au chiffre supérieur**.

## <a name="example-1"></a>Exemple 1

### <a name="parameter-values"></a>Valeurs des paramètres

| Méthode de calcul | Arrondi à    | Origine                   | Base marginale       |
| ------------------ | -------------- | ------------------------ | ------------------- |
| Ligne               | Code taxe de vente | Pourcentage du montant HT | Montant HT par ligne |

### <a name="calculation-and-rounding-behavior"></a>Calcul et comportement de l’arrondi

| Numéro de la ligne | Code taxe de vente | Base de la taxe | Montant de la taxe de vente |
| ------------| ---------------| --------------| -----------------|
| 1           | Code 1         | 42.42         | 4.25             |
| 1           | Code 2         | 42.42         | 4.25             |
| 2           | Code 1         | 42.42         | 4.25             |
| 2           | Code 2         | 42.42         | 4.25             |

Le montant de base de la taxe est calculé par ligne :

- **Ligne 1:** 42,42
- **Ligne 2:** 42,42

Le montant de taxe est calculé par code taxe :

- **Ligne 1 :**

    - Montant de la taxe pour le code taxe 1 = 42,42 &times; 10 % = 4,242
    - Montant de la taxe pour le code taxe 2 = 42,42 &times; 10 % = 4,242

- **Ligne 2 :**

    - Montant de la taxe pour le code taxe 1 = 42,42 &times; 10 % = 4,242
    - Montant de la taxe pour le code taxe 2 = 42,42 &times; 10 % = 4,242

Le montant de taxe est arrondi par code taxe :

- **Ligne 1 :**

    - Montant de la taxe arrondi pour le code taxe 1 = 4,25
    - Montant de la taxe arrondi pour le code taxe 2 = 4,25

- **Ligne 2 :**

    - Montant de la taxe arrondi pour le code taxe 1 = 4,25
    - Montant de la taxe arrondi pour le code taxe 2 = 4,25

## <a name="example-2"></a>Exemple 2

### <a name="parameter-values"></a>Valeurs des paramètres

| Méthode de calcul | Arrondi à    | Origine                   | Base marginale                 |
| ------------------ | -------------- | ------------------------ | ----------------------------- |
| Ligne/Total         | Code taxe de vente | Pourcentage du montant HT | Montant HT du solde de la facture |

### <a name="calculation-and-rounding-behavior"></a>Calcul et comportement de l’arrondi

| Numéro de la ligne | Code taxe de vente | Base de la taxe | Montant de la taxe de vente |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Code 1         | 42.42         | 4.25             |
| 1           | Code 2         | 42.42         | 4.25             |
| 2           | Code 1         | 42.42         | 4.24             |
| 2           | Code 2         | 42.42         | 4.24             |

Le montant de base de la taxe est calculé par document :

- Montant de base de la taxe = 42,42 + 42,42 = 84,84

Le montant de taxe est calculé par code taxe :

- Montant de la taxe pour le code taxe 1 = 84,84 &times; 10 % = 8,484
- Montant de la taxe pour le code taxe 2 = 84,84 &times; 10 % = 8,484

Le montant de taxe est arrondi par code taxe :

- Montant de la taxe arrondi pour le code taxe 1 = 8,49
- Montant de la taxe arrondi pour le code taxe 2 = 8,49

Le montant de taxe arrondi est affecté à chaque ligne par code taxe :

- Affectez le montant de taxe arrondi pour le code taxe 1 (8,49) à la ligne 1 (4,25) et à la ligne 2 (4,24).
- Affectez le montant de taxe arrondi pour le code taxe 2 (8,49) à la ligne 1 (4,25) et à la ligne 2 (4,24).

## <a name="example-3"></a>Exemple 3

### <a name="parameter-values"></a>Valeurs des paramètres

| Méthode de calcul | Arrondi à    | Origine                              | Base marginale       |
| ------------------ | -------------- | ----------------------------------- | ------------------- |
| Ligne               | Code taxe de vente | Pourcentage calculé du montant HT | Montant HT par ligne |

### <a name="calculation-and-rounding-behavior"></a>Calcul et comportement de l’arrondi

| Numéro de la ligne | Code taxe de vente | Base de la taxe | Montant de la taxe de vente |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Code 1         | 42.42         | 4.72             |
| 1           | Code 2         | 42.42         | 4.72             |
| 2           | Code 1         | 42.42         | 4.72             |
| 2           | Code 2         | 42.42         | 4.72             |

Le montant de base de la taxe est calculé par ligne :

- **Ligne 1:** 42,42
- **Ligne 2:** 42,42

Le montant de taxe est calculé par code taxe :

- **Ligne 1 :**

    - Montant de la taxe pour le code taxe 1 = 42.42 &times; 10 % &divide; (1 – 10 %) = 4,7133
    - Montant de la taxe pour le code taxe 2 = 42.42 &times; 10 % &divide; (1 – 10 %) = 4,7133

- **Ligne 2 :**

    - Montant de la taxe pour le code taxe 1 = 42.42 &times; 10 % &divide; (1 – 10 %) = 4,7133
    - Montant de la taxe pour le code taxe 2 = 42.42 &times; 10 % &divide; (1 – 10 %) = 4,7133

Le montant de taxe est arrondi par code taxe :

- **Ligne 1 :**

    - Montant de la taxe arrondi pour le code taxe 1 = 4,72
    - Montant de la taxe arrondi pour le code taxe 2 = 4,72

- **Ligne 2 :**

    - Montant de la taxe arrondi pour le code taxe 1 = 4,72
    - Montant de la taxe arrondi pour le code taxe 2 = 4,72

## <a name="example-4"></a>Exemple 4

### <a name="parameter-values"></a>Valeurs des paramètres

| Méthode de calcul | Arrondi à    | Origine                              | Base marginale                 |
| ------------------ | -------------- | ----------------------------------- | ----------------------------- |
| Ligne/Total         | Code taxe de vente | Pourcentage calculé du montant HT | Montant HT du solde de la facture |

### <a name="calculation-and-rounding-behavior"></a>Calcul et comportement de l’arrondi

| Numéro de la ligne | Code taxe de vente | Base de la taxe | Montant de la taxe de vente |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Code 1         | 42.42         | 4.72             |
| 1           | Code 2         | 42.42         | 4.72             |
| 2           | Code 1         | 42.42         | 4.71             |
| 2           | Code 2         | 42.42         | 4.71             |

Le montant de base de la taxe est calculé par document :

- Montant de base de la taxe = 42,42 + 42,42 = 84,84

Le montant de taxe est calculé par code taxe :

- Montant de la taxe pour le code taxe 1 = 84.84 &times; 10 % &divide; (1 – 10 %) = 9,4267
- Montant de la taxe pour le code taxe 2 = 84.84 &times; 10 % &divide; (1 – 10 %) = 9,4267

Le montant de taxe est arrondi par code taxe :

- Montant de la taxe arrondi pour le code taxe 1 = 9,43
- Montant de la taxe arrondi pour le code taxe 2 = 9,43

Le montant de taxe arrondi est affecté à chaque ligne par code taxe :

- Affectez le montant de taxe pour le code taxe 1 (9,43) à la ligne 1 (4,72) et à la ligne 2 (4,71).
- Affectez le montant de taxe pour le code taxe 2 (9,43) à la ligne 1 (4,72) et à la ligne 2 (4,71).

## <a name="example-5"></a>Exemple 5

### <a name="parameter-values"></a>Valeurs des paramètres

| Méthode de calcul | Arrondi à                | Origine                   | Base marginale       |
| ------------------ | -------------------------- | ------------------------ | ------------------- |
| Ligne               | Combinaison de codes taxe | Pourcentage du montant HT | Montant HT par ligne |

### <a name="calculation-and-rounding-behavior"></a>Calcul et comportement de l’arrondi

| Numéro de la ligne | Code taxe de vente | Base de la taxe | Montant de la taxe de vente |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Code 1         | 42.42         | 4.25             |
| 1           | Code 2         | 42.42         | 4.24             |
| 2           | Code 1         | 42.42         | 4.24             |
| 2           | Code 2         | 42.42         | 4.24             |

Le montant de base de la taxe est calculé par ligne :

- **Ligne 1:** 42,42
- **Ligne 2:** 42,42

Le montant de taxe est calculé par code taxe :

- **Ligne 1 :**

    - Montant de la taxe pour le code taxe 1 = 42,42 &times; 10 % = 4,242
    - Montant de la taxe pour le code taxe 2 = 42,42 &times; 10 % = 4,242

- **Ligne 2 :**

    - Montant de la taxe pour le code taxe 1 = 42,42 &times; 10 % = 4,242
    - Montant de la taxe pour le code taxe 2 = 42,42 &times; 10 % = 4,242

Le montant de taxe est arrondi par combinaison de codes taxe :

- Montant total de la taxe = 4,242 + 4,242 + 4,242 + 4,242 = 16,968, qui est arrondi à 16,97

Le montant de taxe arrondi est affecté à chaque ligne par code taxe :

- Affectez le montant de la taxe (16,97) aux lignes 1 et 2 :

    - **Ligne 1 :**

        - Montant de la taxe pour le code taxe 1 = 4,25
        - Montant de la taxe pour le code taxe 2 = 4,24

    - **Ligne 2 :**

        - Montant de la taxe pour le code taxe 1 = 4,24
        - Montant de la taxe pour le code taxe 2 = 4,24

## <a name="example-6"></a>Exemple 6

### <a name="parameter-values"></a>Valeurs des paramètres

| Méthode de calcul | Arrondi à                | Origine                   | Base marginale                 |
| ------------------ | -------------------------- | ------------------------ | ----------------------------- |
| Ligne/Total         | Combinaison de codes taxe | Pourcentage du montant HT | Montant HT du solde de la facture |

### <a name="calculation-and-rounding-behavior"></a>Calcul et comportement de l’arrondi

| Numéro de la ligne | Code taxe de vente | Base de la taxe | Montant de la taxe de vente |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Code 1         | 42.42         | 4.25             |
| 1           | Code 2         | 42.42         | 4.24             |
| 2           | Code 1         | 42.42         | 4.24             |
| 2           | Code 2         | 42.42         | 4.24             |

Le montant de base de la taxe est calculé par document :

- Montant de base de la taxe = 42,42 + 42,42 = 84,84

Le montant de taxe est calculé par code taxe :

- Montant de la taxe pour le code taxe 1 = 84,84 &times; 10 % = 8,484
- Montant de la taxe pour le code taxe 2 = 84,84 &times; 10 % = 8,484

Le montant de taxe est arrondi par combinaison de codes taxe :

- Montant total de la taxe = 8,484 + 8,484 = 16,968, qui est arrondi à 16,97

Le montant de taxe arrondi est affecté à chaque ligne par code taxe :

- Affectez le montant de la taxe (16,97) aux lignes 1 et 2 :

    - **Ligne 1 :**

        - Montant de la taxe pour le code taxe 1 = 4,25
        - Montant de la taxe pour le code taxe 2 = 4,24

    - **Ligne 2 :**

        - Montant de la taxe pour le code taxe 1 = 4,24
        - Montant de la taxe pour le code taxe 2 = 4,24

## <a name="example-7"></a>Exemple 7

### <a name="parameter-values"></a>Valeurs des paramètres

| Méthode de calcul | Arrondi à                | Origine                              | Base marginale       |
| ------------------ | -------------------------- | ----------------------------------- | ------------------- |
| Ligne               | Combinaison de codes taxe | Pourcentage calculé du montant HT | Montant HT par ligne |

### <a name="calculation-and-rounding-behavior"></a>Calcul et comportement de l’arrondi

| Numéro de la ligne | Code taxe de vente | Base de la taxe | Montant de la taxe de vente |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Code 1         | 42.42         | 4.72             |
| 1           | Code 2         | 42.42         | 4.71             |
| 2           | Code 1         | 42.42         | 4.71             |
| 2           | Code 2         | 42.42         | 4.72             |

Le montant de base de la taxe est calculé par ligne :

- **Ligne 1:** 42,42
- **Ligne 2:** 42,42

Le montant de taxe est calculé par code taxe :

- **Ligne 1 :**

    - Montant de la taxe pour le code taxe 1 = 42.42 &times; 10 % &divide; (1 – 10 %) = 4,7133
    - Montant de la taxe pour le code taxe 2 = 42.42 &times; 10 % &divide; (1 – 10 %) = 4,7133

- **Ligne 2 :**

    - Montant de la taxe pour le code taxe 1 = 42.42 &times; 10 % &divide; (1 – 10 %) = 4,7133
    - Montant de la taxe pour le code taxe 2 = 42.42 &times; 10 % &divide; (1 – 10 %) = 4,7133

Le montant de taxe est arrondi par combinaison de codes taxe :

- Montant total de la taxe = 4,7133 + 4,7133 + 4,7133 + 4,7133 = 18,8532, qui est arrondi à 18,86

Le montant de taxe arrondi est affecté à chaque ligne par code taxe :

- Affectez le montant de la taxe (18,86) aux lignes 1 et 2 :

    - **Ligne 1 :**

        - Montant de la taxe pour le code taxe 1 = 4,72
        - Montant de la taxe pour le code taxe 2 = 4,71

    - **Ligne 2 :**

        - Montant de la taxe pour le code taxe 1 = 4,71
        - Montant de la taxe pour le code taxe 2 = 4,72

## <a name="example-8"></a>Exemple 8

### <a name="parameter-values"></a>Valeurs des paramètres

| Méthode de calcul | Arrondi à                | Origine                              | Base marginale                 |
| ------------------ | -------------------------- | ----------------------------------- | ----------------------------- |
| Ligne/Total         | Combinaison de codes taxe | Pourcentage calculé du montant HT | Montant HT du solde de la facture |

### <a name="calculation-and-rounding-behavior"></a>Calcul et comportement de l’arrondi

| Numéro de la ligne | Code taxe de vente | Base de la taxe | Montant de la taxe de vente |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Code 1         | 42.42         | 4.72             |
| 1           | Code 2         | 42.42         | 4.71             |
| 2           | Code 1         | 42.42         | 4.71             |
| 2           | Code 2         | 42.42         | 4.72             |

Le montant de base de la taxe est calculé par document :

- Montant de base de la taxe = 42,42 + 42,42 = 84,84

Le montant de taxe est calculé par code taxe :

- Montant de la taxe pour le code taxe 1 = 84.84 &times; 10 % &divide; (1 – 10 %) = 9,4267
- Montant de la taxe pour le code taxe 2 = 84.84 &times; 10 % &divide; (1 – 10 %) = 9,4267

Le montant de taxe est arrondi par combinaison de codes taxe :

- Montant total de la taxe = 9,4267 + 9,4267 = 18,8534, qui est arrondi à 18,86

Le montant de taxe arrondi est affecté à chaque ligne par code taxe :

- Affectez le montant de la taxe (18,86) aux lignes 1 et 2 :

    - **Ligne 1 :**

        - Montant de la taxe pour le code taxe 1 = 4,72
        - Montant de la taxe pour le code taxe 2 = 4,71

    - **Ligne 2 :**

        - Montant de la taxe pour le code taxe 1 = 4,71
        - Montant de la taxe pour le code taxe 2 = 4,72

## <a name="additional-resources"></a>Ressources supplémentaires

- [Modes de calcul des taxes dans le champ Origine](sales-tax-calculation-methods-origin-field.md)
- [Taux de taxe en fonction de la Base marginale et du Mode de calcul](marginal-base-field.md)
- [Options de calcul montant entier et intervalle pour les codes taxe](whole-amount-interval-options-sales-tax-codes.md)
