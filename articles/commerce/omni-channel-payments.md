---
title: Présentation des paiements omnicanaux
description: Cette rubrique fournit une vue d’ensemble des paiements omnicanaux dans Dynamics 365 Commerce.
author: rubendel
manager: AnnBe
ms.date: 09/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: AX 8.1.3
ms.openlocfilehash: 80eaf36fb382e0ebe0a66383ea17ab76faa07dfa
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412389"
---
# <a name="omni-channel-payments-overview"></a>Présentation des paiements omnicanaux

[!include [banner](../includes/banner.md)]

Cette rubrique fournit une vue d’ensemble des paiements omnicanaux dans Dynamics 365 Commerce. Elle inclut une liste complète des scénarios, des informations sur la fonctionnalité, du paramétrage, et de la résolution des problèmes pris en charge, et des descriptions de certains problèmes habituels.

## <a name="key-terms"></a>Termes clés

| Terme | Description |
|---|---|
| Jeton | Chaîne des données qu’un processeur de paiement fournit comme référence. Les jetons peuvent représenter des numéros de carte de paiement, les autorisations de paiement, et des captures précédentes de paiement. Les jetons sont importants, car ils permettent de conserver les données confidentielles hors du système de point de vente (POS). Ils sont parfois également appelés des *références*. |
| Jeton de carte | Jeton qu’un processeur de paiement fournit pour le stockage dans le système POS. Un jeton de carte peut uniquement être utilisé par le marchand qui le reçoit. Les jetons de carte sont parfois également appelés des *références de carte*. |
| Jeton d’autorisation | ID unique qu’un processus de paiement fournit dans le cadre de la réponse qu’il soumet dans un système POS après que le système POS effectue une demande d’autorisation. Un jeton d’autorisation peut être utilisé ultérieurement si le processeur est appelé pour exécuter des actions par exemple contrepasser ou annuler l’autorisation. Toutefois, il est le plus souvent utilisé pour capturer des fonds lorsqu’une commande est réalisée ou qu’une transaction est finalisée. Les jetons d’autorisation sont parfois également appelés des *références d’autorisation*. |
| Jeton de capture | Référence qu’un processeur de paiement fournit à un système POS lorsqu’un paiement est finalisé ou capturé. Le jeton de capture peut être utilisé pour référencer la capture de paiement dans les opérations suivantes, telles que des demandes de remboursement. | 
| Carte absente | Terme qui fait référence à des transactions de paiement où une carte physique n’est pas présentée. Par exemple, elles peuvent se produire dans les scénarios de commerce électronique ou de centre d’appels. Pour ces transactions, les informations associées au paiement sont entrées manuellement dans un site Web de commerce électronique, dans un flux de centre d’appels, ou le POS ou un terminal de paiement. |
| Carte présente | Terme qui fait référence à des transactions de paiement où une carte physique est présentée et utilisée dans un terminal de paiement qui est connecté au système POS Microsoft Dynamics 365. |

## <a name="overview"></a>Présentation

En général le terme *paiements omnicanaux* décrit la possibilité de créer une commande dans un canal et de la terminer dans un autre canal. L’élément clé pour prendre en charge le paiement omnicanal consiste à conserver les détails de paiement avec le reste des détails de la commande, puis d’utiliser ces détails de paiement lorsque la commande est rappelée ou traitée dans un autre canal. Un exemple classique est le scénario « Acheter en ligne, prélever en magasin ». Dans ce scénario, les détails de paiement sont ajoutés lorsque la commande est créée en ligne. Ils sont ensuite rappelés au PDV pour facturer la carte de paiement du client au moment du prélèvement. 

Tous les scénarios décrits dans cette rubrique peuvent être mis en œuvre à l’aide du kit de développement logiciel (SDK) de paiement standard qui est fourni avec Commerce. Le [Connecteur de paiement Dynamics 365 pour Adyen](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3) fournit une mise en œuvre prédéfinie pour chaque scénario décrit ici. 

### <a name="prerequisites"></a>Conditions préalables

Chaque scénario décrit dans cette rubrique nécessite un connecteur de paiement qui prend en charge les paiements omnicanaux. Le processeur Adyen prédéfini peut également être utilisé, car il prend en charge les scénarios disponibles via le kit de développement logiciel (SDK) de paiements. Pour plus d’informations sur la mise en œuvre des connecteurs de paiement, et sur le Kit de développement logiciel Retail en général, visitez la [page d’accueil Retail pour les professionnels de l’informatique et les développeurs](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/dev-retail-home-page#payment-connectors).

#### <a name="supported-versions"></a>Versions prises en charge

Les fonctionnalités de paiement omnicanal décrites dans cette rubrique ont été lancés dans le cadre de la version 8.1.3 de Microsoft Dynamics 365 for Retail. 

#### <a name="card-present-and-card-not-present-connectors"></a>Connecteurs « Carte présente » ou « Carte absente »

Le Kit de développement logiciel (SDK) de paiement repose sur deux ensembles d’interfaces de programmation d’application (API) pour les paiements. Le premier ensemble d’API est appelé **iPaymentProcessor**. Il est utilisé pour mettre en œuvre des connecteurs de paiement « carte absente » qui peuvent être utilisés dans les centres d’appels et avec la plateforme de commerce électronique de Microsoft Dynamics. Pour plus d’informations sur l’interface **iPaymentProcessor**, voir le livre blanc [Mettre en œuvre un connecteur de paiement et un appareil de paiement](https://download.microsoft.com/download/e/2/7/e2735c65-1e66-4b8d-8a3c-e6ef3a319137/The%20Guide%20to%20Implementing%20Payment%20Connector%20and%20Payment%20Device_update.pdf), qui couvre les paiements. 

Le second ensemble d’API est appelé **iNamedRequestHandler**. Il prend en charge la mise en œuvre des intégrations de paiement « carte présente » qui utilisent un terminal de paiement. Pour plus d’informations sur l’interface **iNamedRequestHandler**, voir [Créer une intégration de paiement pour un terminal de paiement](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/end-to-end-payment-extension). 

### <a name="setup-and-configuration"></a>Paramétrage et configuration

Les composants et les étapes de paramétrage suivants sont obligatoires :

- **Intégration du commerce électronique :** une intégration avec Commerce est requise pour prendre en charge les cas où une commande est issue d’une vitrine en ligne. Pour plus d’informations sur le kit de développement logiciel (SDK) de commerce électronique Retail, voir [Kit de développement logiciel (SDK) de la plateforme de commerce électronique](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/ecommerce-platform-sdk). Dans un environnement de démonstration, la vitrine de référence prend en charge les scénarios de paiement omnicanal. 
- **Configuration des paiements en ligne :** Le paramétrage du canal en ligne doit inclure un connecteur de paiement qui a été mis à jour pour prendre en charge les paiements omnicanaux. Sinon, le connecteur de paiement prédéfini peut être utilisé. Pour plus d’informations sur la configuration du connecteur de paiement Adyen pour les magasins en ligne, voir [Connecteur de paiement Adyen](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3#e-commerce). Outre les étapes de paramétrage du commerce électronique décrites dans cette rubrique, le paramètre **Autoriser l’enregistrement des informations de paiement dans le commerce électronique** doit être défini sur **True** dans les paramètres du connecteur Adyen. 
- **Configuration des paiements omnicanaux :** dans le back-office, accédez à **Retail et Commerce \> Paramétrage du siège \> Paramètres \> Paramètres partagés du commerce**. Puis, dans l’onglet **Paiements omnicanaux**, définissez l’option **Utiliser les paiements omnicanaux** sur **Oui**. Dans la version 10.0.12 de Commerce et les versions ultérieures, ce paramètre se trouve dans l’espace de travail **Gestion des fonctionnalités**. Sélectionnez la fonctionnalité **Paiements omnicanaux** et cliquez sur **Activer maintenant**. 
- **Services de paiement :** Le centre d’appels utilise le connecteur de paiement par défaut sur la page **Services de paiement** pour traiter les paiements. Pour prendre en charge les scénarios tels que « Acheter au centre d’appels, prélever au magasin », ce connecteur de paiement par défaut doit être le connecteur de paiement Adyen ou un connecteur de paiement correspondant aux exigences de mise en œuvre des paiements omnicanaux.
- **Service TEF :** Les paiements via un terminal de paiement doivent être paramétrés sur l’organisateur **Service TEF** du profil matériel. Le connecteur Adyen prend en charge les scénarios de paiements omnicanaux prédéfinis. D’autres connecteurs de paiement qui prennent en charge l’interface **iNamedRequestHandler** peuvent également être utilisés s’ils prennent en charge les paiements omnicanaux.
- **Disponibilité du connecteur de paiement :** Lorsqu’une commande est rappelée, les lignes de mode de paiement qui sont rappelées avec la commande comprennent le nom du connecteur de paiement utilisé pour créer les autorisations associées à cette commande. Lorsque la commande est exécutée, le kit de développement logiciel (SDK) des paiements essaie d’utiliser le même connecteur que celui utilisé pour créer l’autorisation d’origine. Par conséquent, un connecteur de paiement ayant les propriétés du même marchand doit être disponible pour la capture. 
- **Types de carte :** Pour que les scénarios omnicanaux fonctionnent correctement, chaque canal doit avoir le même paramétrage pour les modes de paiement qui peuvent être utilisés pour l’omnicanal. Ce paramétrage comprend des ID mode de paiement et des ID de type de carte. Par exemple, si le mode de paiement **Cartes** a un ID de **2** dans le paramétrage du magasin en ligne, il doit avoir le même ID dans le paramétrage du magasin de vente au détail. La même condition préalable s’applique aux ID de type de carte. Si le numéro de carte **12** est défini sur **VISA** dans le magasin en ligne, le même ID doit être paramétré pour le magasin de vente au détail. 
- Retail Modern POS pour Windows ou Android avec une station matérielle intégrée -ou-
- Modern POS pour iOS ou Cloud POS avec une station matérielle partagée connectée. 

### <a name="basic-principle-supporting-omni-channel-payments"></a>Principe de base prenant en charge des paiements omnicanaux

Les connecteurs de paiement et les processeurs de paiements utilisent les jetons, ou références, pour référencer les interactions relatives aux paiements par carte. Par exemple, lorsqu’une autorisation de paiement est demandée, une référence de cette autorisation est fournie. Par conséquent, l’autorisation peut être référencée par la suite, lorsque les fonds sont capturés au moment de l’exécution. Cette autorisation est unique au marchand, au connecteur de paiement, et au processeur. 

Si une commande créée en ligne est prélevée en magasin, les mêmes informations de paiement pour cette commande doivent être rappelés et utilisés. Lorsque les informations d’origine sont fournis dans le cadre de la demande de capture d’un paiement par rapport à l’autorisation d’origine, le processeur de paiement peut traiter la demande et capturer le paiement. 

Pour référencer correctement la commande en ligne, un connecteur de paiement « carte absente » qui prend en charge le même processeur doit également être disponible. Ainsi, le système POS peut avoir un processeur pour les paiements « carte présente », mais il peut également avoir accès à d’autres connecteurs de paiement pour qu’il puisse exécuter les commandes créées dans d’autres canaux à l’aide de différents processeurs de paiements. 

## <a name="supported-scenarios"></a>Scénarios pris en charge

Les scénarios de paiement omnicanaux suivants sont pris en charge :

- Acheter en ligne, récupérer en magasin
- Acheter à un centre d’appels, retirer en magasin
- Acheter dans un magasin A, retirer dans un magasin B
- Acheter dans un magasin A, expédier au client

    > [!NOTE]
    > Les paiements effectués dans le centre d'appels qui correspondent à la fonction de paiement "Normal" doivent être marqués comme **Prépayer** = **Oui** pour être reflétés dans le montant dû lors du rappel de la commande dans le PDV. Les paiements sans prépaiement de type "Normal" ne sont pas reconnus lors du rappel de la commande dans le PDV. 

Des variations de ces scénarios sont également prises en charge. Par exemple, une commande en ligne peut inclure des lignes qui seront expédiées au client et des lignes qui sont prélevées dans un magasin. Toutes les options d’exécution de commande sont prises en charge par les paiements omnicanaux. 

Les sections suivantes décrivent les étapes de chaque scénario et comment exécuter le scénario à l’aide de données de démonstration. 

### <a name="buy-online-pick-up-in-store"></a>Acheter en ligne, récupérer en magasin

Avant de commencer, vérifiez que les conditions préalables suivantes sont respectées :

- Vous avez un vitrine de référence où le connecteur Adyen est configuré.
- L’option **Paiements omnicanaux** sur la page **Paramètres partagés du commerce** est définie sur **True**. Dans les versions ultérieures, ce paramètre est déplacé vers l’espace de travail **Gestion des fonctionnalités** où vous pouvez sélectionner la fonctionnalité **Paiements omnicanaux** et cliquer sur **Activer maintenant**. 
- Le connecteur de paiement Adyen est configuré pour la caisse enregistreuse du PDV de Houston.
- Retail Modern POS pour Windows ou Android avec une station matérielle intégrée -ou-
- Modern POS pour iOS ou Cloud POS avec une station matérielle partagée connectée. 

Procédez comme suit pour exécuter le scénario.

1. Dans la vitrine de référence, créez une commande pour un prélèvement en magasin. Assurez-vous de sélectionner le magasin **Houston**. 
2. Exécutez la procédure de paiement, et payez à l’aide d’un numéro de carte de crédit de test. Vous pouvez trouver des numéros de carte de crédit de test sur la [page de numéros de carte de test Adyen](https://docs.adyen.com/development-resources/test-cards/test-card-numbers/#description).
3. Dans Commerce, utilisez le traitement par lots **Synchroniser les commandes** et le programme de distribution **P-001** pour créer des commandes dans le back-office.
4. Dans le PDV, sur la page d’accueil, sélectionnez l’opération **Commandes à prélever** pour afficher les commandes à prélever en magasin. 
5. Sélectionnez une ou plusieurs lignes de la commande créé dans la vitrine de référence, puis sélectionnez **Prélever**.

    La commande est extraite du back-office. 

6. Lorsque les détails de la ligne de commande sont extraits du back-office, et qu’un paiement par carte pouvant être utilisé pour l’omnicanal est détecté, vous êtes informé qu’un mode de paiement est disponible.
7. Sélectionnez **Utiliser le mode de paiement disponible** pour terminer la transaction à l’aide des informations de carte entrés dans la vitrine de référence.

    Les lignes de commande sont chargées sur la page de la transaction, et le solde dû est de 0 (zéro). 

8. Sélectionnez l’onglet **Paiements** pour afficher la ligne de mode paiement qui a été extraite de la commande en ligne. 
9. Sélectionnez un mode de paiement pour terminer la transaction. 

### <a name="buy-in-call-center-pick-up-in-store"></a>Acheter à un centre d’appels, retirer en magasin

1. Dans Commerce, sur la page **Service client**, saisissez **Karen Berg** dans la barre de recherche, puis sélectionnez **Rechercher**. 
3. Sélectionnez **Karen Berg** dans les résultats de la recherche.
4. Une fois Karen chargée sur la page **Service client**, sélectionnez **Nouvelle commande client**.
5. Sur la nouvelle page de commande client, sélectionnez **En-tête** pour afficher l’en-tête de commande. 
6. Sur la page **En-tête de commande**, définissez le site sur **Central** et l’entrepôt sur **Houston**.
7. Sous l’onglet **Livrer**, définissez le champ **Mode de livraison** sur **60** pour le prélèvement client.
8. Sélectionnez **Lignes**, puis ajoutez une ou plusieurs lignes à la commande. 
9. Sélectionnez **Terminer** pour entrer le flux d’achèvement de la commande.
10. Faites défiler l’écran vers la section des paiements, sélectionnez **Ajouter**, puis sélectionnez une ligne sur laquelle le mode de paiement est défini sur **Cartes**. 
11. Sélectionnez le signe plus (**+**) pour ajouter un paiement par carte. 
12. Entrez les détails d’un numéro de carte de crédit de test que vous avez trouvé sur la [page de numéros de carte de test Adyen](https://docs.adyen.com/development-resources/test-cards/test-card-numbers/#description), puis sélectionnez **OK**.

    > [!NOTE]
    > Si la marque de carte du numéro de carte entré diffère de la marque sélectionnée lorsque le paiement a été initié, le paiement s’effectuera quand même. Toutefois, il sera validé dans les comptes qui sont mis en correspondance avec la marque de carte sélectionnée à l’étape 10.

12. Sélectionnez **OK** de nouveau pour fermer la boîte de dialogue **Paiements d’achèvement de commande**.
13. Sur la page **Résumé de la commande client**, sélectionnez **Soumettre**.
14. Dans le PDV, sur la page d’accueil, sélectionnez l’opération **Commandes à prélever** pour afficher les commandes à prélever en magasin. 
15. Sélectionnez une ou plusieurs lignes de la commande créé dans la vitrine de référence, puis sélectionnez **Prélever**.

    La commande est extraite du back-office. 

16. Lorsque les détails de la ligne de commande sont extraits du back-office, et qu’un paiement par carte pouvant être utilisé pour l’omnicanal est détecté, vous êtes informé qu’un mode de paiement est disponible.
17. Sélectionnez **Utiliser le mode de paiement disponible** pour terminer la transaction à l’aide des informations de carte entrés dans la vitrine de référence.

    Les lignes de commande sont chargées sur la page de la transaction, et le solde dû est de 0 (zéro).

18. Sélectionnez l’onglet **Paiements** pour afficher la ligne de mode paiement qui a été extraite de la commande en ligne. 
19. Sélectionnez un mode de paiement pour terminer la transaction. 

### <a name="buy-in-store-a-pick-up-in-store-b"></a>Acheter dans un magasin A, retirer dans un magasin B

1. Démarrez le POS pour le magasin de Houston.
2. Sur la page **Transaction**, ajoutez Karen Berg à la transaction à l’aide du pavé numérique pour entrer **2001**.
3. Ajoutez une ou plusieurs ligne à la transaction.
4. Sélectionnez **Commandes** pour afficher les options de commande.
5. Sélectionnez **Prélever tout** et, lorsque vous y êtes invité, sélectionnez **Commande client**.
6. Dans la barre de recherche, entrez **Seattle**, puis sélectionnez le magasin de **Seattle** pour le prélèvement. 
7. Sélectionnez **OK** pour accepter la date actuelle comme date de prélèvement.
9. Sélectionner **Carte de paiement** pour initier le paiement.
10. Entrez le paiement par carte pour le montant dû pour l’acompte. 
11. Terminez le paiement de l’acompte sur le terminal de paiement. 
12. Une fois l’acompte payé, sélectionnez l’option pour utiliser la même carte pour l’exécution, et attendez que la commande soit terminée. 
13. Démarrez le POS pour le magasin de Seattle.
14. Dans le PDV, sur la page d’accueil, sélectionnez l’opération **Commandes à prélever** pour afficher les commandes à prélever en magasin. 
15. Sélectionnez une ou plusieurs lignes de la commande créé dans la vitrine de référence, puis sélectionnez **Prélever**.

    La commande est extraite du back-office. 

16. Lorsque les détails de la ligne de commande sont extraits du back-office, et qu’un paiement par carte pouvant être utilisé pour l’omnicanal est détecté, vous êtes informé qu’un mode de paiement est disponible.
17. Sélectionnez **Utiliser le mode de paiement disponible** pour terminer la transaction à l’aide des informations de carte entrés dans la vitrine de référence.

    Les lignes de commande sont chargées sur la page de la transaction, et le solde dû est de 0 (zéro).

18. Sélectionnez l’onglet **Paiements** pour afficher la ligne de mode paiement qui a été extraite de la commande en ligne. 
19. Sélectionnez un mode de paiement pour terminer la transaction. 

### <a name="buy-in-store-a-ship-to-customer"></a>Acheter dans un magasin A, expédier au client

1. Démarrez le POS pour le magasin de Houston.
2. Sur la page **Transaction**, ajoutez Karen Berg à la transaction à l’aide du pavé numérique pour entrer **2001**.
3. Ajoutez une ou plusieurs ligne à la transaction.
4. Sélectionnez **Commandes** pour afficher les options de commande.
5. Sélectionnez **Expédier tout** et, lorsque vous y êtes invité, sélectionnez **Commande client**.
6. Dans la page du mode d'expédition, sélectionnez **Standard jour suivant**, puis sélectionnez **OK** pour accepter la date du jour comme date d'expédition. 
7. Sélectionnez **OK** pour accepter la date actuelle comme date de prélèvement.
8. Sélectionner **Carte de paiement** pour initier le paiement.
9. Entrez le paiement par carte pour le montant dû pour l’acompte. 
10. Terminez le paiement de l’acompte sur le terminal de paiement. 
11. Une fois l’acompte payé, sélectionnez l’option pour utiliser la même carte pour l’exécution, et attendez que la commande soit terminée.

Lorsque la commande est prélevée, emballée et facturée dans le back-office, les détails de paiement fournis dans le système POS sont utilisés pour capturer les fonds pour les marchandises expédiées au client. 

## <a name="scenario-details"></a>Détails du scénario

Outre les scénarios de base qui viennent d’être décrits, plusieurs améliorations ont été apportées au Kit de développement logiciel (SDK) de paiement pour prendre en charge les paiements omnicanaux. 

### <a name="pos"></a>PDV

#### <a name="single-swipedip-for-customer-orders"></a>Passage/insertion de carte uniques pour les commandes client

Avant la mise en œuvre de la fonctionnalité de paiements omnicanaux, lorsque des commandes client incluant des acomptes étaient créées dans le système POS, les clients devaient faire passer leur (ou insérer) leur carte deux fois : une fois pour payer l’acompte et une fois pour utiliser le jeton de la carte pour l’exécution suivante de la commande. Lorsque la fonctionnalité d’utilisation de jeton omnicanal est activée, les clients doivent passer leur carte une seule fois pour payer l’acompte et autoriser le montant dû pour les marchandises qui seront exécutées ultérieurement. Lors de l’achèvement, les fonds autorisés sont capturés. Avant la mise en œuvre de la fonctionnalité d’utilisation du jeton omnicanal, seul un jeton de carte récurrent était créé pour l’exécution consécutive de la commande. Par conséquent, les fonds pour l’exécution en attente n’étaient autorisés, et comme ces fonds n’étaient pas conservés pour cet achat spécifique, il était moins probable qu’ils pourraient être capturés ultérieurement.

> [!NOTE]
> Le passage de carte seul n’est pas pris en charge dans la version 8.1.3 de Retail. Les commandes client dans la version 8.1.3 utilisent le même flux que celui utilisé avant la mise en œuvre de la fonctionnalité d’utilisation de jeton omnicanal. 

### <a name="cards-that-cant-issue-recurring-card-tokens"></a>Cartes qui ne peuvent pas émettre de jetons de carte récurrents

Certains cartes ne peuvent pas être utilisées pour les paiements omnicanaux, car elles ne prennent pas en charge l’émission de jetons de carte récurrents. Lorsqu’une commande est créée dans le POS, si l’acompte est payé à l’aide d’une carte qui ne prend pas en charge les jetons de carte récurrents, le flux d’utilisation de jeton de carte précédent est utilisé. Par conséquent, un client qui souhaite fournir un paiement qui sera utilisé pour l’exécution consécutive de la commande doit présenter une deuxième carte. Si la deuxième carte ne prend pas en charge les jetons de carte récurrents, l’action d’utilisation de jeton est refusée, et le caissier est invité à demander au client de fournir une autre carte. 

### <a name="using-a-different-card"></a>Utilisation d’une autre carte

Un client qui vient au magasin pour prélever une commande a la possibilité d’utiliser une autre carte. Lorsque le caissier reçoit l’invite **Utiliser un mode de paiement disponible** au moment du prélèvement de la commande, il peut demander si le client veut utiliser la même carte. Si le client a perdu la carte utilisée pour créer la commande et souhaite payer celle-ci avec une autre carte, le caissier peut sélectionner **Utiliser un autre mode de paiement**. Si le client revient plus tard pour prélever des articles supplémentaires pour la même commande, si l’autorisation de carte d’origine reste valide, le caissier peut de nouveau demander si le client veut utiliser cette carte.

### <a name="invalid-authorizations"></a>Autorisations non valides

Si la carte utilisée pour créer une commande n’est plus valide, lorsque des produits sont sélectionnés pour un prélèvement, la demande de capture de paiement échoue. Le connecteur de paiement POS essaie ensuite de créer une autorisation et de capturer à l’aide des mêmes informations de carte. Si la nouvelle autorisation ou capture échoue, le caissier est informé que le paiement ne peut pas être traité. Le caissier doit alors obtenir un nouveau paiement du client. 

### <a name="multiple-available-payments"></a>Plusieurs paiements disponibles

Lorsqu’une commande comporte plusieurs modes de paiement et que plusieurs lignes sont prélevées, le caissier reçoit d’abord l’invite **Utiliser le mode de paiement disponible**. S’il existe plusieurs cartes, lorsque le caissier sélectionne **Utiliser le mode de paiement disponible**, les lignes de mode de paiement par carte existantes sont capturées jusqu’à ce que le solde soit atteint pour les marchandises en cours de prélèvement. Le caissier n’aura pas la possibilité de sélectionner la carte à utiliser pour les marchandises qui sont prélevées. 

## <a name="related-topics"></a>Rubriques connexes

- [FAQ Paiements](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/payments-retail)
- [Connecteur de paiement Dynamics 365 pour Adyen](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3)
- [Configurer le BOPIS dans un environnement d’évaluation Dynamics 365 Commerce](https://docs.microsoft.com/dynamics365/commerce/cpe-bopis)

