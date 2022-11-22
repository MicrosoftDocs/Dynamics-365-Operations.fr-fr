---
title: Paramétrer les établissements bancaires et les profils de validation pour les lettres de crédit
description: Cette procédure décrit la création d’un établissement bancaire et un profil de validation requis pour traiter les lettres de crédit.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7fe5b2ba43c4fcb4855c742bdb6f8209ebd92d68
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779460"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a>Paramétrer les établissements bancaires et les profils de validation pour les lettres de crédit

[!include [banner](../../includes/banner.md)]

Cette procédure décrit la création d’un établissement bancaire et un profil de validation requis pour traiter les lettres de crédit. 

La société fictive « USMF » est utilisée dans cette tâche.


## <a name="general-ledger-parameter"></a>Paramètre de comptabilité
1. Accédez à **Gestion de la trésorerie et de la banque > Paramétrage > Paramètres de gestion de la trésorerie et de la banque**.
2. Développez la section **Document bancaire**.
3. Sélectionnez l’option **Activer la lettre de crédit d’importation**.
4. Sélectionnez l’option **Activer la lettre de crédit d’exportation**.
5. Cliquez sur **Enregistrer**.
6. Fermez la page.

## <a name="create-bank-facility"></a>Créer un établissement bancaire
1. Accédez à **Gestion de la trésorerie et de la banque > Paramétrage > Établissements bancaires**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Groupe d’établissements**, entrez le nom du groupe d’établissements bancaires.
4. Dans le champ **Description**, entrez la description du groupe d’établissements bancaires.
5. Cliquez sur **Enregistrer**.
6. Cliquez sur l’onglet **Types d’établissement**.
7. Cliquez sur **Nouveau**.
8. Dans le champ **Type d’établissement**, entrez un code unique.
9. Tapez une valeur dans le champ **Description**.
10. Dans le champ **Groupe d’établissements**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
11. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
12. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
13. Dans le champ **Nature de l’établissement**, sélectionnez la nature de l’établissement bancaire.
14. Cliquez sur **Enregistrer**.
15. Fermez la page.

## <a name="bank-posting-profile"></a>Profil de validation bancaire
1. Accédez à **Gestion de la trésorerie et de la banque > Paramétrage > Profil de validation des documents bancaires**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Numéro de compte/groupe**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Sélectionnez la catégorie principale de l’accord.
    * Ce compte est utilisé lors du calcul de la prévision de flux de trésorerie.  
7. Dans le champ **Compte de frais**, sélectionnez le compte pour les transactions de dépense.
8. Dans le champ **Compte de marge**, sélectionnez le compte pour les transactions de marge.
    * Ce compte est débité lorsque la marge d’ouverture est validée et crédité lorsque le paiement est validé.  
9. Cliquez sur **Enregistrer**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
