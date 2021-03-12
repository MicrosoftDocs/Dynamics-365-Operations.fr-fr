---
title: Frais automatiques avancés omnicanaux
description: Cette rubrique décrit les capacités de gestion des frais de commande supplémentaires pour les commandes du canal Commerce en utilisant les fonctions de frais automatiques avancés.
author: hhaines
manager: annbe
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.dyn365.ops.version: 10
ms.openlocfilehash: 4c0eebedd31a04dc23b396600315206d70fe8876
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997570"
---
# <a name="omni-channel-advanced-auto-charges"></a>Frais automatiques avancés omnicanaux

[!include [banner](includes/banner.md)]

Cette rubrique fournit des informations sur la configuration et le déploiement des fonctionnalités de frais automatiques avancés disponibles dans Dynamics 365 for Retail version 10.0.

Lorsque les fonctionnalités de frais automatiques avancés sont activées, les commandes créées dans tout canal Commerce pris en charge (point de vente (PDV), centre d'appels et en ligne) peuvent tirer parti des configurations de [frais automatiques](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services) définies dans l'application ERP pour les frais associés au niveau de l'en-tête et de la ligne.

Dans les versions antérieures à la version 10.0 de Retail, les configurations de [frais automatiques](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services) sont uniquement accessibles par les commandes créées dans les canaux de e-commerce et de centres d'appels. Dans les versions 10.0 et ultérieures, les commandes créées en PDV peuvent exploiter les configurations de frais automatiques. Ainsi, les différents frais supplémentaires peuvent systématiquement être ajoutés aux transactions de vente.

Lors de l'utilisation de versions précédentes à la version 10.0, un utilisateur du PDV est invité à saisir manuellement des frais d'expédition pendant la création d'une transaction de PDV « Tout expédier » ou « Expédition sélectionnée ». Même si les différentes fonctions de frais de l'application sont utilisées par rapport à la manière dont les frais sont rédigés dans la commande, aucun calcul systématique n'est fourni. Le calcul est basé sur la saisie de l'utilisateur pour déterminer la valeur des frais. Les frais peuvent être ajoutés uniquement en tant que code de frais associés à l'expédition unique et ne peuvent pas être facilement modifiés ou mis à jour dans le PDV après leur création.

L'utilisation des invites manuelles pour ajouter des frais d'expédition reste disponible dans les versions 10.0 et ultérieures. Si une organisation n'active pas le paramètre **Frais automatiques avancés**, les invites du PDV pour la saisie manuelle des frais resteront les mêmes.

Avec la fonctionnalité des frais automatiques avancés, les utilisateurs de PDV peuvent avoir des calculs systématiques pour tous frais divers définis selon les tables de configuration des frais automatiques. En outre, les utilisateurs auront la possibilité d'ajouter ou de mettre à jour un nombre illimité de frais supplémentaires dans une transaction de vente en PDV au niveau de l'en-tête ou de la ligne (pour un paiement au comptant ou une commande client).

## <a name="enabling-advanced-auto-charges"></a>Activation de frais automatiques avancés

Dans la page **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres de Commerce**, accédez à l'onglet **Commandes client**. Dans l'organisateur **Frais**, définissez **Utiliser les frais automatiques avancés** sur **Oui**.

![Paramètre de frais automatiques avancés](media/advancedchargesparameter.png)

Lorsque les frais automatiques avancés sont activés, les utilisateurs ne sont plus invités à saisir manuellement des frais d'expédition au terminal de PDV lors de la création d'une commande client de type « Expédier tout » ou « Expédier sélection ». Les frais de la commande au PDV sont systématiquement calculés et ajoutés à la transaction au PDV (si un tableau de frais automatiques correspondant qui répond au critère de la commande créée est trouvé). Les utilisateurs peuvent également ajouter ou conserver manuellement des frais au niveau de l'en-tête ou de la ligne manuellement via les opérations en PDV récemment ajoutées qui peuvent être ajoutées aux mises en page de l'écran de PDV.

Lorsque les frais automatiques avancés sont activés, les **paramètres de Commerce** existants pour **Code frais d'expédition** et **Rembourser les frais d'expédition** ne sont plus utilisés. Ces paramètres s'appliquent uniquement si le paramètre **Utiliser les frais automatiques avancés** est défini sur **Non**.

Avant d'activer cette fonctionnalité, veillez à avoir testé et formé vos employés, puisque la fonctionnalité activée changera le flux de processus métier de la manière dont les frais d'expédition ou autres frais sont calculés et ajoutés aux commandes client du PDV. Veillez à comprendre l'impact du flux du processus sur la création des transactions depuis le PDV. Pour les commandes du centre d'appels et du commerce électronique, l'impact de l'activation des frais automatiques avancés est minime. Les applications du centre d'appels et du commerce électronique continueront à avoir le même comportement qu'elles ont eu historiquement par rapport aux tableaux de frais automatiques pour calculer les frais de commande supplémentaires. Les utilisateurs du canal de centre d'appels continueront à avoir la capacité de modifier manuellement tous les frais automatiques calculés par le système au niveau de l'en-tête ou de la ligne, ou d'ajouter manuellement des frais divers au niveau de l'en-tête ou de la ligne.

## <a name="additional-pos-operations"></a>Opérations de PDV supplémentaires

Pour que les frais automatiques avancés fonctionnent correctement dans votre environnement d'application de PDV, de nouvelles opérations de PDV ont été ajoutées. Ces opérations doivent être ajoutées à vos [Mises en page de l'écran du PDV](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts) et être déployées sur les périphériques de PDV à mesure que vous déployez les frais automatiques avancés. Si ces opérations ne sont pas ajoutées, les utilisateurs ne seront pas en mesure de gérer ou de conserver des frais divers sur les transactions du PDV et n'auront pas la possibilité d'ajuster ou de modifier les valeurs des frais qui sont systématiquement calculés selon les configurations de frais automatiques. Au minimum, il est suggéré que vous déployiez l'opération **Gérer les frais** vers votre mise en page de PDV.

Les nouvelles opérations sont les suivantes.

- **142 - Gérer les frais** - Utilisez cette opération pour permettre aux utilisateurs du PDV d'afficher et de modifier les frais divers de la transaction du PDV qui ont été ajoutés manuellement ou systématiquement via les calculs de frais automatiques.
- **141 - Ajouter des frais d'en-tête** - Utilisez cette opération pour donner à l'utilisateur la possibilité d'ajouter manuellement divers frais au niveau de l'en-tête à toute transaction de vente au PDV (et sélectionnez le code de frais à utiliser).
- **140 - Ajouter des frais de ligne** - Utilisez cette opération pour donner à l'utilisateur la possibilité d'ajouter manuellement divers frais au niveau d'une ligne à toute transaction de vente au PDV (et sélectionnez le code de frais à utiliser).
- **143 - Recalculer les frais** - Utilisez cette opération pour effectuer un recalcul complet des frais pour la transaction de vente. Tous les frais automatiques précédemment remplacés par l'utilisateur seront recalculés selon la configuration actuelle du panier.

Comme avec toutes les opérations du PDV, les configurations de sécurité peuvent être faites pour exiger l'approbation du responsable afin d'exécuter l'opération.

Il est important d'observer que les opérations de PDV répertoriées ci-dessus peuvent être également ajoutées à la mise en page du PDV même si le paramètre **Utiliser les frais automatiques avancés** est désactivé. Dans ce scénario, les organisations bénéficient toujours d'avantages supplémentaires pour visualiser les frais ajoutés manuellement et les modifier avec l'opération **Gérer les frais**. Les utilisateurs peuvent également utiliser les opérations **Ajouter des frais d'en-tête** et **Ajouter des frais de ligne** pour les transactions de PDV même lorsque le paramètre **Utiliser les frais automatiques avancés** est désactivé. L'opération **Recalculer les frais** a une fonctionnalité moindre si elle est utilisée lorsque l'option **Utiliser les frais automatiques avancés** est désactivée. Dans ce scénario, rien n'a été recalculé et tous les frais ajoutés manuellement à la transaction sont réinitialisés sur 0,00 USD.

## <a name="use-case-examples"></a>Utiliser des exemples de scénario

Cette section présente des exemples de scénarios d'utilisation pour vous aider à comprendre la configuration et l'utilisation des frais automatiques et autres frais divers dans le contexte des commandes du canal. Les exemples suivants illustrent le comportement de l'application lorsque le paramètre **Utiliser les frais automatiques avancés** a été activé.

### <a name="auto-charges-header-charges-example"></a>Exemple de frais d'en-tête Frais automatiques

#### <a name="use-case-scenario"></a>Scénario d'utilisation

Un détaillant souhaite ajouter automatiquement des frais pour le transport lorsque les transactions sont créées dans un canal de commerce qui exige une expédition des produits au client. Le détaillant propose 2 modes de livraison : terrestre et aérien. Si un client opte pour la livraison terrestre et si la valeur de la commande est inférieure à 100 USD, le détails souhaite imputer les frais de transport au client pour un montant de 10 USD. Si la commande est supérieure à 100 USD et si le client opte pour l'expédition terrestre, le client ne sera pas imputé de frais de transport supplémentaires. Si le client opte pour la livraison aérienne de toutes les commandes, peu importe leur valeur totale, il sera facturé d'un montant de frais de transport de 20 USD.

#### <a name="setup-and-configuration"></a>Paramétrage et configuration

Ce scénario exige la configuration de deux tables de frais automatiques.

Accédez à **Comptabilité client \> Paramétrage des frais \> Frais automatiques**.

Configurez deux types de frais automatiques au niveau de l'en-tête. Configurez des frais pour la livraison en « mode terrestre » et des frais pour la livraison en « mode aérien ». Pour ce scénario, configurez-les pour une utilisation pour « Tous les clients ».

Pour les frais de livraison terrestre, dans la section des lignes de la page **Frais automatiques**, définissez les frais qui seront appliqués pour les commandes entre 0,01 USD et 100 USD sur 10 USD. Créez une autre ligne de frais pour indiquer que les commandes supérieures à 100,01 USD n'auront pas de frais de livraison.

![Exemple de deux tables de frais automatiques](media/headerchargesexample.png)

Pour les frais de livraison aérienne, dans la section des lignes du formulaire Frais automatiques, définissez des frais de 20 USD qui seront appliqués pour toutes les commandes (entre 0,01 USD et 9 999 999 USD).

Envoyez les modifications vers l'unité d'échelle commerciale/la base de données du canal de telle sorte que le PDV puisse les utiliser en exécutant la tâche **programme de distribution 1040**.

#### <a name="sales-processing-for-this-scenario"></a>Traitement des ventes pour ce scénario

Une fois les étapes de configuration ci-dessus validées et les modifications appliquées à la base de données du canal, toute commande client ou transaction de vente créée au PDV, centre d'appels ou via les canaux de commerce électroniques qui ont des modes de livraison terrestre ou aérien définis au niveau de l'en-tête utiliseront ces frais et les appliqueront automatiquement à la vente.

Actuellement, les frais s'appliqueront à toutes les transactions de vente créées dans l'entité juridique qui utilise ces modes de livraison puisqu'il n'y a pas de fonctionnalité pour définir qu'une configuration de frais automatiques ne s'appliquera qu'à un canal de vente spécifique.

Pour les scénarios de PDV et de commerce électronique, car il n'y a pas d'« en-tête » clairement définie sur ces commandes, les frais au niveau de l'en-tête s'appliqueront uniquement si toutes les lignes de vente sur la transaction sont définies pour une expédition avec exactement le même mode de livraison. S'il existe des « modes mixtes » d'exécution sur les transactions créées par le PDV ou le commerce électronique, seuls les frais automatiques au niveau de la ligne seront pris en compte et appliqués.

Dans les scénarios du centre d'appels, l'utilisateur a le contrôle du paramètre du mode de livraison à l'en-tête de commande, par conséquent des frais au niveau de l'en-tête s'appliqueront pour ces commandes même si certaines des lignes de vente ont été configurées pour utiliser un autre mode de livraison. Les frais au niveau de l'en-tête pour les commandes de centre d'appels seront toujours basés sur le mode de livraison défini au niveau de l'en-tête de commande de la commande client.

### <a name="auto-charges-line-charges-example"></a>Exemple de frais de ligne Frais automatiques

#### <a name="use-case-scenario"></a>Scénario d'utilisation 

Un détaillant souhaite ajouter des frais supplémentaires au client pour configurer les frais lorsque le client achète un modèle d'ordinateur en particulier. Cet ordinateur exige des actions de configuration non facultatives supplémentaires que le détaillant exécutera pour le client. Le détaillant a informé les clients qu'il y aura des frais supplémentaires pour ce paramétrage. Le détaillant préfère gérer les frais liés à ces frais séparément depuis le prix de vente du produit à des fins d'états financiers. Un forfait de configuration de 19,99 $ est facturé au client lorsque cet ordinateur spécifique est acheté dans un canal.

#### <a name="setup-and-configuration"></a>Paramétrage et configuration

Ce scénario exige la configuration d'un tableau de frais automatiques au niveau d'une ligne.

Accédez à **Comptabilité client \> Paramétrage des frais \> Frais automatiques**.

Définissez le menu déroulant **Niveau** sur **Ligne**, puis créez un nouvel enregistrement de frais automatiques pour tous les clients et pour le produit ou le groupe de produits spécifique sur lequel les frais de configuration seront facturés.

![Exemple de table de frais automatiques au niveau de la ligne](media/linechargesexample.png)

Envoyez les frais vers l'unité d'échelle commerciale/la base de données du canal de telle sorte que le PDV puisse les utiliser en exécutant la tâche **programme de distribution 1040**.

#### <a name="sales-processing-for-this-scenario"></a>Traitement des ventes pour ce scénario

Une fois les étapes de configuration ci-dessus validées et les modifications appliquées à la base de données du canal, toute commande client ou transaction de vente créée au PDV, centre d'appels ou via les canaux de commerce électroniques qui ont cet article sur la commande déclencheront des frais au niveau de la ligne ajoutés systématiquement au total de la commande.

Actuellement, les frais s'appliqueront à toute ligne de vente qui correspond à la configuration des frais automatiques au niveau de la ligne dans l'entité juridique, puisqu'il n'y a pas de fonctionnalité pour configurer des frais automatiques au niveau de la ligne à appliquer uniquement à un canal de vente en particulier.

### <a name="manual-header-charges-example"></a>Exemple de frais d'en-tête manuel

#### <a name="use-case-scenario-description"></a>Description du scénario d'utilisation

Un détaillant effectue une exception aux processus traditionnels en décidant de fournir une livraison des produits à domicile à un client dont les produits sont en magasin. Le détaillant et le client ont convenu que le client paierait des frais de traitement supplémentaires de 25 USD pour ce service. Le preneur de commande doit ajouter ces frais supplémentaires à la transaction. Parce que les frais sont un forfait global et ne sont pas associés à un produit unique de la commande, des frais d'en-tête seront utilisés.

#### <a name="setup-and-configuration"></a>Paramétrage et configuration

Veillez à ce que le code de frais qui sera utilisé dans ce scénario a été correctement configuré en accédant à **Comptabilité client \> Paramétrage des frais \> Frais** pour définir un code de frais approprié pour le scénario.

![Exemple de frais](media/chargesexample.png)

Si les frais doivent être considérés comme des frais associés « d'expédition » destinés aux remises et aux promotions pratiquées sur l'expédition, définissez **Frais d'expédition** du code de frais sur **Oui**. Si ces frais sont également autorisés pour être systématiquement remboursés pendant le traitement d'une transaction de retour dans l'application du PDV, définissez **Remboursable** sur **Oui**. L'indicateur **Remboursable** est applicable uniquement lorsque le paramètre **Utiliser les frais automatiques avancés** est défini sur **Oui**.

Envoyez les frais vers l'unité d'échelle commerciale/la base de données du canal de telle sorte que le PDV puisse les utiliser en exécutant la tâche **programme de distribution 1040**.

L'opération **Ajouter des frais d'en-tête** doit être configurée dans votre [Mise en page de l'écran du PDV](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts) afin qu'un bouton qui est accessible à l'utilisateur du PDV puisse appeler cette opération (opération 141). Les modifications de la mise en page de l'écran doivent être réparties sur le canal ainsi que via la fonction de programme de la distribution.

#### <a name="sales-processing-of-manual-header-charges"></a>Traitement des ventes des frais d'en-tête manuel

Pour exécuter le scénario dans l'application de PDV, l'utilisateur du PDV créera la transaction des ventes de manière habituelle, en ajoutant les produits et toute autre configuration à la vente. Avant de recueillir le paiement, l'utilisateur doit exécuter l'opération **Ajouter des frais d'en-tête**, ce qui invitera l'utilisateur à sélectionner un code de frais et à saisir la valeur des frais. Une fois que l'utilisateur exécute le processus, les frais sont ajoutés à la commande client en tant que frais d'en-tête.

Ce processus peut être appliqué au centre d'appels à l'aide de la fonction **Frais** existante disponible dans l'onglet **Vendre** de la barre d'outils. Sur la page **Tenir les frais à jour**, l'utilisateur peut ajouter une nouvelle ligne de frais à l'en-tête de commande.

### <a name="manual-line-charges-example"></a>Exemple de frais de ligne manuel

#### <a name="use-case-scenario"></a>Scénario d'utilisation

Un client a demandé que 2 des 5 éléments sur leur commande client soient mis dans un emballage cadeau. Le détaillant propose ce service en option moyennant un forfait de 2 USD par article. Le preneur d'ordre devra ajouter ces frais aux articles spécifiques qui doivent être mis dans un emballage cadeau.

#### <a name="setup-and-configuration"></a>Paramétrage et configuration

Veillez à ce que le code de frais qui sera utilisé dans ce scénario a été correctement configuré en accédant à **Comptabilité client \> Paramétrage des frais \> Frais** pour définir un code de frais approprié pour le scénario.

Si les frais doivent être considérés comme des frais associés « d'expédition » destinés aux remises et aux promotions pratiquées sur l'expédition, définissez les **Frais d'expédition** du code de frais sur **Oui**. Si les frais sont également autorisés pour être systématiquement remboursés pendant le traitement d'une transaction de retour dans l'application du PDV, définissez **Remboursable** sur **Oui**. L'indicateur **Remboursable** est applicable uniquement lorsque le paramètre **Utiliser les frais automatiques avancés** est défini sur **Oui**.

Envoyez les frais vers l'unité d'échelle commerciale/la base de données du canal de telle sorte que le PDV puisse les utiliser en exécutant la tâche **programme de distribution 1040**.

L'opération **Ajouter des frais de ligne** doit être configurée dans votre [Mise en page de l'écran du PDV](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts) afin qu'un bouton qui est accessible à l'utilisateur du PDV puisse appeler cette opération (opération 140). Les modifications de la mise en page de l'écran doivent être réparties sur le canal ainsi que via la fonction de programme de la distribution.

#### <a name="sales-processing-of-the-manual-line-charge"></a>Traitement des ventes des frais de ligne manuelle

Pour exécuter le scénario dans l'application de PDV, l'utilisateur du PDV créera la transaction des ventes de manière habituelle, en ajoutant les produits et toute autre configuration à la vente. Avant de collecter le paiement, l'utilisateur doit sélectionner une ligne spécifique sur laquelle les frais s'appliqueront depuis la liste d'articles du PDV et exécuteront l'opération **Ajouter des frais de ligne**. L'utilisateur sera invité à sélectionner un code de frais et à saisir la valeur des frais. Une fois que l'utilisateur exécute le processus, les frais seront associés à la ligne et ajoutés au total de la commande comme frais d'en-tête. L'utilisateur peut répéter le processus pour ajouter des frais de ligne supplémentaires à d'autres lignes d'articles sur la transaction, le cas échéant.

Le même processus peut être appliqué au centre d'appels à l'aide de la fonctionnalité « Tenir à jour les frais » sous le menu déroulant **Finances** dans la section **Lignes de commande client** sur la page **Commande client**. La sélection de cette option va ouvrir la page **Tenir les frais à jour** sur laquelle l'utilisateur peut ajouter une nouvelle ligne de frais spécifiques à la transaction.

## <a name="additional-features"></a>Fonctionnalités supplémentaires

### <a name="editing-charges-on-a-pos-sales-transaction"></a>Modifier les frais sur une transaction de vente au PDV

L'opération **Gérer les frais** (142) doit être ajoutée à la [mise en page de l'écran du PDV](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts) afin qu'un utilisateur puisse afficher et modifier ou remplacer les frais au niveau de la ligne ou de l'en-tête créés manuellement ou calculés par le système. Si l'opération n'est pas ajoutée, les utilisateurs ne seront pas en mesure d'ajuster la valeur des frais sur la transaction du PDV, et ne pourront pas non plus afficher les détails des frais tels que le type de code de frais associé aux frais.

Sur la page **Gérer les frais** dans le PDV, l'utilisateur peut afficher les détails des frais au niveau de la ligne et de l'en-tête. L'utilisateur peut utiliser la fonction **Modifier** disponible sur cette page pour apporter des modifications au montant imputé à une ligne spécifique de frais. Une fois qu'une ligne de frais est remplacée manuellement, elle ne sera pas systématiquement recalculée sauf si l'utilisateur initie l'opération **Recalculer les frais**.

Si le **Code du motif de remplacement des frais** a été configuré dans la page de configuration **Paramètres de Commerce**, l'utilisateur est invité à fournir un code motif lorsque les frais sont modifiés dans l'application du PDV.

Si les codes de motif ont été capturés pour remplacer les frais, un nouveau rapport est également disponible pour passer en revue et auditer ces remplacements. L'état se trouve sous **Retail et Commerce \> Recherches et états \> Historique de remplacement des frais**.

### <a name="refunding-charges-on-a-pos-return-transaction"></a>Remboursement des frais dans le cadre d'une transaction de retour au PDV

Si le paramètre **Utiliser les frais automatiques avancés** est défini sur **Oui**, le paramètre de commerce existant pour **Rembourser les frais d'expédition** ne s'applique plus. Pour indiquer quels frais doivent être systématiquement remboursés à un client lors de l'utilisation de frais automatiques avancés, assurez-vous que le code de frais associé a été configuré comme **Remboursable** sur la page de configuration **Code de frais**. Veillez à ce que les paramètres soient synchronisés vers les bases de données du canal de commerce par le traitement du programme de distribution.

### <a name="refunding-charges-on-a-return-order-transaction"></a>Remboursement des frais dans le cadre d'une transaction d'ordre de retour

Les frais ne sont pas systématiquement remboursés sur les **Ordres de retour** créés dans Commerce. Les utilisateurs doivent sélectionner l'option **Copier les frais** en créant l'**Ordre de retour**. Si **Copier les frais** n'est pas sélectionné, les frais de la transaction de vente d'origine ne seront pas automatiquement remboursés. Si **Copier les frais** est sélectionné, tous les frais sont copiés dans l'ordre de retour et l'utilisateur peut modifier ou supprimer manuellement tous les frais pour lesquels il ne souhaite pas être remboursé. Le processus d'ordre de retour du centre d'appels ne reconnaît actuellement pas l'indicateur **Remboursable** sur la configuration **Code de frais**.

### <a name="configuring-pos-receipts-to-show-charges"></a>Configuration des reçus du PDV pour afficher les frais

Les éléments de reçu suivants ont été ajoutés à la ligne et au pied de page de reçu pour prendre en charge la fonctionnalité des frais automatiques avancés.

- **Frais d'expédition de la ligne** - Cet élément au niveau de la ligne peut être utilisé pour résumer les codes de frais spécifiques appliqués à la ligne de vente. Seuls les codes frais qui ont été marqués comme des frais d'**Expédition** sur la page **Code de frais** seront affichés ici.
- **Autres frais de la ligne** - Cet élément au niveau de la ligne peut être utilisé pour résumer les codes de frais spécifiques hors expédition appliqués à la ligne de vente. Il s'agit de codes de frais où l'indicateur **Expédition** sur la page **Code de frais** n'a pas été activé.
- **Détails des frais d'expédition de la commande** - Cet élément au niveau du pied de page affiche les descriptions des codes de frais appliquées à la commande et marqué comme frais d'**Expédition** sur la page de configuration **Code de frais**.
- **Frais d'expédition de la commande** - Cet élément au niveau du pied de page indique la valeur en dollar des frais associés à l'expédition.
- **Détails des autres frais de la commande** - Cet élément au niveau du pied de page affiche les descriptions des codes de frais appliquées à la commande et marqué comme frais d'expédition.
- **Autres frais de la commande** - Cet élément au niveau du pied de page indique la valeur en dollar des autres frais associés, mais pas à l'expédition.

Nous recommandons à l'organisation d'ajouter également des champs de texte libre au pied de page de réception afin de définir les zones où les frais seront récapitulés.

### <a name="preventing-charges-from-being-calculated-until-the-pos-order-is-completed"></a>Prévenir contre le calcul des frais avant la fin de la commande du PDV

Certaines organisations préfèreront attendre jusqu'à ce que l'utilisateur ait fini d'ajouter toutes les lignes de vente à la transaction du PDV avant de calculer les frais. Pour empêcher le calcul des frais puisque les articles sont ajoutés à la transaction en PDV, activez le paramètre **Calcul manuel des frais** dans le **Profil de la fonctionnalité** utilisé par le magasin. Si vous activez ce paramètre, l'utilisateur du PDV pourra utiliser l'opération **Calculer les totaux** lorsqu'il aura terminé d'ajouter les produits à la transaction du PDV. L'opération **Calculer les totaux** déclenchera ensuite le calcul de tous les frais automatiques de l'en-tête ou des lignes de la commande, le cas échéant.

### <a name="charges-override-reports"></a>États de remplacement des frais

Si les utilisateurs remplacent manuellement les frais calculés ou ajoutent des frais manuels à la transaction, ces données sont disponibles pour audit dans l'état **Historique de remplacement des frais**. L'état est accessible depuis **Retail et Commerce \> Recherches et états \> Historique de remplacement des frais**. Il est important d'observer que les données requises pour cet état sont importées depuis la base de données des canaux dans le siège social via les tâches de programme de distribution « P ». Par conséquent, les informations concernant les remplacements effectués dans le PDV peuvent ne pas être immédiatement disponibles sur cet état tant que cette tâche n'a pas chargé les données de transaction du magasin au siège.

## <a name="additional-resources"></a>Ressources supplémentaires

[Activer et configurer les frais automatiques par canal](auto-charges-by-channel.md)

[Calcul au prorata des frais d'en-tête pour les lignes de vente correspondantes](pro-rate-charges-matching-lines.md)

