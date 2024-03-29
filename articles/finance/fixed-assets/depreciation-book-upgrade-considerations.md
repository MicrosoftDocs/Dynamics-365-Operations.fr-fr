---
title: Vue d’ensemble de la mise à niveau du registre des amortissements
description: Cet article décrit la fonctionnalité de registre actuelle dans Immobilisations. Cette fonctionnalité est basée sur la fonctionnalité de modèle de valeur qui était disponible dans des versions précédentes, mais inclut également toutes les fonctionnalités fournies précédemment uniquement dans les registres des amortissements.
author: moaamer
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: kfend
ms.custom:
- "221624"
- intro-internal
ms.assetid: cf434099-36f9-4b0f-a7c8-bed091e34f39
ms.search.region: global
ms.author: moaamer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 784ec32ae886ef7ea9342b085f893eeeec761961
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855489"
---
# <a name="depreciation-book-upgrade-overview"></a>Vue d’ensemble de la mise à niveau du registre des amortissements

[!include [banner](../includes/banner.md)]

Cet article décrit la fonctionnalité de registre actuelle dans Immobilisations. Cette fonctionnalité est basée sur la fonctionnalité de modèle de valeur qui était disponible dans des versions précédentes, mais inclut également toutes les fonctionnalités fournies précédemment uniquement dans les registres des amortissements. La fonctionnalité de modèle de valeur et la fonctionnalité du registre des amortissements ont été fusionnées en un concept unique appelé registre. La fonctionnalité de registre vous permet d’utiliser un seul ensemble de pages, de demandes et de rapports pour tous les processus d’immobilisations de votre organisation. Cet article fournit des éléments à prendre en compte avant de procéder à la mise à niveau. 

La procédure de mise à niveau déplacera votre paramétrage actuel et toutes les transactions existantes dans la structure du nouveau registre. Les modèles de valeur restent telles qu’elles sont, comme registre qui valide dans la comptabilité. Les registres d’amortissements seront déplacés vers un registre dont l’option Valider dans la comptabilité est définie sur Non. Les noms des journaux du registre des amortissements seront transférés vers un nom de journal de comptabilité dont la couche de validation est définie sur Aucune. Les transactions du registre des amortissements seront déplacées vers les transactions d’immobilisation.

Avant d’exécuter la mise à niveau des données, vous devez comprendre les deux options disponibles pour mettre à niveau des lignes du journal du registre des amortissements vers les N° de documents de transaction, et la souche de numéros qui sera utilisée pour la souche de N° de justificatif.

Option 1 :  **Souche de numéros définie par le système** – Il s’agit de l’option par défaut pour optimiser les performances de mise à niveau. La mise à niveau n’utilise pas la structure de souches de numéros, mais à la place répartit les N° de documents avec une approche basée sur les jeux. Après la mise à niveau, la nouvelle souche de numéros est créée avec le **Jeu de numéros suivant** basé comme il se doit sur les transactions mises à niveau. Par défaut, la souche de numéros utilisée est au format FADBUpgr\#\#\#\#\#\#\#\#\#. Il existe quelques paramètres disponibles pour ajuster le format en utilisant cette approche :

-   **Code de souche de numéros** – Code pour identifier la souche de numéros. Ce code de souche de numéros ne peut pas exister, car il sera créé par la mise à niveau.
    -   Nom constant : **NumberSequenceDefaultCode**
    -   Valeur par défaut : « FADBUpgr »
-   **Préfixe** – Valeur de chaîne constante à utiliser comme préfixe pour les N° de justificatif.
    -   Nom constant : **NumberSequenceDefaultParameterPrefix**
    -   Valeur par défaut : « FADBUpgr »
-   **Longueur alphanumérique** – Longueur du segment alphanumérique de la souche de numéros.
    -   Nom constant : **NumberSequenceDefaultParameterAlpanumericLength**
    -   Valeur par défaut : 9
-   **Numéro de début** – Premier numéro à être utilisé dans la souche de numéros.
    -   Nom constant : **NumberSequenceDefaultParameterStartNumber**
    -   Valeur par défaut : 1

Option 2 : **Souche de numéros définie par l’utilisateur existante** – Cette option vous permet de définir la souche de numéros à utiliser pour la mise à niveau. Envisagez d’utiliser cette option si vous avez besoin de la configuration de souche de numéros avancée. Pour utiliser une souche de numéros, vous devez modifier la classe de mise à niveau ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans avec les informations suivantes :

-   **Code de souche de numéros** – Code de la souche de numéros.
    -   Nom constant : **NumberSequenceExistingCode**
    -   Valeur par défaut : Pas de valeur par défaut, elle doit être mise à jour dans le code de souche de numéros.
-   **Souche de numéros partagée** – Valeur booléenne pour identifier la portée de la souche de numéros. Utilisez « true » pour les souches de numéros partagées entre toutes les sociétés, et « false » pour une portée spécifique à une société. Lorsque vous utilisez « false », la souche de numéros avec le nom spécifié doit exister dans chaque société qui contient les transactions du registre des amortissements. Les souches de numéros partagées existent dans chaque partition contenant des transactions du registre des amortissements.
    -   Nom constant : **NumberSequenceExistingIsShared**
    -   Valeur par défaut ; true

Les paramètres sont situés au début de la classe ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans. 

*// Spécifiez une approche préférable pour la répartition de documents* 
 *//true, si vous souhaitez utiliser un code souche de numéros existant* 
 *//false, si vous souhaitez utiliser la souche de numéros définie par le système (par défaut)* const boolean NumberSequenceUseExistingCode = false;  

*// Si vous utilisez la méthode de souches de numéros définies par le système, spécifiez les paramètres de la souche de numéros.*
 *// Une nouvelle souche de numéros sera créée avec ces paramètres.* const str NumberSequenceDefaultCode = ’FADBUpgr’; const str NumberSequenceDefaultParameterPrefix = ’FADBUpgr’; const int NumberSequenceDefaultParameterAlpanumericLength = 9; const int NumberSequenceDefaultParameterStartNumber = 1;   

*// Si vous utilisez l’approche de souche de numéros existante, spécifiez le code de souche de numéros existant.* 
 *// La répartition de N° de justificatifs se fera ligne par ligne pour les souches de numéros existantes.* const str NumberSequenceExistingCode = ’’; *// Spécifiez la portée du code de la souche de numéros existante.* 
 *// true, si la souche de numéros spécifiée est partagée* 
 *// false, si la souche de numéros spécifiée est par société* 
 *// La souche de numéros définie par le système par défaut sera utilisée si un code de souche de numéros avec la portée spécifiée est introuvable.* const boolean NumberSequenceExistingIsShared = true; 

Permet de recréer le projet contenant la classe une fois les constantes suivantes modifiées. 

Lorsque vous utilisez l’approche de souches de numéros générée par le système (option 1), la mise à niveau utilise le traitement basé sur les jeux pour répartir les N° de justificatifs spécifiés dans les paramètres de script de mise à niveau. Elle crée également une souche de numéros avec les paramètres spécifiés après la répartition. 

Lorsque vous utilisez l’approche de souches de numéros définie par l’utilisateur existante (option 2), la mise à niveau des données vérifie si la souche de numéros avec la portée spécifiée existe dans la base de données pour chaque partition et société avec des transactions du registre des amortissements. Si tel est le cas, la mise à niveau utilise le traitement ligne par ligne pour répartir les N° de justificatifs comme spécifié par la souche de numéros à l’aide de la structure de souche de numéros. Si la souche de numéros n’existe pas avec la portée spécifiée, la mise à niveau utilise l’approche de souche de numéros définie par le système par défaut pour répartir les N° de justificatifs, et crée une souche de numéros avec les paramètres par défaut spécifiés après la répartition.

Quelle que soit l’approche, le script de mise à niveau des données utilise également la souche de numéros pour le champ **Souche de justificatifs** sur les nouveaux noms de journaux comptables créés pour les anciens noms des journaux du registre des amortissements.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
