---
title: Création d'un plan d'avantages
description: Configurez des plans d'avantages dans Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitPlanListPage, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 05d08862b880271fb4842bd7e77f04208f9c0bed
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112550"
---
# <a name="create-a-benefits-plan"></a>Création d'un plan d'avantages

Cet article vous montre comment configurer des plans d'avantages sociaux dans Dynamics 365 Human Resources.

1. Dans l'espace de travail **Gestion des avantages**, sous **Plans**, sélectionnez **Plans d'avantages**.

2. Sélectionnez **Nouveau**.

3. Dans l'onglet **Général**, spécifiez les valeurs pour les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Plan** | Identificateur unique d'un plan. |
   | **Description** | Description du plan. |
   | **Type de plan** | Lorsque vous créez un nouveau plan, vous devez spécifier le type de plan. Un type de plan est un regroupement de haut niveau de types spécifiques d'avantages. Chaque type de plan spécifie si un employé peut souscrire à plusieurs plans de ce type, spécifie si les contacts sont des bénéficiaires ou des personnes à charge et définit les options de couverture. Vous pouvez créer de nouveaux types de plans personnalisés pour répondre aux besoins de vos offres d'avantages. Les principaux types de régimes de prestations sociales sont les suivants : <ul><li>401K</li><li>ADD</li><li>Soins dentaires</li><li>Fitness</li><li>FSA</li><li>Vie</li><li>LTD</li><li>Assurance-maladie</li><li>Congés payés</li><li>STD</li><li>Vision</li></ul> |
   | **Code de type de plan** | Code du type de plan. |
   | **Programme** | Spécifie un programme auquel affecter éventuellement le plan. |
   | **Offre groupée** | Spécifie une offre groupée à laquelle affecter le plan. |
   | **Élément maître** | Spécifie si le plan est le plan général de l'offre groupée à laquelle il est affecté. |
   | **État** | Indique l'état actuel du plan d'avantages. La valeur par défaut est Actif. Si vous modifiez le statut sur Inactif, le plan ne sera pas disponible en tant que sélection lors de l'inscription. |
   | **Valide à partir d'une date et heure** | Date et l'heure de début du plan. La date par défaut est la date système actuelle. |
   | **Valide jusqu'à une date et heure** | Date et heure de fin du plan (le statut est défini sur Inactif). La valeur par défaut est 12/31/2154, ce qui signifie jamais. |

4. Dans l'onglet **Configuration**, spécifiez des valeurs pour les champs suivants, selon le type de plan que vous créez :

   | Type de plan | Champ | Description |
   | --- | --- | --- |
   | Médical (médical, dentaire, vision, HMO) | COBRA | Spécifie si le plan est éligible à COBRA (Consolidated Omnibus Budget Reconciliation Act). |
   | Médical (médical, dentaire, vision, HMO) | HIPAA | Spécifie si le plan est éligible à HIPAA (Health Insurance Portability and Accountability Act). |
   | <ul><li>Médical (médical, dentaire, vision, HMO)</li><li>Autre (PTO, Fitness)</li><li>Other</li><li>Invalidité à long terme</li><li>ADD (assurance-vie de base, assurance-vie volontaire)</li><li>Épargne (par exemple, 401 (k))</li><li>FSA</li></ul> | Option avant impôt éligible | Spécifie si des contributions peuvent être versées au plan avant que les taxes soient appliquées. |
   | <ul><li>Médical (médical, dentaire, vision, HMO)</li><li>Autre (PTO, Fitness)</li><li>Invalidité à long terme</li><li>ADD (assurance-vie de base, assurance-vie volontaire)</li><li>Épargne (par exemple, 401 (k))</li><li>FSA</li></ul> | Valider la taxe éligible | Spécifie si des contributions peuvent être versées au plan après que les taxes ont été appliquées. |
   | <ul><li>Médical (médical, dentaire, vision, HMO)</li><li>Autre (PTO, Fitness)</li><li>Invalidité à long terme</li><li>ADD (assurance-vie de base, assurance-vie volontaire)</li><li>Épargne (par exemple, 401 (k))</li><li>FSA</li></ul> | Contributeur | Spécifie qui contribue au plan - l'employé, l'employeur ou les deux. |
   | <ul><li>Invalidité à long terme</li><li>ADD (assurance-vie de base, assurance-vie volontaire)</li></ul> | Couverture minimale | Montant minimum de couverture d'assurance requis pour le plan. |
   | <ul><li>Invalidité à long terme</li><li>ADD (assurance-vie de base, assurance-vie volontaire)</li></ul> | Couverture maximale | Montant maximum de couverture d'assurance requis pour le plan. |
   | <ul><li>Invalidité à long terme</li><li>ADD (assurance-vie de base, assurance-vie volontaire)</li></ul> | Utiliser les incréments de couverture | Spécifie s'il faut valider que le montant de couverture correspond à un montant incrémentiel valide. |
   | <ul><li>Invalidité à long terme</li><li>ADD (assurance-vie de base, assurance-vie volontaire)</li></ul> | Montant incrémentiel | Montant incrémentiel de couverture d'assurance pour le plan. Par exemple, si le montant incrémentiel est de 1 000, un employé ne peut pas avoir 200 500 $ d'assurance, il faudra arrondir à 201 000 $ ou descendre à 200 000 $. |
   | <ul><li>Invalidité à long terme</li><li>ADD (assurance-vie de base, assurance-vie volontaire)</li></ul> | Sens incrémentiel | Spécifie le sens de l'arrondi, soit vers le haut soit vers le bas, lorsque le montant de la couverture n'est pas conforme à la valeur du montant incrémentiel. |
   | ADD (assurance-vie de base, assurance-vie volontaire) | Preuve d'assurabilité | Spécifie si un employé doit fournir une preuve d'assurabilité. |
   | ADD (assurance-vie de base, assurance-vie volontaire) | Montant | Montant en devise comptable. Ce champ n'est actif que si la case à cocher Preuve d'assurabilité est cochée. |
   | <ul><li>Épargne (par exemple, 401 (k))</li><li>FSA</li></ul> | Contribution annuelle minimale | Montant de contribution minimum requis pour le plan. |
   | <ul><li>Épargne (par exemple, 401 (k))</li><li>FSA</li></ul> | Contribution annuelle maximale | Montant de contribution maximum requis pour le plan. |
   | Épargne (par exemple, 401 (k)) | Montant annuel maximal de l'employeur | Montant maximal qu'un employeur est autorisé à cotiser à un plan d'épargne salariale pendant une période d'avantages. Vous devez cocher la case Correspondance employeur pour utiliser ce champ. |
   | Épargne (par exemple, 401 (k)) | Correspondance employeur | Spécifie si l'employeur cotise au plan d'épargne salariale. |
   | Épargne (par exemple, 401 (k)) | Pourcentage de correspondance de l'employeur | Pourcentage d'une cotisation salariale que l'employeur égalera. |
   | Épargne (par exemple, 401 (k)) | Limite de correspondance employeur | Pourcentage maximum que l'employeur égalisera. Par exemple, si un employeur égalise à 100 % des cotisations des employés jusqu'à 6 % de la rémunération de l'employé, le plafond de contrepartie de l'employeur est de 6 %. |

5. Dans l'onglet **Configuration**, spécifiez les valeurs pour les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Autoriser/continuer l'inscription** | Spécifie si les employés peuvent s'inscrire au plan s'ils répondent aux critères d'éligibilité.</br></br>Si ce paramètre est défini sur Non, le plan ne sera pas disponible pour les employés lorsque vous traiterez l'admissibilité. |
   | **Inscription automatique à partir de l'année précédente** | Spécifie si un employé éligible doit être inscrit automatiquement dans le plan s'il a été inscrit au cours de l'année précédente. |
   | **Inscription automatique par défaut** | Spécifie s'il faut sélectionner le plan d'inscription par défaut. Le plan n'est pas obligatoire, donc l'employé peut modifier la sélection par défaut. |
   | **Clôturé pour de nouvelles inscriptions** | Spécifie s'il faut limiter le plan aux seuls employés éligibles qui étaient inscrits au plan au cours de l'année précédente. |
   | **Plan obligatoire** | Spécifie s'il faut inscrire automatiquement les employés dans le plan. Les employés ne peuvent pas modifier la sélection d'inscription. |
   | **Date de prise d'effet** | Date de création du plan dans l'entreprise. |
   | **Compte fournisseur** (fournisseur des avantages) | Fournisseur auquel l'entreprise verse des primes pour le plan. |
   | **Nom** (fournisseur des avantages) | Nom du fournisseur. |
   | **Référence fournisseur** (fournisseur des avantages) | Référence du fournisseur pour le plan. Par exemple, numéro du plan de groupe de l'entreprise. |
   | **Autre référence** (fournisseur des avantages) | Autre référence du fournisseur pour le plan. Par exemple, numéro du compte d'entreprise. |
   | **Devise** (fournisseur des avantages) | Devise utilisée pour payer les primes au fournisseur. |
   | **Compte de dépenses** (fournisseur des avantages) | Compte du grand livre qui est utilisé comme compte de dépenses pour les primes du plan. |
   | **Compte fournisseur** (administrateur des avantages) | Fournisseur que l'entreprise paie pour administrer le plan. Si le plan est auto-administré, laissez ce champ vide. |
   | **Nom** (administrateur des avantages) | Nom du fournisseur administrateur des avantages. |
   | **Référence fournisseur** (administrateur des avantages) | Référence du fournisseur administrateur pour le plan. |
   | **Autre référence** (administrateur des avantages) | Autre référence du fournisseur administrateur pour le plan. |
   | **Devise** (administrateur des avantages) | Devise utilisée pour payer les primes à l'administrateur des avantages. |
   | **Compte de dépenses** (administrateur des avantages) | Compte du grand livre qui est utilisé comme compte de dépenses pour les coûts associés à l'administration du plan. |

6. Dans l'onglet **Filtres**, filtrez si nécessaire. Vous pouvez filtrer à l'aide des champs suivants :

   - **Unité commerciale**
   - **Département**
   - **Entité juridique**
   - **Emplacement**
   - **Poste**

7. Dans l'onglet **Règles d'éligibilité**, spécifiez les valeurs pour les champs suivants :

   | Champ | Description |
   | --- | --- |
   | **Numéro de ligne** | Numéro de ligne de la règle d'éligibilité. |
   | **Règle d'éligibilité** | Règle d'éligibilité à appliquer au plan d'avantages. Cette règle d'éligibilité sera appliquée au type d'action correspondant et associée à la période d'attente de couverture et aux déductions spécifiées. |
   | **Type d’action** | Action d'appliquer la règle d'éligibilité : inscription ou expiration des avantages. |
   | **Période d'attente de la couverture** | Valeur du formulaire Périodes d'attente. La période d'attente de couverture détermine le nombre de jours ou de mois pendant lesquels un employé attend la couverture ou l'expiration des avantages en fonction des critères de la règle d'éligibilité et du type d'action. |
   | **Période d'attente de la déduction** | Valeur du formulaire Périodes d'attente. La période d'attente de déduction détermine le nombre de jours ou de mois pendant lesquels un employé attend les déductions de son salaire en fonction des critères de la règle d'éligibilité et du type d'action. |

8. Sélectionnez **Enregistrer**.

## <a name="view-enrolled-workers"></a>Affichage des collaborateurs inscrits

Vous pouvez afficher les collaborateurs inscrits à un plan d'avantages sélectionné.

1. Dans l'espace de travail **Gestion des avantages**, sous **Plans**, sélectionnez **Plans d'avantages**.

2. Sélectionnez **Collaborateurs inscrits**.

## <a name="attach-coverage-options"></a>Joindre les options de couverture

Vous pouvez ajouter des options de couverture au plan d'avantages sélectionné. L'association d'options de couverture rassemble le taux et la déduction pour une option de couverture.  Exemple : pour un plan médical, l'utilisateur sélectionnerait une option de couverture familiale.  Il lui faudrait ensuite sélectionner le tarif famille pour le plan associé (défini dans la configuration des tarifs) et la déduction pour le plan associé (défini dans la configuration des tarifs). Cela fournit le coût pour l'employeur et l'employé pour une couverture sélectionnée. Ensuite, vous répéteriez le processus pour une couverture Employé + 1 ou une couverture Employé.

1. Dans l'espace de travail **Gestion des avantages**, sous **Plans**, sélectionnez **Plans d'avantages**.

2. Sélectionnez **Associer des options de couverture**.

## <a name="override-eligibility-rules"></a>Remplacement des règles d'éligibilité

Vous pouvez ajouter des collaborateurs à un plan en tant qu'exceptions aux règles d'éligibilité. Chaque collaborateur que vous ajoutez sera admissible au plan d'avantages.

1. Dans l'espace de travail **Gestion des avantages**, sous **Plans**, sélectionnez **Plans d'avantages**.

2. Sélectionnez **Remplacement des règles d'éligibilité**.

## <a name="view-attached-periods"></a>Affichages des périodes associées

Vous pouvez afficher une liste des périodes d'avantages disponibles.

1. Dans l'espace de travail **Gestion des avantages**, sous **Plans**, sélectionnez **Plans d'avantages**.

2. Sélectionnez **Périodes**.

## <a name="view-plan-information"></a>Affichage d'informations sur le plan

Vous pouvez fournir une description du plan pour aider les employés à choisir leurs avantages. Les informations sur le plan que vous saisissez ici s'affichent dans Libre-service employé lorsque vous survolez le plan dans la liste des options de couverture.

1. Dans l'espace de travail **Gestion des avantages**, sous **Plans**, sélectionnez **Plans d'avantages**.

2. Sélectionnez **Informations sur le plan**.

## <a name="view-flex-credit-programs"></a>Afficher les programmes de crédit flexible

1. Dans l'espace de travail **Gestion des avantages**, sous **Plans**, sélectionnez **Plans d'avantages**.

2. Sélectionnez **Programmes de crédits flexibles**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]