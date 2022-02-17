---
title: Créer des régimes de rémunération variable
description: Cette rubrique décrit les composants qui doivent être définis avant d’utiliser une rémunération variable et d’inscrire des employés à un régime de rémunération variable.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HCMCompEligibility, HcmJobFunction, HcmWorker, HRMCompPerfPlan, HcmCompensationWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 16011
ms.assetid: fc3a394e-9ac6-4f8c-9162-dc16ec22720f
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 18347527517d6d051213fbe13caca54ed9214111
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066848"
---
# <a name="create-variable-compensation-plans"></a>Créer un régime de rémunération variable


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

La rémunération variable compose le salaire irrégulier des employés, comme les primes ou des primes en actions. Cette rubrique explique comment configurer les composants nécessaires pour la rémunération variable et inscrire des employés à un régime de rémunération variable.

Le calcul des montants de rémunération variable pour vos employés peut être basé sur plusieurs facteurs, tels que les performances de l’employé, son niveau de rémunération, et les performances du département.

## <a name="variable-compensation-components"></a>Composants de la rémunération variable
### <a name="create-compensation-types"></a>Créer des types de rémunération

Les **types de rémunération variable** sont des composants obligatoires. Les **Types de rémunération variable** permettent de décrire les types de rémunération variable que votre organisation attribue. Ils vous permettent également d’indiquer si la rémunération sera en espèces ou dans une forme non monétaire, par exemple en actions.

### <a name="describe-vesting-rules"></a>Décrire les règles d’acquisition

Le cas échéant, les sociétés peuvent paramétrer des **Règles d’acquisition**. Les **Règles d’acquisition** décrivent comment la prime variable doit être affectée au fil du temps. Par exemple, une règle d’acquisition peut déclarer que l’employé recevra 25 % de sa prime totale chaque année pour les quatre années à venir. Les règles d’acquisition sont uniquement à titre d’information.

## <a name="variable-compensation-plans"></a>Régimes de rémunération variable
Le **régime de rémunération variable** contient les règles, les modes de calcul, et les valeurs par défaut pour le calcul de la rémunération variable des employés inscrits. Lorsque vous créez un régime de rémunération variable, vous devez définir le type de rémunération variable. Le type de rémunération variable détermine si le système calcule un montant en devise ou un nombre d’unités pour la prime. Vous devez également définir le mode de calcul :

-   **Moment donné** – Le calcul de la prime variable est basé sur la rémunération fixe que l’employé a reçue à une date spécifique. Cette date est spécifiée sur l’événement de processus lorsque de nouveaux montants de rémunération sont traités.
-   **Composite** – Un montant de prime est calculé pour chaque taux de salaire de rémunération fixe que l’employé a reçu entre la date de début de cycle et la date de fin de cycle sur l’événement de processus. Les taux sont ensuite additionnés pour déterminer la prime finale. Par exemple, au cours du cycle, un employé est transféré vers un autre poste dont le taux de salaire est différent. Dans ce cas, la prime variable est ajustée selon la durée pendant laquelle l’employé a eu chaque taux de salaire.

Le montant de la prime variable peut être basé soit sur un pourcentage de la rémunération de base de l’employé, soit sur un nombre d’unités défini.

-   Sélectionnez l’option **Pourcentage de base** pour entrer le pourcentage par défaut, puis spécifiez si la base doit être le taux de salaire fixe de l’employé ou le point de contrôle du niveau de rémunération de l’employé. Le niveau de rémunération est défini sur la tâche de l’employé. Un des points de référence de la structure de rémunération peut être défini comme point de contrôle sur le régime de rémunération fixe. Le système utilise le niveau de rémunération de la tâche de l’employé et le compare au point de contrôle répertorié sur le régime de rémunération fixe de l’employé pour rechercher le montant du point de contrôle pour le niveau de rémunération de l’employé. Le montant du point de contrôle est ensuite utilisé à la place du taux de salaire fixe de l’employé comme base pour la prime.
-   Sélectionnez l’option **Nombre d’unités** pour entrer un nombre d’unités par défaut, la valeur de chaque unité et la devise de la valeur unitaire si le régime de rémunération concerne une prime non monétaire (par exemple, 200 unités d’actions qui correspondent à 40 EUR), ou seulement le nombre d’unités si le régime de rémunération concerne une prime en espèces. Pour une prime en espèces, l’employé recevra le nombre d’unités spécifié de la devise utilisée pour le régime de rémunération fixe (par exemple, 500 unités de 1 EUR). Le contrôle de la relation de 1 à 1 peut être utilisé pour indiquer s’il existe une mise en correspondance linéaire directe entre le nombre d’unités et la valeur unitaire. Lorsque vous créez un régime de rémunération variable pour un régime basé sur des espèces en utilisant le nombre d’unités, cette option est automatiquement verrouillée sur **Oui**, et la valeur unitaire est **1,0000**.

Le paramètre **Règle d’embauche** spécifie si tous les employés doivent recevoir la même augmentation, indépendamment de la date à laquelle ils ont été engagés (**Règle d’embauche** = **Aucune**), ou si les employés doivent recevoir un pourcentage de la prime, selon la durée pendant laquelle ils ont été employés au cours du cycle (**Règle d’embauche** = **Pourcentage**). 

**Valeur** ajuste la prime d’un employé, selon les performances du département de l’employé. Les mesures de performance peuvent être définies pour chaque département dans la page **Départements**, sous **Écrans associés** &gt; **Rémunération** &gt; **Performances**. La prime que les employés de ce département reçoivent dépend de la valeur du champ **Pourcentage de l’objectif atteint**, qui indique les performances du département :

-   Si les performances du département sont de 100 %, la prime pour les employés de ce département est factorisée par le pourcentage défini dans le champ **Paiement à 100 %**.
-   Si les performances du département sont supérieures à 100 %, le système ajoute le pourcentage défini dans le champ **Pour 1 % au-dessus de l’objectif** au pourcentage défini dans le champ **Paiement à 100 %** jusqu’à ce que la valeur définie dans le champ **Paiement maximal autorisé** soit atteinte.
-   Si les performances du département sont inférieures à 100 %, le système soustrait le pourcentage défini dans le champ **Pour 1 % en dessous de l’objectif** du pourcentage défini dans le champ **Paiement à 100 %** jusqu’à ce que la valeur définie dans le champ **Paiement minimal autorisé** soit atteinte.

Vous pouvez définir des **Niveaux de tolérance** sur les pourcentages de seuil, afin qu’un message d’avertissement apparaisse si le chiffre fait dépasser le pourcentage du pourcentage de seuil. 

Par défaut, le département qui est défini sur le poste de l’employé est utilisé pour les primes des employés. Toutefois, la prime pour certains employés peut dépendre des performances de plusieurs départements. Dans ce cas, les divers départements et le pourcentage de prime alloué aux performances de chaque département peuvent être définis dans l’enregistrement de la rémunération variable de l’employé. Pour plus d’informations, voir la section « Inscription à la rémunération variable » ci-après. 

Le chiffre n’est utilisé que si **Paiement en fonction des résultats** est sélectionné lorsque le processus de rémunération est exécuté. 

L’onglet **Remplacements de niveaux** permet de remplacer le pourcentage par défaut ou le nombre d’unités de la prime, en fonction du niveau de rémunération de l’employé. Si **Activer les remplacements pour les niveaux** est défini sur **Oui** pour les employés inscrits dans le régime de rémunération variable, le système prend le niveau de la tâche d’un employé, puis le recherche dans le tableau des remplacements de niveaux pour déterminer le pourcentage ou le nombre d’unités pour ce niveau. Si le niveau est introuvable dans le tableau des remplacements de niveaux, le pourcentage par défaut ou le nombre d’unités de l’onglet **Général** est utilisé. Le pourcentage et le nombre d’unités peuvent également être remplacés sur l’inscription de l’employé dans le régime de rémunération variable.

## <a name="variable-compensation-enrollment"></a>Inscription à la rémunération variable
### <a name="determine-who-is-eligible-for-the-plan"></a>Déterminez qui peut prétendre au régime

Quand vous êtes prêt à inscrire des employés dans un régime de rémunération variable, la première étape est de déterminer qui peut prétendre à la rémunération spécifiée dans le régime. Vous ne pouvez affecter le régime à aucun employé tant que vous n’avez pas déterminé l’admissibilité. Pour paramétrer l’admissibilité, ouvrez la page **Règles d’admissibilité** pour créer une règle d’admissibilité pour votre régime, puis définissez les critères qu’un employé doit remplir pour pouvoir prétendre au régime de rémunération. Vous pouvez limiter l’admissibilité par département, syndicat, région de rémunération (emplacement), tâche, fonction, type de tâche et/ou niveau de rémunération. Les employés peuvent être inscrits dans un régime de rémunération uniquement s’ils répondent à **tous** les critères définis sur la règle d’admissibilité. 

**Remarque :** les règles d’admissibilité déterminent l’admissibilité aux régimes de rémunération fixe et variable. Les règles d’admissibilité utilisent les champs suivants dans les enregistrements de la tâche, du poste, et de l’employé pour déterminer si un employé peut prétendre à un régime de rémunération :

- Dans la page **Tâche** :
  -   le champ **Tâche**
  -   Les champs **Fonction** et **Type de tâche** sous l’onglet **Classification des tâches**
  -   Le champ **Niveau** sous l’onglet **Rémunération**
- Dans la page **Postes** : les champs **Département** et **Région de rémunération**
- Dans la page <strong>Employés</strong> : les informations sur les syndicats associées à l’employé sous <strong>Informations personnelles</strong> &gt; <strong>Syndicats</strong> dans l’onglet *<strong><em>Collaborateur</em></strong>*

### <a name="enable-enrollment-for-the-variable-compensation-plan"></a>Activer l’inscription au régime de rémunération variable

Dans la page **Régimes de rémunération variable**, définissez l’option **Activer l’inscription** sur **Oui** pour autoriser les employés admissibles à être inscrits dans le régime.

### <a name="enroll-the-employee"></a>Inscrire l’employé

Vous pouvez maintenant inscrire des employés dans le régime de rémunération variable. Pour inscrire un employé, accéder à la page **Employés**, puis sélectionnez l’employé. Puis, dans le Volet Actions, cliquez sur **Rémunération** &gt; **Inscription au régime variable**. 

**Remarque :** **Inscription** doit être défini sur **Oui** dans le régime de rémunération variable. Le champ **Régime** affiche seulement les régimes auxquels l’employé peut prétendre selon les règles d’admissibilité paramétrées pour ces régimes. Si une règle d’admissibilité n’est pas définie pour un régime, aucun employé ne pourra y prétendre. 

Vérifiez que le champ **Date d’effet** est défini correctement. Si le régime de rémunération variable utilise le mode de calcul **Composite**, la date d’effet de l’inscription peut être prise en considération lors du calcul de la prime de l’employé. 

Vous pouvez utiliser l’onglet **Remplacements** pour remplacer des valeurs spécifiques pour l’employé. Par exemple, si **Règle d’embauche** est défini sur **Pourcentage** dans le régime, et si une date différente d’embauche doit être utilisée lors du calcul du pourcentage d’embauche de l’employé, vous pouvez définir la date d’embauche dans le champ **Date de la règle d’embauche**. Vous pouvez également remplacer la valeur **Pourcentage de prime** ou la valeur **Nombre d’unités** d’un employé spécifique, selon les paramètres du régime. Ces valeurs sont factorisées par la règle d’embauche, les facteurs de performances et d’autres paramètres du régime. 

Les **Remplacements organisationnels** permettent de baser la prime d’un employé sur les performances d’un ou plusieurs départements. Le pourcentage qui est réparti entre les départements doit se monter à un total de 100 %. Les performances individuelles d’un employé sont également prises en compte. Ces paramètres sont utilisés uniquement si **Paiement en fonction des résultats** est sélectionné lorsque le processus de rémunération est exécuté.





[!INCLUDE[footer-include](../includes/footer-banner.md)]
