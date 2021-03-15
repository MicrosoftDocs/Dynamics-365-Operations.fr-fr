---
title: Prix de vente des abonnements
description: Lors de la création d'un abonnement, le prix de vente est calculé à partir du paramétrage de prix de vente défini dans l'écran Prix de vente (abonnement).
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASalespriceSubscription
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35f4e3f3bdbdad7a48b89bad7da96d221f09bdb4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974209"
---
# <a name="subscription-sales-prices"></a>Prix de vente des abonnements   

[!include [banner](../includes/banner.md)]


Lors de la création d'un abonnement, le prix de vente est calculé à partir du paramétrage de prix de vente défini dans l'écran **Prix de vente (abonnement)**.

L'écran **Prix de vente (abonnement)** permet de créer des prix de vente pour un abonnement spécifique ou pour un champ d'application plus vaste. Pour un prix de vente s'appliquant à un abonnement, le code période et la devise de l'abonnement doivent être identiques à ceux du prix de vente.

Si le code période et la devise de l'abonnement et du prix de vente sont identiques, les prix de vente d'abonnement sont sélectionnés en fonction des priorités indiquées dans le tableau suivant. Une cellule vide dans le tableau indique un champ sans valeur et un X indique une valeur égale à celle de l'abonnement à partir duquel la transaction est générée.

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Priorité</p></th>
<th><p><strong>Catégorie</strong></p></th>
<th><p><strong>ID Projet</strong></p></th>
<th><p><strong>Abonnement</strong></p></th>
<th><p><strong>Devise de vente</strong></p></th>
<th><p><strong>Code période</strong></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>O</p></td>
<td><p>O</p></td>
<td><p>O</p></td>
<td><p>O</p></td>
<td><p>O</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p></p></td>
<td><p>O</p></td>
<td><p>O</p></td>
<td><p>O</p></td>
<td><p>O</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>O</p></td>
<td><p></p></td>
<td><p>O</p></td>
<td><p>O</p></td>
<td><p>O</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>O</p></td>
<td><p>O</p></td>
<td><p>O</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>O</p></td>
<td><p>O</p></td>
<td><p></p></td>
<td><p>O</p></td>
<td><p>O</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p></p></td>
<td><p>O</p></td>
<td><p></p></td>
<td><p>O</p></td>
<td><p>O</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>O</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>O</p></td>
<td><p>O</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>O</p></td>
<td><p>O</p></td>
</tr>
</tbody>
</table>


Lors de la création de frais d'abonnement, le prix de vente le plus détaillé, voir le tableau ci-dessus, est sélectionné comme prix de vente de l'abonnement.

## <a name="update-and-index-subscription-sales-prices"></a>Mise à jour et indexation des prix de vente des abonnements

Vous pouvez mettre à jour le prix de vente des abonnements en mettant à jour le prix de base ou l'indice. Ceux-ci peuvent être mis à jour en entrant un pourcentage ou une nouvelle valeur.

## <a name="subscription-fee-sales-prices"></a>Prix de vente des frais d'abonnement

Lors de la création de frais d'abonnement, le prix de vente est calculé à partir du paramétrage de prix de vente de l'abonnement. Vous pouvez soit utiliser le prix de base indiqué dans le paramétrage de prix de l'abonnement, soit créer des prix de vente indexés.

## <a name="example"></a>Exemple

Vous souhaitez paramétrer des prix de vente de 500 EUR pour un nouveau projet 9030. Dans l'écran **Prix de vente (abonnement)**, créez une ligne de prix de vente d'abonnement comme indiqué dans le tableau suivant :

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Valide du</p></th>
<th><p>Catégorie</p></th>
<th><p>Projet</p></th>
<th><p>Abonnement</p></th>
<th><p>Code période</p></th>
<th><p>Devise de vente</p></th>
<th><p>Prix de vente</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28-08-2006</p></td>
<td></td>
<td><p>9030</p></td>
<td></td>
<td><p>Mois</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Notez que les champs **Catégorie** et **Abonnement** sont vides.

Vous pouvez ensuite créer les abonnements suivants.

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Service récurrent</p></th>
<th><p>Projet</p></th>
<th><p>Groupe d'abonnements</p></th>
<th><p>Catégorie</p></th>
<th><p>Devise</p></th>
<th><p>Code période</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>Sous1</p></td>
<td><p>SousCat1</p></td>
<td><p>EUR</p></td>
<td><p>Mensuel</p></td>
</tr>
<tr class="even">
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>Sous1</p></td>
<td><p>SousCat2</p></td>
<td><p>EUR</p></td>
<td><p>Mensuel</p></td>
</tr>
</tbody>
</table>


Créez maintenant des frais d'abonnement pour les deux abonnements du groupe d'abonnements Sous1 :

1.  Cliquez sur **Gestion des services** \> **Paramétrage** \> **Services récurrents** \> **Groupes d'abonnements**.

2.  Dans l'écran **Groupes d'abonnements**, cliquez sur **Fonction** \> **Créer des frais d'abonnement**.

3.  Dans l'écran **Créer des frais d'abonnement**, entrez les informations appropriées. Pour plus d'informations, voir [Créer des transactions de redevance](create-subscription-fee-transactions.md).

Des frais d'abonnement avec un prix de vente de 500 EUR sont créés pour les deux abonnements, comme indiqué dans le tableau suivant.

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Date du projet</p></th>
<th><p>Service récurrent</p></th>
<th><p>Projet</p></th>
<th><p>Catégorie</p></th>
<th><p>Date de début</p></th>
<th><p>Date de fin</p></th>
<th><p>Devise de vente</p></th>
<th><p>Prix de vente</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28-08-2006</p></td>
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>SousCat1</p></td>
<td><p>01-01-2007</p></td>
<td><p>31-03-2007</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>28-08-2006</p></td>
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>SousCat2</p></td>
<td><p>01-01-2007</p></td>
<td><p>31-03-2007</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Plus tard, vous souhaitez spécifier des prix de vente pour la catégorie SousCat1 du projet 9030. Vous créez donc une ligne de prix de vente avec un prix de vente de 550 EUR pour la combinaison du projet 9030 et de la sous-catégorie SousCat1. Il existe désormais deux lignes de prix de vente d'abonnement pour le projet 9030, comme indiqué dans le tableau suivant.

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Valide du</p></th>
<th><p>Catégorie</p></th>
<th><p>Projet</p></th>
<th><p>Abonnement</p></th>
<th><p>Code période</p></th>
<th><p>Devise</p></th>
<th><p>Prix de vente</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28-08-2007</p></td>
<td></td>
<td><p>9030</p></td>
<td></td>
<td><p>Mois</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>28-08-2007</p></td>
<td><p>SousCat1</p></td>
<td><p>9030</p></td>
<td></td>
<td><p>Mois</p></td>
<td><p>EUR</p></td>
<td><p>550</p></td>
</tr>
</tbody>
</table>


Répétez la procédure ci-dessus pour créer des frais d'abonnement pour les deux abonnements du groupe d'abonnements Sous1. Le tableau suivant indique les transactions qui sont créées pour chaque abonnement lié au groupe d'abonnements.

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Date du projet</p></th>
<th><p>Abonnement</p></th>
<th><p>Projet</p></th>
<th><p>Catégorie</p></th>
<th><p>Date de début</p></th>
<th><p>Date de fin</p></th>
<th><p>Devise de vente</p></th>
<th><p>Prix de vente</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28-07-2007</p></td>
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>SousCat1</p></td>
<td><p>01-01-2008</p></td>
<td><p>31-03-2008</p></td>
<td><p>EUR</p></td>
<td><p>550</p></td>
</tr>
<tr class="even">
<td><p>28-07-2008</p></td>
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>SousCat2</p></td>
<td><p>01-01-2008</p></td>
<td><p>31-03-2008</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Pour la première transaction d'abonnement 00020\_135, le prix de vente de 550 EUR est calculé à partir du paramétrage du prix de vente d'abonnement défini pour la combinaison du projet et de la catégorie spécifiques. Pour la deuxième transaction d'abonnement 00021\_135, le prix de vente de 500 EUR est utilisé comme prix de vente d'abonnement du projet car aucun prix n'est défini pour la combinaison du projet 9030 et de la catégorie SousCat2.

## <a name="see-also"></a>Voir également :

[Mise à jour et indexation des prix de vente des abonnements](update-and-index-subscription-sales-prices.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]