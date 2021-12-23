---
title: Paramétrer des modèles de valeur
description: Cette procédure indique comment créer un nouveau registre d’immobilisations et l’associer à un groupe d’immobilisations.
author: moaamer
ms.date: 12/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetGroupBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: be3b5578bd6509859c36f6a50ea9730e9ef1780e
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2021
ms.locfileid: "7890710"
---
# <a name="set-up-value-models"></a>Paramétrer des modèles de valeur

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../../includes/preview-banner.md)]

Cette procédure indique comment créer un nouveau registre d’immobilisations et l’associer à un groupe d’immobilisations.

## <a name="create-a-book"></a>Créer un registre
1. Accédez à **Immobilisations \> Configuration \> Registres**.
2. Cliquez sur **Nouveau**.
3. Entrez une valeur dans le champ **Registre**.
4. Dans le champ **Description**, entrez une valeur.
5. Définissez l’option **Calculer l’amortissement** sur **Oui**.

    Si l'option **Calculer amortissement** est défini sur **Oui**, le registre d’actifs associé sera donc inclus dans les propositions d’amortissement. Si elle est définie sur **Non**, le registre d’actifs ne sera pas automatiquement amorti.

6. Dans le champ **Profil d’amortissement**, entrez ou sélectionnez une valeur.

    * L’autre profil d’amortissement est également appelé : méthode de basculement d’amortissement. La proposition d’amortissement bascule sur ce profil lorsque l’autre profil calcule un montant d’amortissement égal ou supérieur au profil d’amortissement par défaut.
    * Le profil d’amortissement exceptionnel est utilisé pour l’amortissement supplémentaire d’un actif dans des circonstances peu courantes. Par exemple, vous pouvez utiliser cette opération pour enregistrer l’amortissement résultant d’une catastrophe naturelle.
    * Si vous sélectionnez **Créer des ajustements d’amortissement avec des amortissements de base**, les ajustements d’amortissement sont automatiquement créés lorsque la valeur de l’actif est mise à jour. Sinon, la valeur d'actif mise à jour n'affectera que les futurs calculs d'amortissement.

7. Définissez l'option **Créer des ajustements d’amortissement avec des amortissements de base** sur **Oui**.

    * Par défaut, les transactions du registre des immobilisations sont validées dans la comptabilité. Toutefois, vous pouvez aussi désactiver la validation dans la comptabilité pour le registre en définissant l'option **Valider dans la comptabilité** sur **Non**. Les registres qui ne sont pas validés dans la comptabilité sont généralement utilisés à des fins de déclaration de taxe. Cette option vous donne une flexibilité supplémentaire pour supprimer les transactions historiques du registre des actifs, car elles n’ont pas été validées dans la comptabilité.
    * Par défaut, le champ **Couche de validation** est défini sur **Couche actuelle** si le registre est validé dans la comptabilité, et sur **Aucun** s’il n’est pas validé dans la comptabilité. Mettez à jour la valeur du champ **Couche de validation** si des transactions de ce registre doivent être validées sur une couche de validation différente.

8. Option Calculer l’amortissement positif.

    * Par défaut, l’option **Calculer l’amortissement positif** est définie sur **Non**. Ce paramètre indique que l'amortissement créditera le registre d’actifs sélectionné. De plus, les options **Accepter une valeur nette comptable supérieure au prix d'acquisition** et **Accepter la valeur nette négative** sont toutes les deux définies sur **Non**, et les paramètres peuvent être modifiés indépendamment. 
    * Pour calculer l’amortissement positif, définissez l'option **Calculer l’amortissement positif** sur **Oui**. Ce paramètre indique que l'amortissement débitera le registre d’immobilisations. Quand l'option **Calculer l'amortissement positif** est définie sur **Oui**, les options **Accepter une valeur nette comptable supérieure au prix d'acquisition** et **Accepter la valeur nette négative** seront automatiquement définies sur **Oui**, et seront verrouillées. Ce verrouillage permet de garantir que l'amortissement positif ne sera appliqué qu'aux immobilisations qui ont été acquises avec une valeur comptable négative (crédit). 

10. Saisissez ou sélectionnez une valeur dans le champ **Calendrier** .

    Les registres dérivés valident simultanément les transactions sur des registres différents. Vous créez les transactions avec le registre principal et pendant la validation, une copie exacte de la transaction est validée dans le registre dérivé. Aucun recalcul n’est nécessaire avec les transactions du registre dérivé ; il ne doit donc pas être utilisé pour les transactions d’amortissement.

## <a name="associate-the-book-with-a-fixed-asset-group"></a>Associer le registre à un groupe d’immobilisations

1. Sélectionnez **Groupes d’immobilisations**.
2. Entrez ou sélectionnez une valeur dans le champ **Groupe d’immobilisations**.
3. Entrez un nombre dans le champ **Durée de vie**.

    * Les périodes d’amortissement sont calculées après la saisie de la durée de vie de l'actif.
    * La convention d’amortissement peut être définie comme requis pour les besoins fiscaux.
    * Pour les immobilisations associées à des baux, la valeur du champ **Durée de vie** sera remplacée par la moins élevée dans la durée du bail dans le registre des actifs ou de la durée de vie utile de l'actif. Si l'option **Transfert de propriété** est définie sur **Oui** pour le registre des baux, la valeur du champ **Durée de vie** sera toujours la durée de vie utile de l’actif.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
