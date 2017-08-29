---
title: "Gestion d'équipe et de tiroir-caisse"
description: "Cet article explique comment configurer et utiliser les deux types d'équipes de travail de point de vente au détail (PDV) - partagée et autonome. Les équipes de travail partagées peuvent être utilisées par plusieurs utilisateurs à plusieurs endroits, alors que les équipes de travail autonomes peuvent être utilisées par un seul collaborateur à la fois."
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 105011
ms.assetid: 49a0fcc9-d4db-45ad-8c4b-213ccaced82b
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 0d5e05e8f1edcc01af985c25459d93de0bc2acf1
ms.contentlocale: fr-fr
ms.lasthandoff: 06/20/2017

---

# <a name="shift-and-cash-drawer-management"></a>Gestion d'équipe et de tiroir-caisse

[!include[banner](includes/banner.md)]


Cet article explique comment configurer et utiliser les deux types d'équipes de travail de point de vente au détail (PDV) - partagée et autonome. Les équipes de travail partagées peuvent être utilisées par plusieurs utilisateurs à plusieurs endroits, alors que les équipes de travail autonomes peuvent être utilisées par un seul collaborateur à la fois.

Il existe deux types d'équipes de point de vente (PDV) : autonome et partagé. Les équipes autonomes peuvent être utilisées par un seul collaborateur à la fois. Les équipes de travail partagées peuvent être utilisées par plusieurs utilisateurs à plusieurs endroits. Par conséquent, ils créent efficacement une seule équipe pour plusieurs collaborateurs dans un magasin.

## <a name="standalone-shifts"></a>Équipes autonomes
Les équipes autonomes sont utilisées dans un scénario de PDV traditionnel fixe, où les disponibilités sont rapprochées indépendamment pour chaque caisse enregistreuse de PDV. Par exemple, dans un schéma d’épicerie, il existe généralement plusieurs caisses enregistreuses de PDV fixe et un caissier est affecté à chaque caisse enregistreuse. Dans ce cas, chaque caisse enregistreuse est susceptible d’utiliser une équipe autonome, et le caissier est responsable du tiroir-caisse ou des disponibilités physiques à cette caisse enregistreuse. Une équipe de travail autonome englobe toutes les activités sur cette caisse enregistreuse au cours de l’équipe du caissier. Ces activités peuvent inclure le montant déposé à l’ouverture dans le tiroir-caisse, tous les soustraction et addition de disponibilités par des opérations de remises en banque et de saisie flottante, et le comptage de caisse à la fin de l’équipe.

### <a name="set-up-a-stand-alone-shift"></a>Définir une équipe autonome

Une équipe autonome est désignée au niveau du tiroir-caisse. Cette procédure explique comment définir une équipe autonome sur une caisse enregistreuse de PDV.

1.  Cliquez sur **Vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage POS** &gt; **Profils POS** &gt; **Profils du matériel**.
2.  Sélectionnez le profil matériel à utiliser pour l’équipe autonome.
3.  Sur l'organisateur **Tiroir**, confirmez que l'option **Tiroir-caisse partagé par l'équipe de travail** est définie sur **Non**.
4.  Cliquez sur **Enregistrer**.
5.  Cliquez sur **Vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage POS** &gt; **Caisses enregistreuses**.
6.  Sélectionnez la caisse enregistreuse nécessitant une équipe autonome, puis cliquez sur **Modifier**.
7.  Dans le champ **Profil matériel**, sélectionnez le profil matériel que vous avez sélectionné à l’étape 2.
8.  Cliquez sur **Enregistrer**.
9.  Cliquez sur **Vente au détail** &gt; **Informatique de vente au détail** &gt; **Programme de distribution**.
10. Sélectionnez le programme de distribution **1090**, puis cliquez sur **Exécuter maintenant** pour synchroniser les modifications apportées au PDV.

### <a name="use-a-stand-alone-shift"></a>Utiliser une équipe autonome

1.  Connectez-vous au PDV.
2.  Si aucune équipe n’est ouverte, sélectionnez **Ouvrir une nouvelle équipe de travail**.
3.  Accédez à l'opération **Déclarer le montant de départ**, spécifiez le montant de disponibilités qui est ajouté au tiroir-caisse pour démarrer la journée de travail.
4.  Effectuez des transactions.
5.  À la fin de la journée, sélectionnez **Comptage de caisse** pour déclarer le montant de disponibilités qui reste dans le tiroir-caisse.
6.  Entrez le montant en espèces, puis cliquez sur **Enregistrer** pour enregistrer le comptage de caisse.
7.  Sélectionnez **Clôturer l'équipe de travail** pour clôturer l’équipe de travail.

**Remarque :** d'autres opérations sont disponibles pendant l’équipe de travail, selon les processus d'entreprise en place. Les opérations **Mise en coffre-fort**, **Remise en banque**, et **Vider la caisse** peuvent être utilisées pour supprimer l'argent du tiroir-caisse pendant la journée, ou avant la clôture de l’équipe de travail. Si un tiroir-caisse vient à manquer de disponibilités, l'opération **Entrée de fond de caisse** peut être utilisée pour ajouter des espèces au tiroir-caisse.

## <a name="shared-shifts"></a>Équipes partagées
Une équipe partagée est utilisée dans un environnement où plusieurs caissiers partagent un tiroir-caisse ou un ensemble de tiroirs-caisses tout au long de la journée de travail. En général, une équipe partagée est utilisée dans les environnements de PDV mobiles. Dans un environnement mobile, chaque caissier n’est pas affecté ni responsable d'un tiroir-caisse unique. Au lieu de cela, tous les caissiers doivent pouvoir enregistrer une vente et ajouter des disponibilités au tiroir-caisse le plus proche d'eux. Dans ce scénario, les tiroirs-caisses qui sont partagés entre les caissiers sont inclus dans une équipe partagée. Tous les tiroirs-caisses d'une équipe partagée sont inclus dans la même équipe de travail aux fins des activités liées à la gestion des disponibilités de cette équipe. Par conséquent, le montant de départ de l'équipe de travail doit inclure la somme de toutes les disponibilités de tous les tiroirs-caisses qui sont inclus dans l’équipe de travail partagée. De même, le comptage de caisse sera la somme de toutes les disponibilités de tous les tiroirs-caisses qui sont inclus dans l’équipe de travail partagée. **Remarque :** une seule équipe partagée peut être ouverte à la fois dans chaque magasin. Les équipes partagées et les équipes autonomes peuvent être utilisées dans le même magasin.

### <a name="set-up-a-shared-shift"></a>Configuration d'une équipe partagée

1.  Cliquez sur **Vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage POS** &gt; **Profils POS** &gt; **Profils du matériel**.
2.  Sélectionnez le profil matériel à utiliser pour l’équipe partagée.
3.  Sur l'organisateur **Tiroir**, définissez l'option **Tiroir-caisse partagé par l'équipe de travail** sur **Oui**.
4.  Cliquez sur **Enregistrer**.
5.  Cliquez sur **Vente au détail** &gt; **Paramétrage du canal** &gt; **Paramétrage POS** &gt; **Caisses enregistreuses**.
6.  Sélectionnez la caisse enregistreuse nécessitant une équipe partagée, puis cliquez sur **Modifier**.
7.  Dans le champ **Profil matériel**, sélectionnez le profil matériel que vous avez sélectionné à l’étape 2.
8.  Cliquez sur **Enregistrer**.
9.  Cliquez sur **Vente au détail** &gt; **Informatique de vente au détail** &gt; **Programme de distribution**.
10. Sélectionnez le programme de distribution **1090**, puis cliquez sur **Exécuter maintenant** pour synchroniser les modifications apportées au PDV.

### <a name="use-a-shared-shift"></a>Utiliser une équipe de travail partagée

1.  Connectez-vous au PDV.
2.  Si le PDV n’est pas encore connecté à une station matérielle, sélectionnez **Opération sans lien avec le tiroir-caisse**, puis sélectionnez l'opération **Sélectionner une station matérielle** pour activer une station matérielle pour l’équipe partagée. Cette étape est requise uniquement la première fois qu’une caisse enregistreuse est ajoutée à un environnement d’équipe partagée.
3.  Déconnectez-vous du PDV et puis reconnectez-vous.
4.  Sélectionnez **Créer une équipe**.
5.  Sélectionnez **Déclarer le montant de départ**.
6.  Entrez le montant de départ de tous les tiroirs-caisses dans le magasin qui font partie de l’équipe partagée, puis cliquez sur **Enregistrer**.
    -   Pour ajouter la partie de la quantité de départ de chaque tiroir-caisse suivant, utilisez l'opération **Sélectionner une station matérielle** pour activer la station matérielle.
    -   Pour ajouter tiroir-caisse à une caisse enregistreuse spécifique, utilisez l'opération **Ouvrir tiroir-caisse**.
    -   Continuez jusqu'à ce que toutes les caisses enregistreuses de l’équipe de travail partagée aient leur part de la quantité de départ.

7.  À la fin de la journée, ouvrez chaque caisse enregistreuse et supprimer les disponibilités.
8.  Après avoir effacé les disponibilités du dernier tiroir-caisse, comptez toutes les disponibilités de toutes les tiroirs-caisses.
9.  Utilisez l'opération **Comptage de caisse** pour déclarer le montant total des disponibilités de tous les tiroirs-caisses qui sont inclus dans l’équipe de travail partagée.
10. Utilisez l'opération **Clôturer l'équipe de travail** pour clôturer l’équipe de travail partagée.





