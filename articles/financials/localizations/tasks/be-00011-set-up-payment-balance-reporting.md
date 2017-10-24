--- 
title: "Paramétrer la déclaration de la balance des paiements (Belgique)"
description: "Utilisez cette procédure pour paramétrer les informations BLWI (Belgisch Luxemburgs Wissel Instituut) pour la Belgique."
author: v-oloski
manager: AnnBe
ms.date: 07/12/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Belgium
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: f2916d4c0e9f81f7c596ec801f6d365858896819
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-payment-balance-reporting-belgium"></a>Paramétrer la déclaration de la balance des paiements (Belgique)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Utilisez cette procédure pour paramétrer les informations BLWI (Belgisch Luxemburgs Wissel Instituut) pour la Belgique. Cette procédure a été créée à l'aide de la société fictive USSI.

Cette fonctionnalité est disponible pour les entités juridiques dont l'adresse principale est en Belgique. Avant d'exécuter cette procédure, vous devez paramétrer l'ID enregistrement pour la Belgique et entrer le numéro d'enregistrement qui doit être utilisé pour créer la déclaration BLWI.


## <a name="set-up-a-blwi-countryregion-group"></a>Paramétrer un groupe de pays/régions BLWI
1. Accédez à Taxe > Paramétrage > Commerce extérieur > Groupes de pays/régions BLWI.
2. Cliquez sur Nouveau.
3. Dans le champ ID groupe, tapez une valeur.
4. Dans le champ Description, entrez une valeur.
5. Cliquez sur Ajouter.
6. Dans le champ Pays/Région, sélectionnez ou entrez une valeur.
7. Tapez une valeur dans le champ Description.
8. Cliquez sur Traductions.
9. Dans le champ Langue, saisissez ou sélectionnez une valeur.
10. Fermez la page.

## <a name="set-up-blwi-currencies"></a>Paramétrer les devises BLWI
1. Accédez à Taxe > Paramétrage > Commerce extérieur > Devises BLWI.
2. Cliquez sur Nouveau.
3. Dans le champ Devise, saisissez ou sélectionnez une valeur.
4. Activez la case à cocher État dans cette devise.
5. Dans le champ Numéro colonne, entrez une valeur.

## <a name="set-up-blwi-parameters"></a>Définition des paramètres BLWI
1. Accédez à Taxe > Paramétrage > Commerce extérieur > Paramètres BLWI.
2. Sélectionnez Oui dans le champ BLWI.
    * Ce paramètre doit être activé avant de valider les transactions client/fournisseur, afin que les transactions soient transférées vers la balance des paiements.  
3. Dans le champ E-mail, tapez une valeur.
4. Tapez une valeur dans le champ Nom.
5. Dans le champ Téléphone, tapez une valeur.
6. Dans le champ Télécopie, tapez une valeur.
7. Dans le champ Vérifier le code BLWI dans les journaux, sélectionnez une option.
    * Dans le champ Vérifier le code BLWI, sélectionnez la règle permettant de vérifier qu'un code objectif de paiement est spécifié dans les documents. Les options disponibles sont Aucun, Avertissement et Erreur. Si une transaction a un client/fournisseur situé à l'étranger (autrement dit, le pays/la région du client/fournisseur est différent du pays/de la région de l'entité juridique), la transaction n'a pas de code objectif de paiement affecté et la vérification est définie sur Avertissement ou Erreur, un message d'avertissement ou d'erreur s'affiche lors de la validation. Cette validation est appliquée à toutes les transactions client/fournisseur sauf les transactions de paiement.  
8. Saisissez ou sélectionnez une valeur dans le champ Mise en correspondance des formats.
    * Conditions préalables : vous devez télécharger la configuration (BE) du format BLWI pour les états électroniques auprès de Microsoft Dynamics Lifecycle Services (LCS).  

## <a name="set-up-payment-survey-codes"></a>Paramétrer des codes étude de paiement
1. Accédez à Taxe > Paramétrage > Commerce extérieur > Codes étude de paiement.
2. Cliquez sur Nouveau.
3. Dans le champ Code étude, tapez une valeur.
4. Dans le champ Mois/trimestre, sélectionnez une option.
5. Dans le champ Type de calcul, sélectionnez une option.
    * Si vous sélectionnez Chiffre d'affaires dans le champ Type de calcul, les transactions client/fournisseur validées au cours de la période de déclaration sont transférées vers la balance des paiements, et le montant déclaré est le montant total de la transaction validée.  Si vous sélectionnez Solde, les transactions client/fournisseur en cours (partiellement réglées/clôturées) à la fin de la période de déclaration sont transférées vers la balance des paiements, et le montant déclaré est le montant en cours (non réglé) de la transaction validée à la fin de la période de déclaration.  
6. Dans le champ Description, entrez une valeur.
7. Dans le champ Synthèse pays/région, tapez une valeur.
8. Cliquez sur Ajouter.
9. Dans le champ Code objectif de la banque centrale, entrez ou sélectionnez une valeur.
10. Activez la case à cocher Inclure le paiement.
    * Notez que les transactions de paiement ne sont pas transférées vers l'étude de la balance des paiements par défaut. L'utilisateur doit activer le champ Inclure le paiement pour les codes objectif.  


