---
title: FAQ Mode de création de client asynchrone
description: Cet article répond aux questions fréquemment posées (FAQ) sur le mode de création d’un client asynchrone dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: 64c895fb9f3e55f7680759fa72626be6660aa67c
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690200"
---
# <a name="asynchronous-customer-creation-mode-faq"></a>FAQ Mode de création de client asynchrone

[!include [banner](includes/banner.md)]

Cet article répond aux questions fréquemment posées (FAQ) sur le mode de création d’un client asynchrone dans Microsoft Dynamics 365 Commerce.

### <a name="why-cant-i-enable-the-enable-editing-customers-in-asynchronous-mode-feature"></a>Pourquoi ne puis-je pas activer la fonctionnalité « Activer la modification des clients en mode asynchrone » ?

Avant d’activer la fonctionnalité **Activer la modification des clients en mode asynchrone**, vous devez activer les fonctionnalités suivantes :

- Améliorations des performances pour les commandes client et les transactions client
- Activez la création de client asynchrone amélioré
- Activer la création asynchrone pour les adresses client

### <a name="why-do-i-still-see-real-time-service-calls-made-to-commerce-headquarters-after-the-enable-editing-customers-in-asynchronous-mode-feature-is-enabled"></a>Pourquoi est-ce que je continue de voir des appels de service en temps réel passés à Commerce headquarters après l’activation de la fonctionnalité « Activer la modification des clients en mode asynchrone » ?

Ce problème se produit lorsque les tâches Commerce Data Exchange (CDX) n’ont pas été exécutées pour garantir que l’état de la fonctionnalité et les autres métadonnées du canal sont synchronisées avec le canal. Avant de réessayer le scénario, assurez-vous que les tâches CDX suivantes sont exécutées dans Commerce headquarters :

- 1110 (Configuration globale)
- 1010 (Clients)
- 1070 (Configuration des canaux)

Les données mises en cache dans Commerce Scale Unit (CSU) peuvent ne pas être immédiatement répercutées dans Commerce headquarters après l’exécution des tâches CDX.

### <a name="why-doesnt-commerce-headquarters-show-customer-creation-or-updates-from-the-point-of-sale-pos-or-e-commerce-channel"></a>Pourquoi Commerce headquarters n’affiche-t-il pas la création ou les mises à jour des clients à partir du point de vente (PDV) ou du canal d’e-commerce ?

Assurez-vous que les actions suivantes ont été effectuées dans l’ordre répertorié ici.

1. Exécutez la tâche CDX P dans Commerce headquarters pour vous assurer que les données client asynchrones stockées dans les tableaux **RETAILASYNCCUSTOMERV2**, **RETAILASYNCADDRESSV2**, **RETAILASYNCCUSTOMERCONTACT**, **RETAILASYNCCUSTOMERAFFILIATION** et **RETAILASYNCCUSTOMERATTRIBUTEV2** sont disponibles dans Commerce headquarters.
1. Exécutez la tâche par lot **Synchroniser les demandes des clients et des canaux** dans Commerce headquarters. Après l’exécution réussie de la tâche par lots, tous les enregistrements qui ont été traités avec succès à partir des tableaux mentionnés précédemment auront le champ **OnlineOperationCompleted** défini sur **1**.

### <a name="how-do-i-know-which-customer-management-in-asynchronous-mode-operation-has-failed-and-how-do-i-make-changes-if-they-are-required"></a>Comment puis-je savoir quelle gestion des clients en mode asynchrone a échoué et comment puis-je apporter des modifications si elles sont nécessaires ?

Pour afficher toutes les opérations en mode asynchrone et leur état de synchronisation, dans Commerce headquarters, accédez à **Commerce et vente au détail \> Clients \> Statut de synchronisation client**. Pour apporter des modifications, modifiez une opération spécifique, mettez à jour les champs, sélectionnez **Enregistrer**, puis sélectionnez **Synchroniser** pour synchroniser les modifications.

