---
title: Matières dangereuses dans les produits, les commandes, les expéditions et les chargements
description: Cette rubrique explique comment définir les propriétés des matières dangereuses pour les produits lancés, comment fixer des limites de stock aux articles dangereux et comment inclure des matières dangereuses dans une commande client, une expédition ou un chargement.
author: dasani-madipalli
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: b0fb2f77b4e95c90e3eb8a4c74929deead34de5c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829400"
---
# <a name="hazardous-materials-in-products-orders-shipments-and-loads"></a>Matières dangereuses dans les produits, les commandes, les expéditions et les chargements

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment définir les propriétés des matières dangereuses pour les produits lancés, comment fixer des limites de stock aux articles dangereux et comment inclure des matières dangereuses dans une commande client, une expédition ou un chargement.

## <a name="set-hazardous-material-specifications-for-products"></a>Définir les spécifications de matières dangereuses pour les produits

Après avoir défini une réglementation sur les matières dangereuses et configuré les codes de référence associés comme décrit dans [Paramétrer les matières dangereuses](hazmat-setup.md), vous pouvez associer ces informations aux articles validés. Le texte d’expédition des documents d’expédition sera tiré des informations sur les matières dangereuses pour les articles lancés.

Dans le cadre du processus d’association d’un article validé avec une matière dangereuse, vous devez spécifier le code de réglementation et l’article. Différents codes de réglementation peuvent être associés à un article, selon les modes de transport, et vous pouvez associer plusieurs règlements et codes de matière à chaque article.

Pour configurer un produit lancé en tant que matière dangereuse, procédez comme suit.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Sélectionnez ou créez un produit pour ouvrir sa page **Détails des produits lancés**.
1. Dans le raccourci **Gérer le stock**, définissez l’option **Matières dangereuses** sur **Oui**. Ce paramètre identifie l’article comme une marchandise dangereuse et est utilisé lors de l’impression de la documentation d’expédition.
1. Dans le volet Actions, sous l’onglet **Gérer le stock**, dans le groupe **Conformité**, sélectionnez **Article matières dangereuses**.
1. Remplissez la page **Article matières dangereuses** pour l’article sélectionné à l’aide des champs décrits dans les sous-sections suivantes.

### <a name="item-hazardous-materials-header"></a>En-tête Article matières dangereuses

Le tableau suivant décrit les champs disponibles en haut de la page **Article matières dangereuses**.

| Champ | Description |
|---|---|
| Numéro d’article | Le produit lancé avec lequel vous travaillez. |
| Code de réglementation | Sélectionnez la réglementation sur les matières dangereuses qui s’applique au produit. La réglementation définit comment le texte d’expédition imprimé est créé pour un article et les modes de livraison associés. Une fois attribué, le code ne peut pas être modifié sur cette page. Cependant, vous pouvez attribuer un nouveau code de réglementation en sélectionnant **Nouveau**. |
| Code matières | (Facultatif) Sélectionnez le code de matière dangereuse qui s’applique au produit. Le code de matière fournit un modèle qui inclut des valeurs par défaut pour de nombreux autres champs de cette page. Lorsque vous sélectionnez un code, toutes ses spécifications relatives aux matières dangereuses seront copiées dans le produit actuel. Cependant, le système vous invite d’abord à confirmer que les données de matière de l’article doivent être renseignées à partir du code article. |
| Code groupe | (Facultatif) Sélectionnez le code de groupe de classification de matière dangereuse qui s’applique au produit. Quant au champ **Code matière**, lorsque vous sélectionnez un code, toutes ses spécifications relatives aux matières dangereuses seront copiées dans le produit actuel. Cependant, le système vous invite d’abord à confirmer que les données du groupe de classe de matière de l’article doivent être renseignées à partir du code de groupe. |

### <a name="descriptions-fasttab"></a><a name="hazmat-description"></a>Raccourci Descriptions

Le tableau suivant décrit les champs disponibles dans le raccourci **Descriptions**.

| Champ | Description |
|---|---|
| Nom approprié pour l’expédition | Saisissez la description standard de la matière, comme spécifié par la réglementation applicable. Vous pouvez fournir des traductions pour cette valeur sur le raccourci **Traduction du texte d’expédition de l’article**, comme décrit dans la section suivante. |
| Nom technique | Sélectionnez le nom commun ou générique de la matière. Ce nom peut être un nom que votre entreprise utilise en interne pour la matière. |
| S.I.S. | Cochez cette case pour indiquer que la valeur **Nom d’expédition correct** est un nom d’expédition sans indication spécifique (S.I.S.) pour l’article. S.I.S. les noms d’expédition sont utilisés pour des groupes de produits chimiques et de matières similaires qui ont des utilisations finales spécifiques, mais qui peuvent ne pas être énumérés par nom dans le tableau des matières dangereuses dans une réglementation spécifique. |

### <a name="item-ship-text-translation-fasttab"></a>Raccourci Traduction du texte d’expédition de l’article

Le raccourci **Traduction du texte d’expédition de l’article** contient une grille qui affiche les traductions des valeurs **Nom d’expédition correct** définies pour la langue principale sur le raccourci **Descriptions**. Ces traductions peuvent être utilisées dans le texte d’impression d’expédition pour une ou plusieurs langues supplémentaires.

Le tableau suivant décrit les champs disponibles dans le raccourci **Traduction du texte d’expédition de l’article**.


| Champ | Description |
|---|---|
| Langue | Code de langue utilisé par la ligne. Par exemple, **pt-br** indique le portugais brésilien. |
| Texte d’impression des expéditions | Valeur **Nom d’expédition correct** traduite dans la langue utilisée par la ligne. |

Pour ajouter ou modifier une traduction, sélectionnez **Traductions** au-dessus de la grille pour ouvrir la page **Traductions du texte**. Suivez ensuite l’une des procédures suivantes :

- Pour ajouter une nouvelle traduction, sur le volet Actions, sélectionnez **Ajouter**. Sélectionnez la langue à ajouter, puis, dans le champ **Texte traduit**, entrez le texte traduit.
- Pour modifier une traduction existante, sélectionnez une langue cible dans le champ **Langue** et modifiez le texte traduit dans le champ **Texte traduit**, au besoin.

### <a name="material-management-fasttab"></a><a name="material-management"></a>Raccourci Gestion des matières

Le tableau suivant décrit les champs disponibles dans le raccourci **Gestion des matières**.

| Champ | Description |
|---|---|
| Classe | Sélectionnez la classe de matières dangereuses à laquelle appartient le produit, comme défini par la réglementation à laquelle vous vous conformez. Vous devez attribuer à la fois une division et une classe à chaque produit qui comprend des matières dangereuses. |
| Description | Description définie pour la classe sélectionnée dans le champ **Classe**. Ce champ est en lecture seule. |
| Division | Sélectionnez la division de matières dangereuses à laquelle appartient le produit, comme défini par la réglementation à laquelle vous vous conformez. La division est un sous-ensemble de la classe. Vous devez attribuer à la fois une division et une classe à chaque produit qui comprend des matières dangereuses. |
| Identification | Sélectionnez le code d’identification des matières dangereuses. Généralement, ce code est basé sur une norme des Nations Unies (O.N.U.). |
| Groupe d’emballage | Sélectionnez le groupe d’emballage applicable à l’article actuel. |
| Description | Description définie pour le groupe sélectionné dans le champ **Groupe d’emballage**. Ce champ est en lecture seule. |
| Descriptions d’emballages | Sélectionnez le code de description d’emballage applicable. Ce code fait référence à une description qui indique comment le produit doit être emballé. |
| Libellés des matières dangereuses | Sélectionnez un code qui fait référence au libellé de marchandises dangereuses applicable qui doit être apposé au produit. |
| Quantité limitée | Définissez cette option sur **Oui** pour indiquer le poids total du produit inclus dans chaque charge et sur chaque ligne de charge. |
| Quantité | Entrez la quantité de matière dangereuse dans le produit, dans l’unité spécifiée. Cette valeur sera utilisée pour calculer le score total des matières dangereuses pour les chargements et les expéditions qui incluent le produit. |
| Multiplicateur | Entrez le multiplicateur qui est appliqué lorsque le score des matières dangereuses est calculé pour chaque ligne de charge qui comprend le produit. Cette valeur est spécifiée par la réglementation applicable, selon le type de matière dangereuse contenue dans le produit. |
| Unité | Sélectionnez l’unité de mesure qui s’applique à la quantité de matière dangereuse dans le produit, comme spécifié dans le champ **Quantité**. Cette valeur sera utilisée pour calculer le score total des matières dangereuses pour les chargements et les expéditions qui incluent le produit. |

#### <a name="how-the-hazardous-material-score-is-calculated"></a>Calcul du score de matières dangereuses

Plusieurs des valeurs spécifiées sur le raccourci **Gestion des matières** pour un produit sont utilisées pour calculer un *score de matières dangereuses* pour chaque ligne de charge qui comprend ce produit. Le score est calculé à l’aide de la formule suivante :

Score de matières dangereuses = *&lt;QtéLigne&gt;* × *&lt;QtéMatDang&gt;* × *&lt;ConversionUnité&gt;* × *&lt;Multiplicateur&gt;*

Voici une clé de la formule :

- *&lt;QtéLigne&gt;* est la quantité de produit spécifiée pour une ligne de charge.
- *&lt;QtéMatDang&gt;* est la quantité de matière dangereuse spécifiée pour un produit dans le champ **Quantité** sur le raccourci **Gestion des matières**.
- *&lt;ConversionUnité&gt;* est un facteur de conversion pour la conversion entre l’unité utilisée pour la quantité de ligne de charge et l’unité spécifiée pour un produit dans le champ **Unité** sur le raccourci **Gestion des matières**.
- *&lt;Multiplicateur&gt;* est le multiplicateur spécifié pour un produit dans le champ **Multiplicateur** sur le raccourci **Gestion des matières**.

Ce score est indiqué pour chaque ligne de charge contenant un produit pour lequel ces valeurs sont spécifiées. Pour plus d’informations, consultez les sections [Expéditions contenant des matières dangereuses](#hazmat-shipments) et [Charges contenant des matières dangereuses](#hazmat-loads) plus loin dans cette rubrique.

#### <a name="how-the-hazardous-material-weight-is-calculated"></a>Calcul du poids de matières dangereuses

Les charges et les lignes de charge contenant des produits où l’option **Quantité limitée** sur le raccourci **Gestion des matières** est définie sur **Oui** afficheront le poids total des matières dangereuses, comme décrit dans les sections [Expéditions contenant des matières dangereuses](#hazmat-shipments) et [Charges contenant des matières dangereuses](#hazmat-loads) plus loin dans cette rubrique. Le poids des matières dangereuses est calculé à l’aide de la formule suivante :

Poids des matières dangereuses = *&lt;QtéLigne&gt;* × *&lt;PoidsProduit&gt;* × *&lt;ConversionUnité&gt;*

Voici une clé de la formule :

- *&lt;QtéLigne&gt;* est la quantité de produit spécifiée pour une ligne de charge.
- *&lt;PoidsProduit&gt;* est le poids net spécifié pour le produit, dans l’unité de stock spécifiée pour le produit.
- *&lt;ConversionUnité&gt;* est un facteur de conversion pour la conversion entre l’unité utilisée pour la quantité de ligne de charge et l’unité de stock utilisée pour *&lt;PoidsProduit&gt;*.

### <a name="transport-information-fasttab"></a>Raccourci Informations sur le transport

Le tableau suivant décrit les champs disponibles dans le raccourci **Informations sur le transport**.

| Champ | Description |
|---|---|
| Catégorie de transport | Sélectionnez la catégorie de transport associée. |
| Code de tunnel | Sélectionnez le code de restriction de tunnel associé à l’article. |
| Arrimage des matières dangereuses | Sélectionnez le code de référence utilisé pour la manutention d’arrimage du fret maritime lorsque l’article est expédié par fret maritime. |
| Type d’avion | Sélectionnez la restriction aérienne qui s’applique à la matière lorsqu’elle est expédiée par fret aérien. |
| Emballage - avion cargo uniquement | En fonction de la valeur que vous avez sélectionnée dans le **Type d’avion**, sélectionnez le code des instructions d’emballage qui s’applique lorsque le produit ne peut être expédié que par avion cargo. |
| Emballage - avion cargo et de passagers | En fonction de la valeur que vous avez sélectionnée dans le **Type d’avion**, sélectionnez le code des instructions d’emballage qui s’applique lorsque le produit ne peut être expédié que par avion cargo ou avion commercial. |
| IATA Star | Définissez cette option sur **Oui** pour indiquer que les spécifications de transport aérien saisies sur ce raccourci sont liées à la norme relative aux marchandises dangereuses de l’Association du transport aérien international (IATA). Ce champ est fourni uniquement à titre indicatif. |
| Intervention d’urgence | Sélectionnez le code qui fait référence aux instructions de manipulation de la matière en cas d’urgence. |

### <a name="environmental-information-fasttab"></a>Raccourci Informations environnementales

Le tableau suivant décrit les champs disponibles dans le raccourci **Informations environnementales**.

| Champ | Description |
|---|---|
| Dangereux pour l’environnement | Définissez cette option sur **Oui** pour indiquer que le produit est dangereux pour l’environnement. Utilisez ce champ pour vos propres besoins de signalement. |
| Polluant marin | Définissez cette option sur **Oui** pour indiquer que le produit est un polluant marin. Utilisez ce champ pour vos propres besoins de signalement. |

## <a name="set-stock-limits-for-hazardous-products"></a><a name="stock-limits"></a>Définissez des limites de stock pour les produits dangereux

Pour des raisons de sécurité, vous devrez peut-être limiter la quantité totale d’un produit donné qui peut être stocké à un seul endroit. Pour définir des limites de stock pour un produit lancé, procédez comme suit.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Sélectionnez un produit pour ouvrir sa page **Détails des produits lancés**.
1. Dans le volet Actions, sous l’onglet **Gérer le stock**, dans le groupe **Conformité**, sélectionnez **Détails de la déclaration**.
1. Dans les champs **Limite de stock dangereux** et **Limite d’avertissement de danger**, définissez les valeurs appropriées pour le produit sélectionné.

La déclaration **Limite de stock de matières dangereuses** vous permet de surveiller les niveaux de stock des matières dangereuses dans vos entrepôts, pour vous assurer qu’ils restent sous les limites de sécurité établies ici. Pour plus d’informations, consultez [Déclaration de limite de stock de matières dangereuses](hazmat-reports.md#stock-limit-report).

## <a name="sales-order-transactions-that-include-hazardous-materials"></a>Transactions de commande client comprenant des matières dangereuses

Pour inclure un produit classé comme matière dangereuse dans une commande client, vous devez associer le transporteur concerné à la commande client. Ouvrez la commande client, puis, sur le raccourci **Livraison**, définissez les champs **Transporteur maritime** et **Service de transporteur** au besoin.

Le transporteur est également associé au mode de livraison. Par conséquent, vous devez vous assurer que ces informations sont conformes à la réglementation sur les matières dangereuses. En d’autres termes, le mode de livraison spécifié dans la réglementation sur les matières dangereuses doit correspondre aux spécifications de l’en-tête de la commande client. De cette manière, la réglementation, le transporteur et le service sont connectés aux lignes d’expédition utilisées sur une commande client.

Une fois qu’une commande client est finalisée et prête à être expédiée, elle peut être validée vers l’entrepôt pour indiquer le transfert entre les opérations de vente et d’entrepôt.

## <a name="shipments-that-include-hazardous-materials"></a><a name="hazmat-shipments"></a>Expéditions contenant des matières dangereuses

### <a name="view-hazardous-material-scores-for-each-shipment-line"></a>Afficher les scores de matières dangereuses pour chaque ligne d’expédition

La page **Détails de l’expédition** d’une expédition affiche le poids total des matières dangereuses et les valeurs en points calculées pour chaque ligne de chargement comprise dans cette expédition. Pour afficher les scores et les poids, procédez comme suit.

1. Allez dans **Gestion des entrepôts \> Expéditions \> Toutes les expéditions**.
1. Sélectionnez une expédition pour ouvrir sa page **Détails de l’expédition**.
1. Sur le raccourci **Lignes de charge**, inspectez les lignes. Pour chaque ligne, vous verrez les calculs de matières dangereuses dans les champs suivants :

    - **Points de matières dangereuses** – Ce champ affiche le score des matières dangereuses pour la ligne de charge. La valeur est calculée selon les règles et valeurs qui ont été établies pour la réglementation applicable et dans la configuration du produit validé. Le calcul utilise la quantité de la ligne de charge et référence le multiplicateur dans la [configuration de la gestion des matières](#material-management) pour le produit lancé.
    - **Poids net en quantité limitée** – Pour les produits marqués comme produits en quantité limitée en raison de leur contenu de matières dangereuses, ce champ indique le poids net total du contenu dangereux inclus dans la ligne de charge. Le calcul est basé sur les produits marqués comme matières dangereuses dans la configuration du produit lancé. Si un article est marqué comme article en quantité limitée, le calcul prend la quantité sur chaque ligne de charge et fait référence au poids dans la [configuration de la gestion des matières](#material-management) pour le produit lancé.

### <a name="check-for-compatibility-among-hazardous-materials-that-are-included-in-a-shipment"></a>Vérifier la compatibilité entre les matières dangereuses incluses dans une expédition

Le système peut évaluer si toutes les matières dangereuses incluses dans une expédition peuvent être expédiées ensemble. Pour évaluer la compatibilité, le système vérifie le groupe de compatibilité affecté à chaque produit compris dans l’expédition. Pour plus d’informations, consultez [Groupes de compatibilité des matières dangereuses](hazmat-setup.md#compatibility-groups).

Pour exécuter la vérification de la compatibilité, procédez comme suit.

1. Allez dans **Gestion des entrepôts \> Expéditions \> Toutes les expéditions**.
1. Sélectionnez une expédition pour ouvrir sa page **Détails de l’expédition**.
1. Dans le volet Actions, sous l’onglet **Expéditions**, dans le groupe **Actions**, sélectionnez **Vérification de la compatibilité**.

Vous recevez un message qui vous informe des résultats de la vérification.

## <a name="loads-that-include-hazardous-materials"></a><a name="hazmat-loads"></a>Charges contenant des matières dangereuses

### <a name="view-hazardous-material-scores-for-each-load-line"></a>Afficher les scores de matières dangereuses pour chaque ligne de charge

La page **Détails de la charge** d’une charge affiche le poids total des matières dangereuses et les valeurs en points calculées pour cette charge et pour chaque ligne de charge. Pour afficher les scores et les poids, procédez comme suit.

1. Allez dans **Gestion des entrepôts \> Expéditions \> Toutes les charges**.
1. Sélectionnez une charge pour ouvrir sa page **Détails de la charge**. (Vous pouvez également ouvrir les détails de la charge en sélectionnant un lien à partir d’une expédition associée.)
1. Sur le raccourci **Charge**, vous pouvez consulter les scores et poids totaux des matières dangereuses pour l’ensemble de la charge en inspectant les champs suivants :

    - **Points de matières dangereuses** – Ce champ affiche le score des matières dangereuses pour la charge. La valeur est calculée selon les règles et valeurs qui ont été établies pour la réglementation applicable et dans la configuration du produit validé. Le calcul utilise la quantité comprise dans la charge et référence le multiplicateur dans la [configuration de la gestion des matières](#material-management) pour le produit lancé.
    - **Poids net en quantité limitée** – Pour les produits marqués comme produits en quantité limitée en raison de leur contenu de matières dangereuses, ce champ indique le poids net total du contenu dangereux inclus dans la charge. Le calcul est basé sur les produits marqués comme matières dangereuses dans la configuration du produit lancé. Si un article est marqué comme article en quantité limitée, le calcul prend la quantité dans chaque charge et fait référence au poids dans la [configuration de la gestion des matières](#material-management) pour le produit lancé.

1. Pour consulter les scores et les poids des lignes individuellement, sélectionnez le raccourci **Lignes de charge**. Les valeurs fournies pour chaque ligne ressemblent aux valeurs fournies pour l’ensemble de la charge, comme décrit à l’étape précédente.

### <a name="check-for-compatibility-among-hazardous-materials-that-are-included-in-a-load"></a>Vérifier la compatibilité entre les matières dangereuses incluses dans une charge

Le système peut évaluer si toutes les matières dangereuses incluses dans une charge peuvent être expédiées ensemble. Pour évaluer la compatibilité, le système vérifie le groupe de compatibilité affecté à chaque produit compris dans la charge. Pour plus d’informations, consultez [Groupes de compatibilité des matières dangereuses](hazmat-setup.md#compatibility-groups).

Pour exécuter la vérification de la compatibilité, procédez comme suit.

1. Allez dans **Gestion des entrepôts \> Expéditions \> Toutes les charges**.
1. Sélectionnez une expédition pour ouvrir sa page **Détails de la charge**. (Vous pouvez également ouvrir les détails de la charge en sélectionnant un lien à partir d’une expédition associée.)
1. Dans le volet Actions, sous l’onglet **Charges**, dans le groupe **Actions**, sélectionnez **Vérification de la compatibilité**.

Vous recevez un message qui vous informe des résultats de la vérification.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]