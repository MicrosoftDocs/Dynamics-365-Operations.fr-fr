---
title: Taxe de vente harmonisée canadienne
description: Cette rubrique donne des informations sur la fonctionnalité de prise en charge de la taxe de vente harmonisée pour le secteur public.
author: velofog
manager: Ann Beebe
ms.date: 04/2/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PSNCanadianHSTTaxFeature
audience: Application User
ms.devlang: ''
ms.reviewer: roschlom
ms.tgt_pltfrm: ''
ms.custom: ''
ms.search.region: Global
ms.search.industry: public sector
ms.author: roschlom
ms.search.validFrom: 2020-4-01
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 9fce946fd997b0f6b3a86ff4e990700e23b54247
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968239"
---
# <a name="calculating-canadian-harmonized-sales-tax"></a>Calcul de la taxe de vente harmonisée canadienne

[!include [banner](../includes/banner.md)]

Cette fonctionnalité permet à votre organisation de se conformer aux règles de la taxe de vente harmonisée (HST) canadienne. La taxe HST aide les entités du secteur public à se conformer aux politiques fiscales canadiennes. Elle est utilisée par certaines provinces canadiennes et combine la taxe sur les produits et services et la taxe de vente provinciale.
Des parties de la taxe HST peuvent être récupérées par les entités du secteur public si la taxe a été payée aux vendeurs, en fonction de l’intention de l’achat. L’intention est désignée par les valeurs de dimension financière et le compte principal sur une ligne de transaction d’un document d’achat (par exemple, une demande d’achat, une commande fournisseur ou une facture fournisseur).
Remarque : cette fonctionnalité ne s’applique pas au journal des factures de la compabilité fournisseur.

## <a name="enabling-the-hst-feature"></a>Activation de la fonctionnalité HST

1. Allez dans **Comptabilité > Paramétrage de la comptabilité > Paramètres de comptabilité > Groupe de taxe**.
2. Définissez **Appliquer les règles de la taxe de vente harmonisée en vigueur au Canada** sur **Oui** pour activer la fonctionnalité.

## <a name="define-the-dimensions-for-hst-rules"></a>Définir les dimensions des règles HST

1. Allez dans **Taxe > Taxes indirectes > Taxe**, puis cliquez sur **Dimensions de taxe de vente harmonisée**. 
2. Dans la page **Dimensions de taxe de vente harmonisée**, sélectionnez et hiérarchisez les dimensions financières (ainsi que le compte principal, le cas échéant) que vous souhaitez utiliser pour la taxe HST. Les dimensions financières des structures de compte sont associées au plan comptable. La priorité des dimensions aide à définir quelle taxe est appliquée s’il y a plusieurs possibilités. 



### <a name="note-only-the-financial-dimensions-that-are-used-in-the-current-legal-entity-will-be-available"></a>Remarque : seules les dimensions financières utilisées dans l’entité juridique actuelle sont disponibles.

## <a name="set-up-hst-rules"></a>Configurer les règles HST

Après avoir défini les dimensions de la taxe HST, vous définissez les règles de dimension comptable qui s’appliquent. Les règles HST affectent des codes de taxe en fonction des répartitions de compte d’une ligne de document. En effet, différents codes de taxe peuvent être appliqués, en fonction de l’objectif de l’achat.
1. Allez dans **Taxe > Taxes indirectes > Taxe**, puis cliquez sur **Règles de la taxe de vente harmonisée**. 
2. Dans la page **Règles de la taxe de vente harmonisée**, les dimensions que vous avez sélectionnées pour la taxe HST s’affichent par ordre de priorité de gauche à droite. Les colonnes restantes concernent les codes de taxe associés à cette combinaison de dimensions. 
3. Dans le volet Actions, cliquez sur **Nouveau** pour créer un enregistrement.
4. Définissez les valeurs de dimension. 

### <a name="notes"></a>Notes :
- Deux lignes ne peuvent pas avoir des paramètres identiques.
- Vous pouvez supprimer ou modifier des règles existantes.
- Vous pouvez choisir de laisser un segment vide. Il fonctionnera comme un « caractère générique ». Une ligne totalement vide s’applique à toutes les combinaisons de comptes pour lesquelles une règle plus spécifique n’est pas appliquée. Vous pouvez ajouter une ligne avec toutes les dimensions financières vides si des codes de taxe doivent s’appliquer lorsqu’aucune règle ne correspond.

5. Sélectionnez jusqu’à cinq codes de taxe pouvant être appliqués aux dimensions sélectionnées pour la taxe HST. Remarque : pour être appliqués, les codes de taxe définis ici doivent être présents dans la règle HST et dans les deux champs **Groupe de taxe** et **Groupe de taxe d’article** sélectionnés sur les lignes du document de transaction. 
6. Cliquez sur **Enregistrer** pour enregistrer les modifications. 

### <a name="notes"></a>Notes :
- Après avoir défini les règles de la taxe HST, vous ne pouvez pas modifier les dimensions préexistantes de la taxe HST. Pour apporter des modifications, vous devez d’abord supprimer l’ensemble des règles et codes de taxe dans le formulaire **Règles de la taxe de vente harmonisée**.
- Plusieurs codes de taxe peuvent s’appliquer à une règle.
- Une seule règle s’applique à une répartition de compte.
- Plusieurs règles peuvent s’appliquer à une ligne d’un document de transaction comportant plusieurs répartitions.

## <a name="how-rules-are-applied"></a>Mode d’application des règles

L’ordre dans lequel les règles sont appliquées est relativement complexe. Le graphique suivant illustre le principe :

> [![Définir les règles HST](./media/define-hst-rules.png)](./media/define-hst-rules.png)

Les codes de taxe sélectionnés pour la ligne de dimension sont les suivants si la transaction utilise un groupe de taxe et un groupe de taxe d’article avec tous les codes de taxe inclus.

|Dimensions financières                     | Codes taxe|
|-----------------------------------------|-----------------|   
|Fonds 101, n’importe quelle division à l’exception des divisions 111 et 121| Taxe1            |
|   Fonds 101, Division 111                  |   Taxe1, Taxe2, Taxe3|
|   Fonds 101, Division 121                  | Taxe2, Taxe3      |
|   Fonds 303, n’importe quelle division à l’exception de la division 141         | Taxe1, Taxe2, Taxe3|
|   Fonds 303, Division 141                  | Taxe1            |
