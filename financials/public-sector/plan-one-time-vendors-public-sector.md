---
title: Plan pour les fournisseurs occasionnels dans le secteur public
description: "Cet article décrit la préparer pour importer et créer les fournisseurs occasionnels et les factures."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 27251
ms.assetid: 936570cb-932f-4027-b3c7-2235ad79bc1c
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: a76abfa35e53673f9780d1a6f8816bd24f9f8e48
ms.openlocfilehash: ddf990bb29dde89c267b4aed169948d7a7925433
ms.lasthandoff: 03/31/2017


---

# <a name="plan-for-one-time-vendors-in-the-public-sector"></a>Plan pour les fournisseurs occasionnels dans le secteur public

Cet article décrit la préparer pour importer et créer les fournisseurs occasionnels et les factures. 

Généralement, si vous planifiez d'importer en masse des informations facturation et sur les fournisseurs, vous commencez par créer un fichier de données au format feuille de calcul et l'enregistrez au format CSV (valeurs séparées par des virgules).

-   Étant donné que les virgules sont utilisées pour séparer les champs dans un fichier CSV, n'utilisez pas les virgules dans le texte d'une entrée. Par exemple, si vous souhaitez spécifier le nom de la société « Smith, Smith, and Jones », entrez-la le en tant que **Smith Smith and Jones**.
-   Si vous effectuez pas réglées les valeurs pour les champs dans cette page, les valeurs de nouvelles d'utilisation des comptes fournisseur du fournisseur occasionnel profil référencé dans ** des paramètres des achats ** la page. Par exemple, si le mode de paiement est défini ** chèque ** pour le profil du fournisseur occasionnel dans ** des paramètres des achats ** la page, ce mode de paiement est également défini pour les fournisseurs occasionnels que vous ajoutez.
-   La souche de numéros de la Comptabilité fournisseur **Fournisseur occasionnel** permet d'affecter les comptes des fournisseurs occasionnels et ne doit pas être défini sur **Continu** pour ce service. Les factures sont générées dans un état de brouillon. Avant de créer des propositions de paiement, vous devez valider les factures.

Le tableau suivant répertorie les champs que le fichier d'importation doit contenir. Chaque nom de champ est équivalent à un en-tête de colonne dans une feuille de calcul, et chaque ligne de la feuille de calcul contient les données pour chaque colonne applicable.

**Section du fournisseur**

| Champ                                          | Détails                                                 |
|------------------------------------------------|---------------------------------------------------------|
|Type d'enregistrement                                     | **Personne** ou **Organisation**                          |
| Prénom                                     | (Si la valeur du type d'enregistrement est **Personne**)                |
| Deuxième prénom (facultatif)                         | (Si le type d'enregistrement est **Personne**)                      |
| Nom                                      | (Si le type d'enregistrement est **Personne**)                      |
| Nom du fournisseur                                    | (Si le type d'enregistrement est **Organisation**)                |
| Groupe                                          | Limité à dix caractères                                     |
| Pays/Région                                 | Limité à dix caractères                                     |
| Code postal                                |                                                         |
| Rue                                         |                                                         |
| Ville                                           |                                                         |
| Ville                                           |                                                         |
|ID taxe fédérale (facultatif)                       | (États-Unis uniquement) nombre 1099                                 |
| Type d'ID taxe                                    | (Pour les États-Unis uniquement) les valeurs peuvent être ** inconnu **, ** numéro d'identification de l'employeur **, ** numéro de Sécurité sociale **, ** numéro d'identification individuel du contribuable **, ou ** numéro d'identification adopté du contribuable **.  ** Remarque : ** Si aucun ID taxe fédérale n'est livré, ce champ doit être défini ** inconnu **.                                               |
| Compte bancaire (facultatif)                        | Nom du compte bancaire                                       |
| Numéro de compte bancaire                            |                                                         |
| Numéro d'acheminement (facultatif)                      |                                                         |
| Code SWIFT (facultatif)                          | Également appelé BIC (Bank Identifier Code)                |
|Code IBAN (facultatif)                                 | Numéro de compte bancaire international, limité à 34 caractères.   |



**Invoice section**

| Champ                                                | Détails                                           |
|------------------------------------------------------|---------------------------------------------------|
| Numéro de facture                                       | Numéro de facture ; limité à 20 caractères                |
| Description de facture (facultative)                       |                                                   |
| Date de validation (facultative)                              | Format de date                                       |
| Date de facture                                         | Format de date                                       |
| Date d'échéance (facultative)                                  | Format de date                                       |
| Numéro de ligne                                          |                                                   |
|Numéro d'article (facultatif)                                | 20 character limite ** note : ** Si aucun numéro d'article n'est livrée, vous devez fournir des valeurs dans ** catégorie d'approvisionnement ** et ** hiérarchie des catégories d'approvisionnement ** des champs. Si aucune valeur de catégorie d'approvisionnement ou de hiérarchie de catégorie d'approvisionnement n'est fournie, vous devez fournir une valeur dans le champ **Numéro d'article**.                    |
| Nom de l'article (facultatif)                                 |  Limité à 60 caractères                               |
| Hiérarchie de catégories d'approvisionnement (facultative)            |    **Remarque :** si vous indiquez une valeur pour ce champ, le champ **Catégorie d'approvisionnement** est également obligatoire.                                                                         |
| Catégorie d'approvisionnement (facultative)                      | **Remarque :** si vous indiquez une valeur pour ce champ, le champ **Hiérarchie de catégories d'approvisionnement** est également obligatoire.                                                                        |
| Quantité (facultative)                                  |                                                   |
| Unité (facultative)                                      | Limité à dix caractères                               |
|Montant net de ligne                                       | Les valeurs décimales sont autorisées.                       |
| Prix unitaire (facultatif)                                | Les valeurs décimales sont autorisées.                       |


**Section de distribution**
| Champ                                                | Détails                                  |
|------------------------------------------------------|------------------------------------------|
| Nombre                                               | Numéro de ligne de répartition comptable      |
| Compte général                                       |                                          |
| Pourcentage                                              | Les valeurs décimales sont autorisées.              |




## <a name="what-do-i-do-next"></a>Que faire ensuite ?
Après avoir paramétré les conditions préalables nécessaires, consultez [Fournisseurs occasionnels dans le secteur public](one-time-vendors-public-sector.md).

<a name="see-also"></a>Voir également :
--------

[One-time vendors in the public sector](one-time-vendors-public-sector.md)

[Comptabilité fournisseur dans le secteur public](accounts-payable-public-sector.md)


