---
title: Configurer le mode de paiement du compte client pour les sites de commerce électronique B2B
description: Cet article décrit comment configurer le mode de paiement du compte client dans Microsoft Dynamics 365 Commerce. Il décrit également comment les limites de crédit affectent la capture des paiements sur compte sur les sites e-commerce interentreprises (B2B).
author: josaw1
ms.date: 04/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 20af517b9a69f4fb490d4d93ada8bc4063e895dd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878645"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a>Configurer le mode de paiement du compte client pour les sites de commerce électronique B2B

[!include [banner](../../includes/banner.md)]

Cet article décrit comment configurer le mode de paiement du compte client dans Microsoft Dynamics 365 Commerce. Il décrit également comment les limites de crédit affectent la capture des paiements sur compte sur les sites e-commerce interentreprises (B2B).

Les détaillants peuvent accepter différents types de paiement en échange des produits et des services qu’ils vendent dans un canal d’e-commerce. Chaque type de paiement accepté par un détaillant doit être configurée dans Dynamics 365 Commerce au moment du paramétrage du système. Le mode de paiement du compte client (ou « en compte ») doit être pris en charge sur les sites e-commerce B2B. 

## <a name="prerequisites"></a>Conditions préalables

1. Ajoutez le mode de paiement du compte client dans Commerce Headquarters.
2. Associez le mode de paiement du compte client au canal e-commerce.
3. Vérifiez que la propriété **Autoriser en compte** est activée pour le client dans **Retail et Commerce \> Clients \> Tous les clients \> Valeurs par défaut du paiement** dans Commerce Headquarters.

    > [!NOTE]
    > Si tous les clients doivent être autorisés à activer le mode de paiement sur compte, vous pouvez définir la propriété **Autoriser sur compte** sur **Oui** pour le client par défaut du canal associé au site B2B. 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a>Activer le mode de paiement du compte client dans le générateur de site Commerce 

Pour activer le mode de paiement du compte client dans le générateur de site Commerce, procédez comme suit :

1. Accédez à **Paramètres du site \> Extensions**.
1. Définissez la propriété **Activer les paiements du compte client** sur **Activé pour les clients B2B**. 
1. Sélectionnez **Enregistrer et publier**.

> [!NOTE]
> Les nouveaux paramètres de site ne prennent effet qu’après la mise à jour du fichier app.settings.json. Pour plus d’informations, voir [Mise à jour des kits de développement logiciel (SDK) et des bibliothèques de modules](../e-commerce-extensibility/sdk-updates.md).

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a>Activer le mode de paiement du compte client sur la page de paiement du site e-commerce B2B

Pour activer le mode de paiement du compte client sur la page de paiement du site e-commerce B2B, procédez comme suit :

1. Dans le générateur de site Commerce, recherchez et modifiez la page de paiement ou le fragment contenant le module de paiement du site de commerce électronique B2B.
1. Dans l’emplacement **Conteneur de section de caisse**, sélectionnez **Ajouter un module**, puis ajoutez un module **Paiement du compte client**.
1. Positionnez le module **Paiement du compte client** en sélectionnant les points de suspension (**...**), puis en sélectionnant **Déplacer vers le haut** ou **Déplacer vers le bas** selon les besoins.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a>Confirmer que le mode de paiement du compte client a été activé et publié

Pour confirmer que le mode de paiement du compte client a été activé et publié, procédez comme suit :

1. Connectez-vous au site d’e-commerce.
1. Ajoutez un produit dans le panier.
1. Allez sur la page de caisse. Vous devriez voir le nouveau mode de paiement **Compte client**.

## <a name="work-with-credit-limits"></a>Utiliser des limites de crédit

Quand les fonctionnalités de paiement du compte client sont activées sur le site B2B, les organisations souhaitent généralement afficher des informations sur les limites de crédit et les soldes de limite de crédit pendant le processus de capture de commande. La limite de crédit d’un client est définie par la propriété **Limite de crédit** via le raccourci **Crédit et recouvrement** dans le dossier client dans Commerce headquarters. Cependant, dans les scénarios B2B, une commande passée par un client doit souvent être facturée sur le compte de l’organisation à laquelle appartient le client. Par conséquent, vous devez définir la propriété **Compte de facturation** via le raccourci **Facture et livraison** de l’enregistrement client vers l’ID de compte client de l’organisation. Ensuite, quand le client passera une commande sur le site B2B, la commande sera facturée à l’organisme. Le site B2B utilisera également la limite de crédit de l’organisation au lieu de la limite de crédit définie sur la fiche client.

Le calcul et le solde de la limite de crédit affichés sur le site Web B2B dépendent du paramétrage de la propriété **Type de limite de crédit** dans Commerce Headquarters. L’emplacement de cette propriété varie selon que la fonctionnalité **Gestion de crédit** est activée dans l’espace de travail **Gestion des fonctionnalités** :

- Si la fonctionnalité **Gestion de crédit** est activée, la propriété est située au niveau du raccourci **Limites de crédit** sur **Crédit et recouvrement \> Configuration \> Paramètres de crédit et de recouvrement \> Crédit**. 
- Si la fonctionnalité **Gestion de crédit** est désactivée, la propriété est située sous **Cote de crédit** sous **Comptes débiteurs \> Configuration \> Paramètres des comptes clients \> Cote de crédit**.

Les valeurs que la propriété **Type de limite de crédit** prend en charge sont **Aucun**, **Équilibre**, **Solde + bon de livraison ou ticket de caisse** et **Solde + Tout**. Pour plus d’informations sur ces valeurs, voir [Valeurs de type limite de crédit](/dynamics365/supply-chain/sales-marketing/credit-limits-customers).

> [!NOTE]
> Nous vous recommandons de définir la propriété **Type de limite de crédit** sur **Solde + bordereau d’emballage ou bordereau produit**, afin que les commandes client en cours ne contribuent pas au calcul du solde. Ensuite, si vos clients passent de futures commandes, ils n’ont pas à s’inquiéter que ces commandes affectent leur solde actuel.

Une autre propriété qui affecte les commandes sur compte est la propriété **Limite de crédit obligatoire** qui est située via le raccourci **Crédit et recouvrement** de la fiche client. En définissant cette propriété sur **Oui** pour des clients spécifiques, vous pouvez forcer le système à vérifier leur limite de crédit, même si la propriété **Type de limite de crédit** a été définie sur **Aucun** pour préciser que la limite de crédit ne doit être vérifiée pour aucun client.

Actuellement, un client utilisant le mode de paiement sur compte ne peut pas payer plus que le solde créditeur restant pour une commande. Par exemple, si le solde créditeur restant d’un client est de 1 000 $, mais que la commande vaut 1 200 $, le client ne peut payer que 1 000 $ en utilisant la méthode sur compte. Le client doit ensuite utiliser un autre mode de paiement pour payer le solde. Dans une future version, une configuration Commerce permettra aux utilisateurs de dépenser au-delà de leur limite de crédit au moment de passer des commandes.

Le module **Crédit et recouvrement** a de nouvelles capacités de gestion de crédit. Pour activer ces fonctionnalités, activez la fonctionnalité **Gestion de crédit** dans l’espace de travail **Gestion des fonctionnalités**. L’une des nouvelles fonctionnalités permet de mettre en attente les commandes clients en fonction de règles de blocage. Le responsable du crédit peut ensuite libérer ou rejeter les commandes après une analyse plus approfondie. Toutefois, la possibilité de mettre les commandes client en attente ne s’applique pas aux commandes Commerce, car les commandes client comportent souvent un acompte et la fonctionnalité **Gestion de crédit** ne prend pas complètement en charge les scénarios de prépaiement. 

Indépendamment du fait que la fonctionnalité **Gestion de crédit** est activée, si le solde d’un client dépasse la limite de crédit pendant l’exécution de la commande, les commandes clients ne seront pas mises en attente. Au lieu de cela, Commerce générera soit un message d’avertissement, soit un message d’erreur, selon la valeur du champ **Message au moment du dépassement de la limite de crédit** via le raccourci **Limites de crédit**.

La propriété **Exclure de la gestion du crédit** qui empêche le blocage des commandes client Commerce se trouve dans l’en-tête de la commande client (**Commerce et vente au détail \> Clients \> Tous les bons de commande**). Si cette propriété est définie sur **Oui** (la valeur par défaut) pour les commandes client Commerce, les commandes seront exclues du workflow en attente de la gestion des crédits. Bien que la propriété s’appelle **Exclure de la gestion du crédit**, la limite de crédit définie sera toujours utilisée au moment de l’exécution de la commande. Les commandes ne seront tout simplement pas en attente.

La possibilité de suspendre les commandes client Commerce en fonction des règles de blocage est prévue pour les futures versions de Commerce. Jusqu’à ce qu’il soit pris en charge, si vous devez forcer les commandes client Commerce à passer par les nouveaux flux de gestion des crédits, vous pouvez personnaliser les fichiers XML suivants dans votre solution Visual Studio. Dans les fichiers, modifiez la logique pour que l’indicateur **CredManExcludeSalesOrder** soit défini sur **Non**. De cette façon, la propriété **Exclure de la gestion du crédit** sera définie sur **Non** par défaut pour les commandes client Commerce.

- RetailCreateCustomerOrderExtensions_CredMan_Extension.xml
- RetailCallCenterOrderExtensions_CredMan_Extension.xml

Si l’indicateur **CredManExcludeSalesOrder** est défini sur **Non**, et qu’un client B2B peut acheter dans des magasins à l’aide de l’application de point de vente (PDV), la publication des transactions en espèces et à emporter peut échouer. Par exemple, il existe une règle de blocage sur le type de paiement en espèces et le client B2B a acheté certains articles dans le magasin en utilisant des espèces. Dans ce cas, la commande client résultante ne sera pas facturée avec succès car elle sera mise en attente. Par conséquent, la publication échouera. Pour cette raison, nous vous recommandons d’effectuer des tests de bout en bout après avoir implémenté cette personnalisation.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer un site d’e-commerce B2B](set-up-b2b-site.md)

[Gérer les partenaires commerciaux B2B à l’aide des hiérarchies de clients](partners-customer-hierarchies.md)

[Gérer les utilisateurs des partenaires commerciaux sur les sites e-commerce B2B](manage-b2b-users.md)

[Définir des limites de quantité de produits pour les sites de commerce électronique B2B](quantity-limits.md)

[Mise à jour du kit de développement logiciel et de la bibliothèque de modules](../e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
