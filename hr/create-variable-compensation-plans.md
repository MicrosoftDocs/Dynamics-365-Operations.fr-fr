---
title: "Créer un régime de rémunération variable"
description: "La rémunération variable compose le salaire irrégulier des employés, comme les primes ou des primes en actions. Cette rubrique décrit les composants qui doivent être définis avant d&quot;utiliser la rémunération variable et inscrire un employé à un régime de rémunération variable."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HCMCompEligibility, HcmJobFunction, HcmWorker, HRMCompPerfPlan
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16011
ms.assetid: fc3a394e-9ac6-4f8c-9162-dc16ec22720f
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9397e84f03ee5b340fa2aa0a64e582fc0078526e
ms.openlocfilehash: be156afa73de731e54985485b617bcbae883db3a
ms.lasthandoff: 03/31/2017


---

# <a name="create-variable-compensation-plans"></a>Créer un régime de rémunération variable

La rémunération variable compose le salaire irrégulier des employés, comme les primes ou des primes en actions. Cet article décrit les composants qui doivent être définis avant d'utiliser une rémunération variable et inscrire des employés à un régime de rémunération variable.

Le calcul des montants de rémunération variable pour vos employés peut être basé sur plusieurs facteurs, tels que les performances de l'employé, son niveau de rémunération, et les performances du département.

## <a name="variable-compensation-components"></a>Composants de la rémunération variable
### <a name="create-compensation-types"></a>Créer des types de rémunération

Les **types de rémunération variable **sont des composants obligatoires. Les types de rémunération variable permettent de décrire les types de rémunération variable que votre organisation attribue. Ils vous permettent également d'indiquer si la rémunération sera en espèces ou dans une forme non monétaire, par exemple en actions.

### <a name="describe-vesting-rules"></a>Décrire les règles d'acquisition

Le cas échéant, les sociétés peuvent paramétrer des **règles d'acquisition**. Règles les règles décrivent comment la prime variable doit être affectée au fil du temps. Par exemple, une règle d'acquisition peut état que l'employé reçoit 25 % de la prime totale chaque année pour les quatre ans à venir. Règles les règles sont informationnelles uniquement.

## <a name="variable-compensation-plans"></a>Régimes de rémunération variable
Le **régime de rémunération variable** contient les règles, les modes de calcul, et les valeurs par défaut pour le calcul de la rémunération variable des employés inscrits. Lorsque vous créez un régime de rémunération variable, vous devez définir le type de rémunération variable. Type de rémunération variable déterminent si le système calcule un montant en devise ou un nombre d'unités comme prime. Vous devez également définir le mode de calcul :

-   ** La durée ** – Le calcul de la prime variable est basée sur la rémunération fixe que l'employé a obtenue une date spécifique. Cette date est spécifiée sur l'événement des traitements de données lorsque de nouveaux montants de rémunération sont traités.
-   **Composite** – Un montant de prime est calculé pour chaque taux de salaire de rémunération fixe que l'employé a reçu entre la date de début de cycle et la date de fin de cycle sur l'événement de processus. Les taux sont ensuite ajoutés simultanément pour déterminer la prime finale. Par exemple, au cours de le cycle, un employé transféré vers un autre poste qui a un taux de salaire différent. Dans ce cas, la prime variable est ajustée selon la durée pendant laquelle l'employé a eu chaque taux de salaire.

Le montant de la prime variable peut être basé soit sur un pourcentage de la rémunération de base de l'employé, soit sur un nombre d'unités défini.

-   Sélectionnez l'option **Pourcentage de base** pour entrer le pourcentage par défaut, puis spécifiez si la base doit être le taux de salaire fixe de l'employé ou le point de contrôle du niveau de rémunération de l'employé. Le niveau de rémunération est défini sur la tâche de l'employé. Un des points de référence de la structure de rémunération peut être défini comme point de contrôle dans le régime de rémunération fixe. Le système utilise le niveau de rémunération de tâche et la référence croisée de l'employé il au point de contrôle répertorié dans le régime de rémunération fixe de l'employé de trouver le montant du point de contrôle pour le niveau de rémunération de l'employé. Montant de point de contrôle est ensuite utilisé à la place du taux de salaire fixe de l'employé comme base pour la prime.
-   Sélectionnez l'option** Nombre d'unités** pour entrer un nombre d'unités par défaut, la valeur de chaque unité et la devise de la valeur unitaire si le régime de rémunération concerne une prime non monétaire (par exemple, 200 unités d'actions qui correspondent à 40 EUR), ou seulement le nombre d'unités si le régime de rémunération concerne une prime en espèces. Pour une prime en espèces, il reçoit le nombre spécifié d'unités de la devise utilisée pour son régime de rémunération fixe (par exemple, 500 unités de 1 USD). Le contrôle linéaire de relation peut être utilisé pour indiquer s'il existe une mise en correspondance linéaire directe entre le nombre d'unités et la valeur unitaire. Lorsque vous créez un régime de rémunération variable pour un plan disponibilités- basé en utilisant le nombre d'unités, cette option est automatiquement verrouillée ** Oui **, et la valeur unitaire est ** 1,0000 **.

** Règle d'embauche ** le paramètre permet de spécifier si tous les employés doivent recevoir la même augmentation, indépendamment de la date à laquelle ils ont été engagés (** règle d'embauche ** = ** aucun **), ou si les employés doivent recevoir un pourcentage de la prime basé sur la longueur de son emploi au cours de le cycle (** règle d'embauche ** = ** pourcentage **). 

** Levier ** vous permet d'adapter la prime d'un employé, selon les performances du département de l'employé. Les mesures de performances peuvent être définies pour chaque département dans ** des départements ** la page, sous ** les écrans apparentés ** &gt; ** rémunération ** &gt; ** performances **. La prime que les employés de ce département reçoivent dépend de la valeur ** pourcentage de objectif atteint ** du champ, qui indique les performances du département :

-   Si les performances du département sont de 100 %, la prime pour les employés de ce département est factorisée par le pourcentage défini dans le champ** Paiement à 100 %**.
-   Si les performances du département sont supérieures à 100 %, le système ajoute le pourcentage défini dans le champ **Pour 1 % au-dessus de l'objectif** au pourcentage défini dans le champ **Paiement à 100 %** jusqu'à ce que la valeur définie dans le champ **Paiement maximal autorisé** soit atteinte.
-   Si les performances du département sont inférieures à 100 %, le système soustrait le pourcentage défini dans le champ **Pour 1 % en dessous de l'objectif** du pourcentage défini dans le champ **Paiement à 100 %** jusqu'à ce que la valeur définie dans le champ **Paiement minimal autorisé** soit atteinte.

Vous pouvez définir des** niveaux de tolérance** sur les pourcentages de seuil, afin qu'un message d'avertissement apparaisse si le chiffre fait dépasser le pourcentage du pourcentage de seuil. 

Par défaut, le système recherche le département qui est défini sur le poste de l'employé. Toutefois, la prime pour certains employés peut dépendre de les performances des plusieurs départements. Dans ce cas, les divers départements et le pourcentage de la prime répartie sur les performances de chaque département peuvent être configurés pour l'inscription à la rémunération variable de l'employé. Pour plus d'informations, voir la section « d'inscription de rémunération variable » ci-après. 

Le chiffre n'est utilisé que si **Paiement en fonction des résultats** est sélectionné lorsque le processus de rémunération est exécuté. 

** Niveau de niveaux ** l'onglet permet de remplacer le pourcentage de prime ou le numéro par défaut d'unités, selon le niveau de rémunération de l'employé. Si ** activez les remplacements de niveaux ** est défini ** Oui ** pour des employés inscrits dans le régime de rémunération variable, le système prend le niveau de la tâche d'un employé, puis le recherche dans la table des priorités des niveaux pour déterminer le pourcentage ou le nombre d'unités pour ce niveau. Si le niveau est introuvable dans la table de niveau de priorité, le pourcentage ou le numéro par défaut d'unités ** général ** de l'onglet est utilisé. Le pourcentage et le nombre d'unités peuvent également être remplacés dans l'inscription de l'employé au régime de rémunération variable.

## <a name="variable-compensation-enrollment"></a>Inscription à la rémunération variable
### <a name="determine-who-is-eligible-for-the-plan"></a>Déterminez qui peut prétendre au régime

Quand vous êtes prêt à inscrire des employés dans un régime de rémunération variable, la première étape est de déterminer qui peut prétendre à la rémunération spécifiée dans le régime. Vous ne pouvez affecter le régime à aucun employé tant que vous n'avez pas déterminé l'admissibilité. Pour paramétrer l'admissibilité, ouvrez la page **Règles d'admissibilité** pour créer une règle d'admissibilité pour votre régime, puis définissez les critères qu'un employé doit remplir pour pouvoir prétendre au régime de rémunération. Vous pouvez limiter l'admissibilité par département, syndicat, région de rémunération (emplacement), tâche, fonction, type de tâche et/ou niveau de rémunération. Les employés peuvent être inscrits dans un régime de rémunération uniquement s'ils répondent à **tous** les critères définis sur la règle d'admissibilité. 

**Remarque :** les règles d'admissibilité déterminent l'admissibilité aux régimes de rémunération fixe et variable. Les règles d'admissibilité utilisent les champs suivants dans les enregistrements de la tâche, du poste, et de l'employé pour déterminer si un employé peut prétendre à un régime de rémunération :

-   Dans la page **Tâche** :
    -   le champ **Tâche**
    -   Les champs **Fonction** et **Type de tâche** sous l'onglet **Classification des tâches**
    -   Le champ **Niveau** sous l'onglet **Rémunération**
-   Dans la page **Postes** : les champs **Département** et **Région de rémunération**
-   Sous ** employés ** la page : Les informations sur les syndicats associées à des syndicats d'employé sous ** &gt; les informations personnelles ** ** ** sous l'onglet de **** de travailleur de ****

### <a name="enable-enrollment-for-the-variable-compensation-plan"></a>Activer l'inscription au régime de rémunération variable

Dans la page **Régimes de rémunération variable**, définissez l'option **Activer l'inscription** sur **Oui** pour autoriser les employés admissibles à être inscrits dans le régime.

### <a name="enroll-the-employee"></a>Inscrire l'employé

Vous pouvez maintenant inscrire des employés dans le régime de rémunération variable. Pour inscrire un employé, accéder à la page **Employés**, puis sélectionnez l'employé. Puis, dans le volet Actions, cliquez sur ** rémunération ** &gt; ** inscription variable de plan **. 

**Remarque :** **Inscription** doit être défini sur **Oui** dans le régime de rémunération variable. ** Plan ** le champ affiche uniquement les régimes auxquels l'employé est éligibles pour, selon les règles d'admissibilité définies pour ces plans. Si une règle d'admissibilité n'est pas définie pour un plan, aucun employé n'est éligible pour le régime. 

Assurez-vous que ** date d'effet ** le champ est défini correctement. Si le régime de rémunération variable utilise ** composé ** le mode de calcul, la date d'effet de l'inscription peut être prise en compte dans le calcul de la prime de l'employé. 

Vous pouvez utiliser ** des remplacements ** l'onglet pour remplacer les valeurs spécifiques pour l'employé. Par exemple, si ** règle d'embauche ** est défini ** pourcentage ** sur le plan, et une autre date d'embauche doit être utilisé lors de le calcul du pourcentage d'embauche de l'employé, vous pouvez définir la date d'embauche dans ** date de la règle d'embauche ** le champ. Vous pouvez également remplacer ** pourcentage de prime ** la valeur ou ** nombre d'unités ** la valeur pour un employé spécifique, en fonction de les paramètres du plan. Ces valeurs sont toujours factorisées par la règle d'embauche, les facteurs de performances, et d'autres paramètres du plan. 

** Les remplacements organisation ** sont utilisés pour baser la prime d'un employé sur les performances d'un ou plusieurs départements. Pourcentage qui est réparti entre départements doivent totaliser 100 %. La performances individuelles de l'employé est également considérée comme. Ces paramètres sont utilisés uniquement si ** salaire pour les performances ** est sélectionné lorsque le processus de rémunération est exécuté.

<a name="see-also"></a>Voir également :
--------

[Régimes de rémunération](compensation-plans.md)


