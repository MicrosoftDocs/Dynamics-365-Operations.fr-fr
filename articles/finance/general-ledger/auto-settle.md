---
title: Automatiser les lettrages comptables
description: Cet article fournit des informations générales sur l’automatisation du processus de lettrages comptables.
author: abruer
ms.date: 9/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: b43eeeefa581b5d8b40dc2cf0187c7c781b18be3
ms.sourcegitcommit: 27ce4fc706100b626b81c3a1023238acd872e76c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2022
ms.locfileid: "9708329"
---
# <a name="automate-ledger-settlements"></a>Automatiser les lettrages comptables

[!include [banner](../includes/banner.md)]

Dans Microsoft Dynamics 365 Finance, version 10.0.31, la fonctionnalité  **Automatiser le processus de lettrages comptables** est disponible dans l’espace de travail  **Gestion des fonctionnalités** . Vous pouvez activer la fonctionnalité **Automatiser le processus de lettrages comptables** uniquement si la fonctionnalité **Reconnaissance entre un lettrage comptable et la clôture de fin d’exercice** a été activée.

Le règlement comptable désigne le processus de mise en correspondance des transactions de débit et de crédit dans la comptabilité. Les organisations qui effectuent des activités de lettrage comptable selon un calendrier récurrent peuvent désormais automatiser le processus. Au cours du processus automatique de lettrage comptable, une transaction de débit et une transaction de crédit ne peuvent être rapprochées automatiquement que si leurs montants dans la devise comptable sont égaux.Par exemple, un montant débiteur de 1 USD peut être automatiquement mis en correspondance avec un montant créditeur de 1 USD. Cependant, une valeur de débit de 1 USD ne peut pas être automatiquement associée à deux crédits, dont chacun est évalué à 0,50 USD. La correspondance partielle des montants des transactions comptables n’est pas prise en charge.

L’automatisation du lettrage comptable définit les détails suivants :

- À quel moment les lettrages comptables sont exécutés
- Quels critères sont utilisés pour faire correspondre les débits et les crédits susceptibles de faire l’objet d’un lettrage comptable automatique
- Dans quel ordre les informations de lettrage comptable sont traitées

## <a name="define-the-occurrence-of-ledger-settlements"></a>Définir l’occurrence des lettrages comptables

L’automatisation du lettrage comptable utilise le cadre d’automatisation des processus. Différents processus métier utilisent ce cadre pour définir la récurrence d’un processus sélectionné. Pour les lettrages comptables, accédez à  **Administration système \> Configurer \> Automatisations de processus** ou **Comptabilité \> Configuration comptable \> Automatisations de processus**.

Commencez par sélectionner l’option  **Créer une nouvelle automatisation de processus**, puis sélectionnez  **Lettrages comptables**. Un assistant vous guide ensuite dans le processus de configuration de l’automatisation.

## <a name="general-page"></a>Page Général

Sur la page  **Général**  de l’assistance, entrez le nom de l’occurrence de lettrage comptable créée. Par exemple, si vos débits et crédits correspondants sont lettrés dans la comptabilité le lundi, entrez un nom descriptif tel que  **Lettrage Comptable\_Lun**. Le nom que vous entrez s’affiche dans la colonne **Règle d’automatisation** sur la page  **Lettrages comptables** .

Les autres paramètres de la page sont génériques et sont utilisés pour définir le schéma d’occurrence de cette version des lettrages comptables. Par exemple, si une occurrence est pour le lundi, vous pouvez la définir de sorte qu’elle s’exécute chaque semaine et vous pouvez sélectionner le lundi comme jour de la semaine où elle s’exécute. Vous pouvez également saisir une heure de programmation anticipée, telle que 02h00, afin que l’automatisation du processus soit terminée avant le début du jour ouvrable suivant. Nous vous recommandons de programmer l’automatisation du processus de façon à ce que celui-ci soit effectué en dehors de vos heures de travail normales. Vous contribuez ainsi à réduire l’impact sur votre personnel comptable pendant la journée de travail.

Pour plus d’informations sur les autres champs de la page **General** , voir la documentation de l’automatisation des processus.

## <a name="ledger-settlements-match-criteria-page"></a>Page des critères de correspondance des lettrages comptables

La page suivante de l’assistant est  **Critères de correspondance des lettrages comptables** . Elle permet de définir les comptes principaux qui sont inclus dans l’occurrence d’automatisation de processus, ainsi que les critères utilisés afin de déterminer les débits et les crédits correspondants.

### <a name="account-selection"></a>Sélection de compte

Les comptes principaux que vous avez précédemment définis comme comptes de lettrage comptable pour l’entité juridique sont affichés. (Vous définissez les comptes principaux comme comptes de lettrage comptable en accédant à **Comptabilité \> Configuration comptable \> Paramètres comptables \> Lettrages comptables**.)

### <a name="main-account-and-posting-layer"></a>Compte principal et couche de validation

Les valeurs de  **Compte principal** et **Couche de validation**  sont des critères de correspondance obligatoires. Les valeurs de **Compte principal** et **Couche de validation** des transactions de débit et de crédit comptables doivent être égales pour pouvoir être mises en correspondance pendant le processus de lettrage comptable automatique.

### <a name="posting-type"></a>Type de validation

Sélectionnez l’option **Type de validation** si les transactions de débit et de crédit de comptabilité doivent avoir le même type de validation pour pouvoir être mises en correspondance pendant le processus de lettrage comptable automatique.

### <a name="financial-dimensions"></a>Dimensions financières

Sélectionnez l’option **Dimensions financières** si les transactions de débit et de crédit de comptabilité doivent avoir les mêmes dimensions financières pour pouvoir être mises en correspondance pendant le processus de lettrage comptable automatique. Lorsque cette option est sélectionnée, les critères des valeurs de dimension financière doivent être sélectionnés dans la liste **Dimensions financières disponibles**. La liste **Dimensions financières disponibles** ne contient pas la dimension du compte principal, car elle est automatiquement requise dans le cadre des critères de correspondance.

## <a name="view-the-results-of-a-ledger-settlement-automation"></a>Afficher les résultats d’une automatisation de lettrage comptable

Une fois la série d’automatisation de lettrage comptable créée, les occurrences de chaque lettrage comptable sont affichées dans la vue hebdomadaire de l’automatisation des processus. De plus, l’état de chaque occurrence est affiché. Les statuts suivants sont utilisées :

- **Programmé** – L’automatisation est programmée, mais elle n’a pas encore été exécutée.
- **En cours d’exécution** – L’automatisation est en cours d’exécution.
- **Erreur** – L’automatisation a été exécutée, mais une erreur s’est produite. Vous pouvez afficher les erreurs en sélectionnant le bouton  **Afficher les résultats** .
- **Terminé** – L’automatisation a été exécutée avec succès. Vous pouvez consulter les résultats du lettrage sur la page **Lettrages comptables**.

Pour afficher les résultats correspondants, accédez à **Comptabilité \> Tâches périodiques \> Lettrages comptables**. Le champ **Règle d’automatisation** sur la page **Lettrages comptables** affiche le nom de la tâche planifiée de lettrage comptable qui a été utilisé pour lettrer la transaction. Les tentatives de lettrage infructueuses ne mettent pas à jour la valeur **Règle d’automatisation**. Si vous annulez manuellement une transaction qui a été précédemment lettrée avec succès par le processus d’automatisation, la valeur **Règle d’automatisation** est supprimée.

Le champ **Date de lettrage** des enregistrements correspondants indique la date à laquelle le processus d’automatisation a été exécuté.

## <a name="editing-a-ledger-settlement-automation"></a>Modification de l’automatisation d’un lettrage comptable

Le cadre d’automatisation des processus vous permet de modifier le paiement, la série et les occurrences créées pour le lettrage comptable. La série peut être éditée à partir de la page **Automatisation des processus**  ou de la vue hebdomadaire de l’automatisation des processus. Par exemple, si le responsable décide d’effectuer le lettrage comptable le mercredi au lieu du lundi, il peut rechercher une occurrence dans la vue hebdomadaire et sélectionner  **Afficher/Modifier – Série**.

Si vous modifiez une série, vous êtes invité à spécifier si la modification doit être apportée à toutes les occurrences existantes ou uniquement aux nouvelles occurrences. Les occurrences historiques qui ont déjà le statut **Terminé** ou qui ont abouti à un statut  **Erreur**  ne seront pas modifiées.

Vous pouvez également ajouter une nouvelle occurrence ou modifier une occurrence existante. Par exemple, la prochaine occurrence de lettrage comptable doit avoir lieu le mercredi 1er janvier, mais cette date est un jour férié. Vous pouvez modifier l’occurrence à partir de la page  **Automatisation des processus**  ou de la vue hebdomadaire de l’automatisation des processus. Une page s’ouvre qui affiche les détails de la programmation et les critères de correspondance. Ici, vous pouvez modifier l’heure et la date programmées. Vous pouvez également modifier les critères de correspondance, si des modifications sont nécessaires. 

Vous pouvez également désactiver une occurrence ou une série. Pour désactiver une occurrence et suspendre son traitement, sélectionnez-la dans la vue hebdomadaire de l’automatisation des processus, puis sélectionnez  **Désactiver**. Vous pouvez désactiver une série sur la page **Automatisation des processus** .

## <a name="security-for-ledger-settlement-automation"></a>Sécurité de l’automatisation du lettrage comptable

La responsabilité **Gérer les paramètres de la série d’automatisation des lettrages comptables** a été ajoutée aux rôles de responsable comptable et de superviseur comptable, et la responsabilité **Afficher les paramètres de la série d’automatisation des lettrages comptables** a été ajoutée aux rôles de comptable, de responsable comptable et de superviseur comptable pour les automatisations des lettrages comptables. Ces responsabilités sont les paramètres de sécurité par défaut, mais ils peuvent être modifiés en fonction des exigences de votre organisation.

## <a name="general-ledger-parameters-for-ledger-settlement-automation"></a>Paramètres comptables pour l’automatisation du lettrage comptable

Le champ **Solde type du lettrage** indique l’ordre dans lequel le lettrage comptable automatique sera traité. Pour configurer ou afficher la valeur **Solde type du lettrage**, accédez à **Livre comptable \> Configurer \> Paramètres comptables**, puis sélectionnez l’onglet **Lettrages comptables**.

Si **Débit** est sélectionné, le processus de lettrage comptable automatisé démarre côté débit et recherche les crédits correspondants. Si **Crédit** est sélectionné, le processus de lettrage comptable automatisé démarre côté crédit et recherche les débits correspondants. Cette option doit refléter le solde type du compte principal.

## <a name="processing-a-ledger-settlement-automation"></a>Traitement de l’automatisation d’un lettrage comptable

Lorsque l’automatisation est exécutée, le système sélectionne les transactions comptables pour les comptes principaux définis pour la série d’automatisation de processus. Il classe les transactions par date, en utilisant une plage de dates allant du début de l’exercice à la date à laquelle l’automatisation du processus est exécutée. Il établit les correspondances en fonction des critères de correspondance spécifiés. Les valeurs absolues des montants en devise comptable du débit et du crédit doivent correspondre pour être lettrées.

Lorsqu’un compte principal est en cours de traitement par une occurrence d’automatisation du lettrage comptable, vous ne pouvez pas l’afficher dans la page **Lettrages comptables**. Vous devez attendre que le processus d’automatisation soit terminé. Nous vous recommandons de programmer l’automatisation du processus de façon à ce que celui-ci soit exécuté en dehors des heures de travail, afin d’éviter les conflits.

Le processus d’automatisation inclura toutes les transactions qui répondent aux critères, à l’exception des transactions qui ont été marquées manuellement pour le lettrage sur la page **Lettrages comptables**.

## <a name="reversal-of-transactions-that-are-settled-by-the-automation-process"></a>Annulation des transactions qui sont lettrées par le processus d’automatisation

Vous pouvez annuler un lettrage effectué par le processus de lettrage comptable automatisé. Lorsqu’une transaction qui a été précédemment lettrée avec succès par le processus d’automatisation est annulée, la valeur **Règle d’automatisation** est supprimée.
