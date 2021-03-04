---
title: Définir les commissions de paiement fournisseur
description: Paramétrez les frais de paiement fournisseur.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPaymFee, VendPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 404bd1e22caa8098f114a2dcc67dd420509cce2b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443011"
---
# <a name="define-vendor-payment-fees"></a>Définir les commissions de paiement fournisseur

[!include [banner](../../includes/banner.md)]

Paramétrez les frais de paiement fournisseur. La société fictive USMF est citée en exemple dans cette tâche.

1. Accédez à Comptabilité fournisseur > Paramétrage des paiements > Frais de paiement.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ ID frais.
    * L’ID de frais doit décrire quand ces frais sont utilisés, par exemple « Frais_EFT ».  
4. Tapez une valeur dans le champ Nom.
5. Tapez une valeur dans le champ Description des frais.
    * Ajoutez une description pour décrire à quel moment les frais sont imputés.  
6. Sélectionnez Fournisseur ou Comptabilité dans le champ Frais.
    * Le compte Comptabilité est utilisé lorsque les frais sont imputés à votre organisation.  Le compte Fournisseur est utilisé lorsque les frais sont imputés au fournisseur.  
7. Entrez un compte principal pour lequel les frais seront imputés.
    * Cette option n’est disponible que si Comptabilité est sélectionné comme option de frais.  
8. Sélectionnez le journal dans lequel ces frais peuvent être utilisés. 
    * Pour les frais de paiement fournisseur, vous devez sélectionner le journal « Fournisseur - Paiements ».  
9. Cliquez sur Enregistrer.
10. Cliquez sur Paramétrage des frais de paiement.
    * Passez au paramétrage des frais de paiement pour définir à quel moment les frais doivent être définis par défaut dans le journal sélectionné.  
11. Sélectionnez Tableau, Groupe ou Tous.
    * Tableau permet de sélectionner un compte bancaire unique, Groupe permet de sélectionner un groupe de banques, et Tous permet d’appliquer le paramétrage des frais pour tous les comptes bancaires  
12. Sélectionnez un groupe de banques ou un compte bancaire.
    * La recherche affiche le groupe de banques si vous avez sélectionné Groupe, et indique les comptes bancaires si vous avez sélectionné Tableau.  
13. Sélectionnez le mode de paiement pour lequel ces frais seront imputés.
14. Sélectionnez les spécifications de paiement pour le mode de paiement sélectionné.
    * La spécification de paiement est utilisée avec des modes de paiement électroniques.  
15. Sélectionnez si les frais sont un pourcentage, un montant ou un intervalle.
16. Entrez le pourcentage ou le montant des frais.
    * Si les frais sont un pourcentage, entrez le pourcentage. Si les frais sont un montant, entrez le montant des frais. Si les frais sont un intervalle, utilisez l’onglet Intervalle pour définir des frais progressifs.  
17. Dans le champ Devise des frais, sélectionnez la devise dans laquelle les frais seront imputés.
    * Cette devise est pour les frais. La devise de paiement est utilisée pour définir à quel moment la règle en matière de frais doit être évaluée selon la devise du paiement. Par exemple, votre banque peut facturer des frais lorsqu’un paiement est effectué en EUR, mais des frais ne sont pas imputés à tous les autres paiements.  
18. Cliquez sur Enregistrer.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]