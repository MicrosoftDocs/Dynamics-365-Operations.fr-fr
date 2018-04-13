---
title: "Définition des paramètres de RH spécifiques à la société"
description: "Les réglages de certains paramètres des Ressources humaines (RH) sont partagés entre des sociétés, alors que les réglages d'autres paramètres sont spécifiques à la société. Cet article décrit comment définir les paramètres RH spécifiques à la société."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HRMParameters
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c280b5ae3b8fc208759ec486db0a1015a9c24633
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-company-specific-hr-parameters"></a>Définition des paramètres de RH spécifiques à la société

[!INCLUDE [banner](includes/banner.md)]

Les réglages de certains paramètres des Ressources humaines (RH) sont partagés entre des sociétés, alors que les réglages d'autres paramètres sont spécifiques à la société. Cet article décrit comment définir les paramètres RH spécifiques à la société.

Deux pages permettent de définir les paramètres de Ressources humaines (RH). Pour les paramètres communs à des sociétés, vous utilisez la page **Paramètres partagés de ressources humaines**. Pour les paramètres qui sont spécifiques à une société (en d'autres termes, les paramètres s'appliquent à une seule société), vous utilisez la page **Paramètres de ressources humaines**. Sur la page **Paramètres de Ressources humaines**, les paramètres sont répartis sur six onglets :

-   Général
-   Recrutement - Cette fonctionnalité n'est pas incluse dans Dynamics 365 for Talent
-   Rémunération
-   Souches de numéros
-   Family and Medical Leave Act (FMLA)
-   Libre-service employé

Chaque onglet contient les informations qui concernent une seule société. Les paramètres de l'onglet **Général** définissent l'apparence des informations relatives à l'absence, la blessure ou la maladie, et les nouvelles embauches. Les paramètres sous cet onglet définissent également certains entrées par défaut qui s'affichent au fur et à mesure que vous travaillez. Plus particulièrement, cet onglet vous permet de sélectionner une couleur à appliquer aux transactions d'absence en cours, de spécifier la feuille de style à utiliser pour les états, d'activer l'intégration entre les cours de formation et l'enregistrement d'absence et de sélectionner le code absence utilisé pour contrôler cette intégration. Vous pouvez également indiquer combien de temps les incidents de blessure et de maladie doivent être conservés, puis spécifier le numéro d'identification par défaut qui s'affiche lorsqu'un nouveau collaborateur est engagé. 

Les paramètres de l'onglet **Recrutement** définissent les types de documents utilisés pour la correspondance qui est automatiquement envoyés aux candidat, et le projet de recrutement utilisé pour les candidatures spontanées (les candidatures qui ne concernent pas un projet de recrutement spécifique). La période définie pour le projet de recrutement âgé détermine les projets de recrutement inclus dans la vignette **Projets âgés** de l'espace de travail **Gestion des recrutements**. La période définie pour l'avertissement de la date limite de candidature est utilisée pour afficher les projets de recrutement qui approchent leur date limite de candidature dans la vignette **Date limite de candidature qui approche** de l'espace de travail **Recrutement**. 

Les paramètres de l'onglet **Rémunération** définissent si les utilisateurs doivent confirmer qu'ils souhaitent enregistrer des informations pour un régime de rémunération fixe ou variable. Si vous cochez la case **Activer le contrôle de l'enregistrement**, l'utilisateur reçoit un message lui demandant sil souhaite enregistrer l'enregistrement chaque fois qu'il utilise une page associée à la rémunération. Certaine pages de la gestion des rémunérations ne permettent pas aux utilisateurs de supprimer les informations. Par conséquent, en invitant les utilisateurs à confirmer qu'ils souhaitent enregistrer les informations, vous pouvez restreindre la quantité d'informations enregistrées sans possibilité de suppression ultérieure. Si la case **Activer le contrôle de l'enregistrement** décochée, les enregistrements sont toujours sauvegardés immédiatement, peut-être avant que l'utilisateur soit prêt. Si vous utilisez la gestion des performances, l'onglet **Rémunération** vous permet de sélectionner un modèle de classement à utiliser à la place du modèle affecté aux régimes de rémunération lors du classement des performances. 

### <a name="previously-released-functionality"></a>Fonctionnalité précédemment lancée
Les paramètres de l'onglet **Souche de numéros** déterminent les souches de numéros utilisées pour affecter automatiquement des identificateurs aux éléments du module Ressources humaines (candidatures, enregistrements d'absence, résultats des processus de rémunération, numéros d'incidents, cours et emplois du temps des cours). Pour tenir à jour les références et codes des souches de numéros, utilisez la page de liste **Souches de numéros** (cliquez sur **Administration d'organisation** &gt; **Souches de numéros** &gt; **Souches de numéros**).

### <a name="if-youre-using-dynamics-365-for-talent"></a>Si vous utilisez Dynamics 365 for Talent
Les paramètres de l'onglet **Souche de numéros** déterminent les souches de numéros utilisées pour affecter automatiquement des identificateurs aux éléments du module Ressources humaines (candidatures, enregistrements d'absence, résultats des processus de rémunération, numéros d'incidents, cours et emplois du temps des cours). Pour tenir à jour les références et codes des souches de numéros, utilisez la page de liste **Souches de numéros** (cliquez sur **Administration système** &gt; **Onglet Liens** &gt; **Souches de numéros** &gt; **Souches de numéros**). 

Les paramètres de l'onglet **FMLA** définissent le nombre d'heures qu'un employé doit travailler afin d'être éligible aux avantages FMLA, la durée de travail requise pour l'octroi des droits, et la date de début d'emploi utilisée pour déterminer la durée de l'emploi. Les paramètres définissent également le nombre d'heures FMLA auquel les employés ont droit et le calendrier de congé FMLA utilisé pour calculer le nombre d'heures FMLA que les employés ont utilisées. L'onglet **FMLA** est uniquement disponible pour les sociétés basées aux états-unis. 

**Remarque :** le nombre d'heures travaillées ne peut pas dépasser 1 250, et la durée de l'emploi ne peut pas dépasser 12 mois. Ces valeurs maximales sont conformes à la législation fédérale des États-Unis. Enfin, les paramètres de l'onglet **Libre-service employé** déterminent les informations qu'un responsable peut entrer au nom de ses employés.

<a name="see-also"></a>Voir également :
--------

[Configuration des paramètres de RH dans les entités juridiques](set-up-hr-parameters-across-legal-entities.md)




