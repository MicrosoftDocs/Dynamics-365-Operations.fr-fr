---
title: Améliorations de la gestion des disponibilités
description: Cette rubrique décrit les améliorations de la gestion des disponibilités dans POS pour Dynamics 365 Commerce.
author: anpurush
ms.date: 05/21/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-21
ms.dyn365.ops.version: ''
ms.openlocfilehash: 509b70b65469bf14714ceaa390f450ddde1d8b76
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794395"
---
# <a name="cash-management-improvements"></a>Améliorations de la gestion des disponibilités

[!include [banner](includes/banner.md)]


La gestion des disponibilités est une fonction clé pour les détaillants dans les magasins physiques. Les détaillants souhaitent que leurs magasins aient des systèmes qui les aident à fournir la traçabilité et la responsabilité complètes des disponibilités et de leurs mouvements entre les différents caisses enregistreuses et les caissiers d’un magasin. Ils doivent pouvoir rapprocher les différences et déterminer la responsabilité.


Microsoft Dynamics 365 Commerce a des fonctionnalités de gestion des disponibilités dans application de point de vente POS. Toutefois, dans les versions de Retail antérieures à la version 10.0.3, la fonctionnalité de gestion des disponibilités n’est pas assez robuste pour fournir une traçabilité complète des mouvements des disponibilités dans les magasins. Bien que les détaillants puissent rapprocher les disponibilités pour un magasin, ils ne peuvent pas avec précision déterminer la responsabilité en cas d’écart de disponibilités.


Dans la version 10.0.3 de Vente au détail et ultérieurement, les détaillants obtiennent la traçabilité de la gestion des disponibilités. Dans le cadre de cette traçabilité, les détaillants peuvent définir des coffres-forts, créer des transactions bilatérales de disponibilités, et rapprocher les transactions de la gestion des disponibilités.

## <a name="set-up-traceability-and-define-safes"></a>Paramétrer la traçabilité et définir des coffres-forts

Pour paramétrer la nouvelle fonctionnalité de gestion de disponibilités, procédez comme suit pour configurer le profil de la fonctionnalité des magasins.

1. Accédez à **Commerce et vente au détail \> Paramétrage du canal \> Paramétrage Point de vente \> Profils Point de vente \> Profils de fonctionnalité** et sélectionnez un profil de fonctionnalité associé aux magasins où vous souhaitez apporter les modifications pour rendre la gestion des disponibilités disponible.
2. Dans l’organisateur **Fonctionnalités** du profil de la fonctionnalité, sous **Gestion des disponibilités avancée**, définissez l’option **Activer la traçabilité des disponibilités** sur **Oui**.
3. Pour configurer des coffres-forts, accédez à **Commerce et vente au détail \> Canaux \> Magasins de vente au détail \> Tous les magasins de vente au détail** et sélectionnez un magasin.
4. Dans la page **Magasins**, dans le volet Actions, sous l’onglet **Paramétrer**, dans le groupe **Paramétrer**, sélectionnez **Coffres-forts**. Avec cette option, vous pouvez définir et tenir à jour plusieurs coffres-forts pour un magasin.
4. Avant que la fonctionnalité puisse être utilisée, vous devez exécuter la tâche de programme de distribution **Configuration du canal 1070** pour synchroniser ces configurations dans la base de données des canaux.

## <a name="additional-cash-management-changes"></a>Modifications supplémentaires de la gestion des disponibilités

Dans Retail version 10.0.3 et ultérieurement, les fonctionnalités suivantes relatives aux transactions de disponibilités sont également disponibles :

- Un utilisateur qui est invité à « Déclarer le montant de départ » doit entrer la source des disponibilités. L’utilisateur peut rechercher les coffres-forts disponibles définis dans le magasin et sélectionner un coffre-fort dans lequel les disponibilités sortent afin de pouvoir être mises dans la caisse enregistreuse.
- Un utilisateur qui effectue une opération de « vidage de caisse » est invité à sélectionner, dans une liste de transactions de « saisie flottante » en cours, la transaction pour laquelle l’opération est effectuée. Si l’entrée flottante correspondante n’existe pas dans le système, l’utilisateur peut créer une transaction de vidage de caisse non liée.
- Une opération de « saisie flottante » invite un utilisateur à sélectionner, dans une liste de transactions de « vidage de caisse » en cours, la transaction pour laquelle l’opération de saisie flottante est effectuée. Si le vidage de caisse correspondante n’existe pas dans le système, l’utilisateur peut créer une transaction d’entrée flottante non liée.
- Un utilisateur qui effectue une « mise en coffre-fort » est invité à sélectionner le coffre-fort dans lequel les disponibilités sont mises.
- Pour les coffres-forts définis dans un magasin, les utilisateurs peuvent gérer des opérations telles que déclarer le montant de départ, créer une saisie flottante, vider une caisse et réaliser une remise en banque.
- Pour les utilisateurs avec les droits appropriés d’utilisateur, les opérations « gérer les équipes » affiche les soldes de disponibilités des équipes actives, interrompues et clôturées en aveugle.
- Pour rapprocher les transactions de disponibilités dans une équipe ou entre plusieurs équipes, sélectionnez l’équipe à rapprocher, puis sélectionnez **Rapprocher**. La vue qui s’ouvre affiche la liste des transactions rapprochées et des transactions non rapprochées sous différents onglets. Dans cette vue, les utilisateurs peuvent sélectionner des transactions non rapprochées et les rapprocher, ou sélectionner des transactions précédemment rapprochées et annuler le rapprochement.
- Lors du rapprochement, si la transaction sélectionnée n’est pas équilibrée, l’utilisateur doit entrer une description du motif pour le rapprochement non équilibré. Les utilisateurs peuvent sélectionner une seule transaction et la rapprocher de la description du motif approprié au besoin.
- Les utilisateurs peuvent continuer à rapprocher et annuler des rapprochements de transactions jusqu’à ce que l’équipe est clôturée. Une fois une équipe clôturée, le rapprochement des transactions ne peut pas être annulé.
- Lorsqu’un utilisateur choisit de clôturer une équipe, Commerce valide qu’il n’y a aucune transaction non rapprochée dans les transactions de la gestion des disponibilités de l’équipe. Les utilisateurs ne peuvent pas clôturer une fois une équipe s’il reste des transactions non rapprochées.


[!INCLUDE[footer-include](../includes/footer-banner.md)]