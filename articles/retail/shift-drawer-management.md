---
title: "Gestion d'équipe et de tiroir-caisse"
description: "Cet article explique comment configurer et utiliser les deux types d'équipes de travail de point de vente au détail (PDV) - partagée et autonome. Les équipes de travail partagées peuvent être utilisées par plusieurs utilisateurs à plusieurs endroits, alors que les équipes de travail autonomes peuvent être utilisées par un seul collaborateur à la fois."
author: rubencdelgado
manager: AnnBe
ms.date: 02/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: 8a24f8adc4f7886a1f942d83f7a4eb12e7034fcd
ms.openlocfilehash: c1483d3240d266845cea7789b70c038cb98fdfcc
ms.contentlocale: fr-fr
ms.lasthandoff: 03/22/2018

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

## <a name="shift-operations"></a>Opérations d'équipe
Plusieurs actions peuvent être effectuées pour modifier l'état d'une équipe ou pour augmenter ou diminuer la somme d'argent dans le tiroir-caisse. La section ci-après décrit ces opérations d'équipe pour Dynamics 365 for Retail Modern POS et Cloud POS.

**Équipe de travail en cours**

POS exige qu'un utilisateur soit dans une équipe active et ouverte pour exécuter toutes les opérations débouchant sur une transaction financière comme une vente, un retour ou une commande client.  

Lorsque cous vous connectez à POS, le système vérifie d'abord si l'utilisateur est dans une équipe active disponible sur le registre actuel. Si ce n'est pas le cas, l'utilisateur peut alors choisir d'ouvrir une nouvelle équipe, de reprendre une équipe de travail existante ou de continuer en se connectant en mode « non tiroir-caisse », en fonction de la configuration système et de ses autorisations.

**Déclarer le montant de départ**

Cette opération est souvent la première action effectuée avec une équipe récemment ouverte. Les utilisateurs spécifient le montant présent dans le tiroir-caisse en début d'équipe. Ceci est important, car le calcul de fin/court qui se produit à la fermeture d'une équipe tient compte de ce montant.

**Entrée de fond de caisse**

Les entrées de fond de caisse sont des transactions hors ventes qui sont effectuées au cours d'une équipe active et qui augmentent le montant des disponibilités dans le tiroir-caisse. Un exemple courant d'une entrée de fond de caisse consiste à ajouter de la monnaie supplémentaire dans le tiroir-caisse quand celui-ci en manque.

**Vider la caisse**

Les vidages de caisse sont des transactions hors ventes qui sont effectuées au cours d'une équipe active et qui diminuent le montant des disponibilités dans le tiroir-caisse. Ils sont le plus souvent utilisés conjointement à une entrée de fond de caisse dans une équipe différente. Par exemple, le registre 1 manque de fonds, l'utilisateur du registre 2 effectue un vidage de caisse pour réduire le montant du tiroir-caisse. L'utilisateur du registre 1 effectue ensuite une entrée de fond de caisse pour accroître son montant.

**Suspendre l'équipe de travail**

Les utilisateurs peuvent interrompre leur équipe active pour libérer le registre actuel pour un autre utilisateur, ou pour déplacer leur équipe à un registre différent (ceci est souvent appelé « tiroir-caisse flottant »). 

L'interruption de l'équipe empêche toute nouvelle transaction ou changement d'équipe jusqu'à ce qu'elle reprenne.

**Reprendre une équipe de travail**

Cette opération permet à un utilisateur de reprendre une équipe précédemment interrompue sur une caisse enregistreuse qui n'a pas encore une équipe active.

**Comptage de caisse**

Le comptage de caisse est l'action effectuée par l'utilisateur pour spécifier la somme d'argent total actuelle dans le tiroir-caisse, le plus souvent avant fermeture de l'équipe. Il s'agit de la valeur comparée à l'équipe prévue pour calculer montant de fin/court.

**Mise en coffre-fort**

Les mises en coffre-fort peuvent être effectuées à tout moment pendant une équipe active. Cette opération permet de retirer l'argent du tiroir-caisse, afin qu'il puisse être transféré à un plus emplacement plus sûr tel qu'un coffre-fort dans une pièce à part. Le montant total enregistré pour les mises en coffre-fort est toujours inclus dans les totaux de l'équipe, mais n'a pas besoin d'être compté comme faisant partie du comptage de caisse.

**Remise en banque**

Comme les mises en coffre-fort, les remises en banque sont également effectuées pendant les équipes actives. Cette opération permet de retirer l'argent de l'équipe pour préparer le dépôt bancaire.

**Clôturer l'équipe de travail en aveugle**

Une clôture de l'équipe de travail en aveugle est une équipe qui n'est plus active mais qui n'a pas été entièrement clôturée. Les clôtures d'équipes de travail en aveugle ne peuvent pas être reprises comme des équipes interrompues, mais les procédures comme la déclaration des montants de départ et les comptages de caisse peuvent être exécutées ultérieurement ou depuis un registre distinct.

Les clôtures d'équipe de travail en aveugle sont généralement utilisées pour libérer un registre pour un nouvel utilisateur ou une nouvelle équipe, sans devoir d'abord entièrement recompter, rapprocher, et clôturer l'équipe. 

**Clôturer l'équipe de travail**

Cette opération calcule les totaux d'équipe, les montants de fin/courts, puis finalise une équipe active ou clôturée en aveugle. Les équipes clôturées en aveugle ne peuvent pas être reprises ou modifiées.  

**Gérer les équipes**

Cette opération permet aux utilisateurs d'afficher toutes les équipes actives, interrompues, et clôturées à l'aveugle du magasin. En fonction de leurs autorisations, les utilisateurs peuvent effectuer leurs procédures de clôture finale, telles que le comptage de caisse et la clôture des équipes en aveugle pour les équipes clôturées en aveugle. Cette opération permet également aux utilisateurs d'afficher et de supprimer les équipes non valides dans le cas rare d'une équipe en mauvais état après avoir basculé entre les modes hors connexion et en ligne. Ces équipes non valides ne contiennent aucune information financière, ni donnée transactionnelle nécessaire pour le rapprochement. 

