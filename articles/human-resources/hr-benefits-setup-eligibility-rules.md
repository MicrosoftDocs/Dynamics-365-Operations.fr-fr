---
title: Configurer les règles et les options d’éligibilité
description: Cette rubrique décrit comment définir les règles et les options d’éligibilité dans la gestion des avantages dans Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 88893f6ecee6d2bf0bb42bfa9043eb16a5ed4e90
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691271"
---
# <a name="configure-eligibility-rules-and-options"></a>Configurer les règles et les options d’éligibilité 


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Après avoir configuré les paramètres requis pour la gestion des avantages dans Microsoft , vous pouvez créer les règles d’admissibilité, les offres groupées, les périodes et les programmes que vous associez à vos régimes d’avantages.

Les règles d’admissibilité servent à déterminer si les employés sont admissibles à un régime. Les employés doivent remplir la condition d’au moins une règle pour être considérés comme admissibles à l’avantage. Par exemple, vous avez un régime comportant deux règles. La première règle (ligne 1) stipule que le type d’employé doit être **Employé**. La deuxième règle (ligne 2) stipule que le type d’employé doit être Employé à temps plein. Par conséquent, les employés qui satisfont à la règle 1 sont admissibles même s’ils ne sont employés qu’à temps partiel.

Cependant, vous pouvez configurer une seule règle comportant plusieurs conditions. Dans ce cas, les employés doivent remplir toutes les conditions de la règle pour être considérés comme admissibles à l’avantage. Par exemple, vous avez une règle nommée **Employé à temps plein**. Cette règle stipule que le type d’employé doit être **Employé** *et* que l’employé doit être employé à temps plein. Par conséquent, les employés doivent remplir les deux conditions de la règle pour être admissibles.

> [!IMPORTANT]
> Au moins une règle d’admissibilité doit être associée à chaque régime d’avantages. Vous pouvez associer plusieurs règles à un avantage.

## <a name="create-an-eligibility-rule"></a>Création d’une règle d’admissibilité

Les règles d’admissibilité définissent quels employés peuvent adhérer à chaque plan d’avantages. Après avoir défini des règles d’admissibilité, vous les affectez à des plans d’avantages. Ensuite, vous pouvez traiter l’admissibilité à l’inscription pour voir quels employés sont admissibles pour chaque plan. 

Pendant l’inscription ouverte, les employés peuvent sélectionner des plans d’avantages. S’ils deviennent inadmissibles à un régime de prestations en fonction des règles d’admissibilité après leur inscription, ils ne sont pas automatiquement désinscrits. En règle générale, lorsqu’un événement de vie se produit et affecte l’admissibilité au plan, une période d’inscription est lancée pour que l’employé sélectionne les plans auxquels il est admissible. 

1. Dans l’espace de travail **Gestion des avantages**, sous **Installer**, sélectionnez **Règles et options d’admissibilité**.

2. Dans l’onglet **Règles d’éligibilité**, sélectionnez **Nouveau** pour créer une règle d’éligibilité. Pour afficher les plans associés à une règle d’éligibilité, sélectionnez **Plans associés**.

3. Spécifiez des valeurs pour les champs suivants.

   | Champ | Description |
   | --- | --- |
   | **Règle d’éligibilité** | Identificateur unique de la règle d’éligibilité. |
   | **Description** | Brève description de la règle d’éligibilité. |
   | **Valide à partir d’une date et heure** | Date de début de la règle d’éligibilité. | 
   | **Valide jusqu’à une date et heure** | Date de fin de la règle d’éligibilité. |
   | **Type d’employé utilisateur** | Spécifie s’il faut utiliser le type d’employé de l’employé pour la règle d’admissibilité aux avantages. |
   | **Type de collaborateur** | Type de collaborateur si le bouton bascule **Utiliser le type d’employé** est réglé sur **Oui**. |
   | **Utiliser le statut d’employé** | Spécifie s’il faut utiliser le statut d’employé de l’employé pour la règle d’admissibilité aux avantages. |
   | **État** | Statut de l’employé si le bouton bascule **Utiliser le statut d’employé** est réglé sur **Oui**. Si le bouton bascule **Utiliser le statut d’employé** est défini sur **Non**, le champ n’est pas utilisé. |
   | **Utiliser la catégorie d’emploi** | Spécifie s’il faut utiliser la valeur **Catégorie d’emploi** pour la règle d’éligibilité aux avantages. | 
   | **Catégorie d’emploi** | Catégorie d’emploi de l’employé si le bouton bascule **Utiliser la catégorie d’emploi** est défini sur **Oui**. |
   | **Utiliser la nouvelle règle d’embauche** | Spécifie s’il faut utiliser la nouvelle valeur de la période d’embauche d’un nouvel employé dans le cadre de la règle d’éligibilité aux avantages. |
   | **Période d’inscription** | Période pendant laquelle l’inscription du nouvel employé est autorisée. Si vous définissez également cela dans les paramètres, le réglage des paramètres a priorité sur celui-ci. |
   | **Utiliser le statut d’emploi précédent** | Spécifie s’il faut utiliser un statut d’emploi précédent de l’employé dans le cadre de la règle d’éligibilité des avantages. Par exemple, vous pouvez spécifier une règle d’admissibilité qui renonce à une période d’attente de couverture pour tous les employés qui sont passés d’un statut **Mis en page** à un statut **Employé** dans les 90 jours suivant leur emploi précédent. |

4. Sous **Critères supplémentaires**, sélectionnez les options suivantes et ajoutez des informations si nécessaire.

   | Option | Description |
   | --- | --- |
   | **Âge éligible** | Spécifie la ou les tranches d’âge requises pour satisfaire la règle d’éligibilité. |
   | **Département éligible** | Spécifie le ou les départements dans lesquels un employé doit se trouver pour satisfaire à la règle d’éligibilité. |
   | **Type d’emploi éligible** | Spécifie le ou les types d’emploi dans lesquels un employé doit être catégorisé pour satisfaire à la règle d’éligibilité. Par exemple, à temps plein ou à temps partiel. |
   | **Tâche éligible** | Spécifie le ou les emplois qui satisfont à la règle d’éligibilité. Les emplois sont associés à des postes et les postes sont occupés par des employés. |
   | **Fonction de tâche éligible** | Spécifie la ou les fonctions de tâche qui satisfont à la règle d’éligibilité. Par exemple, des vendeurs ou des techniciens. |
   | **Type de tâche éligible** | Spécifie le ou les types de tâche qui satisfont à la règle d’éligibilité. Par exemple, commis ou exécutif. |
   | **Entité juridique éligible** | Spécifie la ou les entités juridiques valides pour la règle d’éligibilité. Par exemple, Contoso Entertainment System USA. |
   | **Région de rémunération éligible** | Spécifie l’emplacement de l’employé qui satisfait à la règle d’éligibilité. Par exemple, centre des États-Unis. |
   | **Poste éligible** | Spécifie le ou les postes qui satisfont à la règle d’éligibilité. Par exemple, assistant ou responsable RH. |
   | **Type de poste éligible** | Spécifie le ou les types de poste qui satisfont à la règle d’éligibilité. Par exemple, à plein temps. |
   | **État éligible** | Spécifie le ou les états ou provinces qui satisfont à la règle d’éligibilité. Par exemple, le Dakota du Nord aux États-Unis ou la Colombie-Britannique au Canada. |
   | **Conditions d’emploi éligibles** | Spécifie les conditions d’emploi qui satisfont à la règle d’éligibilité. Par exemple, à volonté ou contrat de groupe. |
   | **Union éligible** | Spécifie les adhésions à un syndicat qui satisfont à la règle d’éligibilité. Par exemple, Forklift Drivers of America.</br></br>Lorsque vous utilisez une règle d’admissibilité syndicale, le dossier syndical du collaborateur doit avoir la date de fin renseignée. Vous ne pouvez pas la laisser vide. |
   | **Code postal éligible** | Spécifie le ou les codes postaux qui satisfont à la règle d’éligibilité. Par exemple, 58104. |

5. Sous **Détails supplémentaires**, vous pouvez afficher les détails supplémentaires suivants.

   | Champ | Description |
   | --- | --- |
   | **Champ utilisateur éligible** | Spécifie des règles d’éligibilité supplémentaires en fonction des champs définis par le client. |
   | **Type d’éligibilité** | Spécifie la catégorie de critère que vous avez sélectionnée sous **Critères supplémentaires**. |
   | **Référence d’éligibilité** | Spécifie les valeurs que vous avez sélectionnées sous **Critères supplémentaires**. |
   | **Description** | Description que vous avez sélectionnée sous **Critères supplémentaires**. |

6. Sélectionnez **Enregistrer**.

## <a name="using-custom-fields-in-eligibility-rules"></a>Utilisation de champs personnalisés dans les règles d’éligibilité

Des [champs personnalisés](hr-developer-custom-fields.md) peuvent être créés dans Human Resources pour suivre des informations supplémentaires. Ces champs peuvent être ajoutés directement à l’interface utilisateur et une colonne est ajoutée dynamiquement à la table sous-jacente.  

Les champs personnalisés peuvent être utilisés dans le processus d’éligibilité. Les règles d’éligibilité peuvent utiliser une ou plusieurs valeurs de champs personnalisés pour déterminer l’éligibilité d’un employé.  Pour ajouter un champ personnalisé à une règle existante ou pour créer une nouvelle règle, accédez à **Gestion des avantages > Liens> Configuration > Règles d’éligibilité > Éligibilité de champs personnalisés**. Dans cette page, vous pouvez créer une règle qui utilise un ou plusieurs champs personnalisés et vous pouvez définir plusieurs valeurs pour chaque champ personnalisé pour déterminer l’éligibilité.

Les tables suivantes prennent en charge les champs personnalisés qui peuvent être utilisés dans le processus d’éligibilité :

- Collaborateur (HcmWorker)  
- Travail (HcmJob)  
- Poste (HcmPosition)  
- Détail du poste (HcmPositionDetail)  
- Affectation du collaborateur au poste  
- Emploi (HcmEmployment)  
- Détails de l’emploi (HcmEmploymentDetails)  
- Détails du travail (HcmJobDetails)  

Les types de champs personnalisés suivants sont pris en charge dans le processus d’éligibilité :

- Détails  
- Prélèvement  
- Nombre  
- Décimal  
- Case à cocher  

Le tableau suivant affiche des informations sur les champs du formulaire d’éligibilité de champs personnalisés.

| Champ  | Description |
|--------|-------------|
| Nom | Nom des critères en cours de création. |
| Nom de la table | Nom de la table contenant le champ personnalisé utilisé pour la règle d’éligibilité. |
| Nom du champ | Champ qui sera utilisé pour la règle d’éligibilité. |
| Type d’opérateur | Affiche l’opérateur utilisé dans la configuration de l’éligibilité de champs personnalisés. |
| Valeur | Affiche la valeur utilisée dans la configuration de l’éligibilité de champs personnalisés. |

## <a name="eligibility-logic"></a>Logique d’éligibilité

Les sections suivantes décrivent comment l’éligibilité aux avantages est traitée.

### <a name="rules-assigned-to-a-plan"></a>Règles affectées à un plan 
Lorsque plusieurs règles d’éligibilité sont affectées à un plan d’avantages, un employé doit remplir au moins une règle pour pouvoir s’inscrire au plan d’avantages.  Dans l’exemple suivant, l’employé doit répondre aux exigences de la règle **Type d’emploi** ou de la règle **Employés actifs**.

![L’employé doit répondre aux exigences de la règle Type d’emploi ou de la règle Employés actifs.](media/RulesAssignedToAPlan.png)
 
### <a name="criteria-within-an-eligibility-rule"></a>Critères dans une règle d’éligibilité 
Dans une règle, vous définissez les critères qui forment la règle. Dans l’exemple ci-dessus, le critère de la règle **Type d’emploi** est défini sur Type d’emploi = Directeurs. Par conséquent, l’employé doit être un directeur pour être éligible. Il s’agit d’une règle dans laquelle il n’y a qu’un seul critère dans la règle.

Vous pouvez définir des règles avec plusieurs critères. Lorsque vous définissez plusieurs critères dans une règle d’éligibilité, un employé doit répondre à tous les critères de la règle pour être éligible au plan d’avantages. 

Par exemple, la règle **Employés actifs** ci-dessus se compose des critères suivants. Pour que l’employé soit éligible en vertu de la règle **Employés actifs**, il doit être employé dans l’entité juridique USMF *et* avoir un type de poste à temps plein.  

![Critères dans une règle d’éligibilité.](media/CriteriaWithinAnEligibilityRule.png) 
 
### <a name="multiple-conditions-within-criteria"></a>Conditions multiples dans les critères

Les règles peuvent être étendues davantage pour utiliser plusieurs conditions dans un seul critère. L’employé doit remplir au moins une condition pour être éligible. Pour continuer avec l’exemple ci-dessus, la règle **Employés actifs** peut être étendue davatange pour inclure les employés qui sont également des employés à temps partiel. En conséquence, l’employé doit maintenant être un employé d’USMF *et* un employé à temps plein ou à temps partiel.  

![Conditions multiples dans les critères.](media/MultipleConditionsWithinCriteria.png) 
 
### <a name="eligibility-conditions-within-a-custom-field-criterion"></a>Conditions d’éligibilité dans un critère de champ personnalisé 
De la même manière que ce qui précède, les champs personnalisés peuvent être utilisés lors de la création de règles d’éligibilité et fonctionnent de la même manière. Par exemple, vous souhaitez peut-être offrir un remboursement Internet aux employés de Fargo et Copenhagen qui travaillent à domicile, car les coûts d’Internet sont plus élevés dans ces lieux. Pour ce faire, créez deux champs personnalisés : **Emplacement du bureau** (liste de sélection) et **Travail à domicile** (case à cocher). Ensuite, créez une règle appelée **Employés travaillant à domicile**. Le critère de la règle est défini sur **Emplacement du bureau = Fargo** ou **Copenhagen** *et* **Travail à domicile = Oui**.

Les règles d’éligibilité personnalisées doivent être configurées comme indiqué dans l’image suivante. 

![Conditions d’éligibilité dans un critère de champ personnalisé.](media/EligibilityConditionsWithinACustomFieldCriterion.png) 
 
## <a name="configure-bundles"></a>Configuration des offres groupées

Les offres groupées sont un ensemble de plans d’avantages connexes. Vous pouvez utiliser des offres groupées d’avantages pour regrouper les plans d’avantages qu’un employé doit choisir afin de souscrire à certains plans d’avantages qui peuvent dépendre d’autres souscriptions à des régime de prestations. Voici des exemples de cas où vous souhaiterez peut-être utiliser une offre groupée :

- Une offre groupée de plans de santé qui comprend une assurance santé à franchise élevée avec un compte d’épargne santé (HSA) associé.

- Un plan d’assurance-vie avec un plan d’assurance-vie obligatoire pour les employés combiné avec un plan d’assurance-vie pour les personnes à charge. Cela garantirait qu’un employé ne peut pas sélectionner l’assurance-vie pour les personnes à charge sans souscrire à la couverture des employés.

1. Dans l’espace de travail **Gestion des avantages**, sous **Installer**, sélectionnez **Règles et options d’admissibilité**.

2. Dans l’onglet **Offres groupées**, sélectionnez **Nouveau** pour créer une offre groupée. Pour afficher les plans associés à une offre groupée, sélectionnez **Plans associés**.

3. Spécifiez des valeurs pour les champs suivants.

   | Champ | Description |
   | --- | --- |
   | **Offre groupée** | Identificateur unique d’une offre groupée. |
   | **Description** | Description de l’offre groupée. |
   | **Élément maître** | Indique si l’un des plans de l’offre groupée doit être marqué comme plan général. Le régime général doit être sélectionné lors de l’inscription ouverte dans le cadre de l’offre groupée avant que l’administrateur des avantages puisse confirmer les choix d’avantages de l’employé. |
   | **Valide à partir d’une date et heure** | Date et heure d’activation de l’offre groupée. |
   | **Fin de validité** | Date d’expiration de l’offre groupée. La valeur par défaut est 12/31/2154, qui représente jamais. |

4. Sélectionnez **Enregistrer**.

## <a name="configure-periods"></a>Configuration de périodes

Les périodes définissent quand les avantages sont en vigueur et quand les employés sont autorisés à s’inscrire. Vous pouvez créer autant de périodes que vous le souhaitez afin de maintenir les périodes d’inscription ouverte et de couverture des avantages. Les années du régime de prestations peuvent suivre ou non une année civile. 

1. Dans l’espace de travail **Gestion des avantages**, sous **Installer**, sélectionnez **Règles et options d’admissibilité**.

2. Dans l’onglet **Périodes**, sélectionnez **Nouveau** pour créer une période. Pour exécuter un processus qui associe tous les plans d’avantages actifs valides à la période des avantages, sélectionnez **Associer des plans**. Pour afficher les plans associés à une offre groupée, sélectionnez **Plans associés**. 

3. Spécifiez des valeurs pour les champs suivants.

   | Champ | Description |
   | --- | --- |
   | **Période** | Identificateur unique d’une période. |
   | **Valide à partir d’une date et heure** | Date et heure de début pendant lesquelles la période d’avantages est active. |
   | **Valide jusqu’à une date et heure** | Date et heure de fin pendant lesquelles la période d’avantages devient inactive. |
   | **Début de l’inscription** | Date de début de l’inscription ouverte. L’inscription ouverte est lorsqu’un employé peut faire des choix d’avantages en libre service. |
   | **Fin de l’inscription** | Date de fin de l’inscription ouverte. |
   | **Ouvert(e)** | Indique si la période est ouverte en fonction de la date du système et des dates et heures de début et de fin de validité. | 
   | **Période précédente** | Spécifie la période d’avantages qui précède la période d’avantages sélectionnée. Ces informations sont utilisées lors de l’inscription à l’admissibilité aux avantages pour attribuer des plans, des options de couverture et des bénéficiaires d’une année précédente. |
 
4. Sélectionnez **Enregistrer**.

## <a name="use-a-flex-credit-program"></a>Utilisation d’un programme de crédit flexible

Vous pouvez utiliser des programmes de crédits flexibles pour inscrire les employés aux avantages selon un nombre prédéterminé de crédits flexibles. Les employés peuvent choisir comment allouer leurs crédits flexibles. Par exemple, si un employé est couvert par le régime d’assurance maladie de son conjoint, il peut vouloir utiliser les crédits qu’il aurait autrement utilisés sur la couverture maladie pour d’autres avantages.

1. Dans l’espace de travail **Gestion des avantages**, sous **Installer**, sélectionnez **Règles et options d’admissibilité**.

2. Dans l’onglet **Périodes**, sélectionnez **Programmes de crédit flexibles**.

3. Sélectionnez un programme de crédit flexible à appliquer. Les champs contiennent les informations suivantes.

   | Champ | Description |
   | --- | --- |
   | **ID de crédit d’avantage** | Identifiant unique du programme de crédits flexibles. |
   | **Description** | Description du programme de crédits flexibles. | 
   | **Date de début** | Date et heure d’activation du programme de crédits flexibles. |
   | **Au** | Date de fin du programme de crédits flexibles. Vous pouvez laisser la valeur par défaut (31/12/2154) pour indiquer que le programme de crédit flexible n’a pas d’expiration planifiée. |
   | **Valeur de crédit total** | Nombre de crédits que chaque employé devra utiliser pour ses avantages. |
   | **Règle au prorata** | Règle à utiliser pour la répartition proportionnelle des crédits flexibles lorsqu’un employé est embauché au milieu de la période de crédit flexible. </br></br><ul><li>**Aucun** – L’employé ne reçoit aucun crédit flexible s’il est embauché après le début de la période du programme de crédit flexible.</li><li>**Crédit total** – L’employé reçoit le montant total des crédits flexibles, quel que soit le moment de son embauche.</li><li>**Calculer au prorata** – L’employé reçoit un montant proportionnel de crédits flexibles en fonction de sa date de début.</li></ul> |
   | **Formule de calcul au prorata des crédits flexibles** | Règle à utiliser pour la répartition proportionnelle des crédits flexibles lorsque les employés sont embauchés au milieu d’une période d’avantage pour le programme de crédit flexible. La répartition est basée sur la date de début de l’emploi. Ce champ est uniquement utilisé si vous sélectionnez **Calculer au prorata** dans le champ **Règle au prorata**. </br></br><ul><li>**Quotidien** – Calcule au prorata le nombre de crédits flexibles qu’un employé reçoit au niveau quotidien. Le nombre total de crédits flexibles est divisé par le nombre de jours de la période. Par exemple, si votre période d’avantages est de 400 jours, le système divisera le nombre total de crédits flexibles par 400 pour calculer le nombre de crédits flexibles que les employés reçoivent par jour.</li><li>**Mois en cours** – Calcule au prorata le nombre de crédits flexibles qu’un employé reçoit au niveau du mois, arrondi au mois en cours. Le nombre total de crédits flexibles est divisé par le nombre de mois de la période. Par exemple, si votre période d’avantages est de 15 mois, le système divisera le nombre total de crédits flexibles par 15 pour calculer le nombre de crédits flexibles que les employés reçoivent par mois.</li><li>**Mois suivant** – Calcule au prorata le nombre de crédits flexibles qu’un employé reçoit au niveau du mois, arrondi au mois suivant. Le nombre total de crédits flexibles est divisé par le nombre de mois de la période. Par exemple, si votre période d’avantages est de 15 mois, le système divise le nombre total de crédits flexibles par 15 pour calculer le nombre de crédits flexibles que les employés reçoivent par mois.</li></ul> |
   
   Assurez-vous que chaque régime de prestations est inscrit à un seul programme de crédit flexible par période d’avantages. Sinon, le système ne saura pas quel programme de crédit flexible utiliser pour accorder des crédits flexibles et vous rencontrerez des problèmes. 

## <a name="configure-programs"></a>Configuration des programmes

Les programmes sont un ensemble de plans d’avantages qui partagent un ensemble commun de règles d’éligibilité. Vous pouvez définir des règles d’éligibilité pour l’ensemble du programme plutôt que pour chaque plan individuel. Par exemple, un programme ETP Contoso Canada ou un programme de niveau exécutif Contoso Europe. 

1. Dans l’espace de travail **Gestion des avantages**, sous **Installer**, sélectionnez **Règles et options d’admissibilité**.

2. Dans l’onglet **Programmes**, sélectionnez **Nouveau** pour créer un programme. Pour faire des exceptions pour les employés qui ne répondent pas aux exigences des règles d’éligibilité, sélectionnez **Remplacer la règle d’éligibilité**. Pour afficher les plans associés à un programme, sélectionnez **Plans associés**.

3. Spécifiez des valeurs pour les champs suivants.

   | Champ | Description |
   | --- | --- |
   | **Programme** | Identificateur unique du programme. |
   | **Description** | Description du programme. | 
   | **Valide à partir d’une date et heure** | Date et heure d’activation du programme. |
   | **Valide jusqu’à une date et heure** | Date et heure d’expiration du programme. La valeur par défaut est 12/31/2154, qui représente jamais. |
   | **Période d’attente de la couverture** | Période pendant laquelle un employé doit attendre avant le début de la couverture du programme d’avantages. |
   | **Période d’attente de la déduction** | Période pendant laquelle un employé attend avant le début des déductions du programme d’avantages. |
   | **Règles d’éligibilité** | Sélectionnez les règles d’éligibilité à appliquer au programme d’avantages. Vous définissez les règles d’éligibilité dans l’onglet **Règles d’éligibilité** sur cette page. |
   
4. Sélectionnez **Enregistrer**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
