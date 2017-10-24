--- 
title: "Paramétrer des registres"
description: "Cette procédure indique comment créer un nouveau registre d'immobilisations et l'associer à un groupe d'immobilisations."
author: saraschi2
manager: AnnBe
ms.date: 10/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a29cae6cdcd03903359a3a468243c6ad03c7adc6
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-books"></a>Paramétrer des registres

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment créer un nouveau registre d'immobilisations et l'associer à un groupe d'immobilisations. Elle utilise le rôle de comptable et les données de démonstration de l'entité juridique USMF.


## <a name="create-a-book"></a>Créer un registre
1. Accédez à Immobilisations > Configuration > Registres.
2. Cliquez sur Nouveau.
3. Dans le champ Registre, tapez une valeur.
4. Dans le champ Description, entrez une valeur.
    * Si Calculer l'amortissement est sélectionné, le registre d'actifs associé est inclus dans les propositions d'amortissement. Si cette option n'est pas sélectionnée, le registre d'actifs n'est pas automatiquement amorti.  
5. Sélectionnez Oui dans le champ Calculer l'amortissement.
6. Dans le champ Profil d'amortissement, entrez ou sélectionnez une valeur.
    * L'autre profil d'amortissement est également appelé : méthode de basculement d'amortissement. La proposition d'amortissement bascule sur ce profil lorsque l'autre profil calcule un montant d'amortissement égal ou supérieur au profil d'amortissement par défaut.  
    * Le profil d'amortissement exceptionnel est utilisé pour l'amortissement supplémentaire d'un actif dans des circonstances peu courantes. Par exemple, vous pouvez utiliser cette opération pour enregistrer l'amortissement résultant d'une catastrophe naturelle.  
    * Si l'option Créer des ajustements d'amortissement avec des amortissements de base est sélectionnée, les ajustements d'amortissement sont automatiquement créés lorsque la valeur de l'actif est mise à jour. Si elle n'est pas activée, la valeur d'immobilisation mise à jour affecte uniquement les prochains calculs d'amortissement.  
7. Sélectionnez Oui dans le champ Créer des ajustements d'amortissement avec des amortissements de base.
    * Par défaut, les transactions du registre des immobilisations sont validées dans la comptabilité. Vous pouvez désactiver la validation dans la comptabilité pour le registre en définissant le champ Valider dans la comptabilité sur Non. Les registres qui ne sont pas validés dans la comptabilité sont généralement utilisés à des fins de déclaration de taxe. Cela vous donne une flexibilité supplémentaire pour supprimer les transactions historiques du registre des actifs, car elles n'ont pas été validées dans la comptabilité.  
    * La couche de validation est définie par défaut sur la couche actuelle si le registre est validé dans la comptabilité, et sur Aucun s'il n'est pas validé dans la comptabilité. Mettez la couche de validation à jour si des transactions de ce registre doivent être validées sur une couche de validation différente.  
8. Saisissez ou sélectionnez une valeur dans le champ Calendrier.
    * Les registres dérivés valident simultanément les transactions sur des registres différents. Vous créez les transactions avec le registre principal et pendant la validation, une copie exacte de la transaction est validée dans le registre dérivé. Aucun recalcul n'est nécessaire avec les transactions du registre dérivé ; il ne doit donc pas être utilisé pour les transactions d'amortissement.  

## <a name="associate-the-book-with-a-fixed-asset-group"></a>Associer le registre à un groupe d'immobilisations
1. Cliquez sur Groupes d'immobilisations.
2. Saisissez ou sélectionnez une valeur dans le champ Groupe d'immobilisations.
3. Entrez un nombre dans le champ Durée de vie.
    * Notez que les périodes d'amortissement sont calculées après la définition de la durée de vie.  
    * Vous pouvez définir la convention d'amortissement comme requis pour les besoins fiscaux.  


