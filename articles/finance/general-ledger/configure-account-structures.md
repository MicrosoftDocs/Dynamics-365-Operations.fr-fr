---
title: Configurer les structures de compte
description: Cette rubrique fournit des informations sur les structures de compte et les dimensions financières.
author: aprilolson
manager: AnnBe
ms.date: 06/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerEliminationRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c278cefd47b14c44c1949505404d08628cb7f52f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443242"
---
# <a name="configure-account-structures"></a>Configurer les structures de compte

[!include[banner](../includes/banner.md)]

Les structures de compte utilisent le compte principal et les dimensions financières pour créer un ensemble de règles qui déterminent l’ordre et les valeurs utilisées lors de la saisie du numéro de compte. Vous pouvez paramétrer autant de structures de compte que nécessaire pour votre entreprise. Les structures de compte sont affectées au paramétrage de la comptabilité d’une société, elles peuvent donc être partagées.

Lors de la création d’une structure de compte, le nombre maximal de segments est 11. Si vous avez besoin de plus de segments, évaluez soigneusement vos paramètres et vos besoins, car l’expérience de l’utilisateur en sera affectée. Déterminez si un segment peut être dérivé dans un scénario de génération d’états en utilisant une hiérarchie, et non lors de la saisie de données, ou en utilisant un champ défini par l’utilisateur. Par exemple, si vous souhaitez générer un état sur l’emplacement, mais vous pouvez déterminer l’emplacement par département ou centre de coût, il n’est pas nécessaire d’utiliser l’emplacement comme dimension financière. Si, après l’évaluation, vous déterminez que plus de 11 segments sont nécessaires, vous pouvez ajouter des segments supplémentaires à l’aide de règles avancées.

Les structures de compte requièrent le compte principal. Il n’est pas nécessaire que le compte principal soit le premier segment de la structure, mais il identifie la structure de compte utilisée lors de la saisie du numéro de compte. Pour cette raison, une valeur de compte principal peut uniquement exister dans une structure affectée à la comptabilité afin d’éviter tout chevauchement. Une fois que la structure de compte est identifiée, la liste des valeurs autorisées est filtrée pour guider l’utilisateur dans la sélection des valeurs de dimension valides, ce qui réduit la possibilité d’une entrée de journal incorrecte.

> [!NOTE] 
> Si vous prévoyez de budgétiser une dimension financière, elle doit faire partie d’une structure de compte. La budgétisation n’utilise pas actuellement des règles avancées.

## <a name="example"></a>Exemple
Pour illustrer une pratique recommandée de paramétrage d’une structure de compte, supposons qu’une société souhaite suivre ses comptes de bilan (100000..399999) au niveau de la dimension financière du compte et de l’unité commerciale. Pour les comptes de produit et de dépenses (400000..999999), elle suit les dimensions financières Unité commerciale, Département et Centre de coût. Si elle effectue une vente, elle peut également suivre la dimension financière Client. Avec ce scénario, il est recommandé que deux structures de compte soient affectées à la comptabilité de la société (une pour les comptes de bilan et une pour les comptes de résultat). Pour optimiser l’expérience de l’utilisateur et la validation, le client doit être une règle avancée qui est uniquement utilisée lorsqu’un compte de vente est utilisé.

**Structure du compte de bilan**

|Compte principal          | Unité commerciale    |
|----------------------|-----------|
|100000..399999 | *;” “|

**Structure du compte de résultat**

|Compte principal          | Unité commerciale    |Département          | Centre de coût    |
|----------------------|-----------|----------------------|-----------|
|400000..999999 | *;” “|*;” “|*;” “|*;” “|

**Règle avancée pour ajouter un client**

Critères : si le compte principal est compris entre 400000 et 499999, ajoutez le client. Il doit être renseigné.

|Client         |
|-----------------|
|* |

Dans cet exemple simplifié, toutes les valeurs et les vides sont autorisés, * et " " sont donc utilisés.

## <a name="segments-and-allowed-values"></a>Segments et valeurs autorisées
La section **Segments** et **Détails des valeurs autorisées** fournit une expérience sous forme de grille pour saisir les règles à suivre lors de la validation. Vous pouvez taper directement dans les cellules de la grille, l’importer depuis Excel ou utiliser la section **Détails des valeurs autorisées** pour vous guider.

La section **Détails des valeurs autorisées** vous aide à créer des critères à l’aide d’**Opérateurs** tels que commence par, compris entre, comprend, etc.

[![Autoriser des valeurs](./media/account.png)](./media/account.png) 

Les valeurs autorisées seront par défaut celles d’un journal ou d’une page d’entrée de répartition comptable s’il n’y a pas de autres valeurs possibles à sélectionner en fonction du paramétrage de la structure de compte.

Voici un exemple de **Structure de compte de résultat**.

|Compte principal          | Unité commerciale    |Département          | Centre de coût    |
|----------------------|-----------|----------------------|-----------|
|400000..999999 | 002 | 022 | 014 |

Lorsque vous saisissez dans un journal et que vous sélectionnez un compte dans la plage du compte de résultat, sélectionner l’unité commerciale « 002 » génère les valeurs 022 et 014 comme valeurs par défaut du contrôle de compte. Ce comportement se produira également avec la page de répartition comptable. 

## <a name="more-than-7-criteria-needed"></a>Plus de 7 critères requis

Si plus de 7 critères sont requis, vous pouvez continuer à les ajouter sur la ligne suivante. Vous remarquerez lors de l’utilisation de la section **Détails des valeurs autorisées** que le critère **+Ajouter nouveau** n’est plus actif après la saisie du septième critère. Cela est dû à de nombreux facteurs tels que : 
 - Largeur de colonne 
 - Mode de stockage des données 
 - Performances du contrôle **Détails des valeurs autorisées**
 - Facilité d’utilisation  
 
Pour continuer à ajouter des critères supplémentaires, cliquez sur la section **Doublon dans le segment** et **Valeurs autorisées**. Les critères sont copiés sur une nouvelle ligne. Vous pouvez ensuite effectuer votre saisie ou modifier la section **Détails des valeurs autorisées**.

## <a name="best-practices"></a>Utilisation optimale
Lors du paramétrage de vos structures de compte, certaines pratiques recommandées peuvent être suivies. Toutefois, il s’agit seulement de recommandations, une discussion holistique sur votre entreprise, votre plan de croissance et votre plan de maintenance doit être envisagée dans le cadre de cette discussion.

- Placez le compte principal en premier ou le plus proche possible de la structure de compte, afin que les utilisateurs puissent bénéficier de la meilleure expérience guidée possible lors de l’écriture de compte.

- Réutilisez les structures de compte autant que possible pour réduire la maintenance dans vos entités juridiques.

- Pour les écarts entre plusieurs entités juridiques, pensez à utiliser des règles avancées afin que les structures de compte peuvent être réutilisées.

- Lors de la définition des valeurs autorisées, utilisez les plages et les caractères génériques autant que possible. Cela vous permet non seulement de vous développer et d’effectuer des modifications sans maintenance, mais le système fonctionne de manière optimale avec cette configuration.

- Il ne suffit d’ajouter un astérisque pour chaque segment de la structure de compte et de se baser uniquement sur les règles avancées. Cela peut s’avérer difficile à gérer et entraîne généralement des erreurs pendant la maintenance, ce qui rend la validation impossible.

## <a name="account-structure-activation"></a>Activation de la structure de compte
Lorsque vous êtes satisfait de vos nouveaux paramétrages ou des modifications de la structure de compte, vous devez les activer. Si une structure de compte est affectée à une comptabilité, cette activation peut prendre du temps, car toutes les transactions non validées dans le système doivent être synchronisées avec la nouvelle structure. Les transactions validées ne sont pas affectées par les modifications de la structure de compte.

Pour plus d’informations, voir, [Planifier votre plan de comptes](plan-chart-of-accounts.md), [Dimensions financières](financial-dimensions.md) et [Entrer des combinaisons de compte et de dimensions (contrôle d’accès segmenté)](enter-account-dimension-combinations-segmented-entry-control.md).
