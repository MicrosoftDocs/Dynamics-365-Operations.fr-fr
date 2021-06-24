---
title: Planifier pour les fournisseurs occasionnels dans le secteur public
description: Cet article fournit des informations sur l’importation et la création de fournisseurs occasionnels et de factures.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransVoucher, SysConfiguration, Tax1099Summary, VendTableListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 27251
ms.assetid: 936570cb-932f-4027-b3c7-2235ad79bc1c
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b71544672fec13872455fd561cef303db2a41af3
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188575"
---
# <a name="plan-for-one-time-vendors-in-the-public-sector"></a>Planifier pour les fournisseurs occasionnels dans le secteur public

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur l’importation et la création de fournisseurs occasionnels et de factures. 

Généralement, si vous planifiez d’importer en masse des informations facturation et sur les fournisseurs, vous commencez par créer un fichier de données au format feuille de calcul et l’enregistrez au format CSV (valeurs séparées par des virgules).

-   Étant donné que les virgules sont utilisées pour séparer les champs dans un fichier CSV, n’utilisez pas les virgules dans le texte d’une entrée. Par exemple, si vous souhaitez spécifier le nom de la société « Smith, Smith, and Jones », entrez-la le en tant que **Smith Smith and Jones**.
-   Si vous ne définissez pas de valeurs pour les champs de cette page, les comptes fournisseur nouvellement créés utilisent les valeurs du profil fournisseur occasionnel référencé dans la page **Paramètres de la comptabilité fournisseur**. Par exemple, si le mode de paiement est défini sur **Chèque** pour le profil du fournisseur occasionnel dans la page **Paramètres de la comptabilité fournisseur**, ce mode de paiement sera également défini pour les fournisseurs occasionnels que vous ajouterez.
-   La souche de numéros de la Comptabilité fournisseur **Fournisseur occasionnel** permet d’affecter les comptes des fournisseurs occasionnels et ne doit pas être défini sur **Continu** pour ce service. Les factures sont générées dans un état de brouillon. Avant de créer des propositions de paiement, vous devez valider les factures.

Le tableau suivant répertorie les champs que le fichier d’importation doit contenir. Chaque nom de champ est équivalent à un en-tête de colonne dans une feuille de calcul, et chaque ligne de la feuille de calcul contient les données pour chaque colonne applicable.

**Section du fournisseur**

| Champ                                          | Détails                                                 |
|------------------------------------------------|---------------------------------------------------------|
|Type d’enregistrement                                     | **Personne** ou **Organisation**                          |
| Prénom                                     | (Si la valeur du type d’enregistrement est **Personne**)                |
| Deuxième prénom (facultatif)                         | (Si le type d’enregistrement est **Personne**)                      |
| Nom                                      | (Si le type d’enregistrement est **Personne**)                      |
| Nom du fournisseur                                    | (Si le type d’enregistrement est **Organisation**)                |
| Groupe                                          | Limité à dix caractères                                     |
| Pays/Région                                 | Limité à dix caractères                                     |
| Code postal                                |                                                         |
| Rue                                         |                                                         |
| Ville                                           |                                                         |
| Ville                                           |                                                         |
|ID taxe fédérale (facultatif)                       | (États-Unis uniquement) nombre 1099                                 |
| Type d’ID taxe                                    | (États-unis uniquement). Les valeurs peuvent être **Inconnu**, **Numéro d’identification de l’employeur**, **Numéro de Sécurité sociale**, **Numéro d’identification du contribuable individuel** ou **Numéro d’identification du contribuable choisi**.  **Remarque :** si aucun ID taxe fédérale n’est indiqué, ce champ doit être défini sur **Inconnu**.                                               |
| Compte bancaire (facultatif)                        | Nom du compte bancaire                                       |
| Numéro de compte bancaire                            |                                                         |
| Numéro d’acheminement (facultatif)                      |                                                         |
| Code SWIFT (facultatif)                          | Également appelé BIC (Bank Identifier Code)                |
|Code IBAN (facultatif)                                 | Numéro de compte bancaire international, limité à 34 caractères.   |



**Section de facture**

| Champ                                                | Détails                                           |
|------------------------------------------------------|---------------------------------------------------|
| Numéro de facture                                       | Numéro de facture ; limité à 20 caractères                |
| Description de facture (facultative)                       |                                                   |
| Date de validation (facultative)                              | Format de date                                       |
| Date de facture                                         | Format de date                                       |
| Date d’échéance (facultative)                                  | Format de date                                       |
| Numéro de ligne                                          |                                                   |
|Numéro d’article (facultatif)                                | Limité à 20 caractères   **Remarque :** si aucun numéro d’article n’est fourni, vous devez indiquer des valeurs dans les champs **Catégorie d’approvisionnement** et **Hiérarchie des catégories d’approvisionnement**. Si aucune valeur de catégorie d’approvisionnement ou de hiérarchie de catégorie d’approvisionnement n’est fournie, vous devez fournir une valeur dans le champ **Numéro d’article**.                    |
| Nom de l’article (facultatif)                                 |  Limité à 60 caractères                               |
| Hiérarchie de catégories d’approvisionnement (facultative)            |    **Remarque :** si vous indiquez une valeur pour ce champ, le champ **Catégorie d’approvisionnement** est également obligatoire.                                                                         |
| Catégorie d’approvisionnement (facultative)                      | **Remarque :** si vous indiquez une valeur pour ce champ, le champ **Hiérarchie de catégories d’approvisionnement** est également obligatoire.                                                                        |
| Quantité (facultative)                                  |                                                   |
| Unité (facultative)                                      | Limité à dix caractères                               |
|Montant net de ligne                                       | Les valeurs décimales sont autorisées.                       |
| Prix unitaire (facultatif)                                | Les valeurs décimales sont autorisées.                       |


**Section de distribution**

| Champ                                                | Détails                                  |
|------------------------------------------------------|------------------------------------------|
| Nombre                                               | Numéro de ligne de répartition comptable      |
| Dimensions financières                                 | Si le fichier que vous importez comporte des dimensions financières, vous devez inclure toutes les dimensions financières avec la dénomination appropriée. Sinon, un message d’erreur s’affichera pour indiquer que la dimension comptable n’est pas valide. Vous devrez ensuite soit corriger les dimensions financières, soit supprimer les colonnes du fichier.                                         |
| Pourcentage                                              | Les valeurs décimales sont autorisées.              |




## <a name="what-do-i-do-next"></a>Que faire ensuite ?
Après avoir paramétré les conditions préalables nécessaires, consultez [Fournisseurs occasionnels dans le secteur public](one-time-vendors-public-sector.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Fournisseurs occasionnels (Secteur public)](one-time-vendors-public-sector.md)

[Vue d’ensemble de la comptabilité fournisseur dans le secteur public](accounts-payable-public-sector.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]