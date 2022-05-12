---
title: Créer des retours dans le PDV
description: Cette rubrique décrit comment initier des retours pour des transactions au comptant ou des commandes client dans l’application de point de vente (PDV) de Microsoft Dynamics 365 Commerce.
author: hhainesms
ms.date: 04/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.20
ms.openlocfilehash: c8e06c0d83e3bc2f5efea1e3a8124c700706aa2e
ms.sourcegitcommit: 9e1129d30fc4491b82942a3243e6d580f3af0a29
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8648986"
---
# <a name="create-returns-in-pos"></a>Créer des retours dans le PDV

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment initier des retours pour des transactions au comptant ou des commandes client dans l’application de point de vente (PDV) de Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Dans les versions 10.0.20 et ultérieures de Commerce, une nouvelle fonctionnalité nommée **Expérience unifiée du traitement des retours dans la PDV** est disponible. Cette fonctionnalité fournit un processus de retour plus cohérent et unifié dans le point de vente, quel que soit le type de transaction (transaction au comptant ou commande client) ou le canal d’origine dans lequel la commande a été créée. Nous recommandons à toutes les organisations d’activer cette nouvelle fonctionnalité pour améliorer la fiabilité globale du traitement des retours via le PDV.
>
> Une fois la fonctionnalité activée, elle ne peut pas être désactivée.

## <a name="process-returns-by-using-the-return-transaction-operation"></a>Traiter les retours à l’aide de l’opération de transaction de retour

Nous vous recommandons d’ajouter l’opération de transaction de retour à la [disposition d’écran](pos-screen-layouts.md) de votre PDV. Dans les versions antérieures à la version 10.0.20 de Commerce, l’opération de transaction de retour ne prenait correctement en charge que les retours des transactions au comptant. Après avoir activé la fonctionnalité **Expérience unifiée du traitement des retours pour le PDV** de la version Commerce 10.0.20 ou ultérieure, l’opération de transaction de retour prend également en charge le traitement des retours provenant de commandes clients, telles que les commandes « retrait » ou « livraison à domicile » déjà facturées.

À partir de l’opération de transaction de retour, les utilisateurs peuvent rechercher une transaction au comptant ou une commande client pour effectuer le retour en saisissant l’un des quatre critères de recherche suivants. Les utilisateurs peuvent saisir ces critères à l’aide d’un clavier périphérique, d’un clavier à l’écran ou d’un lecteur de codes-barres.

- ID ticket de caisse
- Numéro d’ordre
- ID de référence de canal (également appelé ID de confirmation de commande)
- ID facture

Si une transaction ou une commande correspond aux critères de recherche, la page **Produits retournables** s’affiche. Là, les utilisateurs peuvent spécifier les articles qui sont retournés. Ils peuvent également saisir les quantités de retour et les codes motif.

Pour chaque ligne de commande de la liste des produits retournables, le PDV affiche des informations sur la quantité d’achat d’origine et les quantités de tous les retours qui ont été précédemment traités. La quantité de retour qu’un utilisateur saisit pour une ligne de commande doit être inférieure ou égale à la valeur du champ **Disponible pour le retour**.

![Page des produits retournables.](media/returnslist.png)

Pendant le traitement du retour, si un utilisateur possède le produit physique et que ce produit porte un code-barres, l’utilisateur peut scanner le code-barres pour enregistrer le retour. Chaque lecture du code-barres augmente la quantité de retour d’un article. Cependant, si l’étiquette du code à barres comporte une quantité intégrée, cette quantité sera saisie dans le champ **Retour maintenant**.

Les utilisateurs peuvent également sélectionner manuellement les articles à retourner sur la page **Produits retournables**, puis mettre à jour le champ **Retour maintenant** en utilisant le volet de détails sur la droite.

Si la quantité maximale disponible de **Retour maintenant** est spécifiée pour une transaction, l’utilisateur peut sélectionner l’opération **Tout sélectionner** sur la barre d’application du PDV pour définir la quantité maximale retournée sur toutes les lignes.

Pour chaque ligne qui comporte une quantité **Retour maintenant**, l’utilisateur doit sélectionner un code de motif de retour en utilisant le panneau de détails. Pour les retours de transactions au comptant, les codes de motif de retour sont configurés en tant que codes d’information dans le profil de fonctionnalité du magasin. Pour les retours de commandes clients, les codes motif de retour sont configurés sur la page **Codes de motif de retour** dans Dynamics 365 Commerce Headquarters.

Une fois que la quantité de retour et le code de motif ont été définis pour chaque article qui doit être retourné, l’utilisateur peut sélectionner l’opération **Reour** sur la barre d’application du PDV pour poursuivre le traitement. La page de transaction de PDV s’affiche ; les articles retournables qui ont été sélectionnés sur la page précédente ont été ajoutés au panier. Les quantités de **Retour maintenant** des articles apparaissent sous forme de lignes de quantité négative sur la transaction et le remboursement total est calculé.

Les utilisateurs peuvent ajouter des lignes à une transaction de retour s’ils créent un ordre d’échange. Les utilisateurs peuvent également ajouter plus d’articles de retour à une transaction de retour en utilisant l’opération **Retourner le produit** pour une ligne de vente de quantité positive sélectionnée qui a été ajoutée.

> [!NOTE]
> L’opération **Retourner le produit** dans le PDV ne fournit aucune validation par rapport à une transaction d’origine et permet le retour de tout produit. Par conséquent, nous recommandons que seuls les utilisateurs autorisés soient autorisés à effectuer cette opération, ou qu’elle fasse appel à une prise de contrôle d’un responsable.

Si un remboursement est dû à la caisse, les organisations peuvent configurer des [politiques de remboursement](refund_policy_returns.md) qui limitent les modes de paiement pouvant être utilisés pour rembourser les clients. Si la transaction d’origine a été payée à l’aide d’une carte de crédit, selon l’organisme de traitement du paiement et la configuration du système, les utilisateurs peuvent avoir la possibilité d’[effectuer un remboursement sur la carte d’origine](dev-itpro/linked-refunds.md). Dans ce cas, le remboursement peut être effectué sans exiger que le client glisse à nouveau sa carte de crédit. Le jeton de paiement d’origine est utilisé pour effectuer le remboursement.

## <a name="other-return-options-in-pos"></a>Autres options de retour dans le PDV

Quand la fonctionnalité **Expérience unifiée du traitement des retours dans le PDV** est activée, les utilisateurs peuvent également utiliser l’opération **Afficher le journal** dans le PDV pour initier un retour pour une transaction au comptant ou une commande client. Ils peuvent alors sélectionner une transaction dans le journal, puis sélectionner l’opération **Retourner** sur la barre d’applications du PDV. Cette opération n’est disponible que s’il y a des lignes retournables sur la commande. Elle initie la même expérience utilisateur que l’opération **Transaction de retour**.

Les utilisateurs peuvent également utiliser l’opération **Rappeler la commande** dans le PDV pour rechercher et rappeler les commandes des clients. (Cette opération ne peut pas être utilisée pour les transactions au comptant). Dans ce cas, après sélection d’une commande client, l’opération **Retour** sur la barre d’application du PDV peut être utilisée pour initier un retour pour la commande client. Cette opération n’est disponible que s’il y a des lignes retournables sur la commande. Elle initie la même expérience utilisateur que l’opération **Transaction de retour** o **Afficher le journal**.

## <a name="return-orders-are-posted-to-commerce-headquarters-as-sales-orders"></a>Les retours sont enregistrés dans Commerce Headquarters en tant que bons de commande 

Quand la fonction **Expérience unifiée du traitement des retours dans le PDV** est activée, tous les retours créés dans le PDV sont écrits dans Commerce Headquarters en tant que commandes client comportant des lignes négatives. Dans les versions antérieures à la version 10.0.20 de Commerce, les utilisateurs peuvent choisir si les commandes de retour doivent être validées en tant que commandes client comportant des lignes négatives ou si elles doivent être des commandes de retour créées via le processus d’autorisation de retour de marchandise (RMA). 

Dans la fonction **Expérience unifiée du traitement des retours dans le PDV**, l’option d’utiliser le processus RMA pour créer des retours dans le PDV a été rendue obsolète. Une fois cette fonctionnalité activée, tous les retours seront créés en tant que commandes client comportant des lignes négatives.

## <a name="offline-return-processing-improvements"></a>Améliorations du traitement des retours hors ligne

Dans la plupart des cas, quand un retour est traité dans le PDV, le système essaie de faire un appel de service en temps réel (RTS) à Commerce Headquarters pour valider les quantités actuelles disponibles pour le retour. Cette validation permet d’éviter les scénarios de fraude dans lesquels un client essaie de retourner le même article à plusieurs endroits.

Pour gérer les situations où l’appel RTS ne peut pas être effectué en raison de problèmes de réseau ou de connectivité, un processus a été mis en place pour synchroniser périodiquement les données de quantité de retour entre Commerce Headquarters et la base de données de canal d’un magasin. Ce suivi des retours côté canal permet de s’assurer que les quantités **Disponibles pour le retour** affichées dans le PDV sont raisonnablement précises, même quand le PDV est hors ligne. Cela garantit également que le PDV peut continuer à valider les informations côté canal pour aider à prévenir les retours frauduleux.

Pour utiliser le processus de retour hors ligne de manière appropriée, les organisations doivent planifier la tâche en traitement par lots **Mettre à jour les quantités de retour** dans Commerce Headquarters de manière à ce qu’elle s’exécute fréquemment. Nous recommandons que ce travail s’exécute à la même fréquence que le travail P qui extrait les nouvelles transactions des canaux Commerce vers Commerce Headquarters.

La tâche **Mettre à jour les quantités de retour** calcule la quantité disponible pour le retour pour toutes les commandes client trouvées dans Commerce Headquarters. Les données que la tâche calcule doivent ensuite être envoyées aux bases de données de canal, afin que les canaux de stockage puissent être mis à jour. La tâche de distribution **Quantités de retour** (1200) est utilisé à cette fin. Étant donné que les données sur la quantité retournable sont synchronisées depuis Commerce Headquarters, si un retour est traité dans le PDV, mais que l’appel RTS ne peut pas être effectué, le PDV peut utiliser les informations de retour côté canal pour valider les quantités **Disponibles pour le retour** pour une ligne de vente donnée.

Quand les appels RTS ne peuvent pas être effectués et que le PDV utilise des données côté canal pour la validation du retour, un message d’avertissement informe les utilisateurs qu’ils créent un retour « hors ligne ». Par conséquent, ils sont conscients que la quantité **Disponible pour le retour** indiquée dans le PDV peut être périmée et ne plus être exacte, selon le moment où la tâche **Mettre à jour les quantités de retour** a été traitée et synchronisée avec le canal pour la dernière fois.

Par exemple, un client a récemment traité un retour pour une ligne de commande dans un autre canal, mais ces données n’ont pas encore été synchronisées avec les bases de données du canal via la tâche **Mettre à jour les quantités de retour**. Le client se rend ensuite dans un autre magasin et essaie à nouveau de retourner le même article. Dans ce cas, si le magasin ne peut pas passer l’appel RTS à Commerce Headquarters pour obtenir les données de retour en temps réel, le PDV autorisera à nouveau le retour de l’article. Cependant, l’utilisateur sera averti que les informations qui sont utilisées pour valider le retour peuvent être périmées. Le message que l’utilisateur reçoit n’est qu’un message d’avertissement. Il n’empêche pas l’utilisateur de continuer à traiter le retour.

Si les informations côté canal ne sont pas à jour pour une raison quelconque et qu’un retour hors ligne est traité pour une quantité qui dépasse la quantité **Disponible pour le retour** réelle, une erreur peut être générée au moment de l’exécution de la validation du relevé pour créer la transaction dans Commerce Headquarters.

> [!NOTE]
> Quand la fonction **Expérience unifiée de traitement des retours dans le PDV** est activée, de nouvelles fonctions facultatives prenant en charge la validation des retours de produits à numéro de série deviennent disponibles. Pour plus d’informations, consultez [Retour de produits contrôlés par numéro de série dans le point de vente (PDV)](POS-serial-returns.md).

## <a name="version-details"></a>Détails de la version

La liste suivante fournit les versions minimales requises pour les différents composants.
- Commerce Headquarters ; version 10.0.20
- Commerce Scale Unit (CSU) : version 9.30
- Point de vente (PDV) : version 9.30

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a>Activer le calcul de taxe correct pour les retours avec une quantité partielle

Cette fonctionnalité garantit que quand une commande est retournée à l’aide de plusieurs factures, les taxes seront finalement égales au montant des taxes initialement facturées.

1. Dans l’espace de travail **Gestion des fonctionnalités**, recherchez **Activer le calcul de taxe correct pour les retours avec une quantité partielle**.
1. Sélectionnez la fonctionnalité **Activer le calcul de taxe correct pour les retours avec une quantité partielle**, puis sélectionnez **Activer**.

## <a name="set-up-return-locations-for-retail-stores"></a>Paramétrer des emplacements de retour pour les magasins de vente au détail

Commerce vous permet de paramétrer les emplacements de retour basés sur les codes info de la vente au détail et les codes motif des ventes et du marketing. Quand les clients retournent un achat, les caissiers indiquent généralement le motif du retour. Vous pouvez spécifier que les produits retournés doivent être affectés à des emplacements de retour en stock différents en fonction des codes info et motif sélectionnés par le caissier dans la caisse enregistreuse du PDV.

Par exemple, un client retourne un produit défectueux et le caissier traite la transaction de retour. Quand Retail POS affiche le code d’information pour les retours, le caissier sélectionne le sous-code pour les retours défectueux. Le produit retourné est alors automatiquement affecté à un lieu de retour spécifique.

Un emplacement de retour peut être un entrepôt, un emplacement dans un entrepôt, ou même une palette spécifique, en fonction des emplacements de stock définis par votre organisation. Vous pouvez mettre en correspondance chaque emplacement de retour avec un ou plusieurs codes info dans les codes motif ventes et marketing.

### <a name="prerequisites"></a>Conditions préalables

Vous devez paramétrer les élémets suivants avant de pouvoir paramétrer des emplacements de retour :

- **Codes info de la vente au détail** – Invites au niveau de la caisse enregistreuse du PDV paramétrées dans le module **Retail**. Pour plus d’informations, voir [Configuration des codes info](/dynamicsax-2012/appuser-itpro/setting-up-info-codes).
- **Codes motif Ventes et marketing** – Invites au niveau de la caisse enregistreuse du PDV paramétrées dans le module **Ventes et marketing**. Pour plus d’informations, voir [Configuration des codes motif](/dynamicsax-2012/appuser-itpro/set-up-return-reason-codes).
- **Emplacements de stockage** – Emplacements dans lesquels le stock est conservé. Pour plus d’informations, voir [Paramétrage des emplacements des stocks](/dynamicsax-2012/appuser-itpro/about-locations).
    
### <a name="set-up-return-locations"></a>Paramétrage des emplacements de retour

Pour paramétrer des emplacements de retour, procédez comme suit.

1. Aller à **Retail et Commerce \> Configuration du canal \> Entrepôts**, puis sélectionnez un entrepôt.
1. Sur le raccourci **Retail**, dans le champ **Emplacement de retour par défaut**, sélectionnez l’emplacement de stock à utiliser pour les retours où les codes d’information ou les codes de motif ne sont pas mappés aux emplacements de retour.
1. Dans le champ **Palette de retour par défaut**, sélectionnez la palette à utiliser pour les retours où les codes d’information ou les codes de motif ne sont pas mappés aux emplacements de retour.
1. Accédez à **Retail et Commerce \> Gestion des stocks \> Emplacements de retour**.
1. Sélectionnez **Nouveau** pour créer une stratégie d’emplacement de retour.
1. Entrez un nom unique et une description pour l’emplacement de retour.

    > [!NOTE]
    > Si une souche de N° a été paramétrée pour les emplacements de retour, le nom est entré automatiquement.

1. Sur le raccourci **Général**, définissez l’option **Imprimer des étiquettes** sur **Oui** pour imprimer des étiquettes pour tous les produits affectés à des emplacements de retour.
1. Définissez l’option **Bloquer le stock** sur **Oui** pour retirer du stock les produits retournés dans l’emplacement de retour par défaut et empêcher qu’ils soient revendus.
1. Pour mapper des codes d’information et des sous-codes de vente au détail spécifiques aux emplacements de retour, procédez comme suit :

    1. Dans le raccourci **Codes Info de la vente au détail**, sélectionnez **Ajouter**.
    1. Dans le champ **Code info**, sélectionnez un code info pour les retours.
    1. Dans le champ **Sous-code**, sélectionnez un sous-code motif pour le retour. Le champ **Description** présente la description du sous-code sélectionné.
    1. Dans le champ **Magasin**, sélectionnez le magasin où le code info est utilisé.
    1. Utilisez les champ **Entrepôt**, **Emplacement** et **ID palette** pour spécifier un emplacement de retour. Par exemple, pour spécifier un emplacement particulier dans un magasin, sélectionnez un magasin dans le champ **Magasin** et un emplacement dans le champ **Emplacement**.
    1. Cochez la case **Bloquer le stock** pour retirer du stock des produits retournés et empêcher qu’ils soient revendus.

1. Pour mapper des codes motifs de vente et marketing spécifiques aux emplacements de retour, procédez comme suit :

    1. Sur le racourci **Codes motif de vente et de marketing**, sélectionnez **Ajouter**.
    1. Dans le champ **Code motif**, sélectionnez un code motif pour les retours. Le champ **Description** présente la description du code motif sélectionné.
    1. Dans le champ **Magasin**, sélectionnez le magasin où le code motif est utilisé.
    1. Utilisez les champ **Entrepôt**, **Emplacement** et **ID palette** pour spécifier un emplacement de retour. Par exemple, pour spécifier une palette au niveau d’un emplacement dans un entrepôt, sélectionnez un entrepôt dans le champ **Entrepôt**, un emplacement dans le champ **Emplacement**, et une palette dans le champ **ID palette**.
    1. Cochez la case **Bloquer le stock** pour retirer du stock des produits retournés et empêcher qu’ils soient revendus.

    > [!NOTE]
    > Si une stratégie de lieu de retour est utilisée pour un article, mais que le motif de retour sélectionné par un caissier ne correspond à aucun code spécifié sur le raccourci **Codes info de vente au détail** ou **Codes de vente et de marketing**, l’article est envoyé à l’emplacement de retour par défaut qui est défini sur la page **Entrepôt**. De plus, le paramétrage de la case à cocher **Bloquer le stock** sur le Raccourci **Général** de la page **Emplacements de retour** détermine si l’article retourné doit être bloqué dans le stock.

1. Accédez à **Retail et Commerce \> Hiérarchie des produits vendus au détail**.
1. Sur le raccourci **Gérer les propriétés des catégories de stock**, dans le champ **Emplacement de retour**, sélectionnez un emplacement de retour. Étant donné que plusieurs stratégies d’emplacement de retour peuvent être définies pour le même magasin, la valeur que vous sélectionnez ici détermine la stratégie d’emplacement de retour qui est utilisée.

## <a name="additional-resources"></a>Ressources supplémentaires

[Retour de produits contrôlés par numéro de série dans le point de vente (PDV)](POS-serial-returns.md)

[Remboursements liés aux transactions précédemment approuvées et confirmées](dev-itpro/linked-refunds.md)

[Créer et mettre à jour une stratégie de retour et de remboursement pour un canal](refund_policy_returns.md)

[Configurations visuelles de l’interface utilisateur de PDV](pos-screen-layouts.md)
