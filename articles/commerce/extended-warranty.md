---
title: Créer et configurer des extensions de garantie
description: Cette rubrique couvre les extensions de garantie et décrit leur création et configuration dans Microsoft Dynamics 365 Commerce.
author: sijoshi
manager: annbe
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: sijoshi
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 411895763cc282766b5a668208f20c72496059cd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965114"
---
# <a name="create-and-configure-extended-warranties"></a>Créer et configurer des extensions de garantie

[!include [banner](includes/banner.md)]

Cette rubrique couvre les extensions de garantie et décrit leur création et configuration dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Les clients choisissent de plus en plus une assistance et des services étendus lorsqu’ils achètent des produits, en particulier des produits de consommation vendus à un prix élevé, tels que les téléphones et les ordinateurs. En offrant des garanties prolongées d’achat, les détaillants peuvent aider à fidéliser la clientèle. Les extensions de garantie permettent aux clients de savoir où ils peuvent aller pour le service et le support. Par conséquent, ils peuvent avoir confiance que leurs problèmes seront traités efficacement.

Les garanties prolongées peuvent être vendues aux clients dans un canal de vente au détail lors de l’achat initial du produit. Ils peuvent également être vendus pour une durée limitée après l’achat initial.

### <a name="warranty-item-setup"></a>Configuration d’une garantie

Dynamics 365 Commerce fournit des fonctionnalités qui vous permettent de créer une garantie et de définir ses attributs. Ces attributs incluent l’association entre un produit et une garantie, le prix de la garantie et la durée de la garantie. Une fois une garantie configurée et validée dans l’unité d’organisation, un détaillant peut vendre des garanties via le point de vente moderne (MPOS), les magasins en ligne et d’autres canaux de vente au détail.

### <a name="warranty-item-sales"></a>Ventes avec garantie

Les garanties prolongées sont vendues dans un canal de vente au détail lors de l’achat initial du produit. Ils peuvent également être vendus pour une durée limitée après l’achat initial.

Au point de vente (PDV), les commerciaux sont invités à ajouter une extension de garantie lorsqu’un produit connexe est ajouté au panier d’un client. Par conséquent, une opportunité de vente incitative ou de vente croisée est présentée aux commerciaux dans le cadre du flux de vente.

Les clients peuvent également revenir plus tard et acheter une extension de garantie pour un produit qu’ils ont précédemment acheté. Dans ces cas, un vendeur peut rechercher la transaction d’origine et vendre au client l’article avec extension de garantie correspondant.

### <a name="warranty-terminology"></a>Terminologie de la garantie

Le tableau suivant définit certains termes liés à la garantie.

| Terme | Description |
|------------------------------|--------------|
| Extension de garantie/Garantie | Une *extension de garantie* fait référence à un contrat ou contrat de service qui fournit une garantie prolongée aux clients. L’extension de garantie comprend le service supplémentaire de remplacement ou de réparation de biens pendant la période de couverture de l’extension de garantie. |
| Garantie fabricant | Une *garantie fabricant* (souvent appelée *garantie limitée*) est la garantie que les clients reçoivent lorsqu’ils achètent un produit. Voici quelques caractéristiques de la garantie fabricant :<ul><li>Le coût de la garantie est inclus dans le coût du produit. Les clients n’ont pas à payer de montant supplémentaire pour la garantie fabricant.</li><li>Selon la catégorie de produit, la garantie fabricant dure généralement 30 jours, six mois ou un an. (Pour la plupart des appareils électroniques grand public, la garantie dure un an).</li><li>La garantie couvre tous les défauts causés par des pannes mécaniques ou électriques. La couverture est limitée et n’inclut aucun dommage accidentel au produit acheté. Les clients qui souhaitent protéger les produits qu’ils achètent contre les dommages quotidiens doivent investir dans une extension de garantie. Les extensions de garantie durent de deux à dix ans, selon la catégorie de produit. Ils ont également une couverture plus large et couvrent les incidents quotidiens tels que les gouttes, les déversements et les taches.</li></ul> |
| Garantie | Une *garantie* est un article avec extension de garantie vendu pour un article sous garantie. Un exemple est un plan de protection accidentelle de deux ans pour les ordinateurs portables. |
| Article sous garantie | Un *article sous garanti* est un produit sérialisé pour lequel une garantie est vendue. Par exemple, un ordinateur portable est un article couvert par une garantie pour lequel des garanties prolongées de deux et trois ans sont vendues. |
| Groupe de garanties | Un *groupe de garanties* est une relation entre les garanties et les articles sous garantie. Le PDV utilise des groupes de garantie pour déterminer quels articles de garantie les vendeurs doivent être invités à ajouter lorsqu’un article sous garantie est ajouté au panier d’un client. |
| Stratégie de garantie | Une *stratégie de garantie* est une entité créée dans Commerce lors de la vente d’une stratégie de garantie. Une stratégie de garantie comprend des informations telles que les dates de début et de fin de l’article de garantie acheté, les conditions générales et le numéro de série du produit garanti. Les numéros de stratégie de garantie peuvent être partagés avec les clients, afin qu’ils aient une référence pour l’extension de garantie qu’ils ont achetée. |

## <a name="create-a-warranty-item"></a>Créer un article de garantie

Pour créer un article de garantie dans Commerce, procédez comme suit.

1. Accédez à **Retail et Commerce \> Produits et catégories \> Produits**.
1. Sélectionnez **Nouveau** pour créer un article de garantie.
1. Dans la boîte de dialogue **Nouveau produit**, dans le champ **Type de produit**, sélectionnez **Service**.
1. Dans le champ **Produit générique**, sélectionnez **Produit**.
1. Dans le champ **Type de service d’article**, sélectionnez **Service**.
1. Dans le champ **Nom de produit**, entrez un nom de produit.
1. Dans le champ **Catégorie de vente au détail**, sélectionnez une valeur dans la boîte de dialogue déroulante, puis sélectionnez **OK**.
1. Dans le champ **Numéro de produit**, entrez le nouveau numéro de produit.
1. Cliquez sur **OK**.
1. Sur la page **Détails du produit**, dans le raccourci **Garantie**, définissez les champs **Unité de temps** et **Durée**.

    | Nom du champ | Valeur | Description |
    |------------|-------|-------------|
    | Unité de temps | **Jour(s)**, **Semaine(s)**, **Mois(s)** ou **Année(s)** | Ce champ spécifie l’unité de temps utilisée pour la garantie. |
    | Durée | Valeur entière positive | Ce champ spécifie la durée de la garantie dans l’unité de temps sélectionnée. |

    Par exemple, pour une garantie de deux ans, définissez le champ **Unité de temps** sur **Années** et le champ **Durée** sur **2**. Vous pouvez également définir le champ **Unité de temps** sur **Mois** et le champ **Durée** sur **24**, comme indiqué dans l’illustration suivante.

    ![Page de détails du produit pour un article de garantie](./media/ew-time-properties.png)

1. Sélectionnez **Enregistrer** pour enregistrer la garantie.
1. Remettez le produit sous garantie à l’entreprise afin qu’il puisse être vendu. Pour plus d’informations, voir [Paramétrage des produits vendus au détail](set-up-retail-products.md).
1. Sur la page **Détails du produit lancé**, dans le raccourci **Garantie**, définissez les champs **Base de gamme de prix**, **Limite inférieure** et **Limite supérieure**.

    | Nom du champ | Valeur  | Description |
    |------------|-------|-------------|
    | Base de la plage de prix | **Aucun**, **Prix de base** ou **Prix de vente** | <ul><li>**Aucun** - Les valeurs **Limite inférieure** et **Limite supérieure** des gammes de prix ne sont pas applicables.</li><li>**Prix de base** - Une garantie donnée sera applicable si le prix de base (c’est-à-dire le prix sans remise) de l’article sous garantie se situe entre les valeurs **Limite inférieure** et **Limite supérieure** spécifiées ici, en fonction du prix de l’article sous garantie.</li><li>**Prix de vente** - Cette valeur est réservée pour une utilisation future.</li></ul> |
    | Limite inférieure, Limite supérieure | Valeur entière positive | Ces champs définissent les limites de prix supérieures et inférieures de l’article sous garantie et la manière dont la garantie actuelle s’applique à l’article sous garantie. Ces limites peuvent être basées sur le prix de base de l’article sous garantie (également appelé prix de détail suggéré par le fabricant \[MSRP\]). Si le champ **Base de gamme de prix** est défini sur **Prix de base**, uniquement un article sous garantie (produit) dont le prix de base est compris entre les valeurs **Limite inférieure** et **Limite supérieure** déclenchera une invite pour ajouter la garantie au point de vente. |

    Par exemple, l’illustration suivante montre le champ **Base de gamme de prix** défini sur **Prix de base**, le champ **Limite inférieure** défini sur $500 et le champ **Limite supérieure** défini sur $1000.
    
    ![Page Détails du produit lancé pour une garantie](./media/ew-release-product-details.png)

1. Assortissez la garantie au canal où il sera vendu. Pour plus d’informations, voir [Paramétrer des assortiments](set-up-assortments.md).

### <a name="example"></a>Exemple

Un article sous garantie pour ordinateur portable (produit) a un prix de base de $999, et il existe deux garanties pour ordinateur portable :

- La garantie\_1 a une limite inférieure de $500 et une limite supérieure de $1000, et le champ **Base de gamme de prix** est défini sur **Prix de base**.
- La garantie\_2 a une limite inférieure de $1,001 et une limite supérieure de $2000, et le champ **Base de gamme de prix** est défini sur **Prix de base**.

Dans ce cas, lorsque le portable sous garantie est ajouté au panier d’un client, une invite pour ajouter la garantie\_1 sera affiché au point de vente, car le prix de l’ordinateur portable se situe entre les limites inférieure et supérieure de la garantie\_1.

> [!NOTE]
> Pour cet exemple, si vous souhaitez afficher des invites pour à la fois Garantie\_1 et Garantie\_2, quel que soit le prix de l’article sous garantie, définissez le champ **Base de gamme de prix** sur **Aucun**.

## <a name="configure-channel-specific-settings"></a>Configurer les paramètres spécifiques au canal

Les paramètres spécifiques au canal vous permettent de spécifier si une invite à ajouter une garantie doit être affichée au point de vente lorsqu’un article sous garantie est ajouté au panier d’un client.

Pour configurer le paramètre spécifique au canal dans Commerce, procédez comme suit.

1. Accédez à **Retail et Commerce \> Produits et catégories \> Garantie \> Paramètres de garantie**.
1. Dans l’onglet **Spécifique au canal**, dans la colonne **Demander une garantie** pour votre canal, procédez comme suit :

    - Cochez la case si une invite pour la garantie doit être affichée au point de vente lorsque l’article sous garantie est ajouté au panier.
    - Décochez la case si aucune invite pour la garantie ne doit être affichée au point de vente lorsque l’article sous garantie est ajouté au panier.

1. Exécutez la tâche **1070** pour synchroniser les données sur le canal.

## <a name="configure-a-number-sequence-for-warranty-policies"></a>Configurer une souche de numéros pour les stratégies de garantie

Chaque stratégie de garantie est identifiée de manière unique par un numéro de stratégie de garantie généré par une souche de numéros. Pour plus d’informations sur les souches de numéros, voir [Vue d’ensemble des souches de numéros](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).

Pour configurer une souche de numéros pour les stratégies de garantie dans Commerce, procédez comme suit.

1. Accédez à **Retail et Commerce \> Produits et catégories \> Garantie \> Paramètres de garantie**.
1. Dans l’onglet **Souches de numéros**, sur la ligne de la référence **Stratégie de garantie**, entrez ou sélectionnez une valeur dans le champ **Code souche de numéros**.

## <a name="set-up-a-warranty-group"></a>Paramétrer un groupe de garanties

Un groupe de garanties est une relation entre les garanties et les articles sous garantie. Le PDV utilise des groupes de garantie pour déterminer quels articles de garantie les vendeurs doivent être invités à ajouter lorsqu’un article sous garantie est ajouté au panier d’un client.

Pour paramétrer un groupe de garanties dans Commerce, procédez comme suit.

1. Accédez à **Retail et Commerce \> Produits et catégories \> Garantie \> Groupes de garanties**.
1. Sélectionnez **Nouveau** pour créer un groupe de garanties.
1. Dans le champ **Nom**, entrez un nom pour le nouveau groupe.
1. Dans le raccourci **Général**, dans le champ **Description**, saisissez une description du groupe.
1. Dans le raccourci **Produits avec garantie**, sélectionnez **Ajouter une ligne** pour ajouter une garantie.
1. Dans le champ **Ordre d’affichage**, entrez un nombre pour classer le groupe de garanties au niveau du point de vente. Le PDV affichera les garanties par ordre croissant dans l’invite de garantie.
1. Dans le raccourci **Produits sous garantie**, sélectionnez **Ajouter une ligne** pour ajouter des produits sous garantie.
1. Si la garantie s’applique à une catégorie entière d’articles sous garantie (produits), sélectionnez la catégorie dans le champ **Catégorie**. Si la garantie s’applique à un article sous garantie spécifique (produit), sélectionnez le produit dans le champ **Produit**.
1. Dans le raccourci **Canaux applicables**, sélectionnez **Ajouter une ligne** pour ajouter le canal où vous souhaitez vendre la garantie.
1. Sélectionnez **Enregistrer** pour enregistrer la configuration.
1. Sélectionnez **Publier** pour publier le groupe de garanties.
1. Exécutez la tâche **1040** pour synchroniser les données sur le canal.

## <a name="sell-warranty-items-at-the-pos"></a>Vendre des garanties au point de vente

Deux opérations PDV permettent aux vendeurs de vendre des articles sous garantie pendant le flux de travail pour les achats des clients :

- **Ajouter une garantie** - Cette opération déclenche une invite qui affiche les garanties applicables pour un article sous garantie sélectionné dans le panier.
- **Ajouter une garantie à la transaction existante** - Cette opération permet aux vendeurs de vendre des garanties pour les articles sous garantie qui ont déjà été vendus. Les vendeurs peuvent trouver la transaction d’origine pour un article garanti en entrant le numéro de reçu de la transaction.

L’illustration suivante montre un exemple de page de terminal de point de vente avec une invite pour ajouter un article sous garantie pour l’achat en cours d’un article sous garantie.

![Exemple d’invite permettant d’ajouter une garantie pour l’achat en cours](./media/ew-sell-warranty.png)

L’illustration suivante montre un exemple de la fonctionnalité permettant d’ajouter une garantie pour un article sous garantie déjà vendu.

![Exemple de fonctionnalité permettant d’ajouter une garantie pour un article sous garantie déjà vendu](./media/ew-add-warranty-existing.png)

## <a name="process-warranty-transactions"></a>Traiter les transactions de garantie

Lorsque les garanties sont vendues au comptant, une fois que les transactions sont publiées dans Commerce Headquarters, les utilisateurs de Commerce peuvent exécuter la tâche **Traiter les transactions de garantie** pour traiter les transactions de garantie et créer des stratégies de garantie.

Pour traiter des transactions de garantie dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Retail et Commerce \> Produits et catégories \> Garantie \> Traiter les transactions de garantie**.
1. Dans la boîte de dialogue **Choisir des nœuds d’organisation**, dans le champ **Hiérarchie organisationnelle**, sélectionnez une valeur.
1. Dans la liste **Nœuds d’organisation disponibles**, sélectionnez un magasin individuel ou, si vous souhaitez créer le travail par lots pour un groupe de magasins, un nœud.
1. Sélectionnez le bouton de flèche droite pour ajouter votre sélection à la liste **Nœuds d’organisation sélectionné**.
1. Sélectionnez l’onglet **Exécuter à l’arrière-plan**.
1. Définissez l’option **Traitement par lots** sur **Oui**, puis sélectionnez **Récurrence**.
1. Dans la boîte de dialogue **Définir la récurrence**, dans le champ **Date de début**, sélectionnez ou entrez une date de début pour la récurrence.
1. Dans le **Heure de début**, sélectionnez ou entrez une heure de début pour la récurrence.
1. Utilisez l’une des procédures suivantes :

    - Sélectionnez l’option **Pas de date de fin** si la récurrence ne doit jamais se terminer.
    - Sélectionnez l’option **Fin après le** si la récurrence doit se terminer après un nombre spécifique d’exécutions. Si vous sélectionnez cette option, entrez le nombre d’exécutions.
    - Sélectionnez l’option **Terminé pour** si la récurrence devait se terminer à une date précise. Si vous sélectionnez cette option, sélectionnez ou entrez la date.

1. Cliquez sur **OK**.
1. Cliquez sur **OK**.

## <a name="warranty-policies"></a>Stratégies de garantie

Lorsqu’une extension de garantie est vendue, une entité de stratégie de garantie est automatiquement créée. Les numéros de stratégie de garantie peuvent être partagés avec les clients, afin qu’ils aient une référence pour la garantie qu’ils ont achetée. Les propriétés des stratégies de garantie incluent la date de début effective et la date d’expiration de la garantie, les termes et conditions, et le numéro de série de l’article sous garantie pour lequel la garantie a été vendue.

> [!NOTE]
> Les propriétés de la stratégie de garantie sont générées automatiquement lorsque des entités de stratégie de garantie sont créées. Actuellement, elles ne peuvent pas être configurées ou modifiées manuellement.

Le tableau suivant décrit les propriétés de la stratégie de garantie et leurs valeurs. Dans Commerce Headquarters, la table de base de données est nommée WARRANTYPOLICY.

| Nom de la propriété | Valeur | Description |
|---------------|-------|-------------|
| PolicyNumber | Chaîne de caractères (20 caractères maximum) | Numéro de la stratégie de garantie |
| WarrantiedItemId | Chaîne de caractères (20 caractères maximum) | ID de l’article sous garantie |
| WarrantiedInventoryLotId | Chaîne de caractères (20 caractères maximum) | ID du lot de stock de l’article sous garantie |
| WarrantiedSerialNumber | Chaîne de caractères (20 caractères maximum) | Numéro de série de l’article sous garantie |
| WarrantiedFulfilledDate | Date | Date d’exécution de l’article sous garantie |
| WarrantyItemId | Chaîne de caractères (20 caractères maximum) | ID de la garantie |
| WarrantyInventoryLotId | Chaîne de caractères (20 caractères maximum) | ID du lot de stock du produit avec garantie |
| WarrantySalesDate | Date | Date de vente de la garantie |
| WarrantyEffectiveDate | Date | Date effective de la stratégie de garantie |
| WarrantyExpirationDate | Date | Date d’expiration de la stratégie de garantie |
| CustAccount | Chaîne de caractères (20 caractères maximum) | Numéro de compte client |
| Statut | **Créé**, **Annulé**, **Effectif** ou **Expiré** | Statut de la stratégie de garantie |
| Notes | Chaîne de caractères (255 caractères maximum) | Remarques sur la stratégie de garantie, telles que les termes et conditions |

## <a name="frequently-asked-questions-faq"></a>Forum aux questions (FAQ)

**Pourquoi ne vois-je pas d’invite de garantie dans le PDV ?**

Assurez-vous que la garantie est assortie au canal. Assurez-vous également que le groupe de garanties est configuré de manière à inclure le canal approprié.

**Lorsque j’essaie d’ajouter une garantie à une transaction existante et d’entrer le numéro de reçu de la commande client, pourquoi ne vois-je aucun élément de ligne de transaction ?**

Les reçus ne peuvent être trouvés que si une tâche d’extraction (tâche P) est exécutée pour télécharger les reçus vers Commerce Headquarters. Pour exécuter la tâche P, accédez à **Retail et Commerce \> Retail and Commerce IT \> Calendrier de distribution**, sélectionnez la tâche **P-0001**, puis sélectionnez **Exécuter maintenant**.

**Pourquoi la fonctionnalité de garantie s’applique-t-elle uniquement aux produits sérialisés ?**

Une garantie est un service fourni pour un produit spécifique et unique. Dans Dynamics 365, un produit ne peut être identifié de manière unique que par un numéro de série.

## <a name="additional-resources"></a>Ressources supplémentaires

[Paramétrer les produits vendus au détail](set-up-retail-products.md)

[Paramétrer des assortiments](set-up-assortments.md)

[Vue d’ensemble des souches de numéros](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)
