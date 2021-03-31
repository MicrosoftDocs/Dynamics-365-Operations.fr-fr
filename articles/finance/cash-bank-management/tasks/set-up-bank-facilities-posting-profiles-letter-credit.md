---
title: Paramétrer les établissements bancaires et les profils de validation pour les lettres de crédit
description: Cette procédure décrit la création d’un établissement bancaire et un profil de validation requis pour traiter les lettres de crédit.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bc94100461bc82e9e7cd243f198711ab61a79b0c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5225271"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a>Paramétrer les établissements bancaires et les profils de validation pour les lettres de crédit

[!include [banner](../../includes/banner.md)]

Cette procédure décrit la création d’un établissement bancaire et un profil de validation requis pour traiter les lettres de crédit. 

La société fictive « USMF » est utilisée dans cette tâche.






## <a name="general-ledger-parameter"></a>Paramètre de comptabilité
1. Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Paramètres de gestion de la trésorerie et de la banque.
2. Développez la section Document bancaire.
3. Sélectionnez l’option Activer la lettre de crédit d’importation.
4. Sélectionnez l’option Activer la lettre de crédit d’exportation.
5. Cliquez sur Enregistrer.
6. Fermez la page.

## <a name="create-bank-facility"></a>Créer un établissement bancaire
1. Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Établissements bancaires.
2. Cliquez sur Nouveau.
3. Dans le champ Installations, entrez le nom du groupe d’établissements bancaires.
4. Dans le champ Description, entrez la description du groupe d’établissements bancaires.
5. Cliquez sur Enregistrer.
6. Cliquez sur l’onglet Types d’installations.
7. Cliquez sur Nouveau.
8. Dans le champ Installations, entrez un code unique.
9. Dans le champ Description, entrez une valeur.
10. Dans le champ Groupe d’installations, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
11. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
12. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
13. Dans le champ Nature de l’installation, sélectionnez la nature de l’installation bancaire.
14. Cliquez sur Enregistrer.
15. Fermez la page.

## <a name="bank-posting-profile"></a>Profil de validation bancaire
1. Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Profil de validation des documents bancaires.
2. Cliquez sur Nouveau.
3. Dans le champ Numéro de compte/groupe, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Sélectionnez la catégorie principale de l’accord.
    * Ce compte est utilisé lors du calcul de la prévision de flux de trésorerie.  
7. Dans le champ Frais, sélectionnez le compte pour les transactions de dépense.
8. Dans le champ Marge, sélectionnez le compte pour les transactions de marge.
    * Ce compte est débité lorsque la marge d’ouverture est validée et crédité lorsque le paiement est validé.  
9. Cliquez sur Enregistrer.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]