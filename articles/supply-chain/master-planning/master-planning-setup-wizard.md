---
title: Assistant Paramétrage de planification
description: Cette rubrique décrit les différentes stratégies et les paramètres importants utilisés pour paramétrer la planification.
author: t-benebo
manager: tfehr
ms.date: 10/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-05-31
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: f2f4d115c29cc87b5202ffd372871ae76780236b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232324"
---
# <a name="master-planning-setup-wizard"></a>Assistant Paramétrage de planification

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des instructions pour l’**Assistant Paramétrage de planification**. Elle explique comment des suggestions de paramètre sont calculées et fournit également des exemples qui indiquent comment les différentes sociétés paramètrent la planification, en fonction de leurs besoins commerciaux.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3YnSB]

La vidéo [Assistant Paramétrage de planification dans Dynamics 365 Supply Chain Management](https://youtu.be/c-e6n-8rZb4) (présentée ci-dessus) est incluse dans la [liste de lecture Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible sur YouTube.


## <a name="specific-requirements-of-your-company"></a>Besoins spécifiques de votre société

La première page de l’Assistant s’enquiert des besoins spécifiques de votre société. Vos réponses à ces questions ne doivent pas être précises, mais vous devriez pouvoir fournir une estimation approximative du nombre d’articles et de commandes planifiées prévus pour l’entité juridique. Vos réponses sont utilisées pour configurer les paramètres qui s’appliquent à votre entité juridique, et pas uniquement au plan général sélectionné. Les sections suivantes décrivent les paramètres calculés et les formules utilisées.

### <a name="number-of-threads"></a>Nombre de threads

- **Si vous fabriquez certains des articles :** Nombre de threads = Nombre d’ordres prévisionnels ÷ 1 000
- **Si vous ne fabriquez pas certains des articles :** Nombre de threads = Nombre d’articles ÷ 1 000

Si le nombre de threads calculé dépasse 75 % du nombre de threads disponible, il est plafonné à 75 % du nombre de threads disponible pour chaque client. (Le nombre de threads disponibles est déterminé pour chaque client.)

Pour plus d’informations, voir [Nombre de threads](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/master-planning/master-planning-performance#number-of-threads).

### <a name="bundle-size"></a>Taille de l’offre groupée

La taille de l’offre groupée est définie sur **1**. Cette valeur est souvent la meilleure valeur, car elle permet d’améliorer les performances de la planification.

Pour plus d’informations, voir [Nombre de tâches dans l’offre groupée des tâches de l’application d’assistance](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/master-planning/master-planning-performance#number-of-tasks-in-helper-task-bundle).

### <a name="firming-bundle-size"></a>Confirmation de la taille de l’offre groupée

- **Si vous fabriquez certains des articles :** La confirmation de la taille de l’offre groupée est défini sur la valeur supérieure entre de ces deux valeurs : **10** et le calcul d’offre groupée
- **Si vous ne fabriquez pas d’articles :** La confirmation de la taille de l’offre groupée est défini sur la valeur supérieure entre de ces deux valeurs : **50** et le calcul d’offre groupée

Calcul de l’offre groupée = (Nombre d’ordres prévisionnels × Ordres prévisionnels (Plage de gestion de la confirmation ÷ Plage de gestion de la couverture) ÷ Nombre de threads) ÷ 10

### <a name="cache-size"></a>Taille du cache

La taille du cache est définie sur **Maximum**. Cette valeur est souvent la meilleure valeur, car elle permet d’améliorer les performances de la planification.

Pour plus d’informations, voir [Répartir du temps aux tâches figurant dans un regroupement de tâches](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/allocate-time-jobs-job-bundle).

### <a name="manufacturing-setup"></a>Paramétrage de la fabrication

Si vous fabriquez des articles, une page **Paramétrage de la fabrication** s’affichera plus loin dans l’Assistant.

## <a name="scope-of-the-current-plan"></a>Portée du plan actuel

Dans la page **Portée du plan actuel** de l’Assistant, vous répondez aux questions liées à la durée dans l’avenir pendant laquelle différentes exigences seront prises en compte et calculées dans la planification. Chaque question demande si vous souhaitez utiliser une fonction et comment la configurer.

Par exemple, pour la fonctionnalité de plan prévisionnel, l’Assistant demande, « Souhaitez-vous utiliser un programme prévisionnel dans la planification de sorte que les ordres prévisionnels soient suggérés pour honorer la demande prévue ? »

Les options disponibles sont les suivantes :

- **Non** – La planification ne propose pas d’ordres prévisionnels pour honorer une prévision. Sous l’onglet **Plages de gestion** de la page **Plans généraux** (**Planification \> Paramétrage \> Plans \> Plans généraux**), l’Assistant détermine l’option **Programme prévisionnel (plage de gestion)** sur **Oui** et définit le nombre de jours sur **0** (zéro). Ce paramétrage va remplacer la plage de gestion spécifiée dans le groupe de couverture. Comme le nombre de jours est défini sur **0** (zéro), la fonction n’est pas utilisée.
- **Oui, comme défini dans ce plan général** – Un champ devient disponible, dans lequel vous pouvez entrer le nombre de jours pendant lesquels la planification suggère des ordres prévisionnels pour honorer la demande prévue. L’Assistant détermine l’option **Programme prévisionnel (plage de gestion)** sur **Oui** et définit le nombre de jours sur celui entré dans le champ **Programme prévisionnel** sur l’onglet **Plages de gestion** de la page **Plans généraux**. Ce paramétrage remplacera les valeurs définies dans les groupes de couverture.
- **Oui, comme défini dans la couverture** – L’Assistant détermine l’option **Programme prévisionnel (plage de gestion)** sur **Non**. Les plages de gestion spécifiées dans le groupe de couverture permettent de spécifier la durée de planification de la prévision.

Les questions restantes dans cette page et leurs réponses suivent le même schéma :

- **Non** – L’option **Programme prévisionnel (plage de gestion)** est définie sur **Oui**, et le nombre de jours est défini sur **0** (zéro).
- **Oui, comme défini ce plan général** – L’option **Programme prévisionnel (plage de gestion)** sera définie sur **Oui**. Le nombre de jours que vous entrez sera utilisé et remplacera les valeurs définies dans les groupes de couverture.
- **Oui, comme défini dans le groupe de couverture** – L’option **Programme prévisionnel (plage de gestion)** sera définie sur **Non**.

Pour plus d’informations, voir [Planification des tâches](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="scheduling-options"></a>Options de planification

La page **Options de planification** s’affiche uniquement si vous avez répondu **Oui** à la question « Fabriquez-vous certains des articles planifiés ? » sur la première page de l’Assistant.

Votre réponse à la première question de cette page (« Devez-vous planifier des opérations divisées en tâches individuelles ? ») détermine la méthode de planification de l’onglet **Général** sur la page **Plans généraux**.

- **Oui** – La planification des tâches sera utilisée.
- **Non** – La planification des opérations sera utilisée.

Pour plus d’informations, voir [Planification des opérations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/operations-scheduling) et [Planification des tâches](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="updates-of-demand-and-supply"></a>Mises à jour de la demande et de l’approvisionnement

Les questions sur la page **Mises à jour de la demande et de l’approvisionnement** sont liés à la confirmation, aux messages d’action et aux retards.

Le paramétrage de planification est mis à jour selon vos réponses, d’après le même schéma que celui décrit dans la section précédente :

- **Non** – L’option **Plage de gestion** sur la page **Plans généraux** est définie sur **Oui**, et le nombre de jours est défini sur **0** (zéro).
- **Oui, comme défini dans ce plan général** – L’option **Plage de gestion** sera définie sur **Oui**. Le nombre de jours que vous entrez sera utilisé et remplacera les valeurs définies dans les groupes de couverture.
- **Oui, comme défini dans le groupe de couverture** – L’option **Plage de gestion** sera définie sur **Non**.

Pour les retards calculés, vos réponses aux questions dans l’Assistant mettront à jour les paramètres correspondants dans l’onglet **Retards calculés** de la page **Plans généraux**.

## <a name="summary-of-your-changes"></a>Synthèse de vos modifications

La dernière page de l’Assistant affiche les modifications recommandées selon vos réponses. Elle indique la valeur dans votre installation (**Paramétrage actuel**) et la valeur que l’Assistant recommande (**Nouvelle configuration**).

Vous pouvez également modifier les paramètres de la nouvelle configuration. Les paramètres sont séparés dans les paramètres qui s’appliquent à votre entité juridique et les paramètres qui s’appliquent qu’au plan général sélectionné. Pour afficher tous les paramètres configurés qui peuvent être modifiés à l’aide de l’Assistant, sélectionnez **Afficher tous les paramètres** en bas de la page. Vous pouvez ensuite modifier les paramètres.

Enfin, lorsque vous sélectionnez **Terminer**, la nouvelle configuration est appliquée. Si vous sélectionnez **Annuler**, aucune des modifications n’est appliquée.

## <a name="examples"></a>Exemples

Cette section décrit le paramétrage de deux sociétés fictives pour afficher la manière dont la configuration peut varier selon les besoins de chaque entreprise.

### <a name="example-1-contoso-manufacturer"></a>Exemple 1 : Fabricant Contoso

Le fabricant Contoso est une société de fabrication de haut-parleurs. Elle achète différentes matières premières et composants utilisés pour les haut-parleurs finaux auprès de différents fournisseurs. Voici certaines caractéristiques de l’approvisionnement et de la fabrication :

- Les articles finaux que la société fabrique ont une structure de nomenclature.
- Les articles et les composants finaux sont planifiés par la planification. La planification manuelle n’est pas effectuée.
- Une gamme d’opérations est définie pour la production de chaque article final.
- L’usine de fabrication produit les articles finaux. Elle a défini un nombre de fraiseuses et de foreuses utilisées pour traiter les composants. Les différents composants doivent être traités par ces machines.
- Il existe de nombreux fournisseurs. Le délai moyen pour les articles est d’une semaine. Un groupe d’articles du même fournisseur aura un délai de sept semaines.

Dans l’Assistant, les valeurs suivantes sont entrées pour le fabricant Contoso :

- **Couverture :**

    - **Question :** « Souhaitez-vous spécifier le nombre de jours de votre horizon de planification ? »
    - **Réponse :** « Oui, comme défini dans les groupes de couverture. »

    Comme le délai des articles est très différent, Contoso ne doit pas planifier tous les articles pour la même période à venir. Des groupes de couverture pour les articles sont créés. Les articles ayant un délai similaire sont affectés au même groupe de couverture. L’horizon de planification de chaque groupe de couverture (c’est-à-dire, la plage de gestion de couverture) est approximativement le délai plus une marge d’une semaine. La planification vérifie ensuite que les articles sont planifiés à l’avance, selon leur délai.

    Par conséquent, deux groupes de couverture sont créés pour cet exemple. Un groupe de couverture utilise une plage de gestion de couverture de deux semaines, et l’autre a une plage de gestion de couverture de huit semaines.

    Si **Oui, comme défini dans ce plan général** est sélectionné comme réponse, le nombre de jours entré doit dépasser le plus long délai de tous les articles. Toutefois, puisque de nombreux articles ne doivent pas être planifiés trop longtemps à l’avance, plusieurs ordres prévisionnels seront calculés mais jamais utilisés. Par conséquent, le temps d’exécution de la planification augmentera.

- **Planification :**

    - **Question :** « Devez-vous planifier des opérations divisées en tâches individuelles ? »
    - **Réponse :** « Oui. »

    La fabrication de Contoso doit planifier les tâches individuelles qui seront effectuées dans l’atelier. Par conséquent, elle utilise la planification des tâches.

- **Capacité :**

    - **Question :** « Souhaitez-vous planifier à l’aide de la capacité des ressources ? »
    - **Réponse :** « Oui, comme défini dans ce plan général. » **10 jours** est entré.

    Le nombre de foreuses et de fraiseuses est limité. La planification de la production doit prendre en considération cette limitation et organiser les tâches à temps en fonction de la capacité des ressources. Autrement dit, les tâches prévues sont replanifiées selon les limitations des ressources. La planification utilise le délai en plus de la période définie. (Les ordres de fabrication prévisionnels peuvent se chevaucher.) Comme le délai de production pour les articles est de sept jours, la capacité des ressources pour la planification sera prise en compte pendant 10 jours.

- **Séquençage :**

    - **Question :** « Souhaitez-vous séquencer les ordres prévisionnels avec les valeurs des séquences du produit ? »
    - **Réponse :** « Oui, comme défini dans les groupes de couverture. »

    Une gamme est définie pour la production de chaque article final. Par conséquent, la planification planifie les commandes à temps selon les gammes définies.

- **Éclatement :**

    - **Question :** « Souhaitez-vous planifier les commandes de tous les éléments dans une nomenclature (planifier l’article parent et tous les articles enfants) ? »
    - **Réponse :** « Oui, comme défini dans les groupes de couverture. »

    Tous les articles utilisés pour la production doivent être planifiés. Comme les articles ont des délais très différents, la planification permet d’améliorer les performances lors qu’elle utilise les groupes de couverture. Là aussi, une marge d’une semaine peut être entrée, et l’éclatement peut être effectué pour le même temps que la couverture.

### <a name="example-2-contoso-retailer"></a>Exemple 2 : Détaillant Contoso

Le détaillant Contoso est une société de distribution dans le secteur de la mode. Elle utilise la planification pour calculer quand des commandes fournisseur doivent être placées, selon ses ventes prévues. Voici certaines de ses caractéristiques :

- Le détaillant Contoso utilise une prévision de la demande pour prévoir ses ventes. Les commandes fournisseur sont organisées selon la prévision.
- Les magasins utilisent des demandes de réassort.
- Le délai entre l’entrepôt principal et chaque magasin est d’environ deux semaines pour tous les articles.

Dans l’Assistant, les valeurs suivantes sont entrées pour le détaillant Contoso :

- **Prévision de la demande :**

    - **Question :** « Souhaitez-vous utiliser un programme prévisionnel dans la planification de sorte que les ordres prévisionnels sont suggérés pour honorer la demande prévue ? »
    - **Réponse :** « Oui, comme défini dans ce plan général. »

    Contoso a inclus une prévision de la demande pour prévoir ses ventes. Par conséquent, la planification doit recommander des ordres prévisionnels pour honorer la prévision.

- **Confirmation :**

    - **Question :** « Souhaitez-vous que la planification confirme automatiquement les ordres prévisionnels en documents de commande, par exemple en ordres de production ou en commandes fournisseur ? »
    - **Réponse :** « Oui, comme défini dans ce plan général. » **1 jour** est entré.

    Comme le détaillant Contoso va crée des commandes fournisseur directement à partir des commandes fournisseur prévisionnelles, il est utile que les commandes fournisseur prévisionnelles soient automatiquement confirmées. Étant donné que la société exécute la planification chaque jour, une plage de gestion de confirmation d’un jour confirme automatiquement toutes les commandes requises pour le lendemain.

- **Demandes approuvées :**

    - **Question :** « Souhaitez-vous inclure les demandes approuvées pour le réapprovisionnement des magasins de vente au détail ? »
    - **Réponse :** « Oui, comme défini dans ce plan général. » **1 jour** est entré.

    Contoso utilise les demandes approuvées de ses magasins pour créer des commandes fournisseur prévisionnelles pour réapprovisionner ces magasins. Étant donné que la planification est exécutée chaque jour, les demandes du dernier jour sont incluses dans la planification.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]