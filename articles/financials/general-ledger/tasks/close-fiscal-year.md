--- 
title: "Clôturer l'exercice"
description: "Cette procédure guide l'utilisateur tout au long du processus de clôture de fin d'exercice qui transfère les soldes vers le nouvel exercice."
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerParameters, LedgerFiscalCloseGroup, LedgerFiscalCloseAddLedger, SysLookupMultiSelectGrid, LedgerFiscalCloseRunGroup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4f2f1f1206f3cb3534ef93923d4945bb63814514
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="close-the-fiscal-year"></a>Clôturer l'exercice

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure guide l'utilisateur tout au long du processus de clôture de fin d'exercice qui transfère les soldes vers le nouvel exercice.


## <a name="validate-year-end-close-parameters"></a>Valider les paramètres de clôture de fin d'exercice
1. Accédez à Comptabilité > Paramétrage de la comptabilité > Paramètres de comptabilité.
2. Développez la section Clôture d'exercice.
3. Sélectionnez Oui ou Non pour l'option Supprimer les transactions de clôture d'exercice lors du transfert.
    * Si l'exercice a déjà été clôturé et la clôture de fin d'exercice est réexécutée, ce paramètre est important. S'il est défini sur Oui, le N° document pour la clôture de fin d'exercice précédente est supprimé, et un nouveau N° document est créé pour tous les soldes d'ouverture de compte. S'il est défini sur Non, le N° document précédent est conservé et un nouveau N° document est créé uniquement pour ajuster les entrées qui ont été validées après la dernière clôture de fin d'exercice.  
4. Sélectionnez Oui ou Non selon que vous souhaitez créer des transactions de clôture lors du transfert.
    * Si l'option est définie sur Oui, deux transactions sont créées. Un N° document est créé dans l'exercice en cours de clôture pour remettre les soldes des comptes généraux à zéro et un second N°document est créé dans l'exercice suivant pour les soldes d'ouverture. Si l'option est définie sur Non, un N° document unique est créé dans l'exercice suivant pour les soldes d'ouverture.  
5. Sélectionnez Oui ou Non selon que vous souhaitez définir le statut de l'exercice sur Définitivement clôturé.
    * Si l'option est définie sur Oui, le statut de l'exercice est défini sur Clôturé définitivement.  Comme une année définitivement clôturée ne peut pas être rouverte, il est recommandé de définir cette option sur Non.  
6. Sélectionnez Oui ou Non selon qu'un N° document doit être renseigné lors de la clôture de fin d'exercice.
    * Si l'option est définie sur Oui, un N° document doit être entré manuellement lors du processus de clôture de fin d'exercice. Une souche de numéros n'est pas utilisée pour générer ce N° document. Il est recommandé de définir cette option sur Oui.  
7. Fermez la page.
8. Accédez à Comptabilité > Clôturer la période > Clôture de fin d'exercice.
9. Cliquez sur Nouveau pour créer un modèle de clôture de fin d'exercice.
    * Un modèle peut être créé pour un groupe d'entités juridiques pour lesquelles exécuter la clôture de fin d'exercice. Ce modèle peut être réutilisé année après année.  
10. Dans le champ Nom du groupe, entrez un nom de modèle de clôture de fin d'exercice.
11. Sélectionnez l'exercice pour lequel le modèle est créé.
    * Seules les entités juridiques qui utilisent le même exercice peuvent être regroupées dans le modèle de clôture de fin d'exercice. Cela est dû au fait que la clôture de fin d'exercice est effectuée en sélectionnant un exercice, pas une date.  
12. Utilisez le raccourci pour enregistrer un enregistrement.
13. Cliquez sur Ajouter pour sélectionner les entités juridiques pour ce modèle.
    * Des entités juridiques peuvent être ajoutées en sélectionnant les entités juridiques ou en sélectionnant une hiérarchie d'organisation.  Seules les entités juridiques avec une hiérarchie d'organisation qui utilisent le même calendrier fiscal sélectionné sont ajoutées.  
14. Sélectionnez les entités juridiques ou la hiérarchie d'organisation.
15. Cliquez sur OK.
16. Indiquez si les dimensions financières sont transférées vers l'exercice suivant.
    * Il est recommandé de définir cette option sur Oui pour les comptes de bilan.  Cela permet de tenir à jour les dimensions financières dans les transactions validées lors de la création des soldes d'ouverture des comptes de bilan.  Pour les comptes de résultat, vous pouvez choisir de tenir à jour les dimensions financières (Clôturer tout) lorsque les soldes sont transférés vers le compte de bénéfices non répartis, ou vous pouvez choisir de remplacer les dimensions financières par une valeur de dimension différente (Clôturer individuellement). Si vous choisissez Clôturer individuellement, vous pouvez définir une valeur de dimension spécifique pour chaque dimension ou même choisir de laisser ce champ vide.  
17. Cliquez sur Enregistrer.
18. Démarrez la clôture de fin d'exercice en choisissant Exécuter la clôture fiscale dans le volet Actions.
    * La clôture de fin d'exercice est exécutée pour le modèle sélectionné.  
19. Sélectionnez la totalité ou un sous-ensemble d'entités juridiques à partir du modèle pour lequel exécuter la clôture de fin d'exercice.
    * Lors de la première exécution de la clôture de fin d'exercice, pour obtenir les soldes d'ouverture, la plupart des organisations peuvent choisir d'exécuter la clôture de fin d'exercice pour toutes les entités juridiques du modèle. Si les entrées sont ensuite ajustées, vous pouvez choisir d'exécuter la clôture de fin d'exercice uniquement pour les entités juridiques ayant des ajustements.  
20. Cliquez sur OK.
21. Sélectionnez l'exercice pour lequel exécuter la clôture de fin d'exercice.
22. Dans le champ N° document, tapez une valeur.
    * Il est recommandé d'inclure l'exercice dans le n° document pour faciliter la recherche du document de clôture de fin d'exercice créé.  
23. La clôture de fin d'exercice s'exécute par défaut en mode de traitement par lots.
    * Il est recommandé d'exécuter les processus longs en mode de traitement par lots. Il s'agit généralement de l'un de ces processus, c'est la raison pour laquelle il est recommandé par défaut d'utiliser le mode de traitement par lots.  
24. Cliquez sur OK.


