---
title: FR-00003 Codes NAF et numéros Siret
description: Cet article explique comment créer des codes NAF et comment les entrer pour les entités juridiques, les clients, les fournisseurs, et les prospects.
author: EvgenyPopovMBS
ms.date: 09/10/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CompanyNAFCode, CustTable, VendTable, smmBusRelTable, OMLegalEntity
audience: Application User
ms.reviewer: kfend
ms.search.region: France
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1234ebaccb90b764ba9166565760d1e3c8c7c7ae
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906199"
---
# <a name="fr-00003-naf-codes-and-siret-numbers"></a>FR-00003 Codes NAF et numéros Siret

[!include [banner](../../includes/banner.md)]

Cet article explique comment créer des codes NAF et comment les entrer pour les entités juridiques, les clients, les fournisseurs, et les prospects. Vous pouvez utiliser les codes NAF pour identifier le secteur d’activité d’une entreprise. Par exemple, si votre entité juridique fabrique des ordinateurs, son code NAF pourrait être 300C, à savoir le code NAF de fabrication d’ordinateurs et de matériel informatique. Si votre entité juridique est active dans le secteur de la construction, votre code NAF pourra être 452A.

Cet article décrit également comment entrer des numéros de siret pour les clients, les fournisseurs, et les prospects. Le Siret est un nombre à 14 chiffres qui identifie une entreprise, une branche de cette entreprise et une personne associée aux activités de l’entreprise. Ce numéro permet de vérifier qu’une entreprise est correctement enregistrée et autorisée à exercer ce type d’activité.

Cette procédure a été créée à l’aide des données fictives de la société FRSI. Cette fonctionnalité est disponible pour les entités juridiques dont l’adresse principale est en France.


## <a name="set-up-a-naf-code"></a>Paramétrage d’un code NAF
1. Accédez à **Administration d’organisation** > **Carnet d’adresses global** > **Adresses** > **Codes NAF**.
2. Sélectionnez **Nouveau**.
3. Tapez une valeur dans le champ **Code NAF**.
4. Tapez une valeur dans le champ **Description**.
5. Sélectionnez **Enregistrer**.

## <a name="enter-a-naf-code-and-a-siret-number-for-a-customer"></a>Entrer un code NAF et un numéro SIRET pour un client
1. Accédez à **Comptabilité client** > **Clients** > **Tous les clients**.
2. Sélectionnez l’enregistrement client à mettre à jour.
3. Développez la section **Démographie de vente**.
4. Sélectionnez **Modifier**.
5. Tapez une valeur dans le champ **N° de Siret**.
6. Saisissez ou sélectionnez une valeur dans le champ **Code NAF**.
7. Sélectionnez **Enregistrer**.

## <a name="enter-a-naf-code-and-a-siret-number-for-a-vendor"></a>Entrer un code NAF et un numéro SIRET pour un fournisseur
1. Accédez à **Comptabilité fournisseur** > **Fournisseurs** > **Tous les fournisseurs**.
2. Cliquez sur l’enregistrement fournisseur à mettre à jour.
3. Développez la section **Démographie des achats**.
4. Sélectionnez **Modifier**.
5. Tapez une valeur dans le champ **N° de Siret**.
6. Saisissez ou sélectionnez une valeur dans le champ **Code NAF**.
7. Sélectionnez **Enregistrer**.

## <a name="enter-a-naf-code-and-a-siret-number-for-a-prospect"></a>Entrer un code NAF et un numéro SIRET pour un prospect
1. Accédez à **Ventes et marketing** > **Relation** > **Prospects** > **Tous les prospects**.
2. Dans la liste, localisez et sélectionnez l’enregistrement de prospect que vous voulez mettre à jour.
3. Développez la section **Démographie de vente**.
4. Sélectionnez **Modifier**.
5. Tapez une valeur dans le champ **N° de Siret**.
6. Saisissez ou sélectionnez une valeur dans le champ **Code NAF**.
7. Sélectionnez **Enregistrer**.

## <a name="set-up-commerce-registration-a-legal-form-a-naf-code-and-a-siret-number-for-a-legal-entity"></a>Paramétrer un registre du commerce, une forme juridique, un code NAF et un numéro de SIRET pour une entité juridique
1. Accédez à **Administration d’organisation** > **Organisations** > **Entités juridiques**.
2. Développez la section **Numéros d’enregistrement**.
3. Sélectionnez **Modifier**.
4. Entrez une valeur dans le champ **Registre du commerce**. Entrez le nom de l’agence française dans laquelle l’entité juridique a été enregistrée, par exemple le Registre du commerce et des sociétés.  
5. Saisissez ou sélectionnez une valeur dans le champ **Code NAF**.
6. Entrez une valeur dans le champ **Forme juridique**. Entrez le type légal de l’entité juridique, tel que Organisation sans but lucratif, Entreprise industrielle ou Institution financière.  
7. Sélectionnez **Enregistrer**.
8. Développez la section **Immatriculation fiscale**.
9. Dans le champ **Immatriculation fiscale** saisissez un numéro de SIRET de l’entité juridique.
10. Sélectionnez **Enregistrer**. 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
