---
title: Définir des dimensions financières
description: Cette procédure montre comment ajouter une dimension financière basée sur une entité et une dimension financière personnalisée.
author: aprilolson
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails,  DimensionAttributeTableExtensionActivate, DimensionValueDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10a991938f68c0ade19999e48a02f032c92a6779
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716941"
---
# <a name="define-financial-dimensions"></a>Définir des dimensions financières

[!include [banner](../../includes/banner.md)]

Cette procédure montre comment ajouter une dimension financière basée sur une entité et une dimension financière personnalisée. La société fictive USMF sert d’exemple dans ce guide.

## <a name="create-an-entity-backed-financial-dimension"></a>Créer une dimension financière soutenue par une entité
1. Accédez au **volet Navigation > Modules > Comptabilité > Plan de comptes > Dimensions > Dimensions financières**.
2. Cliquez sur **Nouveau**.
3. Dans le champ du **formulaire Valeur utilisateur**, sélectionnez une entité définie par le système sur laquelle baser la dimension financière. 
4. Dans le champ **Nom de la dimension**, entrez une valeur pour décrire la dimension financière. Le nom peut être différent de celui de l’entité définie par le système mais ne peut pas contenir d’espaces ou de caractères spéciaux.
5. Cliquez sur **Activer**. L’activation de la dimension financière met à jour la table avec le nom de dimension financière et supprime les dimensions supprimées. Vous pouvez entrer des valeurs de dimension avant d’activer une dimension financière, mais une dimension financière ne peut pas être utilisée tant qu’elle n’est pas activée.  
6. Cliquez sur **Fermer** dans le message d’activation.
7. Cliquez sur **Activer**. L’activation de la dimension peut être programmée pour être exécutée par lots à une date et heure spécifiques.  
8. Dans le **volet Actions**, cliquez sur **Valeurs de dimension**. Certaines valeurs de dimension sont spécifiques à la société. Vous pouvez vérifier si elles sont spécifiques à la société en regardant si le nom de la société apparaît dans la liste des valeurs de dimension.  

## <a name="create-a-custom-financial-dimension"></a>Créez une dimension financière personnalisée.
1. Cliquez sur **Nouveau**.
2. Dans le champ **Utiliser les valeurs de**, sélectionnez **Dimension personnalisée**.
3. Dans le champ **Nom de la dimension**, entrez une valeur pour décrire la dimension financière.
    - Le nom ne peut pas contenir d’espaces ou de caractères spéciaux.  
    - Vous pouvez également spécifier un compte pour limiter la quantité et le type d’informations que vous pouvez entrer pour les valeurs de dimension.   
    - Vous pouvez entrer des caractères qui restent identiques pour chaque valeur de dimension, telles que des lettres ou un trait d’union. Vous pouvez également entrer des signes dièse (#) et des esperluettes (&) comme espaces réservés pour les lettres et des chiffres qui changent chaque fois qu’une valeur de dimension est créée. Utilisez un symbole dièse (#) comme espace réservé pour un nombre et une esperluette (&) comme espace réservé pour une lettre.  Exemple : pour limiter la valeur de dimension aux lettres CC et trois chiffres, entrez CC-### comme un masque de format.  
4. Cliquez sur **Activer**. L’activation de la dimension financière met à jour la table avec le nom de dimension financière et supprime les dimensions supprimées. Vous pouvez entrer des valeurs de dimension avant d’activer une dimension financière, mais une dimension financière ne peut pas être utilisée tant qu’elle n’est pas activée.     
5. Cliquez sur **Activer**. L’activation de la dimension peut être programmée pour être exécutée par lots à une date et heure spécifiques.      
6. Dans le **volet Actions**, cliquez sur **Valeurs de dimension**.
7. Cliquez sur **Nouveau**.
8. Dans le champ **Valeur de la dimension**, entrez un nom pour décrire votre valeur de la dimension financière.
9. Dans le champ **Description**, entrez une description qui décrit votre valeur de la dimension financière.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
