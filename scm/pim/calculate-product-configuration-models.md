---
title: "Calculs pour le FAQ de modèles de configuration de produit"
description: "Cet article décrit les calculs des modèles de configuration de produit et décrit l&quot;utilisation des calculs avec les contraintes."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PCConstraintEditor, PCProductConfigurationModelDetails, PCRuntimeConfigurator
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19191
ms.assetid: 8993f9a1-d1c0-49f5-afd3-5e1077ded0fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3d02a15387231160f5b8a237aa11008b91ef1223
ms.openlocfilehash: 3a82fdb8532c79e33c167c43554a3de7d3061fcb
ms.lasthandoff: 03/31/2017


---

# <a name="calculations-for-product-configuration-models-faq"></a>Calculs pour le FAQ de modèles de configuration de produit

Cet article décrit les calculs des modèles de configuration de produit et décrit l'utilisation des calculs avec les contraintes.

Les calculs peuvent être utilisés pour les opérations arithmétiques ou logiques. Ils complètent les contraintes d'expression dans les modèles de configuration de produit. Vous pouvez définir des calculs sur la page **Détails du modèle de configuration de produits basée sur les contraintes**, puis établissez des expressions pour les calculs dans l'éditeur d'expressions. Pour plus d'informations, voir Créer des calculs.

## <a name="what-is-a-calculation"></a>Qu'est-ce qu'un calcul ?
Un calcul est un élément que vous pouvez utiliser dans un modèle de configuration de produits. Les calculs complètent les contraintes en vous permettant d'utiliser des nombres décimaux lorsque vous configurez un produit. En outre, les calculs disposent d'un plus grand nombre d'opérateurs que les contraintes.  

A l'instar d'une contrainte, un calcul est associé à un composant spécifique dans un modèle de configuration de produit et ne peut pas être réutilisé ni partagé par un autre composant. Une importante différence entre les calculs et les contraintes ? Les calculs sont impératifs (unidirectionnels), tandis que les contraintes sont déclaratives (bidirectionnelles). Pour plus d'informations sur les contraintes, voir [Contraintes d'expression et contraintes de table](expression-constraints-table-constraints-product-configuration-models.md).  

Un calcul se compose d'un attribut cible et d'une expression de calcul.

## <a name="what-is-a-target-attribute"></a>Qu'est-ce qu'un attribut cible ?
Un attribut cible est un attribut qui reçoit le résultat du calcul dans une expression.  

Dans l'expression suivante, l'attribut cible est une mesure de nappe :  

** Expression : ** Si\[decimalAttribute1 &lt;= decimalAttribute2,\]réel et faux  

** DecimalAttribute1 ** est la longueur de table, et ** decimalAttribute2 ** est la longueur de nappe. L'expression renvoie la valeur **True** à l'attribut cible si **decimalAttribute2** est supérieur ou égal à **decimalAttribute1**. Sinon, l'expression renvoie la valeur **False**. Par conséquent, la mesure de la nappe est acceptable si la longueur de la nappe est égale ou supérieure à celle de la table.

## <a name="what-attribute-types-can-be-set-to-target-attributes"></a>Quels types d'attributs peuvent être définis sur des attributs cible ?
Tous les types d'attributs pris en charge par le configurateur de produit peuvent être définis pour des attributs cible, à l'exception du texte sans liste fixe.

## <a name="can-the-value-of-a-target-attribute-restrict-the-values-of-the-input-attributes-in-a-calculation"></a>Une valeur pour un attribut cible peut-elle limiter les valeurs pour les attributs d'entrée dans un calcul ?
Non, la valeur pour un attribut cible ne peut pas limiter les valeurs pour les attributs d'entrée, car les calculs sont unidirectionnels. Par conséquent, la valeur de l'attribut cible est définie sur les modifications apportées à la valeur des attributs d'entrée. Toutefois, modifier la valeur de la cible n'a pas de conséquence sur les attributs d'entrée. Ce comportement diffère du comportement des contraintes. Dans les contraintes, le calcul est effectué dans les deux directions.

### <a name="example"></a>Exemple

Dans l'expression suivant, la cible pour le calcul est la durée d'un cordon de courant, et la valeur d'entrée est une couleur :  

** Expression : ** \[si == « et » Couleur, 1,5, 1,0\]  

Lorsque vous configurez l'article, la longueur du cordon de secteur est définie ** 1,5 ** si vous spécifiez ** vert ** comme la valeur de l'attribut de couleur. Si vous spécifiez une autre couleur, la longueur est **1,0**. Toutefois, les calculs étant unidirectionnels, le calcul ne définit pas la valeur de l'attribut de couleur sur **Vert** lorsque vous spécifiez une longueur de **1,5**.

## <a name="what-happens-if-a-calculation-has-a-target-attribute-of-the-integer-type-but-a-calculation-generates-a-decimal-number"></a>Que se passe-t-il si un calcul a un attribut cible de type entier, mais qu'un calcul donne un nombre décimal ?
Le résultat du calcul renvoie uniquement la partie entière du calcul. La partie décimale est supprimée et le résultat n'est pas arrondi. Par exemple, le résultat 12,70 s'affiche comme 12.

## <a name="when-do-calculations-occur"></a>Quand les calculs se produisent-ils ?
Les calculs se produisent lorsqu'une valeur a été fournie pour tous les attributs d'entrée.

## <a name="can-i-overwrite-the-value-that-is-calculated-for-the-target-attribute"></a>Est-ce que je peux remplacer la valeur calculée pour l'attribut cible ?
Vous pouvez remplacer la valeur calculée pour l'attribut cible à moins que l'attribut cible soit défini comme masqué ou en lecture seule.

## <a name="how-do-i-set-a-target-attribute-as-hidden-or-readonly"></a>Comment définir un attribut cible comme masquée ou lecture seule ?
Pour définir un attribut comme masqué ou en lecture seule, procédez comme suit :

1.  Cliquez sur ** gestion des informations sur le produit ** &gt; ** Courant ** &gt; ** modèles de configuration de produit **.
2.  Sélectionnez un modèle de configuration de produit. Dans le volet Actions, cliquez sur **Modifier**.
3.  Sur la page **Détails du modèle de configuration de produits basée sur les contraintes**, sélectionnez l'attribut à utiliser comme attribut cible.
4.  Dans l'organisateur **Attributs**, sélectionnez **Masqué** ou **Lecture seule**.

## <a name="can-a-calculation-overwrite-the-values-that-i-set"></a>Un calcul peut-il remplacer les valeurs que j'ai définies ?
N° Les valeurs que vous définissez lorsque vous configurez un produit sont les valeurs utilisées. Le calcul effectué lorsque les valeurs d'entrée d'un calcul sont modifiées ne peut pas remplacer les valeurs que vous fournissez pour un attribut spécifique.

## <a name="what-happens-if-i-remove-an-input-value-in-a-calculation"></a>Que se passe-t-il si je supprime une valeur d'entrée dans un calcul ?
Si vous supprimez une valeur d'entrée dans un calcul, la valeur de l'attribut cible est également supprimée.

## <a name="why-do-i-receive-an-error-message-that-says-that-my-model-is-in-contradiction"></a>Pourquoi un message d'erreur s'affiche pour indiquer que mon modèle est en contradiction ?
Ce message s'affiche lorsqu'un calcul comprend une erreur ou qu'une contradiction existe dans une ou plusieurs contraintes. Pour plus d'informations sur les contradictions des contraintes, voir la rubrique [Contraintes d'expression et contraintes de table](expression-constraints-table-constraints-product-configuration-models.md). Les erreurs dans les calculs peuvent, par exemple, survenir dans les situations suivantes :

-   Une valeur est divisée par zéro (0).
-   Un conflit existe entre ces deux éléments :
    -   Les valeurs disponibles pour un attribut et qui sont limitées par une contrainte.
    -   Une valeur générée par un calcul.
-   Les valeurs qui sont retournées par le calcul sortent du domaine de l'attribut. Un exemple est un ensemble \[1..10\] qui est calculé à 0.

## <a name="why-do-i-receive-an-error-message-even-though-i-successfully-validated-my-product-model"></a>Pourquoi est-ce que j'obtiens un message d'erreur alors que j'ai correctement contrôlé mon modèle de produit ?
Les calculs ne sont pas inclus dans le contrôle. Vous devez tester le modèle de configuration de produit pour rechercher les erreurs dans les calculs. Pour tester un modèle de configuration de produit, procédez comme suit :

1.  Cliquez sur ** gestion des informations sur le produit ** &gt; ** Courant ** &gt; ** modèles de configuration de produit **.
2.  Sélectionnez un modèle de configuration de produit. Dans le volet Actions, dans le groupe **Exécuter**, cliquez sur **Test**.



