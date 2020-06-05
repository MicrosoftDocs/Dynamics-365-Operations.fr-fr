---
title: Opération de stock sortant dans le PDV
description: Cette rubrique décrit les fonctionnalités de l'opération de stock sortant dans le point de vente (PDV).
author: hhaines
manager: annbe
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 22f057c20898bb4b4c34e38d62313d2634a33511
ms.sourcegitcommit: 3b6fc5845ea2a0de3db19305c03d61fc74f4e0d4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2020
ms.locfileid: "3384127"
---
# <a name="outbound-inventory-operation-in-pos"></a>Opération de stock sortant dans le PDV

[!include [banner](includes/banner.md)]


Dans Microsoft Dynamics 365 Commerce version 10.0.10 et les versions ultérieures, les opérations entrantes et sortantes dans le point de vente (PDV) remplacent l'opération de prélèvement et de réception.

> [!NOTE]
> Dans la version 10.0.10 et les versions ultérieures, les nouvelles fonctionnalités de l'application PDV associées à la réception du stock en magasin pour les commandes fournisseur et les ordres de transfert seront ajoutées à l'opération Opération sortante. Si vous utilisez actuellement l'opération de prélèvement et de réception dans le PDV, nous vous recommandons de développer une stratégie pour passer de cette opération aux nouvelles opérations entrantes et sortantes. Bien que l'opération de prélèvement et de réception ne soit pas supprimée du produit, il n'y aura aucun investissement supplémentaire, du point de vue fonctionnel ou des performances, après la version 10.0.9.

## <a name="prerequisite-configure-an-asynchronous-document-framework"></a>Condition préalable : configurer un cadre de document asynchrone

L'opération sortante comprend des améliorations des performances pour permettre aux utilisateurs ayant des volumes élevés de validations d'accusés de réception dans plusieurs magasins ou sociétés et des documents de stock volumineux de traiter ces documents dans Commerce Headquarters sans rencontrer des erreurs d'expiration du délai ou des échecs. Ces améliorations nécessitent l'utilisation d'un cadre de document asynchrone.

Lorsqu'une structure de document asynchrone est utilisée, vous pouvez valider les modifications du document sortant du PDV dans Commerce Headquarters, puis passer à d'autres tâches pendant que le traitement dans Commerce Headquarters se produit en arrière-plan. Vous pouvez vérifier le statut du document sur la page de liste des documents **Opération sortante** du PDV pour vous assurer que la validation a réussi. Dans l'application PDV, vous pouvez également utiliser la liste de documents active de l'opération sortante pour voir les documents qui n'ont pas pu être validés dans Commerce Headquarters. Si un document échoue, les utilisateurs du PDV peuvent y apporter des corrections, puis réessayer de le traiter dans Commerce Headquarters.

> [!IMPORTANT]
> La structure de document asynchrone doit être configurée avant qu'une société tente d'utiliser l'opération sortante dans le PDV.

Pour configurer une structure de document asynchrone, procédez comme suit.

### <a name="create-and-configure-a-number-sequence"></a>Créer et configurer une souche de numéros

1. Allez dans **Administration d'organisation \> Souches de numéros \> Souches de numéros**.
2. Dans la page **Souches de numéros**, créez une souche de numéros.
3. Dans les champs **Code souche de numéros** et **Nom**, entrez des valeurs définies par l'utilisateur.
4. Dans le raccourci **Références**, sélectionnez **Ajouter**.
5. Dans le champ **Zone**, sélectionnez **Paramètres Commerce**.
6. Dans le champ **Référence**, sélectionnez **Identificateur de l'opération de document de vente au détail**.
7. Dans le raccourci **Général**, dans la section **Configuration**, définissez l'option **Continu** sur **Non** pour vous assurer qu'il n'y a pas de problèmes de performances.

### <a name="create-and-schedule-two-batch-jobs-for-the-document-processing-and-monitoring-tasks"></a>Créer et planifier deux traitements par lots pour les tâches de traitement et de surveillance des documents

Les traitements par lots que vous créez seront utilisés pour traiter les documents qui échouent ou arrivent à expiration. Ils seront également utilisés lorsque le nombre de documents de stock actifs en cours de traitement dans le PDV dépasse une valeur configurée par le système.

1. Allez dans **Administration du système \> Recherches \> Traitements par lots**.
2. Dans la page **Traitement par lots**, créez deux traitements par lots :

    - Configurez une tâche pour exécuter la classe **RetailDocumentOperationMonitorBatch**.
    - Configurez l'autre tâche pour exécuter la classe **RetailDocumentOperationProcessingBatch**.

3. Planifiez les nouveaux traitements par lots pour qu'ils s'exécutent de manière récurrente. Par exemple, définissez le calendrier de telle sorte que les tâches soient exécutées toutes les cinq minutes.

## <a name="prerequisite-add-outbound-operation-to-the-pos-screen-layout"></a>Condition préalable : ajouter une opération sortante à la mise en page de l'écran du PDV

Avant que votre organisation puisse utiliser la fonctionnalité Opération sortante, elle doit configurer l'opération PDV **Opération sortante** sur une ou plusieurs de vos [Mises en page de l'écran du PDV](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts). Avant de déployer la nouvelle opération dans un environnement de production, veillez à la tester et à apprendre à vos utilisateurs à l'utiliser.

## <a name="overview"></a>Vue d'ensemble

L'opération sortante permet aux utilisateurs du PDV d'effectuer les tâches suivantes :

- Valider les expéditions pour les documents d'ordre de transfert dans les cas où le magasin de l'utilisateur est l'entrepôt de sortie désigné.
- Afficher des informations sur les expéditions d'ordre de transfert historiques qui ont été validées par le magasin.
- Créer des demandes d'ordres de transfert sortantes.

Lorsque l'opération sortante est lancée à partir de l'application PDV, une vue de page de liste s'affiche. Cette vue affiche les documents d'ordre de transfert en cours dont les lignes de stock doivent être expédiées et traitées par le magasin actuel de l'utilisateur. Pour rechercher et sélectionner un document, les utilisateurs peuvent faire défiler la liste ou utiliser la fonction de recherche.

La liste des documents de stock sortant comporte trois onglets.

- **Actif** : cet onglet affiche les ordres de transfert dont le statut est **Demandé(e)** ou **Partiellement expédié(e)**. Les commandes contiennent des lignes ou des quantités sur les lignes qui doivent être expédiées par le magasin actuel de l'utilisateur. Cet onglet affiche également les commandes dont le statut est **Traitement au siège** (c'est-à-dire qu'elles attendent la confirmation de la validation réussie de Commerce Headquarters) ou **Échec du traitement** (c'est-à-dire que la validation dans Commerce Headquarters a échoué et que l'utilisateur doit corriger les données et réessayer d'envoyer les commandes).
- **Brouillon** : cet onglet affiche les nouvelles demandes d'ordre de transfert sortantes créées par le magasin de l'utilisateur. Cependant, les documents n'ont été enregistrés que localement. Ils n'ont pas encore été envoyés dans Commerce Headquarters pour traitement.
- **Terminé(e)**  : cet onglet affiche une liste de documents d'ordre de transfert que le magasin a entièrement expédiés au cours des sept derniers jours. Cet onglet est fourni uniquement à titre indicatif. Toutes les informations sur les documents sont des données en lecture seule pour le magasin.

Lorsque vous affichez des documents dans l'un des onglets, le champ **Statut** peut vous aider à comprendre à quel stade se trouve le document.

- **Brouillon** : le document d'ordre de transfert n'a été enregistré que localement dans la base de données du canal du magasin. Aucune information sur la demande d'ordre de transfert n'a encore été envoyée à Commerce Headquarters.
- **Demandé(e)**  : la commande fournisseur ou l'ordre de transfert a été créé dans Commerce Headquarters et est entièrement ouvert(e). Le magasin actuel de l'utilisateur n'a encore traité aucune expédition pour le document.
- **Partiellement expédié(e)**  : le document d'ordre de transfert comporte une ou plusieurs lignes ou quantités de ligne partielles qui ont été validées comme expédiées par l'entrepôt sortant. Ces lignes expédiées sont disponibles pour réception via l'opération entrante.
- **Intégralement expédié(e)**  : toutes les lignes et quantités de lignes de l'ordre de transfert ont été validées comme expédiées par l'entrepôt sortant.
- **En cours** : ce statut est utilisé pour informer les utilisateurs de l'appareil que le document est en cours d'utilisation par un autre utilisateur.
- **Suspendu(e)**  : ce statut est affiché après la sélection de **Suspendre la réception** pour arrêter temporairement le processus de réception.
- **Traitement au siège** : le document a été envoyé à Commerce Headquarters à partir de l'application PDV, mais il n'a pas encore été validé avec succès dans Commerce Headquarters. Le document passe par le processus de validation de document asynchrone. Une fois le document validé avec succès dans Commerce Headquarters, son statut doit être mis à jour sur **Entièrement reçu(e)** ou **Partiellement reçu(e)**.
- **Échec du traitement** : le document a été validé dans Commerce Headquarters et rejeté. Le volet **Détails** indique la raison de l'échec de la validation. Le document doit être modifié pour résoudre les problèmes de données, puis il doit être renvoyé à Commerce Headquarters pour traitement.

Lorsque vous sélectionnez une ligne de document dans la liste, un volet **Détails** s'affiche. Ce volet affiche des informations supplémentaires sur le document, comme les informations d'expédition et de date. Une barre de progression indique le nombre d'articles qui doivent encore être traités. Si le document n'a pas été traité avec succès dans Commerce Headquarters, le volet **Détails** affiche également des messages d'erreur liés à l'échec.

Dans la vue de page de liste des documents, vous pouvez sélectionner **Détails de la commande** sur la barre d'application pour afficher les détails du document. Vous pouvez également activer le traitement des accusés de réception sur les lignes de document éligibles.

Dans la vue de page de liste des documents, vous pouvez également créer un ordre de transfert sortant pour un magasin.

## <a name="transfer-order-shipping-process"></a>Processus d'expédition d'un ordre de transfert

Après avoir sélectionné un document d'ordre de transfert dans l'onglet **Actif**, vous pouvez sélectionner **Détails de la commande** pour commencer le processus de traitement. La vue **Liste complète des commandes** s'affiche. Cette page affiche toutes les lignes de document contenant l'article. Elle affiche également les détails de la quantité commandée.

Chaque lecture d'un code-barres met à jour la quantité dans le champ **Livrer maintenant** d'une unité. Vous pouvez également saisir une quantité d'expédition en sélectionnant **Expédier le produit** sur la barre d'application, en saisissant un ID article, puis en saisissant la quantité. Si l'article est contrôlé par l'emplacement, vous pouvez confirmer ou définir l'emplacement d'expédition pour la ligne de document.

Dans la vue **Liste complète des commandes**, vous pouvez sélectionner manuellement une ligne dans la liste, puis mettre à jour la quantité **Livrer maintenant** pour la ligne sélectionnée dans le volet **Détails**.

### <a name="over-delivery-shipping-validations"></a>Validations d'expédition pour livraison excessive

Les validations se produisent pendant le processus de réception pour les lignes de document. Elles comprennent les validations pour livraison excessive. Si un utilisateur tente de recevoir plus de stock que à ce qui a été commandé sur une commande fournisseur, mais la livraison excessive n'est pas configurée ou la quantité reçue dépasse la tolérance de livraison excessive configurée pour la ligne de commande fournisseur, l'utilisateur reçoit une erreur et n'est pas autorisé à recevoir la quantité excédentaire.

### <a name="underdelivery-close-lines"></a>Lignes de clôture de livraison incomplète

Dans la version 10.0.12 de Commerce, une fonctionnalité a été ajoutée et permet aux utilisateurs du PDV de clôturer ou d'annuler les quantités restantes pendant l'expédition de la commande sortante si l'entrepôt sortant détermine que toute la quantité demandée ne peut pas être expédiée. Les quantités peuvent également être clôturées ou annulées ultérieurement. Pour utiliser cette fonctionnalité, la société doit être configurée pour autoriser les livraisons incomplètes des ordres de transfert. De plus, un pourcentage de livraisons incomplètes doit être défini pour la ligne d'ordre de transfert.

Pour configurer la société afin d'autoriser les livraisons incomplètes des ordres de transfert, dans Commerce Headquarters, accédez à **Gestion des stocks \> Configuration \> Paramètres de gestion des stocks et des entrepôts**. Sur la page **Paramètres de gestion des stocks et des entrepôts** de l'onglet **Ordres de transfert**, activez le paramètre **Accepter les livraisons incomplètes**. Exécutez ensuite la tâche du planificateur de distribution **1070** pour synchroniser les modifications des paramètres avec le canal de votre magasin.

Les pourcentages de livraison incomplète pour une ligne d'ordre de transfert peuvent être prédéfinis sur les produits dans le cadre de la configuration des produits dans Commerce Headquarters. Ils peuvent également être définis ou remplacés sur une ligne d'ordre de transfert spécifique via Commerce Headquarters.

Une fois qu'une organisation a fini de configurer les livraisons incomplètes de l'ordre de transfert, les utilisateurs voient une nouvelle option **Clôturer la quantité restante** dans le volet **Détails** lorsqu'ils sélectionnent une ligne d'ordre de transfert sortant via l'opération **Opération sortante** dans le PDV. Ensuite, lorsque les utilisateurs ont terminé l'expédition à l'aide de l'opération **Terminer l’exécution**, ils peuvent envoyer une demande à Commerce Headquarters pour annuler la quantité non expédiée restante. Si un utilisateur choisit de clôturer la quantité restante, Commerce effectue une validation pour vérifier que la quantité qui est annulée se situe dans la tolérance de pourcentage de livraison incomplète définie sur la ligne d'ordre de transfert. Si la tolérance de livraison incomplète est dépassée, l'utilisateur reçoit un message d'erreur et ne peut pas clôturer la quantité restante jusqu'à ce que la quantité précédemment expédiée et « expédier maintenant » atteigne ou dépasse la tolérance de livraison incomplète.

Une fois l'expédition synchronisée avec Commerce Headquarters, les quantités définies dans le champ **Expédier maintenant** pour la ligne d'ordre de transfert dans le PDV sont mises à jour sur l'état « expédié » dans Commerce Headquarters. Toutes les quantités non expédiées qui auraient précédemment été considérées comme des quantités « expédiées » (c'est-à-dire les quantités qui seront expédiées ultérieurement) sont considérées comme des quantités annulées à la place. La quantité « restant à expédier » pour la ligne d'ordre de transfert est définie sur **0** (zéro) et la ligne est considérée comme entièrement expédiée.

### <a name="shipping-location-controlled-items"></a>Articles contrôlés par l'emplacement d'expédition

Si les articles expédiés sont contrôlés par l'emplacement, les utilisateurs peuvent choisir l'emplacement de sortie du stock pendant le processus d'expédition. Nous vous recommandons de configurer un emplacement de sortie par défaut pour votre entrepôt de magasin, afin de rendre ce processus plus efficace. Même si un emplacement par défaut est configuré, les utilisateurs peuvent remplacer l'emplacement de sortie sur les lignes sélectionnées selon leurs besoins.

L'opération respecte la configuration **Accusé de réception vide autorisé** sur la dimension de stockage **Emplacement** et ne nécessite pas la saisie d'une dimension d'emplacement si un accusé de réception vide est configuré. Si les emplacements de réception vides ne sont pas autorisés pour un article, l'application PDV affiche une erreur et demande qu'un emplacement soit saisi avant que l'accusé de réception puisse être validé.

### <a name="ship-all"></a>Expédier tout

Selon vos besoins, vous pouvez sélectionner **Expédier tout** sur la barre d'application pour mettre à jour rapidement la quantité **Expédier maintenant** pour toutes les lignes de document sur la valeur maximale disponible pour traitement pour ces lignes.

### <a name="cancel-fulfillment"></a>Annuler l'exécution

Vous devez utiliser la fonction **Annuler l'exécution** sur la barre d'application uniquement si vous souhaitez fermer le document sans enregistrer les modifications. Par exemple, vous avez initialement sélectionné le document incorrect et vous ne voulez pas enregistrer les données d'expédition précédentes.

### <a name="pause-fulfillment"></a>Suspendre l’exécution

Si vous exécutez l'ordre de transfert, vous pouvez utiliser la fonction **Suspendre l'exécution** si vous souhaitez suspendre le processus. Par exemple, vous souhaitez effectuer une autre opération dans le PDV, comme enregistrer une vente client ou retarder la validation de l'expédition dans Commerce Headquarters.

Lorsque vous sélectionnez **Suspendre l'exécution**, le statut du document est modifié en **Suspendu(e)**. Ainsi, l'utilisateur saura que des données ont été saisies dans le document, mais le document n'a pas encore été validé. Lorsque vous êtes prêt à reprendre le processus d'exécution, sélectionnez le document mis en pause, puis sélectionnez **Détails de la commande**. Les quantités **Expédier maintenant** précédemment enregistrées seront conservées et disponibles dans la vue **Liste complète des commandes**.

### <a name="finish-fulfillment"></a>Terminer l’exécution

Lorsque vous avez terminé de saisir toutes les quantités **Expédier maintenant** pour les produits, vous devez sélectionner **Terminer l'exécution** sur la barre d'application.

Lorsque le traitement de document asynchrone est utilisé, l'accusé de réception est envoyé via une structure de document asynchrone. Le temps de validation du document dépend de la taille du document (le nombre de lignes) et du trafic de traitement général sur le serveur. Généralement, ce processus se produit en quelques secondes. Si la validation du document échoue, l'utilisateur en est informé via la liste de documents **Opération sortante** dans l'onglet **Actif**, où le statut du document sera mis à jour sur **Échec du traitement**. L'utilisateur peut ensuite sélectionner le document ayant échoué dans le PDV pour afficher les messages d'erreur et la raison de l'échec dans le volet **Détails**. Un document ayant échoué reste non validé et nécessite que l'utilisateur retourne aux lignes de document en sélectionnant **Détails de la commande** dans le PDV. L'utilisateur doit ensuite mettre à jour le document avec les corrections, en fonction des erreurs. Une fois un document corrigé, l'utilisateur peut réessayer de le traiter en sélectionnant **Terminer l'exécution** sur la barre d'application.

## <a name="create-an-outbound-transfer-order"></a>Créer un ordre de transfert sortant

Dans le PDV, les utilisateurs peuvent créer des documents d'ordre de transfert. Pour commencer le processus, sélectionnez **Nouveau** sur la barre d'application lorsque vous êtes dans la liste de documents **Opération sortante** principale. Vous êtes ensuite invité à sélectionner un entrepôt ou un magasin **Transférer à** auquel votre magasin actuel enverra le stock. Les valeurs sont limitées à la sélection définie dans la configuration du groupe d'exécution du magasin. Dans une demande de transfert sortante, votre magasin actuel sera toujours l'entrepôt **Transférer depuis** pour l'ordre de transfert. Les valeurs ne peuvent pas être modifiées.

Vous pouvez saisir des valeurs dans les champs **Date d'expédition**, **Date de réception** et **Mode de livraison** selon vos besoins. Vous pouvez également ajouter une note qui sera stockée avec l'en-tête de l'ordre de transfert, en tant que pièce jointe au document dans Commerce Headquarters.

Une fois les informations d'en-tête créées, vous pouvez ajouter des produits à l'ordre de transfert. Pour démarrer le processus d'ajout des articles et des quantités demandées, lisez des codes-barres ou sélectionnez **Ajouter un produit**.

Une fois les lignes saisies dans l'ordre de transfert sortant, vous devez sélectionner **Enregistrer** pour enregistrer les modifications du document localement ou **Envoyer la demande** pour envoyer les détails de la commande à Commerce Headquarters pour traitement ultérieur. Si vous sélectionnez **Enregistrer**, le brouillon du document est stocké dans la base de données du canal et l'entrepôt sortant ne peut pas exécuter le document tant qu'il n'a pas été traité avec succès via **Envoyer la demande**. Vous devez sélectionner **Enregistrer** uniquement si vous n'êtes pas prêt à valider la demande dans Commerce Headquarters pour traitement.

Si un document est enregistré localement, il se trouve dans l'onglet **Brouillons** de la liste de documents **Opération entrante**. Lorsqu'un document est à l'état **Brouillon**, vous pouvez le modifier en sélectionnant **Modifier**. Vous pouvez mettre à jour, ajouter ou supprimer des lignes selon vos besoins. Vous pouvez également supprimer l'intégralité du document lorsqu'il est à l'état **Brouillon** en sélectionnant **Supprimer** dans l'onglet **Brouillons**.

Une fois le brouillon de document envoyé avec succès à Commerce Headquarters, il s'affiche dans l'onglet **Actif** et a le statut **Demandé(e)**. À ce stade, seuls les utilisateurs de l'entrepôt sortant peuvent modifier le document en sélectionnant **Opération sortante** dans l'application PDV. Les utilisateurs de l'entrepôt entrant peuvent voir l'ordre de transfert dans l'onglet **Actif** de la liste de documents **Opération entrante**, mais ils ne peuvent pas le modifier ni le supprimer. Le verrou de modification garantit qu'aucun conflit ne se produit car un demandeur entrant modifie l'ordre de transfert en même temps que l'expéditeur sortant prélève et expédie activement la commande. Si des modifications sont nécessaires dans le magasin ou l'entrepôt entrant une fois l'ordre de transfert envoyé, l'expéditeur sortant doit être contacté et invité à entrer les modifications.

Une fois le document à l'état **Demandé(e)**, il est prêt pour traitement par l'entrepôt sortant. Lorsque l'expédition est traitée à l'aide de l'opération sortante, le statut des documents d'ordre de transfert est mis à jour de **Demandé(e)** à **Intégralement expédié(e)** ou **Partiellement expédié(e)**. Une fois les documents à l'état **Intégralement expédié(e)** ou **Partiellement expédié(e)**, le magasin ou l'entrepôt entrant peut valider les accusés de réception à l'aide du processus de réception de l'opération entrante.

Les ordres de transfert entièrement expédiés sont déplacés vers l'onglet **Terminé(e)** de la liste de documents **Opération sortante**. Ils restent visibles par les utilisateurs dans le magasin ou l'entrepôt sortant, en mode lecture seule, pendant sept jours.

## <a name="related-topics"></a>Rubriques connexes

[Opération de stock entrant dans le PDV](pos-inbound-inventory-operation.md)
