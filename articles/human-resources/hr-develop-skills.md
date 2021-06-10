---
title: Configurer les compétences
description: Vous pouvez suivre les compétences de votre collaborateur dans Dynamics 365 Human Resources. Vous pouvez également spécifier les compétences requises pour une tâche spécifique.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 816822d1f3d365b4c5571c13e9f596e1c5d5e59c
ms.sourcegitcommit: 48528233e0f02dbd47e96e030254ef65f2bb899e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2021
ms.locfileid: "6076557"
---
# <a name="configure-skills"></a>Configurer les compétences

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Vous pouvez suivre les compétences de votre collaborateur dans Dynamics 365 Human Resources. Vous pouvez également spécifier les compétences requises pour une tâche spécifique.

Voici des exemples de compétences que vous pouvez suivre :

- Supervision – Capacité de superviser le travail des autres.
- Leadership – Capacité de diriger des employés et des secteurs d’entreprise.
- Planification – Capacité à anticiper les choses, à former des énoncés de vision et à les mener à bien.
- HTML – Capacité d’écrire du code HTML.

Si vous n’avez pas déjà configuré des types de compétences et des modèles d’évaluation, vous devrez en ajouter avant de créer des compétences.

Les personnes suivantes peuvent saisir des compétences pour un collaborateur :

- Les collaborateurs peuvent saisir des compétences pour eux-mêmes dans le libre-service des employés. Ces compétences nécessitent l’approbation du responsable.
- Les responsables peuvent saisir des compétences pour leurs collaborateurs. Vous pouvez créer un flux de travail qui approuve automatiquement ces compétences.

## <a name="create-a-skill-type"></a>Créer un type de compétence

Les types de compétences sont des catégories dans lesquelles entrent les compétences individuelles, telles que Administration ou Vente.

1. Dans l’espace de travail, **Perfectionnement de l’employé**, sélectionnez **Liens**.

2. Sous **Configuration des compétences**, sélectionnez **Types de compétences**.

3. Sélectionnez **Nouveau**.

4. Complétez les champs suivants :

   - **Type de compétence** : entrez un nom pour le type de compétence.
   - **Description** : entrez une description pour le type de compétence.

5. Sélectionnez **Enregistrer**.

## <a name="create-a-rating-model"></a>Créer un modèle d’évaluation

Les modèles d’évaluation permettent d’évaluer le niveau de compétence réel d’une personne, le niveau qu’ils doivent atteindre, ou le niveau de compétence nécessaire pour une tâche. Un facteur est affecté à chaque niveau dans un modèle de classement.

1. Dans l’espace de travail, **Perfectionnement de l’employé**, sélectionnez **Liens**.

2. Sous **Configuration des compétences**, sélectionnez **Modèles d’évaluation**.

3. Sélectionnez **Nouveau**.

4. Complétez les champs suivants :

   - **Évaluation** : entrez un nom pour le modèle d’évaluation, tel que **Compétences**.
   - **Description** : entrez une description pour le modèle d’évaluation, telle que **Évaluations des compétences**.

5. Dans la section **Niveaux**, sélectionnez **Nouveau**. Pour chaque niveau que vous souhaitez ajouter, complétez les champs suivants :

   - **Niveau** : entrez un nom pour le niveau.
   - **Description** : entrez une description pour le niveau.
   - **Facteur** : entrez une valeur de facteur comprise entre 0 et 9. Les facteurs aident à normaliser les scores de compétences qui utilisent différents modèles d’évaluation. Chaque niveau doit avoir un facteur unique. Les niveaux avec des valeurs de facteur plus élevées ont plus de poids dans un modèle de classement.

   Continuez à ajouter des niveaux si nécessaire. Vous pouvez entrer jusqu’à 10 niveaux pour chaque modèle d’évaluation.

6. Sélectionnez **Enregistrer**.

## <a name="create-a-skill"></a>Créer une compétence

Avant d’affecter une compétence, de créer une recherche par mise en correspondance des compétences ou de créer un profil de compétence, vous devez entrer des informations sur les compétences dans la page **Compétences**. Pour chaque compétence, vous pouvez sélectionner un type de compétence et un modèle de classement.

1. Dans l’espace de travail, **Perfectionnement de l’employé**, sélectionnez **Liens**.

2. Sous **Configuration des compétences**, sélectionnez **Compétences**.

3. Sélectionnez **Nouveau**.

4. Complétez les champs suivants :

   - **Compétence** : entrez un nom pour la compétence.
   - **Description** : entrez une description pour la compétence.
   - **Évaluation** : sélectionnez le modèle d’évaluation que vous souhaitez utiliser pour cette compétence.
   - **Type de compétence** : sélectionnez une option dans la liste des types de compétences.

5. Sélectionnez **Enregistrer**.

## <a name="see-also"></a>Voir également :

[Saisir les compétences](hr-develop-enter-skills.md)<br>
[Mettre en correspondance les compétences](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]