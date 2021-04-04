---
title: Définir le processus de rémunération et calculer les résultats
description: Des processus de rémunération permettent de déterminer de nouveaux montants et primes de rémunération pour les employés inscrits aux régimes de rémunération fixes et variables.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompProcess, HRMCompProcessLine, HRMCompEvent, HRMCompEventEmpl, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3564e7807ed81684d51de3185cea9b4f35f38d8b
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468273"
---
# <a name="define-compensation-process-and-calculate-results"></a>Définir le processus de rémunération et calculer les résultats

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Des processus de rémunération permettent de déterminer de nouveaux montants et primes de rémunération pour les employés inscrits aux régimes de rémunération fixes et variables. Vous pouvez exécuter les processus de rémunération plusieurs fois afin d’effectuer une analyse d’hypothèse, et vérifier ainsi que toutes les modifications et tous les paramètres sont corrects. Cette procédure crée un processus de rémunération, exécute le processus, et affiche les résultats. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="create-a-compensation-process"></a>Créer un processus de rémunération
1. Accédez à Ressources humaines > Rémunération > Processus > Processus de rémunération.
2. Cliquez sur Nouveau.
3. Dans le champ Processus, tapez une valeur.
4. Dans le champ Description, entrez une valeur.
5. Dans le champ Type de processus, sélectionnez une option.
    * Un cycle spécifie la période évaluée pour déterminer la rémunération. L’évaluation prend en compte les postes détenus par les employés, les classements de résultats à inclure, le calcul du pourcentage de temps pendant lequel le collaborateur a été employé au cours du cycle, et plus encore. Un exemple d’une date de début de cycle peut être le premier jour du dernier exercice.  
6. Dans le champ Début de cycle, entrez une date.
    * La date de fin de cycle est importante car il s’agit de la date permettant de déterminer quels employés ont été en service actif et inscrits à un ou plusieurs régimes de rémunération.  
7. Dans le champ Fin de cycle, entrez une date.
    * La date active de transaction est la date à laquelle les nouveaux taux de rémunération doivent entrer en vigueur. De nombreuses sociétés incluent quelques mois entre la fin d’un cycle et la date à laquelle les nouveaux taux de rémunération entrent en vigueur. Le temps supplémentaire est utilisé pour traiter et examiner la nouvelle rémunération.  
8. Dans le champ Date de transaction active, entrez une date.
    * La date de moment donné est utilisée pour les régimes de rémunération variable qui déterminent le montant de la prime des employés en fonction de leur taux de rémunération à ce moment.  
    * La date d’embauche au pro rata du salaire fixe est utilisée avec les régimes de rémunération fixe, avec une règle d’embauche en pourcentage.  Les employés qui sont embauchés entre le début de cycle et la date d’embauche au pro rata du salaire fixe recevront 100 % de leur augmentation de rémunération calculée, plutôt qu’un pourcentage proportionnel.  
9. Dans le champ Paiement fixe au pro rata de la date d’embauche, entrez une date.
    * Le date limite de révision est la date à laquelle tous les résultats de processus doivent être examinés afin qu’ils puissent être chargés dans l’enregistrement de rémunération d’un employé avant la date active de transaction. Ce champ est fourni uniquement à titre indicatif.  
10. Dans le champ Examiner la date limite, entrez une date.
11. Cliquez sur Enregistrer.

## <a name="setup-the-compensation-plans-and-actions-for-a-compensation-process"></a>Configurer les régimes et actions de rémunération pour un processus de rémunération.
1. Cliquez sur Paramétrage.
    * La page de paramétrage permet de sélectionner les régimes à traiter dans le cadre de ce processus de rémunération, ainsi que les actions à entreprendre pour chaque régime.  
2. Dans le champ Régime, saisissez ou sélectionnez une valeur.
3. Cliquez sur Enregistrer.
4. Cliquez sur Ajouter.
5. Dans le champ Action, sélectionnez une action de type Capitaux propres.
6. Cliquez sur Ajouter.
7. Dans le champ Action, sélectionnez une action de type Mérite.
    * Les actions de rémunération peuvent être « chaînées » ensemble à l’aide du champ Utiliser le résultat précédent afin d’indiquer si l’action sélectionnée doit utiliser le salaire de base de l’employé ou le résultat de l’action précédente comme point de départ pour le calcul de cette action.  
8. Dans le champ Utiliser le résultat précédent, sélectionnez Oui.
9. Cliquez sur Ajouter.
10. Dans le champ Action, sélectionnez une action de type Générale.
    * Différents types d’action de rémunération activent différents champs. Pour un type d’action de rémunération générale, vous pouvez spécifier un pourcentage d’augmentation ou un montant d’augmentation.  
11. Sélectionnez l’option Sélectionner le montant de l’augmentation.
12. Dans le champ Montant de l’augmentation, entrez un nombre.
13. Cliquez sur Ajouter.
14. Dans le champ Action, sélectionnez une action de type Promotion.
    * La promotion et les types d’action Autre changement de niveau permettent aux utilisateurs permet d’effectuer des ajustements manuels à la rémunération d’employé. Les recommandations peuvent être activées pour ces types d’action, ainsi que pour d’autres types d’action afin de vous permettre de spécifier une nouvelle valeur de rémunération recommandée pour un employé.  
15. Cliquez sur Ajouter.
16. Sélectionnez une option dans le champ Type.
    * Les régimes de rémunération fixe et variable peuvent être exécutés dans le même processus de rémunération.  
17. Dans le champ Régime, saisissez ou sélectionnez une valeur.
    * Utilisez la case Activer le paiement basé sur les résultats pour déterminer si les montants de rémunération fixe et variable doivent être ajustés sur l’évaluation des performances d’un employé.  
    * Le chiffre peut être remplacé dans les régimes de rémunération variable.  
18. Cliquez sur Enregistrer.
19. Cliquez sur Ajouter.
20. Fermez la page.

## <a name="run-the-compensation-process"></a>Exécuter le processus de rémunération
1. Cliquez sur Exécuter le processus.
    * La commande Afficher les résultats du traitement vous permet d’afficher les messages de traitement pour le processus de rémunération complet lorsque le processus est terminé.  
2. Dans le champ Afficher les résultats du traitement, sélectionnez Oui.
3. Cliquez sur OK.

## <a name="view-the-results"></a>Afficher les résultats
1. Cliquez sur Résultats du processus.
2. Cliquez sur Résultats des employés.
3. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
4. Développez la section Rémunération fixe.
    * Développez les organisateurs pour afficher les résultats du processus. Si l’activation des recommandations est marquée pour une action de rémunération, les champs Recommandation sont activés pour cette action.  
5. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    * Vous pouvez afficher les résultats pour un seul employé en cliquant sur le bouton Afficher les résultats.  
    * Vous pouvez remplacer le montant de rémunération calculé en ajustant le pourcentage ou le montant de l’augmentation dans les champs de recommandation.  
6. Dans le champ Pourcentage recommandé, entrez un nombre.
7. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
8. Dans le champ Pourcentage recommandé, entrez un nombre.
    * La fonction Recalculer vous permet d’ignorer toutes modifications apportées à l’enregistrement existant et de générer un nouveau résultat de rémunération pour l’employé sélectionné.  
    * Lorsque toutes les modifications sont terminées pour un employé, modifiez le statut pour le définir à Approuvé.  
9. Cliquez sur Modifier le statut.
10. Cliquez sur Approuvé.
    * Une fois l’enregistrement approuvé, il peut être chargé vers l’enregistrement de rémunération officiel de l’employé. La nouvelle rémunération est effective dès la date de la transaction définie dans le processus de rémunération.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]