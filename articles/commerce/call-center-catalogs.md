---
title: Catalogues de centre d'appels
description: Cette rubrique décrit la fonctionnalité spécifique au centre d'appel des catalogues dans Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, RetailCatalogDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e4d2b1f4b7fb9394f54674f9622c8a8edd435311
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022488"
---
# <a name="call-center-catalogs"></a>Catalogues de centre d'appels

[!include [banner](includes/banner.md)]

Cette rubrique décrit la fonctionnalité spécifique au centre d'appels associée aux fonctions de catalogue dans Dynamics 365 Commerce.

Les fonctions de catalogue disponibles dans Commerce peuvent être utilisées à plusieurs fins. Les fonctions de catalogue ont été initialement créées pour prendre en charge les intégrations de e-Commerce tierces. Le paramétrage du catalogue a permis aux sociétés de créer un regroupement de produits et d'attributs qui pouvaient être publiés en externe pour la consommation par une solution de e-Commerce tierce.

Lorsque la prise en charge du canal du centre d'appels a été ajoutée, le concept de catalogue a été développé pour ajouter des fonctions supplémentaires de prise en charge et de gestion des fonctionnalités associées aux catalogues marketing traditionnels destinés directement aux consommateurs. Une société qui traite directement avec les consommateurs produit souvent des catalogues imprimés, qui sont ensuite envoyés par courrier électronique à un ou plusieurs segments de clients. Ces catalogues contiennent généralement des promotions ou offres spécifiques qui sont honorées uniquement si le client fournit un code d'identification du catalogue au moment de la création de la commande.

Les sociétés marketing qui traitent directement avec les consommateurs sont très attentives au suivi de la réponse à ces catalogues pour garantir que les coûts de production et de publipostage sont justifiés. Pour suivre la réponse, un code est traditionnellement imprimé à l'arrière du catalogue et ce code est ensuite demandé et appliqué lorsque le destinataire du catalogue appelle pour passer une commande par téléphone (ou plus traditionnellement, le code peut être saisi lorsque le client passe une commande en ligne). Bien que différents termes ont été utilisés dans l'industrie pour identifier ce code de suivi du catalogue (notamment le code de clé, le code de promotion, le code de catalogue, le code source), nous appelons ce code **ID code source** dans Commerce.

## <a name="basic-catalog-setup"></a>Paramétrage de base du catalogue

Accédez à **Commerce et vente au détail** \> **Catalogues et assortiments** \> **Tous les catalogues** pour configurer votre catalogue.

Lorsque vous créez un catalogue, vous devez d'abord associer le catalogue à un ou plusieurs canaux. Pour ce faire, accédez à l'organisateur **Canaux Commerce** dans l'écran **Paramétrage du catalogue**. Cliquez sur **Ajouter** et sélectionnez un ou plusieurs canaux. Seuls les articles associés aux [assortiments](https://docs.microsoft.com/dynamics365/unified-operations/retail/assortments) du canal sélectionné peuvent être utilisés lors de la création du catalogue.

Pour ajouter des produits à un catalogue, une hiérarchie de navigation doit être choisie. La hiérarchie de navigation prend en charge la structure de catégories pour le catalogue. Vous devez sélectionner l'une des hiérarchies de navigation associées aux canaux sélectionnés dans le raccourci **Canaux Commerce** de la page **Catalogue**. Si un canal de navigation n'a pas été associé précédemment à un canal, accédez à **Commerce et vente au détail** \> **Paramétrage du canal** \> **Catégories de canal et attributs de produit** pour associer une valeur par défaut de hiérarchie de navigation à chacun de vos canaux.

Sous l'onglet **Catalogues**, dans la page **Paramétrage du catalogue**, cliquez sur **Ajouter des produits** pour configurer les produits à ajouter au catalogue, ou sélectionnez un nœud dans la hiérarchie de navigation (la sélection d'un nœud modifie la présentation de l'écran et vous permet d'ajouter des produits directement à une catégorie du catalogue).

Cliquez sur le nœud supérieur de la hiérarchie de catalogues pour revenir à la vue principale de l'en-tête du catalogue. Configurez si nécessaire les dates d'effet et d'expiration sous l'organisateur **Général**.

Avant que le catalogue puisse être utilisé, il doit être publié. Cliquez sur **Contrôler le catalogue** dans le menu **Catalogues** pour procéder à la validation. Cette action est nécessaire pour valider que le paramétrage requis est exact. Cliquez sur **Afficher les résultats** pour afficher les détails de la validation. Si des erreurs sont détectées, vous devez corriger les données et réexécuter la validation jusqu'à ce qu'elle réussisse.

Une fois que la validation est confirmée, cliquez sur **Workflow** dans le menu pour démarrer le workflow d'approbation. Cliquez sur **Envoyer** dans le menu **Workflow** pour exécuter le processus. Configurez les étapes et les utilisateurs autorisés pour le workflow sous **Commerce et vente au détail** \> **Configuration du siège** \> **Workflows Commerce**. Le workflow définit les étapes requises pour faire passer le catalogue à l'état **Approuvé**. Lorsque le catalogue est à l'état **Approuvé**, vous pouvez cliquer sur l'option **Publier** dans le menu **Catalogues** pour terminer le processus. Une fois que le catalogue est à l'état **Publié**, il peut être utilisé dans les processus d'envoi du catalogue et de saisie de commande dans le centre d'appels.

## <a name="use-catalogs-to-drive-sales-order-pricing-and-promotions"></a>Utiliser les catalogues pour définir la tarification et les promotions sur les commandes client

La définition d'un catalogue à utiliser avec un centre d'appels permet de configurer des prix et des promotions spécifiques pour ce catalogue. Les clients qui passent une commande à partir de ce catalogue reçoivent ces prix et promotions lors de la saisie de commande dans le centre d'appels si l'**ID code source** du catalogue est appliqué à l'en-tête ou la ligne de commande.

Pour configurer des prix spécifiques au catalogue, sélectionnez l'option **Groupes de prix** sous l'onglet **Catalogues** pour associer un ou plusieurs groupes de prix au catalogue. Les accords commerciaux, les journaux d'ajustement de prix et les remises avancées (seuil, quantité, assortiment) qui ont été associés au même groupe de prix sont appliqués lorsque les clients passent une commande à partir de ce catalogue.

Dans l'organisateur **Codes source**, cliquez sur **Ajouter** pour ajouter un ou plusieurs identificateurs **ID code source** à ce catalogue. Il s'agit du code qui sera appliqué lors de la saisie de commande dans le centre d'appels à l'en-tête (et aux lignes) de la commande client. Ce code est utilisé pour associer la commande client au catalogue, ainsi qu'aux groupes de prix et aux offres et promotions spéciales qui ont été configurées.

## <a name="use-the-source-id-to-track-costs-and-response-rates"></a>Utiliser l'ID source pour suivre les coûts et les taux de réponse

Lorsque vous définissez l'**ID code source**, vous pouvez éventuellement associer cet ID à un**ID marché cible**. L'**ID marché cible** peut être défini dans **Commerce et vente au détail** \> **Clients** \> **Marché cible**. Le marché cible est une liste de clients et/ou prospects qui appartiennent à un segment défini par l'utilisateur. L'association des données du client ou du prospect à l'ID code source offre une meilleure visibilité sur les destinataires du catalogue. Si un client est associé à un marché cible et que ce marché cible est associé à un ID code source/catalogue actif, les utilisateurs du centre d'appels peuvent voir les catalogues reçus par un client en sélectionnant l'option de menu **Codes source** sous l'onglet de menu **Clients** de la page **Service client**. Lors de la saisie de commande, les utilisateurs du centre d'appels peuvent également voir les catalogues spécifiques envoyés à un client dans la liste déroulante **Source** de l'en-tête de la commande client. Lorsque vous modifiez le filtre **Tous** en **Ciblé**, l'utilisateur peut voir les catalogues actifs spécifiques envoyés au client. Cela est utile dans les cas où le client a oublié son catalogue ou ne peut pas localiser ou lire le code de catalogue lorsqu'il appelle pour créer une commande client.

Il est possible d'associer plusieurs ID code source à un catalogue. Cela est souvent nécessaire lorsqu'une société souhaite suivre le taux de réponse selon différents segments. La société fournit un code de catalogue unique à différents segments de clients, ce qui permet de suivre le taux de réponse jusqu'au niveau du segment, dans un événement de catalogue spécifique.

Lorsque vous sélectionnez un enregistrement **ID code source** spécifique et cliquez sur l'option **Détails** dans l'organisateur **Codes source**, des champs supplémentaires s'affichent pour vous permettre de capturer les prévisions de vente, les coûts de publipostage et les dates de publipostage. Ces données sont utiles pour effectuer une analyse détaillée de l'efficacité du catalogue. Les utilisateurs peuvent revenir à cette page et utiliser les boutons **Analyse du code source** et **Comparaison les promotions** pour déclencher des états d'analyse basés sur les données de vente actuelles et comparer les coûts et le budget aux chiffres réels.

## <a name="configure-catalog-specific-order-and-item-scripts"></a>Configurer les scripts de commande et d'article spécifiques au catalogue

Lorsqu'un utilisateur du centre d'appels crée une commande client, il peut utiliser les scripts à l'écran. Ces scripts de texte peuvent fournir des informations supplémentaires que l'utilisateur doit indiquer au client, ou il peut s'agir de notes/rappels internes que l'utilisateur du centre d'appels doit examiner et prendre en compte lorsqu'il crée la commande client.

Il est souvent utile d'avoir différents ensembles de scripts pour différents catalogues. Dans l'organisateur **Scripts**, les scripts prédéfinis peuvent être associés à un catalogue. Utilisez le champ **Calcul de temps** pour déterminer si le script s'affiche au début de la commande (dès que l'ID code source est saisi dans l'en-tête de la commande), ou à la fin de la commande (dans l'écran récapitulatif de la commande client).

Lors de la sélection d'un nœud dans la hiérarchie du catalogue et de l'utilisation des données de l'organisateur **Produits**, les utilisateurs peuvent également associer des scripts spécifiques aux catalogues ou articles à l'aide de l'action **Scripts**.

## <a name="configure-catalog-specific-up-sell-and-cross-sell-items"></a>Configurer les articles de vente de gamme supérieure/croisée spécifiques au catalogue

L'association de suggestions de vente de gamme supérieure/croisée à un article peut être effectuée à partir des paramètres des produits, mais dans certains cas, une société souhaite promouvoir des articles spéciaux de vente de gamme supérieure/croisée auprès des clients qui commandent un produit spécifique à partir d'un catalogue spécifique. Dans l'organisateur **Produits**, sélectionnez un article et cliquez sur **Articles de vente de gamme supérieure/croisée** pour configurer des produits à vendre aux clients qui achètent l'article sélectionné dans le catalogue. Lors de la saisie de commande du centre d'appels, les articles de vente de gamme supérieure/croisée s'affichent à l'écran, au lieu des produits de vente de gamme supérieure/croisée qui ont peut-être été configurés pour cet article par le biais de la configuration habituelle des produits.

Les articles de vente de gamme supérieure/croisée peuvent également tirer parti des fonctions de script pour afficher des messages spécifiques qui sont visibles par l'utilisateur lorsque l'article de vente de gamme supérieure/croisée est affiché lors de la saisie de commande. Les scripts associés aux produits de vente de gamme supérieure/croisée configurés spécifiquement pour un produit du catalogue s'affichent uniquement lorsque le code source de ce catalogue est appliqué lors de la saisie de commande dans le centre d'appels.

## <a name="catalog-page-analysis"></a>Analyse d'une page du catalogue

Sous l'onglet **Catalogues**, des options sont disponibles pour configurer les **Pages du catalogue**. Cette fonction vous permet de définir des pages et des types de pages spécifiques pour le catalogue imprimé et leurs coûts associés.

Lorsque vous configurez les produits du catalogue, utilisez l'action **Mise en page du produit** pour définir les pages spécifiques, le pourcentage de page et la position des détails de page pour l'article. La configuration de ces données permet aux utilisateurs de tirer parti de l'**État de l'analyse d'une zone de catalogue**. Cet état est accessible sous **Commerce et vente au détail** \> **États du centre d'appels** \> **État de l'analyse d'une zone de catalogue**. Cet état analyse les commandes passées dans le catalogue (les commandes client dont l'ID source du catalogue a été associé à l'en-tête ou la ligne de commande) ainsi que le pourcentage de page et les coûts associés pour générer un état **Analyse par pouce carré** pour le marketing direct traditionnel.

## <a name="catalog-requests"></a>Demandes de catalogue

Comme les catalogues sont configurés et publiés dans Commerce, la fonction **Envoyer le catalogue** peut être utilisée. Cette fonction est disponible dans les pages **Recherche du client** et **Service client**. Après avoir sélectionné un enregistrement client via la fonction **Recherche du client** ou lors de l'affichage d'un compte client sélectionné à partir du **Service client**, les utilisateurs peuvent sélectionner l'option **Envoyer le catalogue** qui ouvre une boîte de dialogue permettant à l'utilisateur de choisir dans la liste des catalogues publiés et actifs. Un utilisateur peut sélectionner un catalogue et une quantité, ainsi qu'un ID code source spécifique à envoyer. Lorsqu'il clique sur le bouton **Envoyer**, une demande est enregistrée et peut ensuite être gérée en imprimant l'état **Demandes de catalogue**. Cet état est accessible sous **Commerce et vente au détail** \> **États du centre d'appels** \> **État des demandes de catalogue**. Il répertorie toutes les demandes de catalogue, y compris le nom et l'adresse du client ayant demandé le catalogue. Cet état peut être utilisé en interne ou les données peuvent être transmises à un tiers qui prend en charge les processus externes pour l'envoi physique du catalogue au client.

## <a name="additional-features"></a>Fonctionnalités supplémentaires

Sous l'onglet **Catalogues**, des options de configuration d'un **Échéancier de paiement** et des **Produits gratuits** sont également disponibles. Si l'ID code source associé au catalogue est appliqué lors de la saisie de commande du centre d'appels, le client peut bénéficier des produits gratuits ou utiliser les échéanciers de paiement spécifiques définis. S'il est nécessaire de limiter le client à choisir uniquement parmi les échéanciers de paiement associés à son catalogue, et non tous les échéanciers de paiement actifs dans le système, la case à cocher **Autoriser uniquement les plans liés au catalogue** peut être sélectionnée pour un ou plusieurs des ID code source définis pour appliquer cette limitation.

## <a name="additional-notes"></a>Notes supplémentaires

Actuellement, lorsqu'un ID code source est appliqué à une commande client du centre d'appels, il est utilisé pour piloter les prix, les promotions, les scripts et les articles de vente de gamme supérieure/croisée qui sont spécifiques au catalogue. Le système n'interdit pas, ni n'empêche la commande d'un produit qui ne figure pas dans le catalogue. Si un article commandé ne figure pas dans le catalogue, le système utilise d'abord l'option **Groupe de prix** définie dans le canal du centre d'appels (**Commerce et vente au détail** \> **Canaux** \> **Centres d'appels** \> **Tous les centres d'appels**) pour définir le prix de l'article ou les promotions. Si aucun prix de canal spécifique n'est trouvé, le prix de vente de base de l'article est utilisé.
