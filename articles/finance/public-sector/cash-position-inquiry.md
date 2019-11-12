---
title: Renseignements sur l'emplacement des disponibilités
description: Cette rubrique fournit des informations sur la façon de déterminer les emplacements de disponibilités correspondants pour les ensembles de dimensions financières contenant des dimensions en équilibre.
author: velofog
manager: AnnBe
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations, Core
ms.search.region: Global
ms.search.industry: public sector
ms.author: v-alpavk
ms.search.validFrom: 2019-10-24
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 450b59290eea6bf7460d4b239341203c13f2d1ba
ms.sourcegitcommit: 574309903f15eeab7911091114885b5c7279d22a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2019
ms.locfileid: "2659040"
---
# <a name="cash-position-inquiry"></a>Renseignements sur l'emplacement des disponibilités
[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Les renseignements **Emplacement des disponibilités** vous permet de déterminer les emplacements de disponibilités correspondants pour les ensembles de dimensions financières contenant des dimensions en équilibre. Les renseignements affiche le solde des disponibilités de début, ainsi que l'effet de l'addition des rentrées de fonds, de la soustraction des remboursements de disponibilités, et la soustraction des transferts interfonds pour obtenir un solde de fin. Ensuite, les réservations budgétaires générales, les engagements ou les engagements préalables sont soustraits du solde de clôture pour obtenir à un solde non engagé.

Ces renseignements sont uniques, car ils permettent aux utilisateurs de personnaliser la terminologie pour les noms de colonne et pour les comptes principaux utilisés pour fournir des montants aux colonnes. Dans la page **Paramètres de l'emplacement des disponibilités**, les colonnes affichées dans les renseignements sont numérotées à compter de la colonne de données à l'extrême gauche comme première colonne.

## <a name="cash-position-inquiry-setup"></a>Configuration des renseignements sur l'emplacement des disponibilités

1. Accédez à **Comptabilité générale** > **Paramétrage de la comptabilité** > **Paramètres de l'emplacement des disponibilités**.
2. Dans la page **Paramètres de l'emplacement des disponibilités**, dans la section **Première colonne** :

- Dans le champ **Nom de la colonne**, tapez une étiquette à utiliser comme en-tête pour la première colonne de la recherche (par exemple, « Solde d'ouverture »).
- Dans le champ **Comptes principaux de solde d'ouverture**, sélectionnez les comptes que vous souhaitez référencer pour lancer une recherche sur le solde d'ouverture.

3. Dans la section **Deuxième colonne** : 

- Spécifiez un libellé pour la deuxième colonne dans la recherche (par exemple, « Rentrées de fonds »).
- Dans la liste **Comptes principaux de débit et de crédit**, sélectionnez les comptes principaux à partir desquels utiliser uniquement la somme de tous les montants de transactions de débit et de crédit pour les données de la recherche. 

> [!NOTE]
> La recherche ajoute le net des comptes débiteurs et créditeurs ainsi que le montant de débit et les montants de crédit des comptes principaux dans les autres champs du groupe.

- Dans la liste **Comptes principaux de débit uniquement**, sélectionnez les comptes principaux à partir desquels utiliser uniquement la somme de tous les montants de transactions de débit pour les données de la recherche.
- Dans la liste **Comptes principaux de crédit uniquement**, sélectionnez les comptes principaux à partir desquels utiliser uniquement la somme de tous les montants de transactions de crédit pour les données de la recherche.

4. Dans les sections **Troisième colonne** et **Quatrième colonne** : 

- Spécifiez un libellé pour la troisième colonne (par exemple, « Déboursements de disponibilités ») et la quatrième colonne (par exemple, « Transferts interfonds »).
- Pour les deux colonnes, spécifiez les numéros de compte des comptes principaux de débit et de crédit, des comptes principaux réservés au débit et des comptes principaux réservés au crédit.

5. Dans la section de groupe **Cinquième colonne**, spécifiez un libellé pour la cinquième colonne (par exemple, « Solde de clôture »). 

> [!NOTE]
> Dynamics 365 Finance calcule automatiquement une somme à partir des comptes spécifiés pour les quatre premières colonnes : Solde d'ouverture plus les rentrées de fonds, moins les déboursements de disponibilités, moins les transferts interfonds.

6. Dans les sections **Sixième colonne** et **Septième colonne** : 

- Spécifiez une étiquette pour la colonne six (par exemple, Réservations budgétaires générales ou Non engagements ») et la colonne sept (par exemple, « Engagements préalables »).
- Pour les deux colonnes, spécifiez les numéros de compte des **Comptes principaux de débit et de crédit**, des **Comptes principaux réservés au débit** et des **Comptes principaux réservés au crédit**.

7. Dans la section **Huitième colonne**, spécifiez une étiquette de colonne (par exemple, « Solde non engagé »). 

> [!NOTE]
> Dynamics 365 Finance calcule automatiquement un résultat à partir des comptes spécifiés pour les colonnes cinq à sept : Solde de clôture moins Engagements, moins Engagements préalables.

8. Cliquez sur **Enregistrer**.

## <a name="running-the-inquiry"></a>Exécuter la recherche

1. Accédez à **Comptabilité générale** > **Recherches et états** > **Emplacement des disponibilités**.
2. Dans la section **Paramètres** : 

- Sélectionnez le code **Intervalle de dates**, ou **Date de début** et **Date de fin**.
- Sélectionnez **Ensemble de dimensions financières**.
- Sélectionnez **Calculer les soldes** pour exécuter la recherche.

(facultatif) 

- Définissez l'option **Supprimer les comptes avec des zéros** sur **Oui** pour exclure les comptes comportant tous des montants nuls issus de la recherche.
- Définissez l'option **Afficher les segments dans des colonnes distinctes** sur **Oui** pour afficher les noms du compte pour chaque dimension en tant que colonnes distinctes dans la grille.
- Pour filtrer les valeurs d'une dimension spécifique sélectionnée, sélectionnez les dimensions que vous souhaitez dans les champs sous le champ **Ensemble de dimensions financières**. Les choix parmi lesquels choisir dépendent de l'ensemble de dimensions financières sélectionné.

