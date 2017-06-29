---
title: "Gestion de la non-conformité"
description: "Cet article décrit le paramétrage de base requis afin d'utiliser les non-conformités. Un paramétrage supplémentaire est requis si vous souhaitez utiliser des ordres de qualité."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 28951
ms.assetid: a62d4ba8-eebc-4b14-b587-630be7298522
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 4aebabfc6160393e5c817cd07af835d3b1268c2e
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="nonconformance-management"></a>Gestion de la non-conformité

[!include[banner](../includes/banner.md)]


Cet article décrit le paramétrage de base requis afin d'utiliser les non-conformités. Un paramétrage supplémentaire est requis si vous souhaitez utiliser des ordres de qualité. 

Pour activer la gestion de non-conformité, procédez comme suit :

1.  Définissez les paramètres de gestion des entrepôts et des stocks liés aux non-conformités.
    -   Définissez l'option **Utiliser la gestion de la qualité** sur **Oui**.
    -   Dans le champ **Taux horaire**, entrez un taux horaire de main-œuvre dans la devise locale. Le taux horaire permet de calculer les coûts des opérations associées à une non-conformité. Le taux horaire et les coûts calculés fournissent des informations de référence pour une non-conformité. Ils n'interagissent pas avec les autres fonctionnalités.
    -   Utilisez l'onglet **Gestion de la qualité** dans la page **Paramétrage d'état** pour définir le type de document à imprimer. Vous pouvez imprimer un état de non-conformité, une balise de non-conformité ou un état des corrections. Vous pouvez définir plusieurs enregistrements pour l'impression de divers types de documents dans un état ou pour l'impression de notes internes et externes. Il peut être utile d'utiliser la page **Type de document** pour définir un type de document unique pour les non-conformités et un type de document unique pour les corrections. Par exemple, si vous souhaitez entrer des commentaires sur une non-conformité à l'aide du type de document unique pour les non-conformités. Vous devez identifier le type de document unique dans les options des états.
    -   Activez les souches de numéros pour la non-conformité et les références de correction.

2.  Activez l'approbation des utilisateurs pour les non-conformités. Utilisez le champ **Nom** de la page **Utilisateurs** pour affecter un employé à chaque utilisateur chargé d'approuver une non-conformité. Le système utilise les employés qui modifient le statut d'une non-conformité pour suivre l'historique des non-conformités. Les utilisateurs ne peuvent pas approuver une non-conformité sauf si un identificateur d'employé leur a été affecté.
3.  Définissez les types de problèmes qui seront affectés aux non-conformités. Utilisez la page **Types de problèmes** pour définir une classification des problèmes de qualité rencontrés pour les divers types de non-conformités. Vous pouvez paramétrer les types de non-conformités suivants : **Interne**, **Client**, **Fournisseur**, **Demande de service**, **Production** et **Production de coproduits**. Utilisez le page **Types de non-conformités** pour autoriser l'utilisation d'un type de problème dans un ou plusieurs types de non-conformités. Par exemple, un type de problème en lien avec un code défaut peut s'appliquer à tous les types de non-conformités, alors qu'un type de problème en lien avec la réclamation d'un client peut s'appliquer uniquement aux types de non-conformités **Client** et **Demande de service**.
4.  Définissez des zones de quarantaine afin de fournir des instructions en relation avec la gestion des matières défectueuses. Utilisez la page **Zones de quarantaines** pour définir les zones pouvant être affectées à une non-conformité. La balise de non-conformité imprimée indique la zone de quarantaine affectée et les informations relatives à l'utilisation, afin de fournir des instructions sur la gestion des matières défectueuses. Les zones peuvent correspondre à des emplacements de stockage ou à des ressources opérationnelles.
5.  Définissez les types de diagnostics qui seront affectés aux corrections. Utilisez la page **Types de diagnostics** pour définir une classification des actions de diagnostic. Une correction spécifie le type d'action de diagnostic à prendre pour une non-conformité approuvée, ainsi que la personne qui doit exécuter cette action. Elle spécifie également la date de fin demandée et la date de fin prévue.
6.  Définissez les opérations associées qui seront affectées aux non-conformités. Utilisez la page **Opérations** pour définir une classification des tâches pouvant être exécutées pour une non-conformité approuvée. Lorsque vous affectez une opération associée à une non-conformité, vous pouvez également fournir des informations détaillées, notamment sur la matière, les heures travaillées et charges diverses associées requises pour l'exécution de l'opération. Ces informations servent à calculer le coût estimé de l'opération. Les informations détaillées et les coûts estimés sont fournis à titre de référence. Les opérations associées pour la qualité diffèrent des opérations pouvant être définies pour une gamme de production.


<a name="see-also"></a>Voir également :
--------

[Créer et traiter une non-conformité (guide de tâche)](https://ax.help.dynamics.com/en/wiki/create-and-process-a-nonconformance/)

[Processus de gestion de la qualité](quality-management-processes.md)

[Paramétrer des conditions préalables pour la gestion de la non-conformité (guide de tâche)](https://ax.help.dynamics.com/en/wiki/set-up-prequisites-for-nonconformance-management/)




