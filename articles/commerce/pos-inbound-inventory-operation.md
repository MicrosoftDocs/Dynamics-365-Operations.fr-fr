---
title: Opération de stock entrant dans le PDV
description: Cette rubrique décrit les fonctionnalités de l’opération de stock entrant dans le point de vente (PDV).
author: hhaines
ms.date: 09/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 6efc20de5309bc7ec209a557a4bc12c6a0a42a43
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804329"
---
# <a name="inbound-inventory-operation-in-pos"></a>Opération de stock entrant dans le PDV

[!include [banner](includes/banner.md)]

Dans Microsoft Dynamics 365 Commerce version 10.0.10 et les versions ultérieures, les opérations entrantes et sortantes dans le point de vente (PDV) remplacent l’opération de prélèvement et de réception.

> [!NOTE]
> Dans Commerce version 10.0.10 et les versions ultérieures, les nouvelles fonctionnalités de l’application PDV associées à la réception du stock en magasin pour les commandes fournisseur et les ordres de transfert seront ajoutées à l’opération PDV **Opération entrante**. Si vous utilisez actuellement l’opération de prélèvement et de réception dans le PDV, nous vous recommandons de développer une stratégie pour passer de cette opération aux nouvelles opérations entrantes et sortantes. Bien que l’opération de prélèvement et de réception ne soit pas supprimée du produit, il n’y aura aucun investissement supplémentaire, du point de vue fonctionnel ou des performances, après la version 10.0.9.

## <a name="prerequisite-configure-an-asynchronous-document-framework"></a>Condition préalable : configurer un cadre de document asynchrone

L’opération entrante comprend des améliorations des performances pour permettre aux utilisateurs ayant des volumes élevés de validations d’accusés de réception dans plusieurs magasins ou sociétés et des documents de stock volumineux de traiter ces documents dans Commerce Headquarters sans rencontrer des erreurs d’expiration du délai ou des échecs. Ces améliorations nécessitent l’utilisation d’un cadre de document asynchrone.

Lorsqu’une structure de document asynchrone est utilisée, vous pouvez valider les modifications du document entrant du PDV dans Commerce Headquarters, puis passer à d’autres tâches pendant que le traitement dans Commerce Headquarters se produit en arrière-plan. Vous pouvez vérifier le statut d’un document sur la page de liste des documents **Opération entrante** du PDV pour vous assurer que la validation a réussi. Dans l’application PDV, vous pouvez également utiliser la liste de documents active de l’opération entrante pour voir les documents qui n’ont pas pu être validés dans Commerce Headquarters. Si un document échoue, les utilisateurs du PDV peuvent y apporter des corrections, puis réessayer de le traiter dans Commerce Headquarters.

> [!IMPORTANT]
> La structure de document asynchrone doit être configurée avant qu’une société tente d’utiliser l’opération entrante dans le PDV.

Pour configurer une structure de document asynchrone, procédez comme suit.

### <a name="create-and-configure-a-number-sequence"></a>Créer et configurer une souche de numéros

1. Allez dans **Administration d’organisation \> Souches de numéros \> Souches de numéros**.
2. Dans la page **Souches de numéros**, créez une souche de numéros.
3. Dans les champs **Code souche de numéros** et **Nom**, entrez des valeurs définies par l’utilisateur.
4. Dans le raccourci **Références**, sélectionnez **Ajouter**.
5. Dans le champ **Zone**, sélectionnez **Paramètres Commerce**.
4. Dans le champ **Référence**, sélectionnez **Identificateur de l’opération de document de vente au détail**.
5. Dans le raccourci **Général**, dans la section **Configuration**, définissez l’option **Continu** sur **Non** pour vous assurer qu’il n’y a pas de problèmes de performances.

### <a name="create-and-schedule-two-batch-jobs-for-the-document-processing-and-monitoring-tasks"></a>Créer et planifier deux traitements par lots pour les tâches de traitement et de surveillance des documents

> [!NOTE]
> Dans Commerce version 10.0.13 et versions ultérieures, vous n’avez pas à configurer ces traitements par lots via l’infrastructure de traitements par lots. Les traitements par lots peuvent être configurés à partir du menu **Retail et Commerce > IT vente au détail et commerce**. Utilisez les options de menu **Moniteur d’opération de document de vente au détail** et **Traitement des opérations de document de vente au détail** pour configurer les traitements par lots.

Les traitements par lots que vous créez seront utilisés pour traiter les documents qui échouent ou arrivent à expiration. Ils seront également utilisés lorsque le nombre de documents de stock actifs en cours de traitement dans le PDV dépasse une valeur configurée par le système.

1. Allez dans **Administration du système \> Recherches \> Traitements par lots**.
2. Dans la page **Traitement par lots**, créez deux traitements par lots :

    - Configurez une tâche pour exécuter la classe **RetailDocumentOperationMonitorBatch**.
    - Configurez l’autre tâche pour exécuter la classe **RetailDocumentOperationProcessingBatch**.

2. Planifiez les nouveaux traitements par lots pour qu’ils s’exécutent de manière récurrente. Par exemple, définissez le calendrier de telle sorte que les tâches soient exécutées toutes les cinq minutes.

## <a name="prerequisite-add-inbound-operation-to-the-pos-screen-layout"></a>Condition préalable : ajouter une opération entrante à la mise en page de l’écran du PDV

Avant que votre organisation puisse utiliser la fonctionnalité Opération entrante, elle doit configurer l’opération PDV **Opération entrante** sur une ou plusieurs de vos [Mises en page de l’écran du PDV](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts). Avant de déployer la nouvelle opération dans un environnement de production, veillez à la tester et à apprendre à vos utilisateurs à l’utiliser.

## <a name="overview"></a>Vue d’ensemble

L’opération entrante permet aux utilisateurs du PDV d’effectuer les tâches suivantes :

- Recevoir le stock dans le stock du magasin à partir des documents de commande fournisseur confirmés ou des documents d’ordre de transfert expédiés.
- Afficher des informations sur les accusés de réception de stock historiques sur une période de sept jours après la réception complète du document.
- Créer des demandes d’ordres de transfert entrantes.

Lorsque l’opération entrante est lancée à partir de l’application PDV, une vue de page de liste s’affiche. Cette vue affiche les documents de commande fournisseur et d’ordre de transfert en cours dont les lignes de stock doivent être reçues par le magasin actuel. Pour rechercher et sélectionner un document spécifique, les utilisateurs peuvent faire défiler la liste ou utiliser la fonction de recherche.

La liste des documents de stock entrant comporte trois onglets :

- **Actif** : cet onglet affiche les documents entièrement ou partiellement ouverts qui contiennent des lignes ou des quantités sur les lignes devant être reçues.
- **Brouillon** : cet onglet affiche les nouvelles demandes d’ordre de transfert entrantes créées par le magasin. Cependant, les documents n’ont été enregistrés que localement. Ils n’ont pas encore été envoyés dans Commerce Headquarters pour traitement.
- **Terminé(e)**  : cet onglet affiche une liste de documents de commande fournisseur ou d’ordre de transfert que le magasin a entièrement reçus au cours des sept derniers jours. Cet onglet est fourni uniquement à titre indicatif. Toutes les informations sur les documents sont des données en lecture seule pour le magasin.

Lorsque vous affichez des documents dans l’un des onglets, le champ **Statut** peut vous aider à comprendre à quel stade se trouve le document.

- **Brouillon** : le document d’ordre de transfert n’a été enregistré que localement dans la base de données du canal du magasin. Aucune information sur la demande d’ordre de transfert n’a encore été envoyée à Commerce Headquarters.
- **Demandé(e)**  : la commande fournisseur ou l’ordre de transfert a été créé dans Commerce Headquarters et est entièrement ouvert(e). Aucun accusé de réception n’a encore été traité pour le document. Pour les documents du type Document de commande fournisseur, la réception peut commencer à tout moment lorsque le statut est **Demandé(e)**.
- **Partiellement expédié(e)**  : le document d’ordre de transfert comporte une ou plusieurs lignes ou quantités de ligne partielles qui ont été validées comme expédiées par l’entrepôt sortant. Ces lignes expédiées sont disponibles pour réception via l’opération entrante.
- **Intégralement expédié(e)**  : toutes les lignes et quantités de lignes de l’ordre de transfert ont été validées comme expédiées par l’entrepôt sortant. L’ensemble du document est disponible pour réception via l’opération entrante.
- **Partiellement reçu(e)**  : certaines lignes ou quantités de ligne sur le document de commande fournisseur ou d’ordre de transfert ont été reçues par le magasin, mais certaines lignes restent ouvertes.
- **Entièrement reçu(e)**  : toutes les lignes et quantités sur le document de commande fournisseur ou d’ordre de transfert ont été entièrement reçues. Les documents ne sont accessibles que dans l’onglet **Terminé(e)** et sont en lecture seule par les utilisateurs du magasin.
- **En cours** : ce statut est utilisé pour informer les utilisateurs de l’appareil que le document est en cours d’utilisation par un autre utilisateur.
- **Suspendu(e)**  : ce statut est affiché après la sélection de **Suspendre la réception** pour arrêter temporairement le processus de réception.
- **Traitement au siège** : le document a été envoyé à Commerce Headquarters à partir de l’application PDV, mais il n’a pas encore été validé avec succès dans Commerce Headquarters. Le document passe par le processus de validation de document asynchrone. Une fois le document validé avec succès dans Commerce Headquarters, son statut doit être mis à jour sur **Entièrement reçu(e)** ou **Partiellement reçu(e)**.
- **Échec du traitement** : le document a été validé dans Commerce Headquarters et rejeté. Le volet **Détails** indique la raison de l’échec de la validation. Le document doit être modifié pour résoudre les problèmes de données, puis il doit être renvoyé à Commerce Headquarters pour traitement.

Lorsque vous sélectionnez une ligne de document dans la liste, un volet **Détails** s’affiche. Ce volet affiche des informations supplémentaires sur le document, comme les informations d’expédition et de date. Une barre de progression indique le nombre d’articles qui doivent encore être traités. Si le document n’a pas été traité avec succès dans Commerce Headquarters, le volet **Détails** affiche également des messages d’erreur liés à l’échec.

Dans la vue de page de liste des documents, vous pouvez sélectionner **Détails de la commande** sur la barre d’application pour afficher les détails du document. Vous pouvez également activer le traitement des accusés de réception sur les lignes de document éligibles.

Dans la vue de page de liste des documents, vous pouvez également créer une demande d’ordre de transfert entrante pour un magasin. Les documents restent à l’état **Brouillon** et ils peuvent être ajustés ou supprimés jusqu’à ce qu’ils soient envoyés à Commerce Headquarters pour traitement. Une fois qu’ils sont envoyés à Commerce Headquarters, les lignes d’ordre de transfert ne peuvent plus être modifiées dans l’application PDV.

## <a name="receiving-process"></a>Processus de réception

Après avoir sélectionné un document de commande fournisseur ou d’ordre de transfert dans l’onglet **Actif**, vous pouvez sélectionner **Détails de la commande** pour commencer le processus de réception.

Par défaut, la vue **Recevoir maintenant** est affichée. Cette vue est optimisée pour la lecture de codes-barres. Elle permet de créer une liste des articles scannés, afin que ces articles puissent être reçus. Pour démarrer le processus de réception, vous pouvez commencer à lire les codes-barres des articles.

Lorsque les codes-barres des articles sont lus dans la vue **Recevoir maintenant**, l’application valide les articles par rapport au document de commande fournisseur ou d’ordre de transfert sélectionné, pour s’assurer que chaque article scanné correspond à un article valide sur le document. Dans la vue **Recevoir maintenant**, chaque lecture d’un code à barres est supposée représenter l’accusé de réception d’une quantité d’une unité, sauf si une quantité est incorporée dans le code-barres. Vous pouvez lire à plusieurs reprises les codes-barres dans cette vue pour créer une liste de tous les articles et toutes les quantités pour l’accusé de réception.

### <a name="example-scenario"></a>Exemple de scénario

Un utilisateur reçoit une commande fournisseur contenant 10 unités du code-barres 5657900266. L’utilisateur peut lire ce code-barres 10 fois pour mettre à jour le champ **Recevoir maintenant** d’une unité par lecture. Lorsque l’utilisateur a terminé les lectures, le champ **Recevoir maintenant** de la ligne de l’article indique qu’une quantité de 10 a été reçue.

Sinon, dans un scénario où la quantité d’articles est importante, l’utilisateur préfère peut-être entrer manuellement la quantité au lieu de lire le code-barres pour chaque article reçu. Dans ce cas, l’utilisateur peut lire le code-barres une fois pour ajouter l’article à la liste **Recevoir maintenant**. L’utilisateur peut ensuite sélectionner la ligne associée dans la vue **Recevoir maintenant**, puis, dans le volet **Détails** qui s’affiche à droite de la page, mettre à jour le champ **Quantité de réception** pour l’article.

Bien que la vue **Recevoir maintenant** soit optimisée pour la lecture de codes-barres, les utilisateurs peuvent également sélectionner **Recevoir le produit** sur la barre d’application, puis saisir l’ID article ou les données du code-barres via une boîte de dialogue. Une fois que l’article saisi est validé, l’utilisateur est invité à saisir la quantité de l’accusé de réception.

La vue **Recevoir maintenant** permet aux utilisateurs de voir les produits qu’ils reçoivent. Sinon, la vue **Liste complète des commandes** peut être utilisée. Cette vue affiche la liste complète des lignes de document pour le document de commande fournisseur ou d’ordre de transfert sélectionné. Les utilisateurs peuvent sélectionner manuellement des lignes dans la liste puis, dans le volet **Détails**, mettre à jour le champ **Quantité de réception** pour la ligne sélectionnée. Dans la vue **Liste complète des commandes**, les utilisateurs peuvent lire les codes-barres, ou ils peuvent utiliser la fonction **Recevoir le produit** pour saisir l’ID article ou le code-barres et les données sur la quantité reçue, sans avoir à sélectionner au préalable la ligne d’article correspondante dans la liste.

### <a name="over-receiving-validations"></a>Validations pour réception excessive

Les validations se produisent pendant le processus de réception pour les lignes de document. Elles comprennent les validations pour livraison excessive. Si un utilisateur tente de recevoir plus de stock que à ce qui a été commandé sur une commande fournisseur, mais la livraison excessive n’est pas configurée ou le montant reçu dépasse la tolérance de livraison excessive configurée pour la ligne de commande fournisseur, l’utilisateur reçoit une erreur et n’est pas autorisé à recevoir la quantité excédentaire.

La réception excessive n’est pas autorisée pour les documents d’ordre de transfert. Les utilisateurs recevront toujours des erreurs s’ils tentent de recevoir plus que ce qui a été expédié pour la ligne d’ordre de transfert.

### <a name="close-purchase-order-lines"></a>Fermer des lignes de commandes fournisseur

Vous pouvez clôturer la quantité restante sur une commande d’achat entrante pendant le processus de réception si l’expéditeur a confirmé qu’il ne peut pas expédier la quantité totale demandée. Pour ce faire, la société doit être configurée pour autoriser les livraisons incomplètes des commandes fournisseur. De plus, un pourcentage de tolérance de livraison incomplète doit être défini pour la ligne de commande fournisseur.

Pour configurer l’entreprise afin qu’elle autorise la livraison incomplète des commandes fournisseur, au siège de Commerce, accédez à **Approvisionnements** > **Configuration** > **Paramètres d’approvisionnement**. Dans l’onglet **Livraison**, activez le paramètre **Accepter les livraisons incomplètes**. Exécutez ensuite la tâche de programme de distribution **1070** (**Configuration de canal**) pour synchroniser les modifications du paramètre entre les canaux.

Les pourcentages de tolérance de livraison incomplète pour une ligne de commande fournisseur peuvent être prédéfinis sur les produits dans le cadre des configurations de produit au siège de Commerce. Ils peuvent également être définis ou remplacés sur une ligne de commande fournisseur spécifique au siège de Commerce.

Une fois qu’une organisation a terminé les configurations de livraison incomplète des commandes fournisseur, les utilisateurs du PDV voient une nouvelle option **Clôturer la quantité restante** dans le volet **Détails** lorsqu’ils sélectionnent une ligne de commande fournisseur entrant dans l’**Opération de stock entrant**. Si l’utilisateur clôture la quantité restante, le PDV effectue une validation pour vérifier que la quantité qui est fermée se situe dans la tolérance de pourcentage de livraison incomplète définie sur la ligne de commande fournisseur. En cas de dépassement de la tolérance de livraison incomplète, un message d’erreur s’affiche et l’utilisateur ne peut pas fermer la quantité restante tant que la quantité précédemment reçue plus la quantité **Recevoir maintenant** atteint ou dépasse la quantité minimale qui doit être reçue en fonction du pourcentage de tolérance de livraison incomplète. 

Quand l’option **Clôturer la quantité restante** est activée pour une ligne de commande fournisseur, lorsque l’utilisateur achève la réception à l’aide de l’action **Terminer la réception**, une demande de clôture est également envoyée au siège de Commerce, et toute quantité non reçue de cette ligne de commande sera annulée. À ce stade, la ligne est considérée comme entièrement reçue. 

### <a name="receiving-location-controlled-items"></a>Articles contrôlés par l’emplacement de réception

Si les articles reçus sont contrôlés par l’emplacement, les utilisateurs peuvent sélectionner l’emplacement de réception des articles pendant le processus de réception. Nous vous recommandons de configurer un emplacement de réception par défaut pour votre entrepôt de magasin, afin de rendre ce processus plus efficace. Même si un emplacement par défaut est configuré, les utilisateurs peuvent remplacer l’emplacement de réception sur les lignes sélectionnées selon leurs besoins.

L’opération respecte la configuration **Accusé de réception vide autorisé** sur la dimension de stockage **Emplacement** et ne nécessite pas la saisie d’une dimension d’emplacement si un accusé de réception vide est configuré. Si les emplacements de réception vides ne sont pas autorisés pour un article, l’application PDV affiche une erreur et demande qu’un emplacement soit saisi avant que l’accusé de réception puisse être validé.

### <a name="receive-all"></a>Recevoir tout

Selon vos besoins, vous pouvez sélectionner **Recevoir tout** sur la barre d’application pour mettre à jour rapidement la quantité **Recevoir maintenant** pour toutes les lignes de document sur la valeur maximale disponible pour réception pour ces lignes.

### <a name="receipt-of-unplanned-items-on-purchase-orders"></a>Réception d’articles non planifiés sur les commandes fournisseur

Dans Commerce version 10.0.14 et ultérieure, les utilisateurs peuvent recevoir un produit qui ne figurait pas à l’origine sur la commande fournisseur. Pour activer cette fonctionnalité, activez **Ajouter des lignes à la commande fournisseur lors de la réception au point de vente**.  

Cette fonctionnalité ne fonctionne que pour la réception des commandes fournisseur. Il n’est pas possible de recevoir des articles avec des ordres de transfert lorsque les articles n’ont pas été précédemment commandés et expédiés depuis l’entrepôt sortant.

Les utilisateurs ne peuvent pas ajouter de nouveaux produits à la commande fournisseur lors de la réception au point de vente si le [workflow de gestion de modification](https://docs.microsoft.com/dynamics365/supply-chain/procurement/purchase-order-approval-confirmation) de la commande fournisseur est activé au siège de Commerce. Pour activer la gestion des modifications, toutes les modifications apportées à une la commande fournisseur doivent d’abord être approuvées avant que la réception ne soit autorisée. Étant donné que ce processus permet à un destinataire d’ajouter de nouvelles lignes à la commande fournisseur, la réception échouera si le workflow de gestion des modifications est activé. Si la gestion des modifications est activée pour toutes les la commandes fournisseur ou pour le fournisseur lié à la la commande fournisseur en cours de réception active dans le PDV, l’utilisateur ne peut pas ajouter de nouveaux produits à la la commande fournisseur lors de la réception au PDV.

La fonctionnalité qui permet d’ajouter des lignes ne peut pas être utilisée comme solution pour recevoir des quantités supplémentaires de produits déjà sur la commande fournisseur. La sur-réception est gérée par les paramètres de [sur-réception](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation#over-receiving-validations) standard de la ligne de produits sur la commande fournisseur.

Si **Ajouter des lignes à la commande fournisseur lors de la réception au point de vente** est activé et qu’un utilisateur effectue la réception avec l’**Opération entrante** dans le PDV, si l’utilisateur scanne ou saisit un code-barres de produit ou un numéro de produit qui n’est pas reconnu comme un article de la commande fournisseur en cours, mais est reconnu comme un article valide, l’utilisateur reçoit un message concernant l’ajout de l’article à la commande fournisseur. Si l’utilisateur ajoute l’article à la commande fournisseur, la quantité saisie dans **Recevoir maintenant** est considérée comme la quantité commandée pour la ligne de commande fournisseur.

Lorsque la réception de la commande fournisseur est terminée et soumise au siège pour traitement, les lignes ajoutées sont créées sur le document principal de la commande fournisseur. Sur la ligne de la commande fournisseur au siège, il y aura un indicateur **Ajouté par le PDV** sur l’onglet **Général** de la de la ligne de la commande fournisseur. L’indicateur **Ajouté par le PDV** indique que la ligne de la commande fournisseur a été ajoutée par le processus de réception du PDV et n’était pas une ligne qui figurait sur la commande fournisseur avant la réception.

### <a name="cancel-receiving"></a>Annuler la réception

Vous devez utiliser la fonction **Annuler la réception** sur la barre d’application uniquement si vous souhaitez fermer le document sans enregistrer les modifications. Par exemple, vous avez initialement sélectionné le document incorrect et vous ne voulez pas enregistrer les données de réception précédentes.

### <a name="pause-receiving"></a>Suspendre la réception

Si vous recevez du stock, vous pouvez utiliser la fonction **Suspendre la réception** si vous souhaitez suspendre le processus de réception. Par exemple, vous souhaitez effectuer une autre opération dans le PDV, comme enregistrer une vente client ou retarder la validation de l’accusé de réception.

Lorsque vous sélectionnez **Suspendre la réception**, le statut du document est modifié en **Suspendu(e)**. Ainsi, les utilisateurs sauront que des données ont été saisies pour le document, mais le document n’a pas encore été validé. Lorsque vous êtes prêt à reprendre le processus de réception, sélectionnez le document mis en pause, puis sélectionnez **Détails de la commande**. Les quantités **Recevoir maintenant** précédemment enregistrées sont conservées et disponibles dans la vue **Liste complète des commandes**.

### <a name="review"></a>Revoir

Avant l’engagement final de la réception au siège Commerce, vous pouvez utiliser la fonction Vérifier pour valider le document entrant. La vérification vous avertit des données potentiellement manquantes ou incorrectes susceptibles de provoquer un échec de traitement et vous offre la possibilité de corriger les problèmes avant de soumettre la demande de réception. Pour activer la fonction **Vérifier** dans la barre d’applications, activez la fonctionnalité **Activer la validation dans les opérations de stock entrant et sortant du point de vente** via l’espace de travail **gestion des fonctionnalités** au siège Commerce.

La fonction **Vérifier** valide les problèmes suivants dans un document entrant :

- **Surréception** – la quantité reçue maintenant est supérieure à la quantité commandée. La gravité de ce problème est déterminée par la configuration de surlivraison au siège de Commerce.
- **Sous-réception** – la quantité reçue maintenant est inférieure à la quantité commandée. La gravité de ce problème est déterminée par la configuration de sous-livraison au siège de Commerce.
- **Numéro de série** – Le numéro de série n’est pas fourni ou validé pour un article sérialisé qui nécessite un numéro de série pour être enregistré dans l’inventaire.
- **Emplacement non défini** – L’emplacement n’est pas spécifié pour un élément contrôlé par emplacement où l’emplacement vide n’est pas autorisé.
- **Lignes supprimées** – La commande comporte des lignes supprimées par un utilisateur du siège Commerce inconnu de l’application PDV.

Définissez le paramètre **Activer la validation automatique** sur **Oui** dans **Paramètres Commerce** > **Stock** > **Stock du magasin** pour que la validation soit exécutée automatiquement lorsque **Terminer la réception** est sélectionné.

### <a name="finish-receiving"></a>Terminer la réception

Lorsque vous avez terminé de saisir toutes les quantités **Recevoir maintenant** pour les produits, vous devez sélectionner **Terminer la réception** sur la barre d’application pour traiter la réception.

Lorsque les utilisateurs finalisent un accusé de réception de commande fournisseur, ils sont invités à saisir une valeur dans le champ **Numéro d’accusé de réception**, si cette fonctionnalité est configurée. Généralement, cette valeur est équivalente à l’identificateur du bon de livraison fournisseur. Les données **Numéro d’accusé de réception** seront stockées dans le journal des accusés de réception de produit dans Commerce Headquarters. Les numéros d’accusé de réception ne sont pas capturés pour les ordres de transfert.

Lorsque le traitement de document asynchrone est utilisé, l’accusé de réception est envoyé via une structure de document asynchrone. Le temps de validation du document dépend de la taille du document (le nombre de lignes) et du trafic de traitement général sur le serveur. Généralement, ce processus se produit en quelques secondes. Si la validation du document échoue, l’utilisateur en est informé via la liste de documents **Opération entrante**, où le statut du document sera mis à jour sur **Échec du traitement**. L’utilisateur peut ensuite sélectionner le document ayant échoué dans le PDV pour afficher les messages d’erreur et la raison de l’échec dans le volet **Détails**. Un document ayant échoué reste non validé et nécessite que l’utilisateur retourne aux lignes de document en sélectionnant **Détails de la commande** dans le PDV. L’utilisateur doit ensuite mettre à jour le document avec les corrections, en fonction des erreurs. Une fois un document corrigé, l’utilisateur peut réessayer de le traiter en sélectionnant **Terminer l’exécution** sur la barre d’application.

## <a name="create-an-inbound-transfer-order"></a>Créer un ordre de transfert entrant

Dans le PDV, les utilisateurs peuvent créer des documents d’ordre de transfert. Pour commencer le processus, sélectionnez **Nouveau** sur la barre d’application lorsque vous êtes dans la liste de documents **Opération entrante** principale. Vous êtes ensuite invité à sélectionner un entrepôt ou un magasin **Transférer depuis** qui fournira le stock dans l’emplacement de votre magasin. Les valeurs sont limitées à la sélection définie dans la configuration du groupe d’exécution du magasin. Dans une demande de transfert entrante, votre magasin actuel sera toujours l’entrepôt **Transférer à** pour l’ordre de transfert. Les valeurs ne peuvent pas être modifiées.

Vous pouvez saisir des valeurs dans les champs **Date d’expédition**, **Date de réception** et **Mode de livraison** selon vos besoins. Vous pouvez également ajouter une note qui sera stockée avec l’en-tête de l’ordre de transfert, en tant que pièce jointe au document dans Commerce Headquarters.

Une fois les informations d’en-tête créées, vous pouvez ajouter des produits à l’ordre de transfert. Pour démarrer le processus d’ajout des articles et des quantités demandées, sélectionnez **Ajouter un produit**. Dans le volet **Détails**, vous pouvez également ajouter une note spécifique à la ligne aux lignes du journal. Ces notes seront stockées sous forme de pièce jointe à la ligne.

Une fois les lignes saisies dans l’ordre de transfert entrant, vous devez sélectionner **Enregistrer** pour enregistrer les modifications du document localement ou **Envoyer la demande** pour envoyer les détails de la commande à Commerce Headquarters pour traitement ultérieur. Si vous sélectionnez **Enregistrer**, le brouillon du document est stocké dans la base de données du canal et l’entrepôt sortant ne peut pas exécuter le document tant qu’il n’a pas été traité avec succès via **Envoyer la demande**. Vous devez sélectionner **Enregistrer** uniquement si vous n’êtes pas prêt à valider la demande dans Commerce Headquarters pour traitement.

Si un document est enregistré localement, il se trouve dans l’onglet **Brouillons** de la liste de documents **Opération entrante**. Lorsqu’un document est à l’état **Brouillon**, vous pouvez le modifier en sélectionnant **Modifier**. Vous pouvez mettre à jour, ajouter ou supprimer des lignes selon vos besoins. Vous pouvez également supprimer l’intégralité du document lorsqu’il est à l’état **Brouillon** en sélectionnant **Supprimer** dans l’onglet **Brouillons**.

Une fois le brouillon de document envoyé avec succès à Commerce Headquarters, il s’affiche dans l’onglet **Actif** et a le statut **Demandé(e)**. À ce stade, les utilisateurs du magasin ou de l’entrepôt entrant ne peuvent plus modifier le document d’ordre de transfert entrant demandé. Seuls les utilisateurs de l’entrepôt sortant peuvent modifier le document en sélectionnant **Opération sortante** dans l’application PDV. Le verrou de modification garantit qu’aucun conflit ne se produit car un demandeur entrant modifie l’ordre de transfert en même temps que l’expéditeur sortant prélève et expédie activement la commande. Si des modifications sont nécessaires dans le magasin ou l’entrepôt entrant une fois l’ordre de transfert envoyé, l’expéditeur sortant doit être contacté et invité à entrer les modifications.

Une fois le document à l’état **Demandé(e)**, il est visible dans l’onglet **Actif**. Cependant, il ne peut pas encore être reçu par le magasin ou l’entrepôt entrant. Une fois que l’entrepôt sortant a expédié une partie ou la totalité de l’ordre de transfert, le magasin ou l’entrepôt entrant peut valider les accusés de réception dans le PDV. Lorsque la partie sortante traite les documents d’ordre de transfert, leur statut est mis à jour de **Demandé(e)** à **Expédié(e)** ou **Partiellement expédié(e)**. Une fois les documents à l’état **Expédié(e)** ou **Partiellement expédié(e)**, le magasin ou l’entrepôt entrant peut valider les accusés de réception à l’aide du processus de réception de l’opération entrante.

## <a name="related-topics"></a>Rubriques connexes

[Opération de stock sortant dans le PDV](pos-outbound-inventory-operation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]