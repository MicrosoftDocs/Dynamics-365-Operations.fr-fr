---
title: Configurer et exécuter les renseignements sur l’emplacement des disponibilités
description: Cet article fournit des informations sur les renseignements sur l’emplacement des disponibilités. Ces renseignements vous permettent de déterminer les emplacements de disponibilités correspondants pour les ensembles de dimensions financières contenant des dimensions en équilibre.
author: velofog
ms.date: 10/07/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.search.industry: public sector
ms.author: twheeloc
ms.search.validFrom: 2019-10-07
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 6598143bade9996ffc9c606aeca2feaff01a8d61
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849699"
---
# <a name="set-up-and-run-the-cash-position-inquiry"></a>Configurer et exécuter les renseignements sur l’emplacement des disponibilités
[!include [banner](../includes/banner.md)]


Cet article fournit des informations sur les renseignements sur l’**emplacement des disponibilités**. Ces renseignements vous permettent de déterminer les emplacements de disponibilités correspondants pour les ensembles de dimensions financières contenant des dimensions en équilibre. Ils montrent les éléments suivants :

- Le solde des disponibilités d’ouverture
- L’effet de l’ajout de rentrées de fonds
- La soustraction des décaissements en espèces
- La soustraction des transferts interfonds pour arriver à un solde final
- La soustraction des réservations budgétaires générales, des engagements ou des engagements préalables du solde de clôture pour obtenir à un solde non engagé.

Ces renseignements diffèrent des autres renseignements, car ils permettent aux utilisateurs de personnaliser la terminologie pour les noms de colonne et pour les comptes principaux utilisés pour fournir des montants aux colonnes. Sur la page **Paramètres de l’emplacement des disponibilités**, les colonnes qui apparaissent dans les renseignements sont numérotées séquentiellement de gauche à droite. La colonne la plus à gauche est la **Colonne Une**.

## <a name="set-up-the-cash-position-inquiry"></a>Configurer les renseignements sur l’emplacement des disponibilités

1. Accédez à **Comptabilité générale \> Paramétrage de la comptabilité \> Paramètres de l’emplacement des disponibilités**.
2. Dans le groupe **Paramètres de l’emplacement des disponibilités**, dans la **Colonne Une** procédez comme suit :

    - Dans le champ **Nom de la colonne**, entrez une étiquette à utiliser comme en-tête pour la première colonne de la recherche (par exemple, **Solde d’ouverture**).
    - Dans le champ **Comptes principaux de solde d’ouverture**, sélectionnez les comptes que vous souhaitez référencer pour lancer des recherches sur le solde d’ouverture.

3. Dans le groupe **Colonne Deux**, procédez comme suit :

    - Entrez un libellé pour l’en-tête de la deuxième colonne (par exemple, **Rentrées de fonds**).
    - Pour utiliser uniquement la somme de tous les montants de transactions de débit et de crédit pour les données incluses dans la recherche, sélectionnez les comptes principaux dans la liste **Comptes principaux de débit et de crédit**.
    
        La recherche ajoute le montant net des comptes débiteurs et créditeurs ainsi que les montants de débit et de crédit des comptes principaux spécifiés dans les autres champs du groupe.

    - Pour utiliser uniquement la somme de tous les montants de transactions de débit pour les données de la recherche, sélectionnez les comptes principaux dans la liste **Comptes principaux de débit uniquement**.
    - Pour utiliser uniquement la somme de tous les montants de transactions de crédit pour les données de la recherche, sélectionnez les comptes principaux dans la liste **Comptes principaux de crédit uniquement**.

4. Dans les groupes **Colonne Trois** et **Colonne Quatre**, procédez comme suit :

    - Entrez un libellé pour l’en-tête de la troisième colonne (par exemple, **Déboursements de disponibilités**) et la quatrième colonne (par exemple, **Transferts interfonds**).
    - Pour les deux colonnes, spécifiez les comptes principaux pour distribuer les entrées de débit et de crédit. Spécifiez également les comptes principaux de débit uniquement et les comptes principaux de crédit uniquement.

5. Dans le groupe **Colonne Cinq**, entrez un libellé pour l’en-tête de la cinquième colonne (par exemple, **Solde de clôture**).

    Un résultat est automatiquement calculé à partir des comptes que vous avez spécifiés dans les quatre premières colonnes. Pour cet exemple, le calcul est Solde de départ + Encaissements – Décaissements – Transferts interfonds.

6. Dans les groupes **Colonne Six** et **Colonne Sept**, procédez comme suit :

    - Entrez une étiquette pour l’en-tête de la sixième colonne (par exemple, **Réservations budgétaires générales** ou **Non engagements**) et la septième colonne (par exemple, **Engagements préalables**).
    - Pour les deux colonnes, spécifiez les numéros de compte des comptes principaux de débit et de crédit, et pour les comptes principaux réservés au débit et des comptes principaux réservés au crédit.

7. Dans le groupe **Colonne Huit**, entrez un libellé pour l’en-tête de la huitième colonne (par exemple, **Solde non engagé**).

    Un résultat est automatiquement calculé à partir des comptes que vous avez spécifiés dans les colonnes cinq à sept. Pour cet exemple, le calcul est Solde final – Engagements – Pré-engagements.

8. Sélectionnez **Enregistrer**.

## <a name="run-the-cash-position-inquiry"></a>Exécutez les renseignements sur l’emplacement des disponibilités

1. Accédez à **Comptabilité générale \> Recherches et états \> Emplacement des disponibilités**.
2. Dans la section **Paramètres**, procédez comme suit :

    - Dans le champ **Intervalle de dates**, sélectionnez le code de l’intervalle de dates. Sinon, dans les champs **Date de début** et **Date de fin**, définissez l’intervalle de dates.
    - Dans le champ **Ensemble de dimensions financières**, sélectionnez l’ensemble de dimensions financières.
    - Facultatif : Définissez l’option **Supprimer les comptes avec des zéros** sur **Oui** pour exclure les comptes comportant tous des soldes nuls issus de la recherche.
    - Facultatif : Définissez l’option **Afficher les segments dans des colonnes distinctes** sur **Oui** pour afficher les noms du compte pour chaque dimension en tant que colonnes distinctes dans la grille.
    - Facultatif : Pour filtrer les valeurs d’une dimension spécifique sélectionnée, dans les champs sous le champ **Ensemble de dimensions financières**, sélectionnez les dimensions que vous souhaitez. Les options disponibles varient en fonction de l’ensemble de dimensions financières que vous avez sélectionné.

3. Sélectionnez **Calculer les soldes** pour exécuter la recherche.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
