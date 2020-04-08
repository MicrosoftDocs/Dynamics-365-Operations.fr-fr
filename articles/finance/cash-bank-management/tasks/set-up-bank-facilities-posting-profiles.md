---
title: Paramétrer les établissements bancaires et les profils de validation pour les lettres de garantie
description: Cette tâche crée un établissement bancaire et un profil de validation qui est nécessaire pour traiter une lettre de garantie.
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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ff5402b11cd2ccdfde2881268d9cd936947cd77e
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144243"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letters-of-guarantee"></a>Paramétrer les établissements bancaires et les profils de validation pour les lettres de garantie

[!include [banner](../../includes/banner.md)]

Cette tâche crée un établissement bancaire et un profil de validation qui est nécessaire pour traiter une lettre de garantie.



La société fictive USMF est citée en exemple dans cette tâche. 




## <a name="general-ledger-parameter"></a>Paramètre de comptabilité
1. Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Paramètres de gestion de la trésorerie et de la banque.
2. Développez la section Document bancaire.
3. Sélectionnez l'option Activer la lettre de garantie.
4. Dans le champ Journal des transactions, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
7. Cliquez sur l'onglet Souches de numéros.
    * Définir le code souche de numéros du numéro de lettre de garantie et les références de transaction de lettre de garantie  
8. Cliquez sur Enregistrer.
9. Fermez la page.

## <a name="create-bank-facility"></a>Créer un établissement bancaire
1. Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Établissements bancaires.
2. Cliquez sur Nouveau.
3. Dans le champ Groupe d'établissements, entrez le nom du groupe d'établissements bancaires pour la transaction de lettre de garantie.
4. Dans le champ Description, entrez une valeur.
5. Cliquez sur Enregistrer.
6. Cliquez sur l'onglet Types d'installations.
7. Cliquez sur Nouveau.
8. Dans le champ Type d'établissement, entrez le nom du type d'établissement bancaire lié à l'accord d'établissement bancaire.
9. Tapez une valeur dans le champ Description.
10. Dans le champ Groupe d'installations, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
11. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
12. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
13. Dans le champ Nature de l'établissement, sélectionnez une option.
14. Cliquez sur Enregistrer.
15. Fermez la page.

## <a name="bank-posting-profile"></a>Profil de validation bancaire
1. Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Profil de validation des documents bancaires.
2. Cliquez sur Nouveau.
3. Dans le champ Numéro de compte/groupe, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Dans le champ Compte de règlement, sélectionnez le compte principal pour le règlement.
7. Dans le champ Frais, sélectionnez le compte pour les transactions de dépense.
8. Dans le champ Marge, sélectionnez le compte pour la transaction de marge.
9. Dans le champ Compte de liquidation, sélectionnez le compte de liquidation pour la transaction de lettre de garantie. 
10. Cliquez sur Enregistrer.
11. Fermez la page.

