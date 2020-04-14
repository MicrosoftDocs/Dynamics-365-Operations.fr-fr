---
title: FR-00003 Codes NAF et numéros Siret
description: Cette procédure indique comment créer des codes NAF et comment les entrer pour les entités juridiques, les clients, les fournisseurs, et les prospects.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CompanyNAFCode, CustTable, VendTable, smmBusRelTable, OMLegalEntity
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: France
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bbe68cece66e661c9114331d43ac9abc03cd4b8d
ms.sourcegitcommit: b92c3e1b3403d0455fc4e0bf9132d6bc0d7aba5e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139013"
---
# <a name="fr-00003-naf-codes-and-siret-numbers"></a>FR-00003 Codes NAF et numéros Siret

[!include [banner](../../includes/banner.md)]

Cette procédure indique comment créer des codes NAF et comment les entrer pour les entités juridiques, les clients, les fournisseurs, et les prospects. Vous pouvez utiliser les codes NAF pour identifier le secteur d'activité d'une entreprise. Par exemple, si votre entité juridique fabrique des ordinateurs, son code NAF pourrait être 300C, à savoir le code NAF de fabrication d'ordinateurs et de matériel informatique. Si votre entité juridique est active dans le secteur de la construction, votre code NAF pourra être 452A.



Cette procédure décrit également comment entrer des numéros de siret pour les clients, les fournisseurs, et les prospects. Le Siret est un nombre à 14 chiffres qui identifie une entreprise, une branche de cette entreprise et une personne associée aux activités de l'entreprise. Ce numéro permet de vérifier qu'une entreprise est correctement enregistrée et autorisée à exercer ce type d'activité.



Cette procédure a été créée à l'aide des données fictives de la société FRSI. Cette fonctionnalité est disponible pour les entités juridiques dont l'adresse principale est en France. Vous devez être dans l'un ou l'autre


## <a name="set-up-a-naf-code"></a>Paramétrage d'un code NAF
1. Accédez à Administration d'organisation > Carnet d'adresses global > Adresses > Codes NAF.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Code NAF.
4. Dans le champ Description, entrez une valeur.
5. Cliquez sur Enregistrer.

## <a name="enter-a-naf-code-and-a-siret-number-for-a-customer"></a>Entrer un code NAF et un numéro SIRET pour un client
1. Accédez à Comptabilité client > Clients > Tous les clients.
2. Cliquez sur l'enregistrement client à mettre à jour.
3. Développez la section Démographie de vente.
4. Cliquez sur Modifier.
5. Tapez une valeur dans le champ N° de Siret.
6. Saisissez ou sélectionnez une valeur dans le champ Code NAF.
7. Cliquez sur Enregistrer.

## <a name="enter-a-naf-code-and-a-siret-number-for-a-vendor"></a>Entrer un code NAF et un numéro SIRET pour un fournisseur
1. Accédez à Comptabilité fournisseur > Fournisseurs > Tous les fournisseurs.
2. Cliquez sur l'enregistrement fournisseur à mettre à jour
3. Développez la section Démographie des achats.
4. Cliquez sur Modifier.
5. Tapez une valeur dans le champ N° de Siret.
6. Saisissez ou sélectionnez une valeur dans le champ Code NAF.
7. Cliquez sur Enregistrer.

## <a name="enter-a-naf-code-and-a-siret-number-for-a-prospect"></a>Entrer un code NAF et un numéro SIRET pour un prospect
1. Accédez à Ventes et marketing > Relation > Prospects > Tous les prospects.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Cliquez sur l'enregistrement de prospect à mettre à jour.
4. Développez la section Démographie de vente.
5. Cliquez sur Modifier.
6. Tapez une valeur dans le champ N° de Siret.
7. Saisissez ou sélectionnez une valeur dans le champ Code NAF.
8. Cliquez sur Enregistrer.

## <a name="set-up-commerce-registration-a-legal-form-and-a-naf-code-for-a-legal-entity"></a>Paramétrer un registre du commerce, une forme juridique, et un code NAF pour une entité juridique
1. Accédez à Administration d'organisation > Organisations > Entités juridiques.
2. Développez la section Numéros d'enregistrement.
3. Cliquez sur Modifier.
4. Entrez une valeur dans le champ Registre du commerce.
    * Entrez le nom de l'agence française dans laquelle l'entité juridique a été enregistrée, par exemple le Registre du commerce et des sociétés.  
5. Saisissez ou sélectionnez une valeur dans le champ Code NAF.
6. Entrez une valeur dans le champ Forme juridique.
    * Entrez le type légal de l'entité juridique, tel que Organisation sans but lucratif, Entreprise industrielle ou Institution financière.  
7. Cliquez sur Enregistrer.

