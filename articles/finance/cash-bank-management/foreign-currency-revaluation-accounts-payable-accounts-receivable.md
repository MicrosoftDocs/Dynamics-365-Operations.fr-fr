---
title: Réévaluer une devise pour la comptabilité fournisseur et la comptabilité client
description: Cette rubrique fournit des informations sur le processus de réévaluation des comptes en devises que vous exécutez pour mettre à jour la valeur des transactions en cours dans Comptabilité fournisseur et Comptabilité client.
author: kweekley
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustExchRateAdjustment, VendExchRateAdjustment
audience: Application User
ms.reviewer: roschlom
ms.custom: 14211
ms.assetid: defb1ea5-1f3e-4859-87d8-3f9954d3f388
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1c84a373363fc066f46eb7891b421be098c0033526f2604d0ee52ff9c3fd9db3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774351"
---
# <a name="currency-revaluation-for-accounts-payable-and-accounts-receivable"></a>Réévaluer une devise pour la comptabilité fournisseur et la comptabilité client

[!include [banner](../includes/banner.md)]

Des fluctuations des taux de change entraînent une variation de la valeur théorique (valeur comptable) des transactions en cours en devises étrangères avec le temps. Cette rubrique fournit des informations sur le processus de réévaluation des comptes en devises que vous exécutez pour mettre à jour la valeur des transactions en cours dans Comptabilité fournisseur et Comptabilité client. 

La valeur théorique (valeur comptable) des transactions fournisseur en cours en devises étrangères varie avec le temps en raison des fluctuations des taux de change. Pour mettre à jour la valeur des transactions en cours dans Ventes et Achats, exécutez le processus de réévaluation des comptes en devises. La réévaluation des comptes en devises peut être exécutée à la fois pour les Achats et les Ventes. Le processus utilise un nouveau taux de change pour réévaluer les montants en cours, ou les montants non réglés, à une date particulière. Les différences entre les montants d’origine validés et les montants réévalués entraîneront un profit/une perte non réalisé(e) pour chaque transaction en cours. Les comptabilités auxiliaires Achats et Ventes sont alors mises à jour pour refléter le profit/la perte non réalisé(e), et une écriture comptable est validée dans la comptabilité.

## <a name="simulate-a-foreign-currency-revaluation"></a>Simulation d’une réévaluation des comptes en devises
Avant de réévaluer les montants en devise étrangère sur les transactions en cours, vous pouvez effectuer une simulation de la réévaluation des comptes en devises pour une même date et une même période. Pour exécuter l’état de simulation, sur la page **Réévaluation des comptes en devises**, cliquez sur le bouton **Simulation**. L’état fournit un aperçu du montant de profit/de perte non réalisé(e), selon les paramètres définis pour la simulation.

## <a name="process-a-foreign-currency-revaluation"></a>Réévaluer des comptes en devises
Utilisez la page **Réévaluation des comptes en devises** sous **Tâches périodiques** pour réévaluer les transactions en cours. Vous pouvez exécuter le processus en temps réel ou le replanifier à l’aide d’un traitement par lots. Lorsque vous définissez les paramètres pour le processus de réévaluation, vérifiez si vous souhaitez imprimer un rapport des résultats. Le rapport de réévaluation ne peut pas être réimprimé une fois le processus terminé. Si vous générez l’état de réévaluation des comptes en devises, il affiche divers soldes au niveau du client/fournisseur et au niveau de la devise :

-   Les soldes des clients ou des fournisseurs comportant des transactions en devises étrangères réévaluées. Les soldes suivants sont déterminés :
    -   Le solde total d’origine dans la devise étrangère.
    -   Le montant de la réévaluation totale de la devise étrangère dans la devise comptable, à compter de la réévaluation précédente.
    -   Le montant de la réévaluation totale de la devise étrangère dans la devise comptable, à compter de la réévaluation actuelle.
    -   La différence entre la réévaluation précédente et la réévaluation actuelle. Cette différence est la perte/le profit non réalisé(e) supplémentaire.
-   Le total du profit/de la perte non réalisé(e) pour chaque devise.

Un enregistrement est conservé chaque fois que vous exécutez la tâche périodique pour la réévaluation des comptes en devises. Depuis l’enregistrement sur la page **Évaluation des comptes en devises**, sélectionnez **Transactions** pour afficher la liste détaillée des transactions créées en raison de la réévaluation. Chaque transaction de document représente la transaction en cours qui a été réévaluée. Si une transaction ouverte a été réévaluée plusieurs fois, vous voyez deux enregistrements qui utilisent le même document. Un enregistrement se rapporte à la contrepassation du profit/de la perte non réalisé(e) précédent(e), et l’autre enregistrement se rapporte au nouveau profit ou à la nouvelle perte non réalisé(e). Pour exécuter le processus de réévaluation, cliquez sur le bouton **Réévaluation des comptes en devises**. Définissez les paramètres appropriés pour les paramètres suivants :

-   **Méthode** – Méthode utilisée lors de la tâche de réévaluation des comptes en devises sélectionnée :
    -   **Standard** – Les tâches de réévaluation des comptes en devises sont validées, que le résultat soit un profit ou une perte.
    -   **Minimum** – Les tâches de réévaluation des comptes en devises sont validées uniquement si le résultat est une perte.
    -   **Date de facture** – Les tâches de réévaluation des comptes en devises utilisent le taux de change d’origine des transactions, qui sont réévaluées à leur valeur d’origine dans la devise comptable. L’effet de toute réévaluation des comptes en devises antérieure est annulé.
-   **Date prévue** – Date de localisation de toutes les transactions ayant des montants en cours (non réglés) à cette date. Les montants en devise étrangère sont réévalués à l’aide des taux de change entrés dans la page **Taux de change des devises** pour la date concernée. Lorsque des montants en devises sont réévalués à une date donnée, celle-ci devient la dernière date de réévaluation des comptes en devises des transactions concernées. Si vous décidez de réévaluer les comptes en devises à une date prévue antérieure à la date de la dernière réévaluation des comptes en devises sur des transactions déjà ajustées, les transactions en cours à la date prévue antérieure, mais ayant une date de dernière réévaluation des comptes en devises plus récente, ne sont pas ajustées par la tâche périodique.
-   **Date de taux** – Date qui détermine le taux de change utilisé lors de la réévaluation des comptes en devises.
-   **Origine du profil de validation** – Le profil de validation utilisé pour entrer le compte principal par défaut pour les comptes Ventes ou Achats pour les écritures comptables des transactions de réévaluation des comptes en devises :
    -   **Validation** – Le profil de validation de la transaction client est utilisé.
    -   **Sélection** – Permet de saisir le profil de validation dans le champ **Profil de validation**.
-   **Profil de validation** – Si l’option **Sélection** est choisie dans le champ **Origine du profil de validation**, le profil de validation des transactions de réévaluation des comptes en devises est déterminé par le profil de validation de ce champ.
-   **Dimensions financières** – Les dimensions financières validées sur les écritures comptables des transactions de réévaluation des comptes en devises. Les dimensions financières ne sont pas validées par rapport aux règles de la structure de compte. La structure de compte qui était en place au moment où les factures ont été validées peut ne pas être la même que les règles qui étaient en place lorsque la réévaluation a été terminée. Il n'y a pas d'option pour sélectionner des dimensions financières spécifiques dans le processus de réévaluation, de sorte que la validation de la structure du compte est ignorée.  
    -   **Aucune** – Aucune dimension financière n’est validée. Si vous avez une dimension financière requise dans votre structure de compte, le processus de réévaluation est toujours exécuté et crée les écritures comptables sans dimension financière. Vous recevrez tout d’abord un message d’avertissement, afin de pouvoir annuler la réévaluation.
    -   **Table** – Les dimensions financières du compte client ou fournisseur sont validées pour les transactions de réévaluation des comptes en devises.
    -   **Validation** – Les dimensions financières de la transaction en cours de réévaluation sont validées pour les transactions de réévaluation des comptes en devises. Par défaut, les dimensions financières du compte général Achats/Ventes de la transaction d’origine sont utilisées pour le compte principal Achats/Ventes de la transaction de réévaluation, et les dimensions financières du compte général Dépense/Actif/Résultat de la transaction d’origine sont utilisées pour le compte principal du profit/perte non réalisé(e) de la transaction de réévaluation.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
