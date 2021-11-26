---
title: Mettre à jour les informations relatives aux blessures et aux maladies des employés
description: Cette tâche décrit comment créer un incident de blessure ou de maladie.
author: twheeloc
ms.date: 11/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMInjuryIncident, HcmWorkerLookUp, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c351919616c8ab5cf15d14c6cc79a5097e248fc
ms.sourcegitcommit: 7e0e2a266d9a9473df72e207554d9bd150e17ce3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/05/2021
ms.locfileid: "7771253"
---
# <a name="maintain-employee-injury-and-illness-information"></a>Mettre à jour les informations relatives aux blessures et aux maladies des employés

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Il est recommandé de terminer d’abord le guide de tâche « Paramétrer les informations sur les blessures et les maladies », car certaines des informations de paramétrage sont utilisées ici. 



Cette enregistrement de tâche décrit les étapes de base pour la création d’un incident de blessure ou de maladie. En plus des détails de la blessure ou de la maladie, un statut d’incident est suivi. Par défaut, les incidents ont un statut de **Ouvert**. Vous pouvez gérer les statuts à partir de l’option de menu **Statut de l’incident** en haut de la page.

1. Accédez à **Ressources humaines \> Collaborateurs \> Blessures et maladies \> Blessures ou maladies**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Description de l’incident**, entrez une valeur (par exemple **Blessure au poignet**).
4. Dans le champ **Collaborateur**, entrez ou sélectionnez une valeur (par exemple **Ana Bowman**).
5. Dans le champ **Date et heure de l’incident**, saisissez une date et une heure (par exemple, le 20 janvier 2016, à 10 h 00).
6. Dans le champ **Type de blessure et de maladie**, saisissez ou sélectionnez une valeur (par exemple **Fracture**).
7. Dans le champ **Partie du corps**, entrez ou sélectionnez une valeur (par exemple **Poignet**).
8. Dans le champ **Type de résultat**, saisissez ou sélectionnez une valeur (par exemple, **Rééducation**).
9. Dans le champ **Date et heure déclarées**, spécifiez une date et une heure.

    La date et l’heure déclarées doivent être postérieures à la date et l’heure de l’incident.

10. Dans le champ **Personne ayant signalé l’incident**, saisissez ou sélectionnez une valeur (par exemple **Ana Bowman**).

    La personne en question peut être l’employé ou un autre témoin de l’incident.

11. Dans la section **Incident**, dans le champ **Lieu de l’incident**, saisissez une valeur (par exemple, **Entrepôt**).
12. Dans le champ **Sur le lieu de travail**, sélectionnez **Oui** si l’incident s’est produit sur le lieu de travail.
13. Dans le champ **Date et heure de début de travail**, entrez la date et l’heure auxquelles la personne concernée a commencé à travailler avant que l’incident ne se produise.
14. Dans le champ **Travail ou tâche de l’employé**, saisissez le travail ou la tâche que le collaborateur effectuait lorsque l’incident s’est produit (par exemple, **Chargement de boîte**). 
15. Dans le champ **Cause de l’incident**, saisissez la cause de l’incident (par exemple, **A glissé sur un sol mouillé**).
16. Dans le champ **Niveau de gravité**, saisissez ou sélectionnez une valeur.
17. Dans le champ **Mesures à prendre**, saisissez une valeur (par exemple, **Nettoyer les écoulements rapidement**).
18. Dans le champ **Jours d’absence prévus**, entrez le nombre de jours pendant lesquels la personne devrait s’absenter du travail.

    Une fois que la personne reprend le travail, mettez à jour le champ **Jours d’absence du travail** avec le nombre de jours d’absence réel.

19. Dans la section **Coûts de la blessure ou de la maladie**, sélectionnez **Ajouter**.
20. Entrez une date dans le champ **Date**.
21. Dans le champ **Type de coût**, saisissez ou sélectionnez une valeur (par exemple, **Rééducation**).

    Vous pouvez également spécifier un montant, et joindre au coût tout document justificatif du coût (par exemple des factures ou des prescriptions du docteur).

22. Sélectionnez **Ajouter**.
23. Entrez une date dans le champ **Date**.
24. Dans le champ **Type de coût**, saisissez ou sélectionnez une valeur (par exemple, **Docteur**).
25. Dans la section **Traitements de blessure ou de maladie**, sélectionnez **Ajouter**.
26. Dans le champ **Date de traitement**, entrez une date et une heure.
27. Dans le champ **Type de traitement**, saisissez ou sélectionnez une valeur (par exemple, **Attelle**).
28. Facultatif : Définissez la section **Consultation aux urgences de l’hôpital** sur **Oui**.
29. Dans le champ **Commentaires sur le traitement**, saisissez ou sélectionnez une valeur (par exemple, **Attelle pendant 2 semaines**).
30. Dans le champ **Nom du médecin**, entrez une valeur (par exemple **Dr. Anderson**).
31. Dans le champ **Établissement et lieu du traitement**, saisissez une valeur (par exemple, **Urgences de la rue Rousseau**).
32. Dans le champ **Détails du traitement**, saisissez une valeur (par exemple, **La radiographie confirme la fracture, porte une attelle**).
33. Cliquez sur **Enregistrer**.

Vous pouvez mettre à jour le statut du dossier à tout moment. Si le traitement de la blessure ou de la maladie est en cours, définissez le statut sur **En cours**. Une fois que vous clôturez l’incident, vous pouvez uniquement ajouter ou supprimer des coûts, des traitements ou des déclarations liés à l’incident. Pour modifier d’autres informations, vous devez rouvrir l’incident.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
