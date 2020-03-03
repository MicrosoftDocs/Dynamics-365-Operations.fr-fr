---
title: Configuration des règles et des options d'admissibilité
description: Définissez les règles et les options d'admissibilité dans la gestion des avantages de Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 448156a2428e99d8b95de547cb6f1621d49b1c7b
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009077"
---
# <a name="configure-eligibility-rules-and-options"></a>Configuration des règles et des options d'admissibilité

[!include [banner](includes/preview-feature.md)]

Après avoir configuré les paramètres nécessaires pour la gestion des avantages dans Microsoft Dynamics 365 Human Resources, vous pouvez créer des règles d'admissibilité, des offres groupées, des périodes et des programmes que vous associez à vos plans d'avantages.

## <a name="create-an-eligibility-rule"></a>Création d'une règle d'admissibilité

Les règles d'admissibilité définissent quels employés peuvent adhérer à chaque plan d'avantages. Après avoir défini des règles d'admissibilité, vous les affectez à des plans d'avantages. Ensuite, vous pouvez traiter l'admissibilité à l'inscription pour voir quels employés sont admissibles pour chaque plan. 

Pendant l'inscription ouverte, les employés peuvent sélectionner des plans d'avantages. S'ils deviennent inadmissibles à un plan d'avantages en fonction des règles d'admissibilité après leur inscription, ils ne sont pas automatiquement désinscrits. En règle générale, lorsqu'un événement de vie se produit et affecte l'admissibilité au plan, une période d'inscription est lancée pour que l'employé sélectionne les plans auxquels il est admissible. 

1. Dans l'espace de travail **Gestion des avantages**, sous **Installer**, sélectionnez **Règles et options d'admissibilité**.

2. Dans l'onglet **Règles d'éligibilité**, sélectionnez **Nouveau**pour créer une règle d'éligibilité. Pour afficher les plans associés à une règle d'éligibilité, sélectionnez **Plans associés**.

3. Spécifiez les valeurs les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Règle d'éligibilité** | Identificateur unique de la règle d'éligibilité. |
   | **Description** | Brève description de la règle d'éligibilité. |
   | **Valide à partir d'une date et heure** | Date de début de la règle d'éligibilité. | 
   | **Valide jusqu'à une date et heure** | Date de fin de la règle d'éligibilité. |
   | **Type d'employé utilisateur** | Spécifie s'il faut utiliser le type d'employé de l'employé pour la règle d'admissibilité aux avantages. |
   | **Type de collaborateur** | Type de collaborateur si le bouton bascule **Utiliser le type d'employé** est réglé sur **Oui**. |
   | **Utiliser le statut d'employé** | Spécifie s'il faut utiliser le statut d'employé de l'employé pour la règle d'admissibilité aux avantages. |
   | **État** | Statut de l'employé si le bouton bascule **Utiliser le statut d'employé** est réglé sur **Oui**. Si le bouton bascule **Utiliser le statut d'employé** est défini sur **Non**, le champ n'est pas utilisé. |
   | **Utiliser la catégorie d'emploi** | Spécifie s'il faut utiliser la valeur **Catégorie d'emploi** pour la règle d'éligibilité aux avantages. | 
   | **Catégorie d'emploi** | Catégorie d'emploi de l'employé si le bouton bascule **Utiliser la catégorie d'emploi** est réglé sur **Oui**. |
   | **Utiliser la nouvelle règle d'embauche** | Spécifie s'il faut utiliser la nouvelle valeur de la période d'embauche d'un nouvel employé dans le cadre de la règle d'éligibilité aux avantages. |
   | **Période d'inscription** | Période pendant laquelle l'inscription du nouvel employé est autorisée. Si vous définissez également cela dans les paramètres, le réglage des paramètres a priorité sur celui-ci. |

4. Sous **Critères supplémentaires**, sélectionnez les options suivantes et ajoutez des informations si nécessaire :

   | Option | Description |
   | --- | --- |
   | **Âge éligible** | Spécifie la ou les tranches d'âge requises pour satisfaire la règle d'éligibilité. |
   | **Département éligible** | Spécifie le ou les départements dans lesquels un employé doit se trouver pour satisfaire à la règle d'éligibilité. |
   | **Type d'emploi éligible** | Spécifie le ou les types d'emploi dans lesquels un employé doit être catégorisé pour satisfaire à la règle d'éligibilité. Par exemple, à temps plein ou à temps partiel. |
   | **Tâche éligible** | Spécifie le ou les emplois qui satisfont à la règle d'éligibilité. Les emplois sont associés à des postes et les postes sont occupés par des employés. |
   | **Fonction de tâche éligible** | Spécifie la ou les fonctions de tâche qui satisfont à la règle d'éligibilité. Par exemple, des vendeurs ou des techniciens. |
   | **Type de tâche éligible** | Spécifie le ou les types de tâche qui satisfont à la règle d'éligibilité. Par exemple, commis ou exécutif. |
   | **Entité juridique éligible** | Spécifie la ou les entités juridiques valides pour la règle d'éligibilité. Par exemple, Contoso Entertainment System USA. |
   | **Région de rémunération éligible** | Spécifie l'emplacement de l'employé qui satisfait à la règle d'éligibilité. Par exemple, centre des États-Unis. |
   | **Poste éligible** | Spécifie le ou les postes qui satisfont à la règle d'éligibilité. Par exemple, assistant ou responsable RH. |
   | **Type de poste éligible** | Spécifie le ou les types de poste qui satisfont à la règle d'éligibilité. Par exemple, à plein temps. |
   | **État éligible** | Spécifie le ou les états ou provinces qui satisfont à la règle d'éligibilité. Par exemple, le Dakota du Nord aux États-Unis ou la Colombie-Britannique au Canada. |
   | **Conditions d'emploi éligibles** | Spécifie les conditions d'emploi qui satisfont à la règle d'éligibilité. Par exemple, à volonté ou contrat de groupe. |
   | **Union éligible** | Spécifie les adhésions à un syndicat qui satisfont à la règle d'éligibilité. Par exemple, Forklift Drivers of America. </br></br>Lorsque vous utilisez une règle d'admissibilité syndicale, le dossier syndical du collaborateur doit avoir la date de fin renseignée. Vous ne pouvez pas la laisser vide. |
   | **Code postal éligible** | Spécifie le ou les codes postaux qui satisfont à la règle d'éligibilité. Par exemple, 58104. |

5. Sous **Détails supplémentaires**, vous pouvez afficher les détails supplémentaires suivants :

   | Champ | Description |
   | --- | --- |
   | **Champ utilisateur éligible** | Spécifie des règles d'éligibilité supplémentaires en fonction des champs définis par le client. |
   | **Type d'éligibilité** | Spécifie la catégorie de critère que vous avez sélectionnée sous **Critères supplémentaires**. |
   | **Référence d'éligibilité** | Spécifie les valeurs que vous avez sélectionnées sous **Critères supplémentaires**. |
   | **Description** | Description que vous avez sélectionnée sous **Critères supplémentaires**. |

6. Sélectionnez **Enregistrer**.

## <a name="configure-bundles"></a>Configuration des offres groupées

Les offres groupées sont un ensemble de plans d'avantages connexes. Vous pouvez utiliser des offres groupées d'avantages pour regrouper les plans d'avantages qu'un employé doit choisir afin de souscrire à certains plans d'avantages qui peuvent dépendre d'autres souscriptions à des plans d'avantages. Voici des exemples de cas où vous souhaiterez peut-être utiliser une offre groupée :

- Une offre groupée de plans de santé qui comprend une assurance santé à franchise élevée avec un compte d'épargne santé (HSA) associé.

- Un plan d'assurance-vie avec un plan d'assurance-vie obligatoire pour les employés combiné avec un plan d'assurance-vie pour les personnes à charge. Cela garantirait qu'un employé ne peut pas sélectionner l'assurance-vie pour les personnes à charge sans souscrire à la couverture des employés.

1. Dans l'espace de travail **Gestion des avantages**, sous **Installer**, sélectionnez **Règles et options d'admissibilité**.

2. Dans l'onglet **Offres groupées**, sélectionnez **Nouveau** pour créer une offre groupée. Pour afficher les plans associés à une offre groupée, sélectionnez **Plans associés**.

3. Spécifiez les valeurs les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Offre groupée** | Identificateur unique d'une offre groupée. |
   | **Description** | Description de l'offre groupée. |
   | **Élément maître** | Indique si l'un des plans de l'offre groupée doit être marqué comme plan général. Le plan général doit être sélectionné lors de l'inscription ouverte dans le cadre de l'offre groupée avant que l'administrateur des avantages puisse confirmer les choix d'avantages de l'employé. |
   | **Valide à partir d'une date et heure** | Date et heure d'activation de l'offre groupée. |
   | **Fin de validité** | Date d'expiration de l'offre groupée. La valeur par défaut est 12/31/2154, qui représente jamais. |

4. Sélectionnez **Enregistrer**.

## <a name="configure-periods"></a>Configuration de périodes

Les périodes définissent quand les avantages sont en vigueur et quand les employés sont autorisés à s'inscrire. Vous pouvez créer autant de périodes que vous le souhaitez afin de maintenir les périodes d'inscription ouverte et de couverture des avantages. Les années du plan d'avantages peuvent suivre ou non une année civile. 

1. Dans l'espace de travail **Gestion des avantages**, sous **Installer**, sélectionnez **Règles et options d'admissibilité**.

2. Dans l'onglet **Périodes**, sélectionnez **Nouveau** pour créer une période. Pour exécuter un processus qui associe tous les plans d'avantages actifs valides à la période des avantages, sélectionnez **Associer des plans**. Pour afficher les plans associés à une offre groupée, sélectionnez **Plans associés**. 

3. Spécifiez les valeurs les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Période** | Identificateur unique d'une période. |
   | **Valide à partir d'une date et heure** | Date et heure de début pendant lesquelles la période d'avantages est active. |
   | **Valide jusqu'à une date et heure** | Date et heure de fin pendant lesquelles la période d'avantages devient inactive. |
   | **Début de l'inscription** | Date de début de l'inscription ouverte. L'inscription ouverte est lorsqu'un employé peut faire des choix d'avantages en libre-service. |
   | **Fin de l'inscription** | Date de fin de l'inscription ouverte. |
   | **Ouvert(e)** | Indique si la période est ouverte en fonction de la date du système et des dates et heures de début et de fin de validité. | 
   | **Période précédente** | Spécifie la période d'avantages qui précède la période d'avantages sélectionnée. Ces informations sont utilisées lors de l'inscription à l'admissibilité aux avantages pour attribuer des plans, des options de couverture et des bénéficiaires d'une année précédente. |
 
4. Sélectionnez **Enregistrer**.

## <a name="use-a-flex-credit-program"></a>Utilisation d'un programme de crédit flexible

Vous pouvez utiliser des programmes de crédits flexibles pour inscrire les employés aux avantages selon un nombre prédéterminé de crédits flexibles. Les employés peuvent choisir comment allouer leurs crédits flexibles. Par exemple, si un employé est couvert par le régime d'assurance maladie de son conjoint, il peut vouloir utiliser les crédits qu'il aurait autrement utilisés sur la couverture maladie pour d'autres avantages.

1. Dans l'espace de travail **Gestion des avantages**, sous **Installer**, sélectionnez **Règles et options d'admissibilité**.

2. Dans l'onglet **Périodes**, sélectionnez **Programmes de crédit flexibles**.

3. Sélectionnez un programme de crédit flexible à appliquer. Les champs contiennent les informations suivantes :

   | Champ | Description |
   | --- | --- |
   | ID de crédit d'avantage | Identifiant unique du programme de crédits flexibles. |
   | Description | Description du programme de crédits flexibles. | 
   | Date de début | Date et heure d'activation du programme de crédits flexibles. |
   | Au | Date de fin du programme de crédits flexibles. Vous pouvez laisser la valeur par défaut (31/12/2154) pour indiquer que le programme de crédit flexible n'a pas d'expiration planifiée. |
   | Valeur de crédit total | Nombre de crédits que chaque employé devra utiliser pour ses avantages. |
   | Règle au prorata | Règle à utiliser pour la répartition proportionnelle des crédits flexibles lorsqu'un employé est embauché au milieu de la période de crédit flexible. </br></br><ul><li>**Aucun** - L'employé ne reçoit aucun crédit flexible s'il est embauché après le début de la période du programme de crédit flexible.</li><li>**Crédit total** - L'employé reçoit le montant total des crédits flexibles, quel que soit le moment de son embauche.</li><li>**Calculer au prorata** - L'employé reçoit un montant proportionnel de crédits flexibles en fonction de sa date de début.</li></ul> |
   | Formule de calcul au prorata des crédits flexibles | Règle à utiliser pour la répartition proportionnelle des crédits flexibles lorsque les employés sont embauchés au milieu d'une période d'avantage pour le programme de crédit flexible. La répartition est basée sur la date de début de l'emploi. Ce champ est uniquement utilisé si vous sélectionnez **Calculer au prorata** dans le champ **Règle au prorata**. </br></br><ul><li>**Quotidien** - Calcule au prorata le nombre de crédits flexibles qu'un employé reçoit au niveau quotidien. Le nombre total de crédits flexibles est divisé par le nombre de jours de la période. Par exemple, si votre période d'avantages est de 400 jours, le système divisera le nombre total de crédits flexibles par 400 pour calculer le nombre de crédits flexibles que les employés reçoivent par jour.</li><li>**Mois en cours** - Calcule au prorata le nombre de crédits flexibles qu'un employé reçoit au niveau du mois, arrondi au mois en cours. Le nombre total de crédits flexibles est divisé par le nombre de mois de la période. Par exemple, si votre période d'avantages est de 15 mois, le système divisera le nombre total de crédits flexibles par 15 pour calculer le nombre de crédits flexibles que les employés reçoivent par mois.</li><li>**Mois suivant** - Calcule au prorata le nombre de crédits flexibles qu'un employé reçoit au niveau du mois, arrondi au mois suivant. Le nombre total de crédits flexibles est divisé par le nombre de mois de la période. Par exemple, si votre période d'avantages est de 15 mois, le système divise le nombre total de crédits flexibles par 15 pour calculer le nombre de crédits flexibles que les employés reçoivent par mois.</li></ul> |
   
   Assurez-vous que chaque plan d'avantages est inscrit à un seul programme de crédit flexible par période d'avantages. Sinon, le système ne saura pas quel programme de crédit flexible utiliser pour accorder des crédits flexibles et vous rencontrerez des problèmes. 

## <a name="configure-programs"></a>Configuration des programmes

Les programmes sont un ensemble de plans d'avantages qui partagent un ensemble commun de règles d'éligibilité. Vous pouvez définir des règles d'éligibilité pour l'ensemble du programme plutôt que pour chaque plan individuel. Par exemple, un programme ETP Contoso Canada ou un programme de niveau exécutif Contoso Europe. 

1. Dans l'espace de travail **Gestion des avantages**, sous **Installer**, sélectionnez **Règles et options d'admissibilité**.

2. Dans l'onglet **Programmes**, sélectionnez **Nouveau** pour créer un programme. Pour faire des exceptions pour les employés qui ne répondent pas aux exigences des règles d'éligibilité, sélectionnez **Remplacer la règle d'éligibilité**. Pour afficher les plans associés à un programme, sélectionnez **Plans associés**.

3. Spécifiez les valeurs les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Programme** | Identificateur unique du programme. |
   | **Description** | Description du programme. | 
   | **Valide à partir d'une date et heure** | Date et heure d'activation du programme. |
   | **Valide jusqu'à une date et heure** | Date et heure d'expiration du programme. La valeur par défaut est 12/31/2154, qui représente jamais. |
   | **Période d'attente de la couverture** | Période pendant laquelle un employé doit attendre avant le début de la couverture du programme d'avantages. |
   | **Période d'attente de la déduction** | Période pendant laquelle un employé attend avant le début des déductions du programme d'avantages. |
   | **Règles d'éligibilité** | Sélectionnez les règles d'éligibilité à appliquer au programme d'avantages. Vous définissez les règles d'éligibilité dans l'onglet **Règles d'éligibilité** sur cette page. |
   
4. Sélectionnez **Enregistrer**.