---
title: Gestion d'équipe et de tiroir-caisse
description: Cette rubrique explique comment paramétrer et utiliser les équipes dans Retail POS.
author: jblucher
manager: AnnBe
ms.date: 05/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailHardwareProfile, RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 105011
ms.assetid: 49a0fcc9-d4db-45ad-8c4b-213ccaced82b
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 7ad3c3fd17e88f364be12c122e2f5c155b7b9064
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "313012"
---
# <a name="shift-and-cash-drawer-management"></a>Gestion d'équipe et de tiroir-caisse

[!include [banner](includes/banner.md)]

Cette rubrique explique comment paramétrer et utiliser les équipes dans Retail POS.

Dans Microsoft Dynamics 365 for Retail, le terme *équipe* décrit l'ensemble des activités et des données de transaction POS entre deux périodes de temps. Pour chaque équipe, la somme d'argent attendue est comparée au montant comptabilisé et déclaré.

Généralement, les équipes sont ouvertes au début du jour ouvrable. À ce stade, un utilisateur déclare le montant de départ contenu dans le tiroir-caisse. Les transactions de vente sont ensuite exécutées tout au long de la journée. Enfin, à la fin de la journée, le tiroir-caisse est comptabilisé, et les montants de clôture sont déclarés. L'équipe est clôturée, et un Z de caisse est généré. Le Z de caisse indique s'il y a un excédent ou un déficit.

## <a name="typical-shift-scenarios"></a>Scénarios d'équipe courants

Retail propose plusieurs options de configuration et opérations POS pour prendre en charge un large éventail de processus d'entreprise de clôture de caisse pour le POS. Cette section décrit certains scénarios d'équipe courants.

### <a name="fixed-till"></a>Tiroir-caisse fixe

Traditionnellement, ce scénario a été utilisé le plus souvent. Il est toujours largement utilisé. Dans une équipe « tiroir-caisse fixe », l'équipe et le tiroir-caisse sont associés à une caisse enregistreuse spécifique. Ils ne sont pas déplacés d'une caisse enregistreuse à une autre. Une équipe « tiroir-caisse fixe » peut être utilisée par un seul utilisateur ou être partagée entre plusieurs utilisateurs. Les équipes « tiroir-caisse fixe » ne nécessitent pas de configuration spéciale.

### <a name="floating-till"></a>Tiroir-caisse flottant

Dans une équipe « tiroir-caisse flottant », l'équipe et le tiroir-caisse peuvent être déplacés d'une caisse enregistreuse à une autre. Bien qu'une caisse enregistreuse ne puisse avoir qu'une seule équipe active par tiroir-caisse, les équipes peuvent être suspendues puis reprises ultérieurement ou sur une autre caisse enregistreuse.

Par exemple, un magasin a deux caisses enregistreuses. Chaque caisse enregistreuse est ouverte au début de la journée lorsque le caissier ouvre une nouvelle équipe et indique le montant de départ. Lorsqu'un caissier est prêt à faire une pause, il suspend son équipe et retire le tiroir-caisse de la caisse enregistreuse. Cette caisse enregistreuse devient alors disponible pour d'autres caissiers. Un autre caissier peut se connecter et ouvrir sa propre équipe sur la caisse enregistreuse. Une fois que la pause du premier caissier est terminée, il peut reprendre son équipe lorsque l'une des autres caisses enregistreuses devient disponible. Les équipes « tiroir-caisse flottante » ne nécessitent pas de configuration ou d'autorisation spéciale.

### <a name="single-user"></a>Utilisateur unique

De nombreuses détaillants préfèrent autoriser un seul utilisateur par équipe, pour garantir le niveau de responsabilité le plus élevé pour les disponibilités dans le tiroir-caisse. Si un seul utilisateur est autorisé à utiliser le tiroir-caisse associé à une équipe, cet utilisateur peut être tenu pour seul responsable en cas d'écarts. Si plusieurs utilisateurs utilisent une équipe, il est difficile de déterminer qui a commis une erreur, ou qui tente de voler de l'argent dans la caisse.

### <a name="multiple-users"></a>Utilisateurs multiples

Certains détaillants préfèrent sacrifier le niveau de responsabilité qu'offrent les équipes à un seul utilisateur et autoriser plusieurs utilisateurs par équipe. Cette approche est courante lorsqu'il y a plus d'utilisateurs que de caisses enregistreuses disponibles, et la nécessité de faire preuve de flexibilité et de rapidité l'emporte sur le risque de perte. Elle permet également aux directeurs de magasin qui n'ont pas leurs propres équipes d'utiliser les équipes de leurs caissiers, si nécessaire. Pour se connecter et utiliser une équipe qui a été ouverte par un autre utilisateur, un utilisateur doit disposer de l'autorisation POS **Autoriser la connexion multiple de plusieurs équipes**.

### <a name="shared-shift"></a>Équipe partagée

Une configuration de type « équipe partagée » permet aux détaillants d'avoir une équipe unique pour plusieurs caisses enregistreuses, tiroirs-caisses et utilisateurs. Une équipe partagée a un montant de départ unique et un montant de clôture unique qui sont résumés sur tous les tiroirs-caisses. Les équipes partagées sont les plus courantes lorsque des appareils mobiles sont utilisés. Dans ce scénario, un tiroir-caisse distinct n'est pas réservé pour chaque caisse enregistreuse. À la place, toutes les caisses enregistreuses peuvent partager un tiroir-caisse.

Pour pouvoir utiliser les équipes partagées dans un magasin, le tiroir-caisse doit être configuré comme « tiroir-caisse partagé par l'équipe de travail » sous **Vente au détail \> Paramétrage de canal \> Paramétrage POS \> Profils POS \> Profils du matériel \>Tiroir-caisse**. En outre, les utilisateurs doivent disposer d'une ou des deux autorisations d'équipe partagées (Autoriser la gestion d'équipes de travail partagées et Autoriser l'utilisation d'équipes de travail partagées).

> [!NOTE]
> Une seule équipe partagée peut être ouverte à la fois dans chaque magasin. Les équipes partagées et les équipes autonomes peuvent être utilisées dans le même magasin.

## <a name="shift-and-drawer-operations"></a>Opérations liées aux équipes et tiroirs-caisses

Plusieurs opérations peuvent être effectuées pour modifier l'état d'une équipe ou pour augmenter ou diminuer la somme d'argent dans le tiroir-caisse. Cette section décrit ces opérations d'équipe pour Microsoft Dynamics 365 for Retail Modern POS et Cloud POS.

### <a name="open-shift"></a>Équipe de travail en cours

Le POS exige que les utilisateurs soient dans une équipe active et ouverte pour exécuter toutes les opérations débouchant sur une transaction financière comme une vente, un retour ou une commande client.

Lorsqu'un utilisateur se connecte au POS, le système vérifie d'abord si une équipe active est disponible pour cet utilisateur dans la caisse enregistreuse actuelle. Si une équipe active n'est pas disponible, l'utilisateur peut ouvrir une nouvelle équipe, reprendre une équipe existante ou se connecter en mode « hors tiroir-caisse », en fonction de la configuration du système et des autorisations de l'utilisateur.

### <a name="declare-start-amount"></a>Déclarer le montant de départ

Cette opération est souvent la première opération effectuée avec une équipe récemment ouverte. Pour cette opération, les utilisateurs spécifient le montant présent dans le tiroir-caisse en début d'équipe. Cette opération est importante, car le calcul de l'excédent ou du déficit qui se produit à la clôture d'une équipe tient compte du montant de départ.

### <a name="float-entry"></a>Entrée de fond de caisse

Les *entrées de fond de caisse* sont des transactions hors ventes qui sont effectuées au cours d'une équipe active et qui augmentent le montant des disponibilités dans le tiroir-caisse. Un exemple typique d'une entrée de fond de caisse est une transaction consistant à ajouter de la monnaie supplémentaire dans le tiroir-caisse quand celui-ci en manque.

### <a name="tender-removal"></a>Vider la caisse

Les *vidages de caisse* sont des transactions hors ventes qui sont effectuées au cours d'une équipe active et qui diminuent le montant des disponibilités dans le tiroir-caisse. Cette opération est le plus souvent utilisée conjointement à une opération d'entrée de fond de caisse dans une équipe différente. Par exemple, comme la caisse enregistreuse 1 manque de fonds, l'utilisateur de la caisse enregistreuse 2 effectue un vidage de caisse pour réduire le montant de son tiroir-caisse. L'utilisateur de la caisse enregistreuse 1 effectue ensuite une entrée de fond de caisse pour augmenter le montant de son tiroir-caisse.

### <a name="suspend-shift"></a>Suspendre l'équipe de travail

Les utilisateurs peuvent interrompre leur équipe active pour libérer la caisse enregistreuse actuelle pour un autre utilisateur, ou pour déplacer leur équipe vers une autre caisse enregistreuse (dans ce cas, l'équipe est souvent appelée une équipe « tiroir-caisse flottant »).

L'interruption d'une équipe empêche toute nouvelle transaction ou changement d'équipe jusqu'à ce qu'elle reprenne.

### <a name="resume-shift"></a>Reprendre une équipe de travail

Cette opération permet aux utilisateurs de reprendre une équipe précédemment interrompue sur une caisse enregistreuse qui n'a pas encore une équipe active.

### <a name="tender-declaration"></a>Comptage de caisse

Cette opération est effectuée pour spécifier la somme d'argent totale actuellement disponible dans le tiroir-caisse. Les utilisateurs effectuent souvent cette opération avant la clôture d'une équipe. Le montant spécifié est comparé au montant prévu de l'équipe pour calculer le montant de l'excédent ou du déficit.

### <a name="safe-drop"></a>Mise en coffre-fort

Les mises en coffre-fort peuvent être effectuées à tout moment pendant une équipe active. Cette opération permet de retirer l'argent du tiroir-caisse, afin qu'il puisse être transféré à un plus emplacement plus sûr tel qu'un coffre-fort dans une pièce à part. Le montant total enregistré pour les mises en coffre-fort est toujours inclus dans les totaux de l'équipe, mais il n'a pas besoin d'être comptabilisé comme faisant partie du comptage de caisse.

### <a name="bank-drop"></a>Remise en banque

Comme les mises en coffre-fort, les remises en banque sont effectuées pendant les équipes actives. Cette opération permet de retirer l'argent de l'équipe pour préparer le dépôt bancaire.

### <a name="blind-close-shift"></a>Clôturer l'équipe de travail en aveugle

Les *équipes clôturées en aveugle* ne sont plus actives mais n'ont pas été entièrement clôturées. Contrairement aux équipes interrompues, les équipes clôturées en aveugle ne peuvent pas être reprises. Toutefois, les opérations comme Déclarer le montant de départ et Comptage de caisse peuvent y être exécutées ultérieurement ou depuis une caisse enregistreuse distincte.

Les équipes clôturées en aveugle sont généralement utilisées pour libérer une caisse enregistreuse pour un nouvel utilisateur ou une nouvelle équipe, sans devoir d'abord entièrement recompter, rapprocher et clôturer l'équipe.

### <a name="close-shift"></a>Clôturer l'équipe de travail

Cette opération calcule les totaux d'équipe, les montants de l'excédent ou du déficit, puis finalise une équipe active ou clôturée en aveugle. Selon les autorisations de l'utilisateur, un Z de caisse est également imprimé pour l'équipe. Les équipes clôturées ne peuvent pas être reprises ou modifiées.

### <a name="print-x"></a>Imprimer X

Cette opération génère et imprime un X de caisse pour l'équipe active actuelle.

### <a name="reprint-z"></a>Réimprimer Z

Cette opération réimprime le dernier Z de caisse généré par le système lorsqu'une équipe a été clôturée.

### <a name="manage-shifts"></a>Gérer les équipes

Cette opération permet aux utilisateurs d'afficher toutes les équipes actives, interrompues et clôturées à l'aveugle du magasin. En fonction de leurs autorisations, les utilisateurs peuvent effectuer leurs procédures de clôture finale, telles que les opérations de comptage de caisse et de clôture d'équipe pour les équipes clôturées en aveugle. Cette opération permet également aux utilisateurs d'afficher et de supprimer les équipes non valides dans le cas rare d'équipes en mauvais état après avoir basculé entre les modes hors connexion et en ligne. Ces équipes non valides ne contiennent aucune information financière, ni donnée transactionnelle nécessaire pour le rapprochement.

## <a name="shift-and-drawer-permissions"></a>Autorisations pour les équipes et les tiroirs-caisses

Les autorisations POS suivantes affectent ce qu'un utilisateur peut et ne peut pas faire dans divers scénarios :

- **Autoriser la clôture en aveugle**
- **Autoriser l'impression du X de caisse**
- **Autoriser l'impression du Z de caisse**
- **Autoriser le comptage de caisse**
- **Autoriser la déclaration fond de caisse**
- **Ouvrir tiroir-caisse sans vente**
- **Autoriser la connexion multiple de plusieurs équipes** - Cette autorisation permet à l'utilisateur de se connecter et d'utiliser une équipe qui a été ouverte par un autre utilisateur. Les utilisateurs qui ne disposent pas de cette autorisation peuvent se connecter et utiliser uniquement les équipes qu'ils ont ouvertes.
- **Autoriser la gestion d'équipes de travail partagées** – Les utilisateurs doivent disposer de cette autorisation pour ouvrir ou fermer une équipe partagée.
- **Autoriser l'utilisation d'équipes de travail partagées** – Les utilisateurs doivent disposer de cette autorisation pour se connecter et utiliser une équipe partagée.

## <a name="back-office-end-of-day-considerations"></a>Considérations relatives à la clôture de caisse dans l'arrière-guichet

La façon dont les équipes et le rapprochement des tiroirs-caisses sont utilisés dans le POS diffère de la façon dont les données de transaction sont résumées lors du calcul des relevés. Il est important que vous compreniez cette différence. Selon votre configuration et vos processus d'entreprise, les données d'équipe dans le POS (Z de caisse) et un relevé calculé dans l'arrière-guichet peuvent donner des résultats différents. Cette différence ne signifie pas nécessairement que les données d'équipe ou le relevé calculé sont incorrectes, ou encore que les données présentent un problème. Cela signifie simplement que les paramètres fournis peuvent inclure des transactions supplémentaires ou moins de transactions, ou que les transactions ont été résumées différemment.

Bien que chaque détaillant a ses propres exigences métier, nous vous recommandons de paramétrer votre système de la façon suivante afin d'éviter les situations où des différences de ce type se produisent :

Accédez à **Vente au détail \> Canaux \> Magasins de vente au détail \> Tous les magasins de vente au détail \> Relevé/clôture**et, pour chaque magasin, définissez le champ **Méthode de relevé** et le champ **Méthode de clôture** sur **Équipe**.

Ce paramétrage permet de garantir que les relevés de l'arrière-guichet incluent les mêmes transactions que les équipes du POS, et que les données sont résumées en fonction de cette équipe.

Pour plus d'informations sur les méthodes de relevé et de clôture, voir [Enregistrer les configurations pour les relevés de vente au détail](https://docs.microsoft.com/dynamics365/unified-operations/retail/tasks/store-configurations-retail-statements).
