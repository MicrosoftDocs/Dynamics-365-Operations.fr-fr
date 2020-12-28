---
title: Paramétrer des conditions préalables pour la gestion de la non-conformité
description: Utilisez cette rubrique pour activer les processus de gestion de la non-conformité.
author: perlynne
manager: tfehr
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, InventTestReportSetup, SysUserManagement, SysUserSetup, InventTestDiagnosticType, InventTestMiscCharges, InventTestOperation, InventProblemType, InventProblemTypeSetup, InventQuarantineZone
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8c4de822dcda604241416165a961e4b0bacaeb5b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428145"
---
# <a name="set-up-prerequisites-for-nonconformance-management"></a>Paramétrer des conditions préalables pour la gestion de la non-conformité

[!include [banner](../../includes/banner.md)]

Utilisez cette rubrique pour activer les processus de gestion de la non-conformité. Une non-conformité décrit une procédure ou un article présentant un problème qualitatif (des informations descriptives incluent la source et le type du problème). La société fictive USMF sert d'exemple dans cette procédure. Cette procédure est généralement effectuée par un responsable de la qualité.


## <a name="enable-quality-management-processes-within-the-company"></a>Activer les processus de gestion de la qualité au sein de la société
1. Dans le volet de navigation, allez dans **Modules > Gestion des stocks > Paramétrage > Paramètres de gestion des stocks et des entrepôts**.
2. Sélectionnez l'onglet **Gestion de la qualité**.
3. Sélectionnez **Oui** dans le champ **Utiliser la gestion de la qualité** pour activer les processus de gestion de la qualité pour la société.
4. Dans le champ **Taux horaire**, entrez un chiffre dans la devise locale. Le taux horaire permet de calculer les coûts des opérations associées à une non-conformité. Le taux horaire et les coûts calculés fournissent des informations de référence pour une non-conformité et n'interagissent pas avec les autres fonctionnalités.  
5. Sélectionnez **Paramétrage d'état** pour définir les types de note d'état de qualité qui seront utilisés dans différents types d'états de gestion de la qualité.

## <a name="enable-user-for-nonconformance-processing"></a>Activer l'utilisateur pour le traitement de non-conformité
1. Dans le volet de navigation, accédez à **Modules > Administration système > Utilisateurs > Utilisateurs**. 
2. Utilisez le filtre rapide pour rechercher l'utilisateur qui va approuver ou rejeter les enregistrements de non-conformité. Par exemple, filtrez sur le champ **Nom** avec une valeur de `Ricardo`. Pour traiter l'approbation d'une non-conformité, l'utilisateur qui approuve ou rejette la non-conformité doit avoir une valeur « Nom » affectée sur la page **Utilisateurs**. Pour utiliser les notes de document, l'utilisateur doit également avoir activé la gestion des documents dans les options d'utilisateur.  
3. Marquez la ligne de l'enregistrement souhaité.
4. Sélectionnez **Options utilisateur**.
5. Sélectionnez l'onglet **Préférences**.
6. Sélectionnez **Oui** dans le champ **Activer la gestion des documents**.

## <a name="define-diagnostic-types-for-nonconformance-processing"></a>Définir les types de diagnostics pour le traitement de non-conformité
1. Dans le volet de navigation, accédez à **Modules > Gestion des stocks > Paramétrage > Gestion de la qualité > Types de diagnostic**. Utilisez la page **Types de diagnostics** pour définir une classification des actions de diagnostic. Une correction identifie le type d'action de diagnostic devant être entreprise pour une non-conformité approuvée, l'utilisateur devant l'exécuter et la date d'exécution demandée et prévue.  
2. Sélectionnez **Nouveau**.
3. Dans le champ **Diagnostic**, tapez une valeur.
4. Tapez une valeur dans le champ **Description**.

## <a name="define-quality-charges-for-nonconformance-processing"></a>Définir les frais de qualité pour le traitement de non-conformité
1. Dans le volet de navigation, accédez à **Modules > Gestion des stocks > Paramétrage > Gestion de la qualité > Frais de qualité**. Utilisez la page **Frais de qualité** pour définir une classification des frais qui seront utilisés dans les opérations liées aux non-conformités.  
2. Sélectionnez **Nouveau**.
3. Dans le champ **Codes frais**, saisissez une valeur.
4. Tapez une valeur dans le champ **Description**.

## <a name="define-the-operations-for-nonconformance-processing"></a>Définir les opérations pour le traitement de non-conformité
1. Dans le volet de navigation, accédez à **Modules > Gestion des stocks > Paramétrage > Gestion de la qualité > Opérations**. Utilisez la page **Opérations** pour définir une classification des tâches pouvant être exécutées pour une non-conformité approuvée. Lorsque vous associez une opération associée à une non-conformité, vous pouvez définir des informations détaillées sur les matériaux, les heures travaillées et les charges diverses associées, requises pour l'exécution de l'opération. Ces informations constituent la base de calcul du coût estimé d'exécution de l'opération.  
2. Sélectionnez **Nouveau**.
3. Dans le champ **Opération**, saisissez une valeur.
4. Tapez une valeur dans le champ **Description**.

## <a name="define-problem-types-for-nonconformance-processing"></a>Définir les types de problème pour le traitement de non-conformité
1. Dans le volet de navigation, accédez à **Modules > Gestion des stocks > Paramétrage > Gestion de la qualité > Types de problème**. Utilisez la page **Types de problèmes** pour définir une classification des problèmes de qualité rencontrés dans les divers types de non-conformités. Parmi les types de non-conformités on trouve : **Interne**, **Client**, **Fournisseur**, **Demande de service**, **Production** et **Production de coproduits**. Un seul type de problème peut être associé à plusieurs types de non-conformités.  
2. Sélectionnez **Nouveau**.
3. Dans le champ **Type de problème**, saisissez une valeur.
4. Tapez une valeur dans le champ **Description**.
5. Sélectionnez **Types de non-conformités**. Utilisez la page **Types de non-conformités** pour autoriser l'utilisation d'un type de problème pour un ou plusieurs types de non-conformités. Par exemple, un type de problème en lien avec un code défaut peut s'appliquer à tous les types de non-conformités, alors qu'un type de problème en lien avec la réclamation d'un client peut uniquement s'appliquer aux types de non-conformités Client et Demande de service.  
6. Sélectionnez **Nouveau**.
7. Dans le champ **Type de non-conformité** de la nouvelle ligne, sélectionnez une option.

## <a name="define-quarantine-zones-for-nonconformance-processing"></a>Définir les zones de quarantaine pour le traitement de non-conformité
1. Dans le volet de navigation, accédez à **Modules > Gestion des stocks > Paramétrage > Gestion de la qualité > Zones de quarantaine**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Zone de quarantaine**, saisissez une valeur.
4. Tapez une valeur dans le champ **Description**.
5. Fermez la page.

