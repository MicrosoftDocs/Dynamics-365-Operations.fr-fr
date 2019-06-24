---
title: EUR-00011 Paramétrer une déclaration de la liste des ventes intracommunautaires
description: Cette tâche vous accompagne dans une présentation des conditions préalables requises à la génération d'états de la liste des ventes intracommunautaires.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionRepositoryTable, ERSolutionImport, SysQueryForm, SysQueryFieldLookUp,  TaxTable, TaxGroup, TaxItemGroup, TaxCountryRegionParameters, TaxVATNumTable, IntrastatParameters, CustTable, DirPartyQuickCreateForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aef1d19aabb7937fcd961a9657b8ca65c064b0b1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564396"
---
# <a name="eur-00011-set-up-eu-sales-list-reporting"></a>EUR-00011 Paramétrer une déclaration de la liste des ventes intracommunautaires

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette tâche vous accompagne dans une présentation des conditions préalables requises à la génération d'états de la liste des ventes intracommunautaires. Pour plus d'informations sur la déclaration de la liste des ventes intracommunautaires, notamment les conditions préalables requises, reportez-vous à l'aide de Dynamics 365 for Finance and Operations.

Cette tâche s'applique à tous les pays/régions européens. Le guide a été créé avec la société fictive DEMF ; par conséquent, l'Allemagne est pris comme exemple de pays/région local. Le guide utilise également le Portugal comme pays/région européen d'exemple.

Ces tâches sont destinées aux administrateurs système.


## <a name="import-electronic-reporting-configurations-for-eu-sales-list-reporting"></a>Importer les configurations de génération d'états électroniques pour la déclaration de la liste des ventes intracommunautaires
1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
2. Cliquez sur Activer.
3. Cliquez sur Référentiels.
4. Cliquez sur Ouvrir.
5. Dans le volet Actions, cliquez sur Options.
6. Cliquez sur Filtre/tri avancé.
7. Cliquez sur Ajouter.
8. Dans le champ Champ, sélectionnez Nom de la configuration.
9. Dans le champ Critère, entrez « Liste des ventes intracommunautaires (DE) ».
10. Cliquez sur OK.
11. Cliquez sur Importer.
12. Cliquez sur Oui.
13. Dans le volet Actions, cliquez sur Options.
14. Cliquez sur Filtre/tri avancé.
15. Cliquez sur Réinitialiser.
16. Cliquez sur Ajouter.
17. Dans le champ Champ, sélectionnez Nom de la configuration.
18. Dans le champ Critère, entrez « État de la liste des ventes intracommunautaires par lignes ».
19. Cliquez sur OK.
20. Cliquez sur Importer.
21. Cliquez sur Oui.

## <a name="set-up-sales-tax-codes-for-eu-sales-list-reporting"></a>Paramétrer les codes taxe pour la déclaration de la liste des ventes intracommunautaires
1. Accédez à Taxes > Taxes indirectes > Taxe > Codes taxe.
2. Utiliser le filtre rapide pour filtrer le champ Taxe avec une valeur de « TVA19 ».
3. Développez la section Paramétrage de l'état.
    * Vérifiez que la sélection Exclue est définie sur Non.  
    * Vous devez peut-être déverrouiller le guide pour modifier ce paramètre.  

## <a name="set-up-sales-tax-groups-for-eu-sales-list-reporting"></a>Paramétrer les groupes de taxe pour la déclaration de la liste des ventes intracommunautaires
1. Accédez à Taxe > Taxes indirectes > Taxe > Groupes de taxe.
2. Utiliser le filtre rapide pour filtrer le champ Groupe de taxes avec une valeur « AR-DOM ».
3. Cliquez sur Modifier.
4. Développez la section Paramétrage.
5. Dans la liste, sélectionnez la première ligne.
6. Activer cette case à cocher Exonéré.
7. Dans la liste, sélectionnez la deuxième ligne.
8. Activer cette case à cocher Exonéré.
9. Dans la liste, sélectionnez la troisième ligne.
10. Activer cette case à cocher Exonéré.

## <a name="set-up-item-sales-tax-groups-for-eu-sales-list-reporting"></a>Paramétrer les groupes de taxe d'article pour la déclaration de la liste des ventes intracommunautaires
1. Accédez à Taxe > Taxes indirectes > Taxe > Groupes de taxe d'article.
2. Utilisez le filtre rapide pour filtrer le champ Groupe de taxe d'article avec une valeur « FULL ».
    * Vérifiez que la sélection du Type de génération d'états est définie sur Article.  
    * Vous devez peut-être déverrouiller le guide pour modifier la valeur de ce champ.  
3. Utilisez le filtre rapide pour filtrer le champ Groupe de taxe d'article avec une valeur « RED ».
    * Vérifiez que la sélection du Type de génération d'états est définie sur Service.  
    * Vous devez peut-être déverrouiller le guide pour modifier la valeur de ce champ.  

## <a name="set-up-countryregion-parameters-for-eu-sales-list-reporting"></a>Paramétrer les paramètres des pays/régions pour la déclaration de la liste des ventes intracommunautaires
1. Accédez à Taxe > Paramétrage > Taxe > Paramètres de pays/région.
2. Cliquez sur Nouveau.
3. Tapez PRT dans le champ Pays/Région.
4. Dans le champ Taxe, entrez « PT ».

## <a name="create-tax-exempt-numbers"></a>Créer des numéros identifiant TVA
1. Accédez à Taxe > Paramétrage > Taxe > Numéros d'exonération fiscale.
2. Cliquez sur Nouveau.
3. Tapez PRT dans le champ Pays/Région.
4. Tapez PT12345 dans le champ Numéros identifiant TVA.

## <a name="set-up-eu-sales-list-reporting-parameters"></a>Paramétrer les paramètres de déclaration de la liste des ventes intracommunautaires
1. Accédez à Taxe > Paramétrage > Commerce extérieur > Paramètres de commerce extérieur.
2. Cliquez sur l'onglet Liste des ventes intracommunautaires.
3. Sélectionnez Oui dans le champ Transférer les achats.
4. Développez la section Règles d'arrondi.
5. Définissez la règle d'arrondi sur 0,1.
6. Sélectionnez Oui dans le champ Utiliser la valeur minimale.
7. Entrez 2 dans le champ Nombre de décimales.
8. Développez la section Génération d'états électroniques.
9. Dans le champ Mise en correspondance des formats de fichier, sélectionnez « liste des ventes intracommunautaires (DE) ».
10. Dans le champ Mise en correspondance des formats d'état, sélectionnez « État de la liste des ventes intracommunautaires par lignes ».
11. Cliquez sur l'onglet Propriétés de pays/régions.
    * Vérifiez que le champ Pays/région est défini sur « Local » défini pour le pays/la région DEU.  
    * Vous devez peut-être déverrouiller le guide pour modifier la valeur de ce champ.  
12. Cliquez sur Nouveau.
13. Tapez PRT dans le champ Pays/Région.
14. Dans le champ Code de déclaration d'échanges de biens, tapez PT.
15. Dans le champ Type de pays/région, sélectionnez UE.
16. Cliquez sur l'onglet Souches de numéros.
    * Vérifiez qu'un code souche de numéros est spécifié pour la référence « Liste des ventes intracommunautaires ».  

## <a name="create-a-customer-for-eu-sales-list-reporting-demo-purposes"></a>Créer un client pour démonstration de la déclaration d'états de liste des ventes intracommunautaires
1. Accédez à Comptabilité client > Clients > Tous les clients.
2. Cliquez sur Nouveau.
3. Tapez PRT-001 dans le champ Compte client.
4. Dans le champ Nom, entrez « Un client du Portugal ».
5. Sélectionnez 10 dans le champ Groupe de clients.
6. Dans le champ Groupe de taxe, sélectionnez AR-DOM.
7. Sélectionnez PT12345 dans le champ Numéros identifiant TVA.
8. Tapez PRT dans le champ Pays/Région.
9. Cliquez sur Enregistrer.

