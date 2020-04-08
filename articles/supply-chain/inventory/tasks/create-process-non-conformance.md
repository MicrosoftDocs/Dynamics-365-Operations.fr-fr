---
title: Créer et traiter une conformité
description: Cette rubrique explique comment effectuer la gestion de non-conformité, en fonction d'un ordre de qualité existant.
author: perlynne
manager: AnnBe
ms.date: 08/07/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d012af1924e9eedee41f46de6c253d009cb52d2
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145707"
---
# <a name="create-and-process-a-conformance"></a>Créer et traiter une conformité

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment effectuer la gestion de non-conformité, en fonction d'un ordre de qualité existant. Vous pouvez exécuter cet enregistrement de la société de démonstration USMF et utiliser les valeurs suggérées. Généralement, cette procédure est réalisée par le commis à la qualité.  Il est indispensable de commencer par suivre les instructions de la section [Inspecter la qualité des marchandises](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md). Pour traiter l'approbation d'une non-conformité, l'utilisateur qui exécute l'enregistrement de la tâche doit spécifier une valeur « Nom » affectée sur la page Utilisateurs. Pour utiliser les notes de document, l'utilisateur doit également avoir activé la gestion des documents dans les options d'utilisateur.


## <a name="select-a-quality-order"></a>Sélectionnez un ordre de qualité.
1. Dans le volet de navigation, accédez à **Modules > Gestion des stocks > Tâches périodiques > Gestion de la qualité > Ordres de qualité**.
2. Dans la liste, sélectionnez l'ordre de qualité créé dans la section [Inspecter la qualité des marchandises](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).  

## <a name="create-a-nonconformance"></a>Créer une non-conformité
1. Dans le volet Actions, sélectionnez **Recherches**.
2. Sélectionnez **Non-conformités**.
3. Sélectionnez **Nouveau**.
4. Dans le menu déroulant du champ **Type de problème**, sélectionnez le problème qui a été trouvé au cours du processus d'inspection.  
5. Cliquez sur **OK**.

## <a name="approvereject-a-nonconformance"></a>Approuver/rejeter une non-conformité
1. Sélectionnez **Fonctions**.
2. Sélectionnez **Approuver la non-conformité**. Pour cet exemple, approuvez la non-conformité. Les non-conformités approuvées peuvent être associées à des opérations associées au travail d'enregistrement qui est exécuté dans le cadre de la gestion de la non-conformité et, comme dans cette rubrique, le traitement de la gestion des corrections.  
3. Cliquez sur **Oui**.

## <a name="create-a-correction-action"></a>Créer une action de correction
1. Sélectionnez **Corrections**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Numéro personnel** de la nouvelle ligne, sélectionnez l'enregistrement souhaité dans le menu déroulant qui s'affiche.
4. Cliquez sur **Sélectionner**.
5. Sélectionnez **Lier**. Créez une remarque sur la correction. Pour cet exemple, l'action consiste à contacter le fournisseur pour présenter l'incident de non-conformité.  
6. Sélectionnez **Nouveau**.
7. Sélectionnez **Note**. Selon le paramétrage d'état, différents types de documents peuvent être imprimés sur les états associés à la gestion de non-conformité.  
8. Tapez une valeur dans le champ **Description**.
9. Fermez la page.

## <a name="maintain-a-correction"></a>Maintenir une correction
1. Sélectionnez **Marquer comme terminé**.
2. Cliquez sur **OK**.
3. Fermez la page.

## <a name="close-a-nonconformance"></a>Clôturer une non-conformité
1. Sélectionnez **Fonctions**.
2. Sélectionnez **Clôturer la non-conformité**.
3. Cliquez sur **Oui**.
4. Fermez les pages.
