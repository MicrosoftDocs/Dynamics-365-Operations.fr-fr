---
title: "Vue d&quot;ensemble de mise à niveau du registre des amortissements"
description: "Dans les versions précédentes, il y a deux concepts d&quot;évaluation pour les immobilisations - modèles de valeur et les registres des amortissements. Dans Microsoft Dynamics 365 for Operations version 1611, la fonctionnalité de modèle de valeur et la fonctionnalité du registre des amortissements ont été fusionnées en un concept unique appelé registre. Cette rubrique fournit des éléments à prendre en compte pour la mise à niveau."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer
ms.search.scope: Operations, Core
ms.custom: 221624
ms.assetid: cf434099-36f9-4b0f-a7c8-bed091e34f39
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: bec019d218d80ba059d5a1c232072f46b1ae3ee2
ms.openlocfilehash: d29cb7bc5acc29be93332b4211adebc4486a7a25
ms.lasthandoff: 03/31/2017


---

# <a name="depreciation-book-upgrade-overview"></a>Vue d'ensemble de mise à niveau du registre des amortissements

Dans les versions précédentes, il y a deux concepts d'évaluation pour les immobilisations - modèles de valeur et les registres des amortissements. Dans Microsoft Dynamics 365 for Operations version 1611, la fonctionnalité de modèle de valeur et la fonctionnalité du registre des amortissements ont été fusionnées en un concept unique appelé registre. Cette rubrique fournit des éléments à prendre en compte pour la mise à niveau. 

La procédure de mise à niveau déplacera votre paramétrage actuel et toutes les transactions existantes dans la structure du nouveau registre. Les modèles de valeur restent telles qu'elles sont, comme registre qui valide dans la comptabilité. Les registres d'amortissements seront déplacés vers un registre dont l'option **Valider dans la comptabilité** est définie sur **Non**. Les noms des journaux du registre des amortissements seront transférés vers un nom de journal de comptabilité avec la couche de validation définie ** aucun **. Les transactions du registre des amortissements sont déplacées aux transactions d'immobilisation. 

Avant d'exécuter la mise à niveau des données, vous devez comprendre les deux options disponibles pour mettre à niveau des lignes du journal du registre des amortissements vers les N° de documents de transaction, et la souche de numéros qui sera utilisée pour la souche de N° documents. 

Option 1 :  **Souche de numéros définie par le système** - Il s'agit de l'option par défaut pour optimiser les performances de mise à niveau. La mise à niveau n'utilise pas la structure de souches de numéros, mais à la place répartit les N° de documents avec une approche basée sur les jeux. Après la mise à niveau, la nouvelle souche de numéros est créée avec ** numéro suivant défini ** correctement selon les transactions mises à niveau. Par défaut, la souche de numéros est utilisée dans le format de FADBUpgr\#\#\#\#\#\#\#\#\#. Il existe certains paramètres disponibles à vous permet d'ajuster le format en utilisant cette approche :

-   ** Code souche de N° ** – Code pour identifier la souche de numéros. Ce code souche de numéros ne peut pas exister car il sera créé par la mise à niveau.
    -   Nom constant : **NumberSequenceDefaultCode**
    -   Valeur par défaut : « FADBUpgr »
-   **Préfixe** – Valeur de chaîne constante à utiliser comme préfixe pour les N° document.
    -   Nom constant : **NumberSequenceDefaultParameterPrefix**
    -   Valeur par défaut : « FADBUpgr »
-   **Longueur alphanumérique** – Longueur du segment alphanumérique de la souche de numéros.
    -   Nom constant : ** NumberSequenceDefaultParameterAlpanumericLength **
    -   Valeur par défaut : 9
-   **Numéro de début** - Premier numéro à être utilisé dans la souche de numéros.
    -   Nom constant : ** NumberSequenceDefaultParameterStartNumber **
    -   Valeur par défaut : 1

Option 2 : ** La souche de numéros définie par l'utilisateur existante ** - Cette option vous permet de définir la souche de numéros à utiliser pour la mise à niveau. Envisagez d'utiliser cette option si vous avez besoin de la configuration Avancé de souche de numéros. Pour utiliser une souche de numéros, vous devez modifier la classe ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans de mise à niveau avec les informations suivantes :

-   **Code de souche de numéros** – Code de la souche de numéros.
    -   Nom constant : ** NumberSequenceExistingCode **
    -   Valeur par défaut : Pas de valeur par défaut, elle doit être mise à jour dans le code de souche de numéros.
-   **Souche de numéros partagée** – Valeur booléenne pour identifier la portée de la souche de numéros. Utilisez « true » pour les souches de numéros partagées entre toutes les sociétés, et « false » pour une portée spécifique à une société. Lorsque l'utilisation « fausse », la souche de numéros avec le nom spécifié doit exister dans chaque société qui contient les transactions du registre des amortissements. Les souches de numéros partagées existent dans chaque partition contenant des transactions du registre des amortissements.
    -   Nom constant : ** NumberSequenceExistingIsShared **
    -   Valeur par défaut ; true

Les paramètres sont situés au début de la classe de ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans. 

* Spécifiez une approche préférable d'allocation* 
de documents * rectifiez, si vous souhaitez utiliser un code* existant 
de souche de numéros * incorrect, si vous souhaitez utiliser la souche de numéros définie par le système sur (par défaut) * const NumberSequenceUseExistingCode booléen = Faux ;  

* Si vous utilisez la méthode définie par le système sur des souches de numéros, spécifiez les paramètres pour le numéro sequence.*
* une souche de numéros est créée avec ces parameters.* streptocoque NumberSequenceDefaultCode de const = « FADBUpgr » ; streptocoque NumberSequenceDefaultParameterPrefix de const = « FADBUpgr » ; const international NumberSequenceDefaultParameterAlpanumericLength = 9 ; const international NumberSequenceDefaultParameterStartNumber = 1 ;   

* Si vous utilisez l'approche existante de souche de numéros, spécifiez la souche de numéros existante code.* 
* la répartition de document disparaîtra la ligne-par- ligne pour le numéro sequences.* existant streptocoque NumberSequenceExistingCode de const = '' ; * Spécifiez celle du code* existant 
de souche de numéros * rectifiez, si la souche de numéros spécifiée est shared* 
* incorrect, si la souche de numéros spécifiée est per-company* 
* la souche de numéros définie par le système sur par valeur par défaut est utilisée si un code souche de numéros à celle spécifiée n'est pas found.* const boolean NumberSequenceExistingIsShared = true; 

Permet de recréer le projet contenant la classe une fois les constantes suivantes modifiées. 

Lorsque vous utilisez l'approche générée par le système de souches de numéros (option 1), la mise à niveau utilise le traitement positionnement- basé pour répartir les N° document spécifié dans les paramètres de script de mise à niveau. Il crée également une souche de numéros avec les paramètres spécifiés après la répartition. 

Lorsque vous utilisez l'approche de souches de numéros définie par l'utilisateur existante (option 2), la mise à niveau des données vérifie si la souche de numéros avec la portée spécifiée existe dans la base de données pour chaque partition et société avec des transactions du registre des amortissements. S'il existe, la mise à niveau utilise la ligne-par- ligne de traitement pour répartir les N° document spécifié par la souche de numéros à l'aide de le cadre de souche de numéros. Si la souche de numéros n'existe pas avec la portée spécifié, la mise à niveau utilise l'approche de souche de numéros définie par le système sur par valeur par défaut pour répartir les n° document, et crée une nouvelle souche de numéros avec les paramètres par défaut spécifiés après la répartition.

Quelle que soit l'approche, le script de mise à niveau des données utilise également la souche de numéros pour le champ **Souche de documents** sur les nouveaux noms de journaux comptables créés pour les anciens noms des journaux du registre des amortissements.


