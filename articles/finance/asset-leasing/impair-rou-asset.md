---
title: Déprécier un droit d’utilisation des actifs
description: Cette rubrique décrit la fonctionnalité qui enregistre une dépréciation et ajuste le plan d’amortissement des immobilisations d’un contrat de location simple 842 (ASC 842) de codification des normes comptables.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 816f65cff77339ef8684c0449ed2e5f0762b17a2e22174412d5ea9f2a1a62069
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723821"
---
# <a name="impair-right-of-use-assets"></a>Déprécier un droit d’utilisation des actifs

[!include [banner](../includes/banner.md)]

Si la valeur comptable d’un droit d’utilisation d’actif (ROU) n’est pas recouvrable, vous devrez peut-être tester si l’actif s’est déprécié. Si vous déterminez que l’immobilisation est dépréciée, la location d’actifs peut enregistrer la dépréciation et ajuster le plan d’amortissement en conséquence. Cette rubrique décrit la fonctionnalité qui enregistre la dépréciation et ajuste le plan d’amortissement des locations simples d’une codification des normes comptables 842 (ASC 842). La même méthode s’applique également aux contrats de location selon la norme internationale d’information financière 16 (IFRS 16).

Le solde du droit d’utilisation de l’actif sera amorti selon la méthode linéaire pour le nombre de périodes restantes, que le contrat de location ait été qualifié de contrat de location-financement selon IFRS 16 ou de contrat de location simple selon ASC 842.

## <a name="impair-an-rou-asset"></a>Déprécier un droit d’utilisation de l’actif

1. Accédez au bail déprécié et sélectionnez **Registres**.
2. Dans le volet Actions, sélectionnez **Dépréciation**.
3. Dans la boîte de dialogue qui apparaît, dans le champ **Montant de la dépréciation**, saisissez le montant de la dépréciation de l’actif. Pour diminuer le droit d’utilisation de l’actif, vous devez entrer une valeur positive.
4. Dans le champ **Date de la transaction**, entrez la date à laquelle l’écriture de dépréciation doit être enregistrée.
5. Dans le champ **Périodes restantes**, entrez le nombre de mois restant à amortir.
6. Activez le paramètre **Publier** si vous souhaitez que le système enregistre automatiquement l’écriture au journal des dépenses de dépréciation. Si vous laissez ce paramètre désactivé, le système crée l’écriture mais ne la valide pas. Vous pouvez ensuite valider l’écriture depuis la page **Journaux de location d’actifs**.
7. Définissez l’option **Aperçu avant de valider** sur **Oui** pour afficher l’écriture proposée avant sa création ou sa validation.
8. Définissez l’option **Fermer le registre** sur **Oui** pour fermer le registre de location. Cette action ne peut pas être annulée. Les écritures ne peuvent pas être imputées aux baux fermés et les baux fermés ne peuvent pas être ajustés.
9. Sélectionnez **OK** pour créer ou valider l’écriture de dépréciation.
10. Pour afficher l’échéancier d’amortissement des actifs dépréciés, ouvrez la page Programmes d’amortissement des actifs du registre de location. L’actif sera désormais amorti de manière linéaire sur le nombre de mois que vous avez saisi dans le champ **Périodes restantes**.
11. Pour afficher l’écriture au journal des dépenses de dépréciation, sélectionnez **Journal de location d’actifs** sur le volet Actions du registre de location avec dépréciation. Le système crée une écriture de journal qui débite le compte général de la dépense de dépréciation et crédite le compte de validation de l’actif de location.
12. Pour afficher la nouvelle valeur comptable du droit d’utilisation de l’actif, sélectionnez **Transactions d’actifs** dans le volet Actions du registre de location.

## <a name="example-of-rou-asset-impairment"></a>Exemple de dépréciation de droit d’utilisation de l’actif

Pour cet exemple, le bail est un actif non spécialisé qui ne transfère pas la propriété ou n’accorde pas au locataire l’option d’achat.

### <a name="setup"></a>Paramétrage

Les tableaux suivants présentent les valeurs définies sur les onglets **Général** et **Lignes de l’échéancier de paiement** pour la location utilisée dans cet exemple.

**Onglet Général**

| Champ                      | Valeur            |
|----------------------------|------------------|
| Juste valeur de l’actif    | 600,000          |
| Taux d’emprunt marginal | 7 %               |
| Intervalle de composition       | Année         |
| Durée de vie utile de l’actif (mois) | 600              |
| Type d’annuité               | Annuité ordinaire |
| Date d’entrée en vigueur          | 01/01/2019       |

**Onglet Lignes d’échéancier de paiement**

| Champ             | Valeur      |
|-------------------|------------|
| Date de début        | 1/1/2019   |
| Intervalle de périodes   | Tous les mois    |
| Périodes           | 120        |
| Date de fin          | 31/12/2028 |
| Fréquence de paiement | Année   |
| Montant du paiement    | 10,000     |

### <a name="steps"></a>Étapes

1. Après avoir créé le contrat de location comme décrit précédemment dans cette rubrique, accédez au registre de location et confirmez l’échéancier de paiement. Enregistrez ensuite l’écriture de journal de reconnaissance initiale. Le droit d’utilisation de l’actif initial et le passif de location doivent être 70 235,81. Pour cet exemple, le contrat de location a été classé comme contrat de location simple sous ASC 842.
2. Exécutez le processus de journal par lots trois fois pour simuler l’écoulement de trois ans pour les paiements de location, les frais d’intérêts et les dépenses d’amortissement.
3. Une fois que vous avez terminé d’exécuter les trois traitements par lots, revenez au registre de location et ouvrez les tableaux de transactions de passif et d’actif pour afficher la valeur comptable actuelle du droit d’utilisation de l’actif et du passif locatif. Après trois ans, la valeur du passif devrait être d’environ -53 893,00 $, et la valeur de l’actif devrait être d’environ 53 893,00 $. 

    Après trois ans, l’entreprise effectue des tests de dépréciation et constate que le droit d’utilisation de l’actif a une dépréciation de 35 000 $. Vous devez maintenant enregistrer cette dépréciation.
    
4. Accédez au registre de location, puis, dans le volet Actions, sélectionnez **Dépréciation**.
5. Sur la page **Paramètre de dépréciation**, entrez les détails suivants.

    | Champ                  | Valeur    |
    |------------------------|----------|
    | Montant de la dépréciation      | 35,000   |
    | Date de la transaction       | 1/1/2022 |
    | Périodes restantes      | 84       |
    | Valider                   | Oui      |
    | Aperçu avant validation | Non       |
    | Clôturer le registre             | Non       |

6. Une écriture au journal des charges de dépréciation a été créée et enregistrée. Pour l’afficher, accédez au journal de location de l’actif dans le registre de location. Notez que le montant de la dépréciation a été débité du compte général des charges de dépréciation, et le compte général du droit d’utilisation de l’actif a été crédité.
7. Pour voir l’effet net de la dépréciation, consultez les tableaux des transactions de passif et d’actif. Notez que la dépense de dépréciation a diminué le droit d’utilisation de l’actif, mais que la valeur comptable du passif locatif n’a pas changé.

La dépréciation a un autre effet que vous devriez considérer. Étant donné que le montant du droit d’utilisation de l’actif est maintenant bien inférieur au passif locatif, le montant doit être amorti différemment qu’il ne l’était auparavant. Plus précisément, l’actif est désormais amorti de manière linéaire pendant les 84 mois restants du bail, à compter de la date de transaction.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]