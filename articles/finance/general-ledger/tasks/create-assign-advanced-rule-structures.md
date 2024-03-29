---
title: Créer et affecter des structures de règle avancées
description: Cet article explique comment créer et affecter une structure de règle avancée à une structure de compte.
author: aprilolson
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 72688642936f9428c96aebb34bf9f240dd48b46b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896317"
---
# <a name="create-and-assign-advanced-rule-structures"></a>Créer et affecter des structures de règle avancées

[!include [banner](../../includes/banner.md)]

Cet article explique comment créer et affecter une structure de règle avancée à une structure de compte. La société fictive USMF sert d’exemple dans ce guide.

## <a name="create-an-advanced-rule-structure"></a>Créer une structure de règle avancée
1. Accédez au **Volet de navigation > Modules > Comptabilité > Plan de comptes > Structures > Structures de règles avancées**.
2. Sélectionnez **Nouveau** pour ouvrir la boîte de dialogue.
3. Dans le champ **Structure de règle avancée**, entrez un nom pour décrire la structure de règle.
4. Cliquez sur **OK**.
5. Sélectionnez **Ajouter un segment**.
6. Dans la liste des segments, sélectionnez une dimension financière. Par exemple, **Magasin**.  
7. Sélectionnez **Ajouter un segment**.
8. Sélectionnez **Activer**.

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a>Appliquer une structure de règle avancée à une structure de compte
1. Accédez au **Volet de navigation > Modules > Comptabilité > Plan de comptes > Structures > Configurer les structures de compte**.
2. Dans la liste, cherchez et sélectionnez la structure de compte à laquelle vous souhaitez appliquer la règle avancée.
3. Sélectionnez **Modifier**. Vous pouvez également sélectionner **Règles avancées** ; vous êtes alors invité à passer la structure de compte en mode **Brouillon**.  
4. Sélectionnez **Règles avancées**.
5. Sélectionnez **Nouveau** pour ouvrir la boîte de dialogue.
6. Tapez une valeur dans le champ **Règle avancée**.
7. Tapez une valeur dans le champ **Nom**.
8. Sélectionnez **Créer**.
9. Sélectionnez **Ajouter de nouveaux critères**.
10. Dans le champ **Où**, sélectionnez le compte principal ou une dimension financière.
11. Dans le champ **Opérateur**, sélectionnez une option, comme **Est compris entre** et **Comprend**.
12. Tapez une valeur dans le champ **Valeur**.
13. Dans le champ **À**, tapez une valeur.
14. Sélectionnez **Ajouter** pour ouvrir la boîte de dialogue.
15. Dans la liste, cherchez la structure de règle avancée à utiliser lorsque les critères que vous avez entrés sont rencontrés.
16. Sélectionnez **Ajouter**.
17. Fermez la page.
18. Sélectionnez **Activer**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
