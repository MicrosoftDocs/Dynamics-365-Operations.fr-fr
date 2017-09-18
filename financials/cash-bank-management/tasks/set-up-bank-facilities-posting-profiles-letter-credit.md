--- 
title: "Paramétrer les établissements bancaires et les profils de validation pour les lettres de crédit"
description: "Cette procédure décrit la création d'un établissement bancaire et un profil de validation requis pour traiter les lettres de crédit."
author: kweekley
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 4cf5d982fa58df93529f3506beef46f660265530
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a>Paramétrer les établissements bancaires et les profils de validation pour les lettres de crédit

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit la création d'un établissement bancaire et un profil de validation requis pour traiter les lettres de crédit. 

La société fictive « USMF » est utilisée dans cette tâche.






## <a name="general-ledger-parameter"></a>Paramètre de comptabilité
1. Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Paramètres de gestion de la trésorerie et de la banque.
2. Développez la section Document bancaire.
3. Sélectionnez l'option Activer la lettre de crédit d'importation.
4. Sélectionnez l'option Activer la lettre de crédit d'exportation.
5. Cliquez sur Enregistrer.
6. Fermez la page.

## <a name="create-bank-facility"></a>Créer un établissement bancaire
1. Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Établissements bancaires.
2. Cliquez sur Nouveau.
3. Dans le champ Installations, entrez le nom du groupe d'établissements bancaires.
4. Dans le champ Description, entrez la description du groupe d'établissements bancaires.
5. Cliquez sur Enregistrer.
6. Cliquez sur l'onglet Types d'installations.
7. Cliquez sur Nouveau.
8. Dans le champ Installations, entrez un code unique.
9. Dans le champ Description, entrez une valeur.
10. Dans le champ Groupe d'installations, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
11. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
12. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
13. Dans le champ Nature de l'installation, sélectionnez la nature de l'installation bancaire.
14. Cliquez sur Enregistrer.
15. Fermez la page.

## <a name="bank-posting-profile"></a>Profil de validation bancaire
1. Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Profil de validation des documents bancaires.
2. Cliquez sur Nouveau.
3. Dans le champ Numéro de compte/groupe, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Sélectionnez la catégorie principale de l'accord.
    * Ce compte est utilisé lors du calcul de la prévision de flux de trésorerie.  
7. Dans le champ Frais, sélectionnez le compte pour les transactions de dépense.
8. Dans le champ Marge, sélectionnez le compte pour les transactions de marge.
    * Ce compte est débité lorsque la marge d'ouverture est validée et crédité lorsque le paiement est validé.  
9. Cliquez sur Enregistrer.

