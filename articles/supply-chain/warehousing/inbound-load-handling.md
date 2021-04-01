---
title: Gestion en entrepôt des chargements entrants pour les commandes fournisseur
description: Cette rubrique décrit le processus de gestion en entrepôt des chargements entrants pour les commandes fournisseur.
author: omulvad
manager: tfehr
ms.date: 03/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadTable, WHSLoadPlanningListPage, WHSLoadPlanningWorkbench, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-21
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: fec2e7f39569c52ec17c5d0b2474eca720e0180a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5235338"
---
# <a name="warehouse-handling-of-inbound-loads-for-purchase-orders"></a>Gestion en entrepôt des chargements entrants pour les commandes fournisseur

Cette rubrique décrit le processus de gestion en entrepôt des chargements entrants pour les commandes fournisseur.

Pour chaque chargement entrant, votre système doit déjà inclure une commande client associée, et il peut également contenir une spécification de chargement et/ou un plan de transport associé. Pour plus d’informations sur la création et la gestion des chargements entrants, consultez [Processus entreprise : Planifier le transport pour les chargements entrants](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/business-process-planning-transportation-for-inbound-loads).

## <a name="overview-how-inbound-loads-are-created-registered-and-received"></a>Vue d’ensemble : Procédures de création, d’enregistrement et de réception des chargements entrants

L’illustration suivante présente le flux classique de gestion des chargements entrants avec des quantités de commandes fournisseur à leur arrivée à votre entrepôt.

![Processus de gestion des chargements entrants](media/inbound-process.png "Le processus de gestion du chargement entrant")

1. **Le fournisseur confirme la commande fournisseur.**

    Le processus commence avec la saisie d’une commande fournisseur dans le système et se poursuit avec son envoi à un fournisseur, qui la confirme. La commande fournisseur doit exister avant de pouvoir créer un enregistrement de chargement entrant. Cependant, vous pouvez créer le chargement entrant même si la commande n’a pas été confirmée. Pour en savoir plus, voir [Approuver et passer en revue des commandes fournisseur](../procurement/purchase-order-approval-confirmation.md).

1. **Un enregistrement de chargement entrant est créé pour planifier l’arrivée et son contenu.**

    L’enregistrement de chargement entrant représente l’expédition par le fournisseur d’une ou de plusieurs commandes fournisseur. L’arrivée du chargement est prévue à l’entrepôt sous la forme d’une unité de transport physique (un chargement de camion par exemple). L’enregistrement du chargement entrant est utilisé à des fins de planification et permet au coordinateur logistique de suivre la progression du chargement à partir du fournisseur. Il est également utilisé pour enregistrer les quantités en ligne de commande et gérer la progression via les opérations d’entrepôt, comme l’arrivée et le travail de rangement. Les chargements peuvent être créés automatiquement ou manuellement et ils peuvent être basés sur une commande fournisseur ou un avis préalable d’expédition (APE) du fournisseur. Pour plus d’informations, voir [Création ou modification d’un chargement entrant](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/create-or-modify-an-inbound-load).

1. **Le fournisseur confirme la répartition du chargement.**

    Lorsque le fournisseur répartit le chargement, le coordinateur logistique de l’entrepôt de réception confirme l’expédition du chargement. Si la société destinataire utilise le module **Gestion du transport**, la confirmation de l’expédition entrante déclenche d’autres processus de gestion des chargements associés aux chargements entrants. Pour plus d’informations, voir [Confirmer un chargement pour l’expédition](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/confirm-a-load-for-shipping).

1. **Le chargement arrive à l’entrepôt et les collaborateurs enregistrent les quantités.**

    Lorsqu’un chargement de camion arrive au quai de réception de l’entrepôt, les collaborateurs de l’entrepôt enregistrent les quantités de chargement. En cas d’utilisation du module **Gestion des entrepôts**, les collaborateurs effectuent l’enregistrement via des appareils mobiles. Pour plus d’informations, voir les sections [Accusé de réception de marchandises et commandes fournisseur - Enregistrement](../procurement/product-receipt-against-purchase-orders.md#registration) et [Enregistrer les quantités d’articles sur un chargement entrant](#register-item-quantities-arriving).

1. **Les quantités de chargement enregistrées sont validées par rapport aux commandes fournisseur.**

    Une fois que les quantités de chargement ont été enregistrées à leur arrivée, ces quantités doivent être validées comme reçues dans la comptabilité du stock de l’entreprise pour enregistrer l’augmentation du stock physique. Pour en savoir plus, voir [Accusé de réception de marchandises et commandes fournisseur - Accusé de réception de marchandises](../procurement/product-receipt-against-purchase-orders.md#product-receipt) et [Post-enregistrement des quantités de produits et des commandes fournisseur](#post-registered-quantities).

## <a name="register-item-quantities-that-arrive-on-an-inbound-load"></a><a name="register-item-quantities-arriving"></a>Enregistrer les quantités d’articles sur un chargement entrant

Microsoft Dynamics 365 Supply Chain Management prend en charge plusieurs approches opérationnelles pour l’enregistrement de l’arrivée des produits commandés. Par conséquent, vous pouvez configurer le système pour qu’il corresponde aux besoins spécifiques de votre entreprise. Cette section décrit comment enregistrer les quantités d’articles entrants via un appareil mobile lorsque la gestion avancée des entrepôts est activée dans le système. Vous pouvez néanmoins avoir recours à un autre flux basé sur l’utilisation du journal d’arrivée des articles plutôt que d’un appareil mobile. Pour en savoir plus sur ce flux, voir [Enregistrer des articles pour un article activé pour l’entreposage avancé à l’aide d’un journal des arrivées d’articles](tasks/register-items-advanced-warehousing.md).

Lorsqu’un chargement entrant arrive pour la première fois dans l’entrepôt, les collaborateurs de l’entrepôt doivent enregistrer les quantités d’articles incluses dans l’expédition. En règle générale, ils utilisent des scanners portables. Ce flux de travail n’est disponible que si les éléments suivants sont présents dans le système :

- **Un enregistrement de chargement entrant qui décrit les quantités d’articles prévues dans l’expédition**

    En règle générale, le fournisseur confirme l’enregistrement de chargement entrant avant que l’envoi n’arrive à l’entrepôt. Par conséquent, le chargement est défini sur le statut _Expédié_. Cependant, les collaborateurs au sein de l’entrepôt peuvent également enregistrer les quantités d’articles pour les chargements définis sur statut _Ouvert_ ou _Reçu_.

- **Un menu d’appareil mobile configuré pour prendre en charge la réception du chargement**

    L’[application d’entrepôt](install-configure-warehousing-app.md) pour les appareils mobiles prend en charge les processus de création de travail suivants :

    - Réception des articles du chargement
    - Réception et rangement des articles du chargement
    - La réception de contenants mixtes, où le champ **Méthode d’identification de la ligne de document source** pour l’option de menu de l’appareil mobile est défini sur _Réception des articles du chargement_. Pour plus d’informations, voir [Réception de contenant mixte](mixed-license-plate-receiving.md).
    - La réception et le rangement de contenant mixte, où le champ **Méthode d’identification de la ligne de document source** pour l’option de menu de l’appareil mobile est défini sur _Réception des articles du chargement_. Pour plus d’informations, voir [Réception de contenant mixte](mixed-license-plate-receiving.md).

    > [!NOTE]
    > Quel que soit le processus, le système génère le travail pour prendre les quantités enregistrées dans l’emplacement de réception et les ranger dans l’emplacement de stockage habituel. Lorsque le processus _Réception et rangement des articles du chargement_ ou _Réception et rangement de contenant mixte_ est utilisé, le collaborateur qui a enregistré la quantité de chargement est également invité par l’appareil à exécuter le travail de rangement dans le cadre de la tâche d’enregistrement. En revanche, pour les processus _Réception des articles du chargement_ et _Réception de contenant mixte_, on suppose que le travail de rangement sera effectué séparément de la tâche d’enregistrement.

- **Un modèle de travail qui définit le travail de prélèvement et de rangement pour les chargements entrants**

    Cet article est lié aux articles précédents. Vous devez avoir au moins un modèle de travail pour l’ordre de travail de type _Commande fournisseur_, et il doit contenir un ensemble de type prélèvement/rangement.

L’appareil mobile guide le commis de réception de l’entrepôt dans le cadre du flux pour l’enregistrement de la quantité de chargement. Ce flux inclut au minimum les étapes suivantes pour chaque ID chargement :

1. Saisissez l’ID chargement.
2. Saisissez le numéro d’article pour un article reçu.
3. Saisissez la quantité de ce numéro d’article reçu.
4. Saisissez le numéro de contenant pour l’emplacement initial de l’article, si le système n’est pas configuré pour générer ce numéro automatiquement.
5. Appuyez sur **OK**.

Une fois que le collaborateur a exécuté ces étapes, le système fait les mises à jour suivantes sur les entités appropriées, à condition que la quantité de ligne de commande fournisseur arrivée sur un chargement et toutes les quantités de chargement aient été enregistrées :

| Entité | Mises à jour | Note |
|---|---|---|
| Charger | Le champ **Quantité créée au travail** sur la ligne de chargement est mis à jour pour afficher la quantité enregistrée. | La valeur **état du chargement** reste définie sur _Expédié_ ou _Ouvert_ si aucune confirmation d’expédition n’a été exécutée pour le chargement. Si au moins une ligne de travail de rangement a été commencée, elle est remplacée par _En cours_. |
| Transaction de stock pour une commande fournisseur pour laquelle les quantités de chargement ont été enregistrées |<p>Les champs suivants sont mis à jour :</p><ul><li>Le champ <b>Réception</b> est défini sur <i>Enregistré.</i></li><li>Le champ <b>Emplacement</b> est mis à jour avec le code d’emplacement du quai de réception. (Ce code est spécifié dans le champ <b>Emplacement de réception par défaut</b> pour chaque entrepôt.)</li><li>Le champ <b>Contenant</b> est mis à jour avec le numéro de contenant qui a été entré ou généré lors de l’enregistrement.</li><li>Le champ <b>ID chargement</b> est mis à jour avec le numéro de chargement pour lequel la quantité a été enregistrée. (Voir la remarque.)</li></ul> | La possibilité d’établir un lien entre la transaction de stock de la commande fournisseur et les quantités enregistrées par rapport au chargement a été introduite dans la version 10.0.9 comme fonctionnalité facultative intitulée _Associer les transactions de stock de la commande fournisseur au chargement_. Cette fonctionnalité est particulièrement avantageuse pour les flux opérationnels où une seule commande de marchandises achetées est livrée en plusieurs chargements, ou lorsqu’un chargement contient des quantités pour plusieurs commandes fournisseur. |
| Rangement entrepôt | Le travail est créé selon un modèle de travail pour inviter le collaborateur à déplacer les quantités enregistrées à partir de l’emplacement de réception vers un emplacement de stockage habituel. | Le choix de l’emplacement de stockage est contrôlé par l’instruction d’emplacement Rangement. Si aucune instruction d’emplacement n’a été définie, l’emplacement de rangement sur le travail est vide. |

Notez que les collaborateurs de l’entrepôt peuvent enregistrer la réception d’une commande fournisseur avec un ou plusieurs chargements associés sans utiliser le processus _Réception des articles du chargement_. Les méthodes disponibles sont les suivantes :

- **Sur l’appareil mobile :** Utilisez les processus _Réception de ligne de commande fournisseur_ et _Réception et rangement de la ligne de commande fournisseur_. (S’il existe plusieurs chargements pour la quantité de ligne de commande, le collaborateur ne peut pas utiliser le processus _Réception de ligne de commande fournisseur_. En lieu et place, le collaborateur est invité à utiliser l’action de périphérique associée au processus _Réception des articles du chargement_.)
- **Sur le client :** Utilisez le journal d’arrivée des articles.
- **Sur le client :** Utilisez l’action **Enregistrement** accessible depuis la ligne de commande fournisseur.

> [!NOTE]
> Si l’accusé de réception de la commande fournisseur est enregistré via l’une des méthodes précédentes, aucun lien n’est créé entre la transaction de stock de la commande fournisseur et le chargement, même si la fonctionnalité _Associer les transactions de stock de la commande fournisseur au chargement_ est activée. Il n’existe qu’une seule exception à cette règle : si vous utilisez l’option **Réception de ligne de commande fournisseur** et si un seul chargement est défini sur un statut autre que _Reçu_ pour la ligne de commande.

### <a name="handle-discrepancies-during-registration-of-inbound-load-quantities"></a>Gérer les écarts lors de l’enregistrement des quantités de chargements entrants

Les collaborateurs de l’entrepôt peuvent effectuer un enregistrement de la réception partielle de la quantité du chargement. Chaque réception partielle de la quantité du chargement génère ensuite une transaction de stock distincte dont le statut de réception est défini sur _Enregistré_ pour la quantité enregistrée et l’ID de lot se réfère à la ligne de commande fournisseur d’origine.

#### <a name="load-under-receiving"></a>Réception incomplète du chargement

À l’arrivée d’un chargement, si les quantités d’articles sont inférieures aux quantités indiquées sur l’enregistrement de chargement, le personnel chargé de la réception à l’entrepôt peut travailler directement chez le client pour reconnaître cet écart en réduisant la quantité sur la ligne de chargement afin qu’elle corresponde à la quantité réelle qui est arrivée et qui a été enregistrée.

#### <a name="load-over-receiving"></a><a name="load-over-receiving"></a>Réception excédentaire du chargement

La réception excédentaire se produit lorsqu’un chargement arrive et que les quantités d’articles dépassent la quantité de ligne de chargement prévue. Vous pouvez contrôler si et dans quelle mesure la réception excédentaire est autorisée pendant l’enregistrement du chargement.

Utilisez le champ **Réception excédentaire du chargement** pour que les options de menu de l’appareil mobile appropriés contrôlent ce qui se produit lorsqu’un collaborateur de l’entrepôt essaie d’enregistrer une livraison excédentaire. Ce champ est disponible pour les options de menu de l’appareil mobile qui utilisent les types de processus de création de travail suivants :

- Réception des articles du chargement
- Réception et rangement des articles du chargement
- La réception de contenant mixte (lorsque le champ **Méthode d’identification de la ligne de document source** est défini sur _Réception des articles du chargement_).
- La réception et le rangement de contenant mixte (lorsque le champ **Méthode d’identification de la ligne de document source** est défini sur _Réception des articles du chargement_).

Le tableau suivant décrit les options disponibles pour le champ **Réception excédentaire du chargement**.

| Valeur  | Description |
|---|---|
| Autoriser | Les collaborateurs peuvent enregistrer la réception des quantités qui dépassent la quantité non enregistrée restante pour un chargement sélectionné, mais uniquement si la quantité totale enregistrée ne dépasse pas la quantité de la ligne de la commande fournisseur qui est associée au chargement (après ajustement du pourcentage de livraison excédentaire). |
| Bloquer | <p>Les collaborateurs ne peuvent pas enregistrer la réception de quantités supérieures à la quantité non enregistrée restante pour un chargement sélectionné (ajusté pour le pourcentage de livraison excédentaire). Un collaborateur qui essaie d’enregistrer les réceptions reçoit une erreur et n’est pas en mesure de continuer tant qu’il n’enregistre pas une quantité inférieure ou égale à la quantité de chargement non enregistrée restante.</p><p>Par défaut, la valeur du pourcentage de livraison excédentaire sur la ligne de chargement est copiée depuis la ligne de la commande fournisseur associée. Quand le champ <b>Réception excédentaire du chargement</b> est défini sur <i>Bloquer</i>, le système utilise la valeur de pourcentage de livraison excédentaire pour calculer la quantité totale qui peut être enregistrée pour une ligne de chargement. Cependant, cette valeur peut être modifiée pour des chargements individuels selon les besoins. Ce comportement devient pertinent lorsque la réception de flux où une certaine quantité de l’excédent, ou toute la quantité excédentaire, qui représente le pourcentage de livraison excédentaire de la ligne de commande est répartie de manière disproportionnelle sur différents chargements. Voici un exemple de scénario :</p><ul><li>Il existe plusieurs chargements pour une ligne de commande fournisseur.</li><li>La ligne de commande fournisseur a un pourcentage de livraison excédentaire supérieur à 0 (zéro).</li><li>Des quantités ont déjà été enregistrées pour un ou plusieurs chargements sans tenir compte du pourcentage de livraison excédentaire.</li><li>La quantité de livraisons excédentaires arrive au dernier chargement.</li></ul><p>Dans ce scénario, un appareil mobile peut être utilisé pour enregistrer la quantité excédentaire pour le dernier chargement uniquement si le superviseur de l’entrepôt augmente le pourcentage de livraison excédentaire pour la ligne de chargement pertinente depuis la valeur par défaut vers une valeur suffisamment large pour que la livraison excédentaire complète puisse être enregistrée avec le chargement final.</p> |
| Bloquer pour les chargements clôturés uniquement | Les collaborateurs peuvent recevoir des quantités de ligne de chargement excédentaires pour les chargements ouverts, mais pas pour les chargements avec un statut défini sur _Reçu_. |

> [!NOTE]
> La valeur par défaut du champ **Réception excédentaire du chargement** est _Autoriser_. Lorsque cette valeur est utilisée, le comportement correspond au comportement standard qui était disponible avant la fonctionnalité _Réception excédentaire des quantités du chargement_ a été introduite dans la version 10.0.11.

### <a name="put-away-the-registered-quantities"></a>Ranger les quantités enregistrées

Une fois l’enregistrement exécuté sur l’appareil mobile, l’action _Enregistrement de la réception de la quantité_ met à jour les enregistrements de stock et de l’entrepôt pour indiquer que les quantités sont maintenant à l’emplacement du quai de réception et disponibles pour réservation. Cependant, les opérations d’entrepôt d’une entreprise nécessitent généralement que les quantités soient déplacées du quai de réception vers l’entrepôt régulier, afin que les processus de prélèvement ultérieurs puissent avoir lieu. Les instructions pour le rangement sont capturées dans le travail de rangement qui est généré automatiquement lorsque le chargement entrant est enregistré comme reçu.

Lorsque le collaborateur au sein de l’entrepôt a terminé le travail de rangement, le système enregistre et suit le résultat en mettant à jour plusieurs entités, comme résumé dans le tableau suivant.

| Entité | Mises à jour | Note |
|---|---|---|
| Charger | <p>Les champs suivants sont mis à jour :</p><ul><li>La valeur <b>État du chargement</b> est modifiée et définie sur <i>En cours</i>.</li><li>La valeur <b>Statut du travail</b> est remplacée par <i>100,00 % de travail terminé</i>.</li></ul> | La valeur **État du chargement** a changé et est définie sur _En cours_ lorsque le collaborateur commence la tâche de rangement pour au moins une ligne de travail de rangement. |
| Les transactions de stock de travail pour lesquelles des quantités associées ont été mises de côté | Les champs **Réception** et **Emplacement** et les autres champs pertinents sont mis à jour pour refléter le mouvement de l’emplacement de réception vers l’emplacement de stockage. | La valeur **État de réception** de la transaction de stock de la commande fournisseur reste définie sur _Enregistré_. |
| Rangement entrepôt | La valeur **Statut du travail** est modifiée et définie sur _Fermé_. | |

## <a name="post-registered-product-quantities-against-purchase-orders"></a><a name="post-registered-quantities"></a>Quantités de marchandises post-enregistrées et aux commandes fournisseur

Une fois que les quantités de marchandises entrantes sont enregistrées dans le système, elles sont disponibles pour réservation dans le cadre des ventes et autres opérations internes et externes. Cependant, le système ne met pas encore à jour les comptes de stock (intermédiaires). Cette mise à jour ne peut se produire que lorsque l’équipe d’exploitation valide les réceptions de marchandises enregistrées.

Pour ouvrir une page où ils peuvent valider une réception de marchandises, les membres de l’équipe des opérations peuvent suivre _une_ de ces étapes :

- Ouvrez l’enregistrement de chargement approprié, puis sélectionnez l’action **Accusé de réception de marchandises**.
- Accédez à **Gestion des entrepôts \> Tâches périodiques \> Mettre à jour les accusés de réception de marchandises**, puis, dans le champ **ID chargement**, précisez le chargement à valider.
- Ouvrez la commande fournisseur appropriée, puis sélectionnez l’action **Accusé de réception de marchandises**.
- Accédez à **Approvisionnements \> Commandes fournisseur \> Réception des marchandises \> Validation de la tâche de réception de produits**.

L’action **Accusé de réception de marchandises** disponible sur la page **Chargement** (et sur la page équivalente pour la tâche de mise à jour, la page **Mettre à jour les accusés de réception de marchandises**) peut mettre à jour les quantités de marchandises reçues uniquement sur les quantités de la commande fournisseur dont le statut est défini sur _Enregistré_. Cependant, l’action **Accusé de réception de marchandises** disponible sur la page **Commande fournisseur** peut inclure les quantités dont les deux statuts de traitement sont définis sur _Commandé_ et _Enregistré_. Elle peut également contrôler l’étendue de validation des accusés de réception de marchandises via des paramètres supplémentaires, tels que _Quantité à recevoir maintenant_ et _Quantité et services enregistrés_.

Seules les commandes dont le statut est défini sur _Confirmé_ peuvent voir leurs accusés de réception de marchandises validés. Pour les commandes fournisseur non confirmées, l’action **Accusé de réception de marchandises** apparaît comme non disponible.

### <a name="post-registered-quantities-from-the-load-page"></a>Valider les quantités enregistrées à partir de la page Chargement

Pour accuser réception des marchandises-valider les quantités enregistrées depuis la page **Chargement**, les conditions préalables suivantes doivent être en place :

- Le chargement doit avoir au moins une unité de quantité dont le statut est défini sur _Enregistré_.
- L’état de chargement doit être défini sur _Expédié_.
- La commande fournisseur associée au chargement doit avoir le statut _Confirmé_.

> [!NOTE]
> Si l’état de chargement n’a pas été défini sur _Expédié_, le système confirme automatiquement le chargement avant d’exécuter la mise à jour de l’accusé de réception des marchandises. (L’état du chargement est défini sur _Expédié_ lorsqu’un utilisateur enregistre l’expédition entrante du chargement.)

Pour accuser réception des marchandises-valider les enregistrements d’arrivée associés à un chargement sélectionné, le collaborateur sélectionne l’action **Accusé de réception de marchandises** sur la page **Chargement**. La page ouverte contient les détails clés suivants :

- Le champ **Quantité** dans la section **Paramètres** sur l’onglet **Réglages** affiche la _quantité enregistrée_. Aucune autre option n’est disponible ici.
- La grille sur le raccourci **Vue d’ensemble** répertorie toutes les commandes fournisseur incluses dans le chargement sélectionné.
- La grille sur le raccourci **Lignes** répertorie toutes les lignes de commande qui ont une quantité enregistrée.

> [!NOTE]
> Les quantités pour les lignes de commande qui apparaissent sur l’onglet **Ligne** sont calculées différemment, selon que la fonctionnalité _Autoriser plusieurs accusés de réception de marchandises par chargement_ est disponible et activée dans votre version de Supply Chain Management.
>
> | Version | Calcul |
> |---|---|
> | Les versions antérieures à la version 10.0.10 et les versions plus récentes où la fonctionnalité _Autoriser plusieurs accusés de réception de marchandises par chargement_ n’est pas activée | La quantité de ligne correspond au total de toutes les quantités enregistrées _pour cette ligne de commande fournisseur_, peu importe que l’enregistrement ait été effectué sur plusieurs chargements, indépendamment du chargement, à partir d’un appareil mobile ou du client. |
> | La version 10.0.10 et les versions plus récentes où la fonctionnalité _Autoriser plusieurs accusés de réception de marchandises par chargement_ est activée | La quantité de ligne correspond au total de toutes les quantités enregistrées _pour l’enregistrement du chargement_ à partir duquel l’action **Validation de l’accusé de réception de produits** a été lancée. |

Lorsque l’utilisateur sélectionne **OK** pour confirmer la validation de l’accusé de réception de produits, le système effectue les mises à jour clés suivantes sur les entités appropriées.

| Entité | Mises à jour |
|---|---|
| Transaction de stock de la commande fournisseur pour laquelle les quantités de ligne ont été incluses dans l’étendue de validation | <p>Les champs suivants sont mis à jour (mais notez qu’il y a également plusieurs autres mises à jour) :</p><ul><li>Le champ <b>Réception</b> est défini sur <i>Reçu.</i></li><li>Le champ <b>Date physique</b> est mis à jour avec la date de la validation.</li></ul> |
| Chargement à partir duquel l’utilisateur a validé l’accusé de réception des marchandises | Les mises à jour des chargements dépendent de la version utilisée et du paramètre du champ **Autoriser plusieurs accusés de réception de marchandises par chargement**. Les règles sont décrites dans le tableau qui apparaît plus loin dans cette section. |

Le champ **Autoriser plusieurs accusés de réception de marchandises par chargement** permet aux entreprises de choisir une stratégie d’accusé de réception du chargement entrant. Selon leurs flux opérationnels, les sociétés peuvent choisir d’autoriser ou d’interdire la validation de plusieurs accusés de réception de marchandises pour le même chargement. Nous recommandons que le responsable de la logistique définisse le champ **Autoriser plusieurs accusés de réception de marchandises par chargement** sur l’une des valeurs suivantes :

- **Non** - Sélectionnez cette valeur si les commis de réception d’entrepôt enregistrent toujours toutes les quantités de commande qui arrivent avec chaque chargement dans une période définie. Si des quantités de chargement ne sont pas enregistrées, le système suppose qu’elles ne sont pas arrivées ou qu’elles n’étaient pas dans le chargement et que, par conséquent, elles ne doivent pas être prises en compte dans le chargement. La validation de l’accusé de réception de produits exécutée depuis un chargement utilise la même supposition. Outre l’accusé de réception des marchandises-la mise à jour de toutes les quantités enregistrées (sa fonction principale), elle déclare le chargement complet et fermé pour tout traitement supplémentaire. Dans ce cas, toutes les quantités de ligne de chargement sont automatiquement mises à jour vers les quantités enregistrées, les lignes de chargement qui n’ont pas de quantité enregistrée sont supprimées, et l’état du chargement est modifié et passe sur _Reçu_.
- **Oui** - Sélectionnez cette valeur si les commis de réception d’entrepôt ont besoin de plus de temps pour enregistrer toutes les quantités sur le chargement qui sont arrivées, mais si vous devez, en parallèle, accuser réception des marchandises/valider les quantités déjà enregistrées. Dans ce cas, le responsable logistique souhaite conserver un chargement ouvert même après avoir exécuté la tâche de validation de l’accusé de réception des marchandises, de telle sorte que les quantités de chargement restantes peuvent être enregistrées et l’accusé de réception des marchandises mis à jour en comptabilité sur une base continue.
- **Invite** - Sélectionnez cette valeur si vos pratiques de réception de chargement sont mixtes et si une décision est requise à chaque exécution de la validation de l’accusé de réception des produits.

Le tableau suivant résume les effets du paramètre **Autoriser plusieurs accusés de réception de marchandises par chargement**.

| Autoriser plusieurs accusés de réception de marchandises par chargement | Quantité de chargement | Statut de charge | Note |
|---|---|---|---|
| Lorsque ce champ n’est pas disponible (versions antérieures à 10.0.10) | <p>La quantité de chargement est définie de manière à ce qu’elle soit égale à la quantité enregistrée.</p><p>Si la quantité de chargement est mise à jour sur 0 (zéro), cela signifie qu’aucun enregistrement n’a été effectué, la ligne de chargement est supprimée.</p><p>S’il n’y a pas de lignes de chargement sur le chargement, le chargement est supprimé.</p> | _Reçu(e)_ | S’il existe plusieurs chargements pour la quantité enregistrée de la ligne de commande, seul l’état du chargement à partir duquel l’accusé de réception a été validé est mis à jour sur _Reçu_. |
| N° | <p>La quantité de chargement est définie de manière à ce qu’elle soit égale à la quantité enregistrée associée à l’ID chargement.</p><p>Si aucun ID chargement n’est enregistré pour la transaction de stock, le comportement correspond au comportement dans les versions antérieures à 10.0.10.</p> | _Reçu(e)_ | |
| Oui | Pas de mise à jour | _Reçu_, si la quantité de chargement totale enregistrée est égale ou supérieure à la quantité de chargement | |
| Oui | Pas de mise à jour | _Expédié_ ou _En cours_, si la quantité de chargement totale enregistrée est inférieure à la quantité de chargement | |

Une fois le champ **État du chargement** défini sur _Reçu_, plus aucune validation de réception de produit ne peut être effectuée pour ce chargement. Cependant, le collaborateur peut enregistrer la quantité de commande restante par rapport au chargement reçu dans les conditions suivantes. (Pour plus d’informations, voir la section [Réception excédentaire du chargement](#load-over-receiving) plus haut dans cette rubrique.)

- La version de Supply Chain Management est antérieure à la version 10.0.11.
- La fonctionnalité _Réception excédentaire des quantités de chargement_ est activée, et le champ **Réception excédentaire de quantité en ligne de chargement** sur l’option de menu de l’appareil mobile pour l’action de réception des articles du chargement est défini sur _Autoriser_.

Pour accuser réception de marchandises-valider les quantités de chargement supplémentaires enregistrées par rapport à un chargement défini sur le statut _Reçu_, l’utilisateur doit exécuter l’action de validation à partir de la commande fournisseur associée.

### <a name="post-registered-quantities-from-the-purchase-order-page"></a>Afficher les quantités enregistrées à partir de la page Commande fournisseur

Pour accuser réception des marchandises-valider les quantités enregistrées depuis la page **Commande fournisseur**, l’utilisateur effectue les tâches suivantes avant de sélectionner l’action **Accusé de réception de marchandises** :

- Définissez le champ **Quantité** dans la section **Paramètres** sur l’onglet **Paramètres** sur _Quantité enregistrée_.
- Dans le champ **Accusé de réception de marchandises**, entrez les numéros des commandes fournisseur inclus dans la validation.

> [!NOTE]
> La quantité de ligne incluse dans l’étendue de validation correspond au total de toutes les quantités enregistrées pour la ligne de commande, peu importe que l’enregistrement de la quantité ait été effectué sur plusieurs chargements, indépendamment du chargement, à partir d’un appareil mobile ou du client. La même règle s’applique lorsque la validation de l’accusé de réception des marchandises est exécutée à partir d’un chargement, si cela est effectué lorsque le champ **Autoriser plusieurs accusés de réception de marchandises par chargement** n’est pas disponible ou n’est pas activé.

Lorsque l’utilisateur sélectionne **OK** pour confirmer la validation de l’accusé de réception de produits, le système effectue les mises à jour clés suivantes sur les entités appropriées.

| Entité | Mises à jour |
|---|---|
| Transaction de stock de la commande fournisseur pour laquelle les quantités de ligne ont été incluses dans l’étendue de validation | <p>Les champs suivants sont mis à jour (mais notez qu’il y a également plusieurs autres mises à jour) :</p><ul><li>Le champ <b>Réception</b> est défini sur <i>Reçu.</i></li><li>Le champ <b>Date physique</b> est mis à jour avec la date de l’action de validation de l’accusé de réception des marchandises.</li></ul> |
| Charger | Les mises à jour des chargements varient selon que le champ **Autoriser plusieurs accusés de réception de marchandises par chargement** est disponible et activé. Ces règles sont décrites dans le tableau suivant. |

Le tableau suivant résume les effets du paramètre **Autoriser plusieurs accusés de réception de marchandises par chargement**.

| Autoriser plusieurs accusés de réception de marchandises par chargement | Quantité de chargement | Statut de charge | Note |
|---|---|---|---|
| Lorsque ce champ est désactivé ou non disponible (dans les versions antérieures à 10.0.10) | Pas de mise à jour | Aucune mise à jour n’est effectuée. (Le statut reste _Ouvert_, _Expédié_ ou _En cours_ .) | Puisque la validation de l’accusé de réception des produits est lancée depuis une commande fournisseur, la logique de mise à jour n’a pas d’informations concernant l’association entre les quantités enregistrées dans cette étendue et les chargements par rapport auxquels l’enregistrement était enregistré. Par conséquent, il ne peut pas sélectionner le chargement pour la mise à jour du statut. |
| Activé(e) | Pas de mise à jour | <p>Une des actions suivantes se produit :</p><ul><li>Le statut passe sur <i>Reçu</i> si les quantités totales reçues et achetées des transactions de stock de la commande fournisseur sont supérieures ou égales à la quantité du chargement auquel elles sont associées.</li><li>Le statut reste défini sur <i>Ouvert</i>, <i>Expédié</i> ou <i>En cours</i> si la condition précédente n’est pas remplie pour toutes les lignes de chargement.</li></ul> | |

### <a name="select-the-appropriate-product-receipt-posting-option-for-your-logistics-operations"></a>Sélectionnez l’option de validation de l’accusé de réception des produits appropriée pour vos opérations logistiques

Comme cela a été décrit précédemment, le système propose deux options de validation d’accusé de réception des produits. Les options sont accessibles aux endroits suivants :

- Sur la page **Chargement** ou à partir du menu **Gestion des entrepôts \> Tâches périodiques** comme tâche de mise à jour
- Sur la page **Commande fournisseur** ou à partir du menu **Approvisionnements \> Commandes fournisseur \> Réception des produits** comme tâche de mise à jour

Les entreprises qui utilisent des chargements pour planifier et gérer le transport et la gestion en entrepôt de leurs commandes entrantes sont invitées à utiliser les fonctions suivantes, conçues pour fonctionner avec les chargements :

- Les actions **Réception des articles du chargement** sur les appareils mobiles de leur entrepôt, pour enregistrer l’arrivée de la quantité de produit pour le chargement
- Les actions **Validation de l’accusé de réception de produits** lancées à partir d’un chargement, pour mettre à jour le registre de stock

> [!NOTE]
> D’autres fonctions d’enregistrement de quantité et de validation d’accusé de réception des marchandises peuvent être utilisées pour prendre en charge les processus opérationnels entrants correspondants. Cependant, si vous les utilisez de manière interchangeable avec ou à la place des fonctions dédiées axées sur le chargement, vous risquez de compromettre la précision des données des enregistrements de chargement et donc la fluidité des flux de gestion de chargement.

## <a name="example-scenarios"></a>Exemple de scénarios

### <a name="prepare-your-system-to-run-the-sample-scenarios"></a>Préparer votre système pour exécuter les exemples de scénarios

Pour parcourir les exemples de scénarios décrits dans cette section, vous devez d’abord vous assurer que toutes les fonctionnalités requises sont activées sur votre système. Les données de démonstration requises doivent également être disponibles dans le système.

#### <a name="turn-on-the-required-features"></a>Activer les fonctionnalités requises

Ces scénarios nécessitent la fonctionnalité _Plusieurs validations d’accusé de réception de marchandises par chargement_ et sa fonction préalable. Les administrateurs peuvent activer ces fonctionnalités en suivant ces étapes.

1. Ouvrez l’espace de travail **Gestion des fonctionnalités**. (Pour plus de détails sur la recherche et l’utilisation de cet espace de travail, voir [Présentation de la gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) .)

1. Activez la fonctionnalité _Associer les transactions de stock de la commande fournisseur au chargement_, qui est répertoriée de la manière suivante :

    - **Module :** _Gestion des entrepôts_
    - **Nom de la fonction :** _Associer les transactions de stock de la commande fournisseur au chargement_

1. Activez la fonctionnalité _Plusieurs validations d’accusé de réception de marchandises par chargement_, qui est répertoriée de la manière suivante :

    - **Module :** _Gestion des entrepôts_
    - **Nom de la fonction :** _Plusieurs validations d’accusé de réception de marchandises par chargement_

#### <a name="enable-sample-data"></a>Activer les exemples de données

Pour utiliser ces scénarios à l’aide des exemples d’enregistrements et de valeurs spécifiés, vous devez utiliser un système sur lequel les données de démonstration standard sont installées. Vous devez également sélectionner l’entité juridique **USMF** avant de commencer.

#### <a name="add-a-menu-item-for-receiving-load-items-when-a-mobile-device-is-used"></a>Ajouter un élément de menu pour recevoir des articles de chargement lorsqu’un appareil mobile est utilisé

Avant que les commis de réception d’entrepôt puissent utiliser un appareil mobile pour enregistrer le stock entrant lié à un chargement, vous devez créer une option de menu d’appareil mobile à cet effet.

Dans cette section, vous allez créer une option de menu d’appareil mobile et l’ajouter à un menu existant. Un magasinier peut ensuite sélectionner l’option de menu dans l’application d’entrepôt.

1. Accédez à **Gestion des entrepôts \> Configurer \> Appareil mobile \> Options de menu d’appareil mobile** et assurez-vous que le menu de votre appareil mobile comprend un élément de menu qui présente les paramètres suivants :

    - **Mode :** _Travail_
    - **Processus de création de travail :** _Charger l’élément en réception_
    - **Générer un contenant :** _Oui_

    Vous pouvez laisser tous les autres paramètres à leurs valeurs par défaut.

    ![Paramètres d’option de menu d’appareil mobile](media/inbound-mobile-menu-items.png "Paramètres d’élément de menu d’appareil mobile")

    Pour plus d’informations sur la manière de configurer les options de menu d’appareil mobile, voir [Configurer des appareils mobiles pour le travail en entrepôt](configure-mobile-devices-warehouse.md).

2. Après avoir terminé la configuration de l’option de menu, accédez à **Gestion des entrepôts \> Configurer \> Appareil mobile \> Options de menu d’appareil mobile** et ajoutez-la à la structure du menu pour vos appareils mobiles.

### <a name="example-scenario-1-register-a-load-where-some-items-are-missing"></a>Exemple de scénario 1 : Enregistrer un chargement où certains articles sont manquants

Ce scénario montre comment enregistrer des quantités pour un chargement entrant où toutes les quantités prévues ne sont pas présentes. Il montre ensuite comment valider l’accusé de réception des marchandises pour la commande fournisseur.

#### <a name="create-a-load-to-plan-receipt-of-a-purchase-order"></a>Créer un chargement pour planifier l’accusé de réception d’une commande fournisseur

Dans cette procédure, vous allez créer manuellement une commande fournisseur et un chargement associé. Vous mettrez ensuite à jour le chargement pour simuler qu’il a été expédié par le fournisseur (ce qui met à jour l’état du chargement). Les planificateurs d’entrepôt peuvent ensuite filtrer les chargements selon l’**État du chargement** pour trouver les chargements entrants prévus.

1. Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.
1. Sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer une commande fournisseur**, définissez le champ **Compte fournisseur** sur _1001_.
1. Sélectionnez **OK** pour fermer la boîte de dialogue et créer la commande fournisseur.
1. La nouvelle commande fournisseur comprend déjà une ligne sous **Lignes de commande fournisseur**. Définissez les valeurs suivantes pour cette ligne :

    - **Numéro d’article :** _A0001_
    - **Entrepôt :** _24_
    - **Quantité :** _10_

1. Dans le volet Actions, sous l’onglet **Achats**, sélectionnez **Actions \> Confirmer**. Le statut de la commande est maintenant _Confirmé_.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Actions \> Atelier de planification des chargements**.
1. Sur la page **Atelier de planification des chargements**, dans le volet Actions, sur l’onglet **Offre et demande**, sélectionnez **Ajouter \> Dans un nouveau chargement**.
1. Dans la boîte de dialogue **Affectation des modèles de chargement**, définissez le champ **ID du modèle de chargement** sur _Conteneur de 20_.
1. Sélectionnez **OK** pour fermer la boîte de dialogue et revenir à l’atelier.
1. Dans la section **Chargements**, sélectionnez **ID chargement** pour ouvrir le chargement récemment créé.
1. Passez en revue l’en-tête de chargement et les détails de ligne et observez les points suivants :

    - Sur le raccourci **Chargement**, le champ **État du chargement** est défini sur _Ouvert_.
    - Dans la section **Lignes de chargement**, il y a une seule ligne où le champ **Quantité** est défini sur _10_ et le champ **Quantité créée par le travail** est défini sur _0_ (zéro).

    ![Détails de la charge](media/inbound-load-details.png "Détails de la charge")

1. Dans le volet Actions, sous l’onglet **Expédier et recevoir**, sélectionnez **Confirmer \> Expédition entrante**. Notez que l’**État du chargement** est passé sur _Expédié_.
1. Prenez note de la valeur **ID chargement** afin de pouvoir l’utiliser dans la procédure suivante.

#### <a name="register-receipt-of-the-quantities-that-arrived-on-the-load"></a>Enregistrer l’accusé de réception des quantités arrivées sur le chargement

Lorsque le chargement arrive au quai de réception de l’entrepôt, un réceptionnaire enregistre les quantités de chargement sur un appareil mobile.

1. Utilisez votre appareil mobile pour vous connecter à l’entrepôt 24. (Dans les données de démonstration standard, connectez-vous en utilisant _24_ comme ID d’utilisateur et _1_ comme mot de passe.)
1. Sélectionnez l’option de menu _Réception des articles de chargement_ que vous avez créé pour ce scénario.
1. Suivez les instructions de saisie de données à l’écran pour saisir les valeurs suivantes. (L’ordre peut varier en fonction de l’appareil mobile ou de l’émulateur que vous utilisez.)

    - **Chargement** - Entrez l’ID chargement que vous avez créé à la procédure précédente.
    - **Article** - Entrez _A0001_, qui est l’article prévu pour ce chargement.
    - **Qté** - Entrez _9_ comme la quantité réelle présente sur le chargement. Notez que cette quantité est inférieure à la quantité prévue.

1. Continuez à parcourir le flux de travail, en laissant tous les autres champs vides ou définis sur leurs valeurs par défaut, jusqu’à ce que votre appareil vous informe que le travail est terminé.

La tâche de réception du chargement est maintenant terminée et le commis de réception peut passer à sa prochaine tâche. Cependant, le personnel de réception de l’entrepôt examinera éventuellement l’enregistrement de chargement et pourra voir que la quantité reçue était inférieure à la quantité prévue. Ils effectueront ensuite la procédure suivante en utilisant le client Web.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Dans la liste, recherchez le chargement que vous venez de recevoir. (Vous devez peut-être sélectionner la case **Afficher fermé** pour inclure les chargements entrants dont l’état de chargement est défini sur _Expédié_.) Sélectionnez ensuite le lien dans la colonne **ID chargement** pour ouvrir le chargement.
1. Dans l’enregistrement de chargement, notez que la valeur **État du chargement** reste définie sur _Expédié_, mais la valeur **Quantité créée par le travail** sur la ligne de chargement est devenue _9_.
1. Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.
1. Dans la liste, recherchez l’achat que vous venez de recevoir, puis sélectionnez le lien dans la **Commande fournisseur** pour ouvrir la commande.
\
1. Sur le raccourci **Lignes de commande fournisseur**, sélectionnez **Stock \> Affichage \> Transactions**.
1. Consultez les détails des deux transactions de commande fournisseur. (Vous devrez peut-être personnaliser la page **Transactions de stock** pour voir l’**ID chargement** à la grille.) Vous devriez voir deux transactions :

    - La transaction avec un accusé de réception avec le statut _Enregistré_ représente la quantité d’enregistrement de _9_ qui a été exécutée sur un chargement spécifique à l’aide de l’appareil mobile. L’**ID chargement** est associé à la transaction en question.
    - La transaction qui a un accusé de réception dans _Commandé_ représente la quantité de ligne de commande non enregistrée restante de _1_.

#### <a name="product-receiptpost-the-registered-load-quantities-against-purchase-orders"></a>Accuser réception des marchandises-valider les quantités de produits enregistrées sur les commandes fournisseur

Dans cette procédure, vous accuserez réception des produits-validerez le stock que vous avez enregistré pour un chargement. Par conséquent, le stock reçu et ses coûts connexes seront ajoutés au grand livre général de l’entreprise.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Dans la liste, recherchez le chargement que vous venez de recevoir. (Vous devez peut-être sélectionner la case **Afficher fermé** pour inclure les chargements entrants dont l’état de chargement est défini sur _Expédié_.) Sélectionnez ensuite le lien dans la colonne **ID chargement** pour ouvrir le chargement.
1. Dans le volet Actions, sous l’onglet **Expédier et recevoir**, sélectionnez **Recevoir \> Accusé de réception de marchandises**. Cliquez sur **Oui** si vous êtes invité à confirmer l’action.
1. Dans la boîte de dialogue **Validation de l’accusé de réception de produits**, sur le raccourci **Lignes**, inspectez la grille. Vous devriez voir la ligne de la commande fournisseur pour laquelle la quantité a été enregistrée par rapport au chargement sélectionné.

    > [!NOTE]
    > Dans les versions où a fonctionnalité _Plusieurs validations d’accusé de réception de marchandises par chargement_ n’est pas disponible ou n’est pas activée, la quantité par défaut indiquée dans la grille **Lignes de chargement** sera la quantité totale qui a été enregistrée pour tous les chargements associés à la ligne de commande fournisseur.

1. Sur le raccourci **Vue d’ensemble**, contrôlez le champ **Accusé de réception de marchandises** dans la grille. Notez qu’il s’agit de définir un nombre qui inclut l’ID chargement sélectionné.
1. Sélectionnez **OK** pour valider l’accusé de réception de produits et fermer la boîte de dialogue **Validation de l’accusé de réception de produits**.
1. Vous revenez aux détails du chargement. Notez les points suivants :

    - Le champ **État du chargement** est désormais défini sur _Reçu_.
    - Sur la ligne de chargement, la valeur **Quantité** pour le chargement est passée de _10_ à _9_ pièces pour correspondre à la quantité enregistrée, mais la valeur **Quantité créée par le travail** reste _9_.

Si l’équipe d’achat ne s’attend pas à ce que le fournisseur livre la quantité de commande restante de 1, elle peut clôturer la commande en mettant à jour le reste de la livraison de la ligne sur _0_. Cependant, s’il est rapidement constaté que la pièce manquante est arrivée sur le chargement d’origine, le personnel de l’entrepôt peut effectuer l’une des actions suivantes :

- Enregistrez la quantité pour le même chargement. Dans ce cas, le champ **État du chargement** sera réinitialisé sur _Expédié_, et la valeur **Quantité créée par le travail** sera mise à jour sur _10_. Ce choix est disponible uniquement dans les cas suivants :

    - La fonctionnalité _Réception excédentaire des quantités du chargement_ n’est pas disponible ou n’est pas activée.
    - La fonctionnalité _Réception excédentaire des quantités du chargement_ est disponible et activée, et le champ **Accusé de réception de la quantité excédentaire de la ligne de chargement** est défini sur _Autoriser_.

- Ajoutez la quantité à un nouveau chargement ou au chargement existant et traitez-le de la manière habituelle.
- Enregistrez et/ou recevez la quantité de façon à ne pas impliquer la manipulation de chargement.

### <a name="example-scenario-2-register-quantities-that-arrive-on-multiple-inbound-loads-where-some-items-are-missing"></a>Exemple de scénario 2 : Enregistrer les quantités qui arrivent sur plusieurs chargements entrants où certains articles sont manquants

Dans ce scénario, un envoi entrant lié à une seule ligne de commande fournisseur sera divisée en deux chargements. Par exemple, une ligne de commande fournisseur peut être divisée en plusieurs chargements en raison de contraintes de chargement physiques en termes de poids et/ou volume.

Ce scénario montre également comment traiter plusieurs validations d’accusé de réception de produits pour le même chargement. Vous enregistrerez les quantités qui arrivent sur plusieurs chargements entrants, mais les quantités ne correspondront pas aux quantités prévues. Les mises à jour des coûts qui se produisent via la validation de l’accusé de réception de produits seront effectuées plusieurs fois pour le même chargement.

#### <a name="set-up-load-receiving-policies"></a>Configurer des stratégies de réception de chargement

Dans cette procédure, vous allez activer plusieurs validations d’accusé de réception de marchandises à partir du même chargement.

1. Accédez à **Gestion des entrepôts \> Configuration \> Paramètres de gestion des entrepôts**.
1. Sur l’onglet **Chargements**, définissez **Autoriser plusieurs accusés de réception de marchandises par chargement** sur _Oui_.

#### <a name="create-two-loads-to-plan-receipt-of-a-purchase-order"></a>Créer deux chargements pour planifier l’accusé de réception d’une commande fournisseur

Dans cette procédure, vous allez créer une commande fournisseur et deux chargements. Vous mettrez ensuite à jour manuellement chaque chargement pour simuler qu’il a été expédié par le fournisseur (qui met à jour l’état du chargement). Les planificateurs d’entrepôt peuvent ensuite filtrer les chargements selon l’**État du chargement** pour trouver les chargements entrants prévus.

Vous apprendrez également à définir la ligne de commande afin que vous puissiez recevoir une quantité supérieure de 20 % à la quantité spécifiée pour la ligne.

1. Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.
1. Sélectionnez **Nouveau**.
1. Sur le raccourci **Fournisseur**, définissez le champ **Compte fournisseur** sur _1001_, puis sélectionnez **OK**.
1. Votre nouvelle commande fournisseur est ouverte et comprend une ligne vierge dans la grille **Lignes de commande fournisseur**. Définissez les valeurs suivantes pour cette ligne de commande :

    - **Numéro d’article :** _A0001_
    - **Entrepôt :** _24_
    - **Quantité :** _10_

1. Sur le raccourci **Détails de ligne**, sur l’onglet **Livraison**, définissez le champ **Livraison excédentaire** sur _20_.
1. Dans le volet Actions, sous l’onglet **Achats**, sélectionnez **Actions \> Confirmer**. Le statut de la commande est maintenant _Confirmé_.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, sélectionnez **Actions \> Atelier de planification des chargements**.
1. Sur la page **Atelier de planification des chargements**, dans le volet Actions, sur l’onglet **Offre et demande**, sélectionnez **Ajouter \> Dans un nouveau chargement**.
1. Dans la boîte de dialogue **Affectation des modèles de chargement**, définissez le champ **ID du modèle de chargement** sur _Conteneur de 20_. Sur l’onglet **Détails**, modifiez la valeur **Quantité** de _10_ à _5_ pour ajouter partiellement la quantité de ligne de commande fournisseur.
1. Sélectionnez **OK** pour appliquer vos paramètres et fermer la boîte de dialogue.
1. Répétez les étapes 8 à 10 pour créer un deuxième chargement. Cette fois, le champ **Quantité** doit déjà être défini sur _5_.
1. Sur la page **Atelier de planification des chargements**, dans la grille **Chargements**, sélectionnez la valeur **ID chargement** pour le premier chargement que vous avez créé. La page **Détails du chargement** apparaît et affiche le chargement sélectionné. Procédez comme suit :

    1. Dans le volet Actions, sous l’onglet **Expédier et recevoir**, sélectionnez **Confirmer \> Expédition entrante**.
    1. Notez que la valeur **État du chargement** est passée sur _Expédié_.
    1. Sélectionnez le bouton de fermeture pour revenir sur la page **Atelier de planification des chargements**.

1. Répétez l’étape précédente pour le deuxième chargement que vous avez créé.
1. Prenez note des deux valeurs **ID chargement** qui apparaissent dans la grille **Chargements**.

#### <a name="register-partial-receipt-of-the-quantities-that-arrived-on-the-first-load-and-post-the-registered-load-quantities"></a>Enregistrer la réception partielle des quantités arrivées lors du premier chargement et enregistrer les quantités de chargement enregistrées

Lorsque les chargements arrivent au quai de réception de l’entrepôt, un réceptionnaire enregistre les quantités de chargement sur un appareil mobile. Le stock enregistré lié à un chargement est ensuite actualisé en fonction des coûts dans le grand livre de la société en validant l’accusé de réception des produits de la commande fournisseur, en fonction du chargement.

Cette procédure montre comment un commis récepteur enregistrera les quantités de chargement sur un appareil mobile.

1. Utilisez votre appareil mobile pour vous connecter à l’entrepôt 24. (Dans les données de démonstration standard, connectez-vous en utilisant _24_ comme ID d’utilisateur et _1_ comme mot de passe.)
1. Sélectionnez l’option de menu _Réception des articles de chargement_ que vous avez créé pour ce scénario.
1. Suivez les instructions de saisie de données à l’écran pour saisir les valeurs suivantes. (L’ordre peut varier en fonction de l’appareil mobile ou de l’émulateur que vous utilisez.)

    - **Chargement** - Entrez le premier ID chargement que vous avez créé dans la procédure précédente.
    - **Article** - Entrez _A0001_, qui est l’article prévu pour ce chargement.
    - **Qté** - Entrez _3_. Notez que cette quantité est inférieure à la quantité prévue. Pour ce scénario, imaginez que vous, en tant que commis réceptionnaire, n’avez pas le temps d’enregistrer toutes les quantités pour ce chargement. Plus tard dans cette procédure, vous enregistrerez les pièces restantes en répétant cette étape et en définissant le champ **Qté** sur _2_.

1. Continuez à parcourir le flux de travail, en laissant tous les autres champs vides ou définis sur leurs valeurs par défaut, jusqu’à ce que votre appareil vous informe que le travail est terminé.
1. Dans le client Web, accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Dans la liste, recherchez le chargement que vous venez de recevoir et sélectionnez la valeur **ID chargement** pour ouvrir le chargement. Notez que la valeur **État du chargement** reste _Expédié_, mais la valeur **Quantité créée par le travail** sur la ligne de chargement est devenue _3_.
1. Dans le volet Actions, sous l’onglet **Expédier et recevoir**, sélectionnez **Recevoir \> Accusé de réception de marchandises**. Cliquez sur **Oui** si vous êtes invité à confirmer l’action.
1. Dans la boîte de dialogue **Validation de l’accusé de réception de produits**, passez en revue, mais ne modifiez pas les valeurs affichées, puis sélectionnez **OK**.
1. Vous revenez à la page **Détails du chargement** pour votre chargement sélectionné. Notez les points suivants :

    - Le champ **État du chargement** reste défini sur _Expédié_.
    - Sur la ligne de chargement, la valeur **Quantité** du chargement reste _5_ pièces, ce qui est la quantité de chargement d’origine, et la valeur **Quantité créée par le travail** reste _3_.

1. Terminez l’enregistrement de la quantité restante sur ce chargement en répétant cette procédure. Cependant, à l’étape 3, définissez le champ **Qté** sur _2_.

La tâche de réception pour le premier chargement est maintenant terminée. Deux journaux de réception de produit ont été créés, un pour chacune des deux mises à jour de réception de produit que vous avez exécutées.

#### <a name="register-receipt-of-the-quantities-that-arrived-on-the-second-load-and-account-for-the-overdelivered-quantity"></a>Enregistrer la réception des quantités arrivées au deuxième chargement et tenir compte de la quantité livrée en excédent

Pour ce scénario, le réceptionnaire enregistrera en entrée une quantité qui dépasse la quantité qui existe sur le chargement. La réception excédentaire sera autorisée, car le système est configuré pour autoriser la livraison excédentaire.

1. Utilisez votre appareil mobile pour vous connecter à l’entrepôt 24. (Dans les données de démonstration standard, connectez-vous en utilisant _24_ comme ID d’utilisateur et _1_ comme mot de passe.)
1. Sélectionnez l’option de menu _Réception des articles de chargement_ que vous avez créé pour ce scénario.
1. Suivez les instructions de saisie de données à l’écran pour saisir les valeurs suivantes. (L’ordre peut varier en fonction de l’appareil mobile ou de l’émulateur que vous utilisez.)

    - **Chargement** - Entrez le deuxième ID chargement que vous avez créé précédemment.
    - **Article** - Entrez _A0001_, qui est l’article prévu pour ce chargement.
    - **Qté** - Entrez _7_, qui est la quantité restante que le fournisseur soit autorisé à livrer dans le cadre de la quantité totale de commande de 12 (où 10 est la quantité de commande d’origine et 2 est la quantité de livraison excédentaire autorisée de 20 %). N’oubliez pas que 5 pièces ont déjà été enregistrées pour le premier chargement.

Le deuxième chargement a maintenant été mis à jour avec la quantité de 7 et peut être mis à jour à la réception du produit en fonction de cette quantité.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]