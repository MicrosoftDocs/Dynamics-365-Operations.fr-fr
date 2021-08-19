---
title: Améliorations des cXML d’achat
description: La fonction Améliorations des cXML d’achat s’appuie sur la fonctionnalité de catalogue externe existante, PunchOut, qui est utilisée pour les demandes d’achat.
author: dasani-madipalli
ms.date: 08/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatCXMLParameters, CatCXMLPurchRequest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-08-03
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: d61087d21035e532ad86b6669626f55e8411a6f421bf69f817199e9063417761
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779612"
---
# <a name="purchasing-cxml-enhancements"></a>Améliorations des cXML d’achat

[!include [banner](../includes/banner.md)]

La fonction _Améliorations des cXML d’achat_ s’appuie sur la [fonctionnalité de catalogue externe existante](set-up-external-catalog-for-punchout.md) qui est utilisée pour les demandes d’achat. Cette fonctionnalité existante est connue sous le nom de _PunchOut_. Bien qu’une commande fournisseur ne doive pas nécessairement provenir d’une demande d’achat, il doit y avoir une connexion entre le fournisseur sur une commande fournisseur et les paramètres utilisés pour envoyer le document de commande fournisseur.

## <a name="turn-on-the-purchasing-cxml-enhancements-feature"></a>Activer la fonction Améliorations des cXML d’achat

Pour activer la fonction, ouvrez la page **[Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** et recherchez la fonctionnalité nommée *Améliorations des cXML d’achat*. Sélectionnez la fonctionnalité, puis sélectionnez **Activer maintenant** pour l’activer.

Après avoir activé la fonctionnalité, vous devez configurer les paramètres dans les trois domaines suivants :

- **[Paramètres cXML](#cxml-parameters)** – Utilisez ces paramètres pour configurer certains paramètres globaux de la fonctionnalité pour l’envoi de commandes fournisseur.
- **[Configuration du fournisseur](#vendor-setup)** – Si commerce eXtensible Markup Language (cXML) doit être utilisé par défaut pour toutes les nouvelles commandes fournisseur créées pour un fournisseur, définissez l’option **Envoyer une commande fournisseur via cXML** sur _Oui_ pour ce fournisseur.
- **[Catalogues externes](#external-catalog-setup)** – Utilisez les nouveaux paramètres de **Propriétés de la commande** pour définir le format du document de commande fournisseur et la manière dont il est envoyé.

L’illustration suivante résume cette configuration.

![Zones de configuration des fonctionnalités cXML.](media/cxml-settings-areas.png "Zones de configuration des fonctionnalités cXML")

De plus, vous devez configurer le [Traitement par lots des demandes de commande fournisseur](#po-batch). Ce traitement par lots est utilisé pour envoyer les commandes fournisseur confirmées.

## <a name="set-up-global-cxml-parameters"></a><a name="cxml-parameters"></a>Configurer les paramètres cXML généraux

Utilisez la page **Paramètres cXML** pour définir quelques paramètres généraux qui s’appliquent à la fonctionnalité d’envoi de commande fournisseur.

![Page des paramètres cXML.](media/cxml-parameters.png "Page des paramètres cXML")

Accédez à **Approvisionnements \> Configuration \> Gestion cXML \> Paramètres cXML** et définissez les paramètres suivants :

- **Mode de test cXML** – Ce paramètre global affecte la manière dont les commandes fournisseur sont physiquement envoyées à partir du traitement par lots. Vous devez sélectionner l’une des valeurs suivantes :

    - **Test** – Dans ce mode, le traitement par lots peut être en cours d’exécution et le document XML du message est généré, mais il n’est pas envoyé. Au lieu de cela, il est enregistré sur la demande de commande fournisseur à des fins d’examen. Ce mode est utile lorsque vous êtes dans une implémentation initiale et que vous souhaitez voir comment les données sont entrées dans le message cXML. Vous pouvez également générer des exemples de messages que vous pouvez envoyer aux fournisseurs pour une validation initiale.
    - **Mise en service** – dans ce mode, la fonction utilise les [paramètres de catalogue externe](#external-catalog-setup) pour transmettre physiquement chaque document au fournisseur.

- **Envoyer les mises à jour de la demande d’achat** – Définissez cette option sur *Oui* pour envoyer un message de mise à jour pour les commandes fournisseur. Définissez-la sur *Non* pour empêcher l’envoi du message. La plupart des fournisseurs préfèrent ne pas recevoir de messages de mise à jour. Au lieu de cela, ils exigent que les clients les contactent par téléphone ou par e-mail si une commande fournisseur doit être modifiée. Ce paramètre est un paramètre global et aucun remplacement ne peut être spécifié sur le catalogue externe pour chaque fournisseur. Une commande fournisseur sera marquée comme mise à jour si vous validez une deuxième confirmation sur une commande fournisseur, mais que la première confirmation a déjà été envoyée et a fait l’objet d’un accusé de réception par le fournisseur. S’il y a une deuxième confirmation, mais que la première confirmation n’a pas été envoyée, la deuxième confirmation sera traitée comme un nouveau document. Vous pouvez confirmer une commande fournisseur autant de fois que vous le souhaitez jusqu’à ce qu’une confirmation soit envoyée. La confirmation suivante sera alors traitée comme un message de mise à jour.
- **Envoyer la suppression de la demande d’achat** – Définissez cette option sur *Oui* pour envoyer un message de suppression pour les commandes fournisseur. Définissez-la sur *Non* pour empêcher l’envoi du message. La plupart des fournisseurs préfèrent ne pas recevoir de messages de suppression. Au lieu de cela, ils exigent que les clients les contactent par téléphone ou par e-mail si une commande fournisseur a été envoyée par erreur. Ce paramètre est un paramètre global et aucun remplacement ne peut être spécifié sur le catalogue externe pour chaque fournisseur. Une commande fournisseur sera marquée comme supprimée si vous annulez la commande fournisseur dans Supply Chain Management.
- **Fichier d’archive** – Spécifiez le chemin d’accès du fichier dans lequel vous souhaitez exporter et enregistrer les documents cXML archivés. Le chemin d’accès est utilisé lorsque vous exécutez la fonction de purge à partir de la page **Demande de commande fournisseur**.
- **Max caractères pour la ligne de rue** – Entrez le nombre maximum de caractères pouvant être utilisés dans le champ de rue pour les adresses dans le document cXML. Ce paramètre global affecte tous les fournisseurs sauf si un remplacement est spécifié dans les propriétés du catalogue externe.

## <a name="set-up-vendor-purchase-orders-to-use-cxml"></a><a name="vendor-setup"></a>Configurer les commandes achat fournisseur pour utiliser cXML

Chaque fois que vous confirmez une commande fournisseur où l’option **Envoyer une commande fournisseur via cXML** est définie sur _Oui_, le système génère automatiquement le message cXML et le remet au fournisseur associé à cette commande fournisseur. Il existe deux façons de contrôler cette option pour vos commandes fournisseur :

- Pour configurer un fournisseur afin qu’il utilise automatiquement cXML pour toutes les nouvelles commandes fournisseur créées à partir d’une demande, accédez à **Approvisionnements \> Fournisseurs \>Tous les fournisseurs** et sélectionnez ou créez un fournisseur pour ouvrir sa page de détails. Puis, sur le FastTab **Commande fournisseur par défaut**, définissez l’option **Envoyer une commande fournisseur via cXML** sur _Oui_. Si cXML doit également être utilisé automatiquement pour les nouvelles commandes fournisseur qui ne sont **pas** créées à partir d’une demande, vous devez également définir la propriété de commande **ENABLEMANUALPO** sur _True_ pour le catalogue externe associé, comme décrit dans la section [Définir les propriétés de commande](#set-order-properties) plus loin dans cette rubrique.
- Pour les commandes fournisseurs individuelles, accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur** et sélectionnez ou créez une commande fournisseur pour ouvrir sa page de détails. Passez à la vue **En-tête**, puis sur le FastTab **Configuration**, définissez l’option **Envoyer une commande fournisseur via cXML** au besoin.

![Paramètres par défaut pour les commandes achat fournisseur.](media/cxml-order-defaults.png "Paramètres par défaut pour les commandes achat fournisseur")

## <a name="set-up-an-external-catalog-to-use-cxml"></a><a name="external-catalog-setup"></a>Paramétrage d’un catalogue externe pour utiliser cXML

Sur la page **Catalogues externes**, pour chacun de vos catalogues, vous pouvez configurer la fonctionnalité PunchOut et la fonctionnalité d’envoi des commandes fournisseur. Pour trouver les paramètres appropriés, accédez à **Approvisionnements \> Catalogues \> Catalogues externes**. Commencez par [configurer chaque catalogue comme d’habitude](set-up-external-catalog-for-punchout.md). Ce processus comprend l’affectation d’un fournisseur, la sélection des catégories que le fournisseur est autorisé à fournir et l’activation du catalogue. Configurez ensuite les paramètres supplémentaires décrits dans cette section.

> [!NOTE]
> Lorsque vous confirmez une commande fournisseur qui peut être envoyée via cXML, le système recherche le fournisseur associé à la commande fournisseur, puis trouve le premier catalogue externe actif associé à ce fournisseur. Le système utilise ensuite les paramètres de ce catalogue externe pour envoyer la commande fournisseur. Si plusieurs catalogues externes sont configurés, le système utilise uniquement le premier catalogue externe qu’il trouve, en fonction du fournisseur sur la commande fournisseur. Par conséquent, nous vous recommandons de créer un seul catalogue externe pour chaque fournisseur.

![Paramètres de catalogue externe.](media/cxml-supplier-catalog.png "Paramètres de catalogue externe")

### <a name="set-the-punchout-protocol-type"></a>Définir le type de protocole PunchOut

Sur le FastTab **Général** de la page **Catalogues externes**, définissez le champ **Type de protocole Punchout** sur _cXML_. Cette option sera la seule option disponible, sauf si un partenaire a étendu la fonctionnalité et fournit une option supplémentaire dans l’extension.

Si vous utilisez également le catalogue pour PunchOut, vous devez également [configurer le format du message](set-up-external-catalog-for-punchout.md). Le format de message est utilisé pour établir la connexion avec le fournisseur dans la transaction PunchOut à partir de la demande. Lorsqu’une commande fournisseur est envoyée, les propriétés de la commande seront utilisées pour établir la connexion avec un fournisseur.

### <a name="set-the-order-properties"></a><a name="set-order-properties"></a>Définir les propriétés de commande

La fonction _Améliorations des cXML d’achat_ ajoute un nouveau FastTab **Propriétés de commande** pour les catalogues externes. Ce FastTab fournit une grille dans laquelle vous pouvez définir les propriétés de commande. Il fournit également une barre d’outils. Cette barre d’outils contient les trois boutons suivants que vous pouvez utiliser pour gérer les propriétés de la commande :

- **Propriétés par défaut** – Lorsque vous configurez un nouveau catalogue, sélectionnez ce bouton pour ajouter une collection prédéfinie de propriétés couramment utilisées à la grille.
- **Nouveau** – Ajoutez une nouvelle propriété à la grille.
- **Supprimer** – Supprimez la propriété actuellement sélectionnée de la grille. Si vous supprimez accidentellement une propriété par défaut, sélectionnez **Propriétés par défaut** pour restaurer toutes les propriétés manquantes.

Chaque fois que vous ajoutez une ou plusieurs propriétés à la grille, utilisez la colonne de droite pour spécifier une valeur pour chacune.

Utilisez les propriétés par défaut de la manière suivante :

- **BUYER\_COOKIE** – Ce champ de suivi peut être utilisé pour indiquer des informations spécifiques à votre entreprise. Sauf si vous avez un accord avec le fournisseur sur l’utilisation de cette propriété, cela n’a pas beaucoup de sens lors de l’envoi d’une commande fournisseur. Par conséquent, vous devez le définir sur une valeur simple.
- **DELIVERTO** – Lorsque l’adresse de livraison est inscrite dans le document à partir du commande fournisseur, le champ **Informations de mise en garde** est utilisé pour définir le champ **Livrer à** dans le message XML. Si vous souhaitez que cette valeur soit un nom de demandeur et que vous définissez le champ du demandeur sur l’en-tête de la commande fournisseur, saisissez la valeur _DEMANDEUR_ pour cette propriété, afin que le nom du demandeur soit entré dans le champ **Livrer à** dans le XML. Dans ce cas, l’adresse e-mail principale et le numéro de téléphone qui sont utilisés proviendront du demandeur et non de l’auteur de la commande.
- **DEPLOYMENTMODE** – Définissez cette propriété comme requis par le fournisseur. Les valeurs sont généralement _PRODUCTION_ ou _TEST_. Définissez la valeur en fonction de votre communication avec le fournisseur. Habituellement, elle doit correspondre au système prévu derrière la valeur **ORDERCHECKURL** que le fournisseur indique comme système de test ou de production.
- **FIXEDBILLADDRESSID** – Quand le champ **addressID** dans le message XML est défini, il récupère l’emplacement spécifié sur l’adresse. Si la valeur de l’ID que vous avez communiquée au fournisseur diffère de la valeur de l’adresse pour une raison quelconque, vous pouvez forcer un remplacement en spécifiant la valeur ici. L’hypothèse est que vous n’utiliserez qu’une seule adresse avec le fournisseur et que l’adresse est configurée dans le système du fournisseur. L’adresse de facturation est l’adresse de facturation principale spécifiée pour l’entité juridique dans Supply Chain Management.
- **FIXEDSHIPADDRESSID** – Quand le champ **addressID** dans le message XML est défini, il récupère l’emplacement spécifié sur l’adresse. Si la valeur de l’ID que vous avez communiquée au fournisseur diffère de la valeur de l’adresse pour une raison quelconque, vous pouvez forcer un remplacement en spécifiant la valeur ici. L’hypothèse est que vous n’utiliserez qu’une seule adresse avec le fournisseur et que l’adresse est configurée dans le système du fournisseur. L’adresse de livraison est l’adresse indiquée dans l’en-tête du commande fournisseur. La plupart des fournisseurs n’acceptent que les adresses d’en-tête, pas les adresses de ligne. Bien qu’il existe des champs pour les adresses de ligne dans le XML, ils seront définis sur l’adresse d’en-tête.
- **FROM\_DOMAIN** – Saisissez la valeur utilisée pour envoyer les documents de commande fournisseur. Cette valeur est fournie par votre fournisseur.
- **FROM\_IDENTITY** – Saisissez la valeur utilisée pour envoyer les documents de commande fournisseur. Cette valeur est fournie par votre fournisseur.
- **ORDERCHECKURL** – Saisissez l’URL à laquelle transmettre les documents de commande fournisseur. Cette URL commence par `https://` et est fournie par votre fournisseur.
- **PAYLOAD\_ID** – Entrez une valeur de préfixe pour l’ID de charge utile, comme requis pour les processus métier mis en place pour le fournisseur actuel.
- **SENDER\_DOMAIN** – Saisissez la valeur utilisée pour envoyer les documents de commande fournisseur. Cette valeur est fournie par votre fournisseur.
- **SENDER\_IDENTITY** – Saisissez la valeur utilisée pour envoyer les documents de commande fournisseur. Cette valeur est fournie par votre fournisseur.
- **SHARED\_SECRET** – Saisissez la valeur utilisée pour envoyer les documents de commande fournisseur. Cette valeur est fournie par votre fournisseur.
- **STREETLENGTH** – Entrez un nombre qui représente le nombre maximum de caractères que le vendeur acceptera comme nom de rue. Si une valeur est entrée ici, elle remplace la valeur spécifiée sur la page **Paramètres cXML**. Le système supprimera les sauts de ligne et les espaces pour essayer d’adapter l’adresse standard dans Supply Chain Management au nombre de caractères spécifié ici. Tous les caractères supplémentaires seront tronqués.
- **TO\_DOMAIN** – Saisissez la valeur utilisée pour envoyer les documents de commande fournisseur. Cette valeur est fournie par votre fournisseur.
- **TO\_IDENTITY** – Saisissez la valeur utilisée pour envoyer les documents de commande fournisseur. Cette valeur est fournie par votre fournisseur.
- **USERAGENT** – Entrez une valeur pour identifier le système que vous utilisez. Par exemple, entrez _Dynamics 365 Supply Chain Management_.
- **VERSION** – Entrez un numéro de version cXML, si le fournisseur demande ces informations. La version par défaut est *1.2.008*. Cette version est stable et est acceptée par la plupart des fournisseurs.
- **RESPONSETEXT** – Entrez le texte personnalisé que vous attendez que le fournisseur vous renvoie dans le message de réponse cXML après l’envoi de la commande. De cette manière, le système peut marquer le message comme _Reçu_. Si la réponse ne correspond pas au texte standard ou au texte du client que vous entrez ici, la demande sera marquée comme _Erreur_.
- **RESPONSETEXTSUB** – Définissez cette propriété sur _TRUE_ si vous souhaitez rechercher dans le texte de la réponse du fournisseur les valeurs spécifiées dans le champ **RESPONSETEXT**. Par exemple, le fournisseur peut renvoyer une longue chaîne qui inclut "OK" dans la réponse. Dans ce cas, vous pouvez saisir _OK_ dans le champ **RESPONSETEXT** et définir **RESPONSETESTSUB** sur _TRUE_ pour rechercher "OK" n’importe où dans la réponse. La commande peut alors être définie sur _Reçu_.
- **CONTENTTYPE** – Dans une configuration de catalogue typique, vous n’avez pas à définir cette propriété. Si vous recevez une erreur de serveur 500 du système d’un fournisseur lorsque vous envoyez une commande fournisseur, vous pouvez effectuer des tests en définissant cette propriété sur _FALSE_. Cette valeur modifiera un paramètre dans la requête Web et pourrait activer l’envoi du message pour certaines plates-formes.
- **ENABLEHEADERS** – Définissez cette propriété sur _TRUE_ pour envoyer des en-têtes avec la commande fournisseur. Vous ne devez définir cette propriété que si le fournisseur l’exige. Si vous définissez cette propriété sur _TRUE_, ajoutez des propriétés personnalisées supplémentaires basées sur les noms fournis par le fournisseur et ajoutez-leur le préfixe _H\__. Les exemples typiques incluent **H\_USERID**, **H\_PASSWORD**, **H\_RECEIVERID**, et **H\_ACTIONREQUEST**. Les propriétés personnalisées suivantes sont incluses dans les propriétés par défaut :

    - **H\_USERID** – Si le partenaire commercial vous demande d’envoyer un identifiant d’utilisateur dans le cadre de l’URL pour soumettre une commande fournisseur, entrez la valeur ici.
    - **H\_PASSWORD** – Si le partenaire commercial vous demande d’envoyer un mot de passe dans le cadre de l’URL pour soumettre une commande fournisseur, entrez la valeur ici.

- **ENABLEMANUALPO** – Si cette propriété est définie sur _TRUE_, lorsque les utilisateurs créent manuellement des commandes fournisseur (c’est-à-dire lorsqu’ils ne démarrent pas à partir d’une demande), ces commandes fournisseur hériteront du paramètre de l’option **Envoyer une commande fournisseur via cXML** du vendeur. Si cette propriété n’est pas définie ou si elle est définie sur _FALSE_, l’option **Envoyer une commande fournisseur via cXML** ne sera pas définie sur l’en-tête de la commande fournisseur pour les commandes fournisseur créées manuellement. Pour les commandes fournisseur créées à partir d’une demande d’achat, le paramètre de l’option **Envoyer une commande fournisseur via cXML** est toujours héritée du fournisseur, quel que soit le paramètre de cette propriété. Pour plus d’informations, consultez la section [Configurer les commandes achat fournisseur pour utiliser cXML](#vendor-setup) plus haut dans cette rubrique.
- **PUNCHOUTPOONLY** – Si cette propriété est définie sur _TRUE_, seules les lignes de demande d’achat créées à partir du processus PunchOut définiront l’option **Envoyer une commande fournisseur via cXML** sur l’en-tête de la commande fournisseur. En outre, le type de ligne de demande d’achat de toutes les lignes de la commande fournisseur doit être _Article de catalogue externe_. Sinon, la commande fournisseur cXML ne peut pas être créée.
- **PUNCHOUTSHIPTO** – Si cette propriété est définie sur _TRUE_, l’adresse par défaut de l’entité juridique sera ajoutée au message de demande de configuration PunchOut lorsque l’utilisateur ouvrira un catalogue externe. Cette adresse est ajoutée en tant qu’adresse de **Destinataire**. Les vendeurs utiliseront l’adresse de **Destinataire** pour afficher les prix en fonction de l’emplacement de l’entreprise.
- **TRACEPUNCHOUT** - Définissez cette propriété sur _TRUE_ si vous recevez un message d’erreur lorsque vous essayez d’accéder à un catalogue externe à partir de la demande. Les informations de trace seront ensuite remplies pour les messages **PunchOutSetupRequest** et **PunchOutResponse** envoyés entre Supply Chain Management et le site du fournisseur. Vous pouvez afficher ces informations sur la page **Journal des messages des paniers cXML**, que vous pouvez ouvrir à partir de la page **Configuration du catalogue externe** du catalogue du fournisseur avec lequel vous rencontrez des problèmes. Vous devez définir cette propriété sur _TRUE_ uniquement si vous dépannez, car cela crée une surcharge des performances importante sur la base de données pour chaque PunchOut. Pour plus d’informations, consultez la section [Afficher le journal des messages des paniers cXML pour le catalogue externe PunchOut](#message-log) plus loin dans cette rubrique.
- **REPLACENEWLINE** - Définissez cette propriété sur _TRUE_ si vous rencontrez un problème parce que le système d’un fournisseur envoie un message **PunchOutResponse** qui inclut des caractères de nouvelle ligne (\\n). Ce problème peut se produire si les messages du fournisseur sont analysés via un middleware ou un hub d’approvisionnement. Si vous rencontrez un problème avec une nouvelle configuration de fournisseur, définissez la propriété **TRACEPUNCHOUT** à _TRUE_ pour voir le message **PunchOutResponse** et déterminer si les balises XML sont séparées par des caractères de nouvelle ligne.
- **POCOMMENTS** - Définissez cette propriété sur _TRUE_ si vous souhaitez que le document cXML comprenne des notes jointes à la commande fournisseur dans Supply Chain Management. Le texte de la pièce jointe est inclus dans les commentaires d’en-tête du message de commande fournisseur. Pour plus d’informations sur la manière dont le système sélectionne et traite ces pièces jointes, consultez la section [Joindre des notes à une commande fournisseur ](#attach-po-notes) plus loin dans cette rubrique.
- **VENDCOMMENTS** - Définissez cette propriété sur _TRUE_ si vous souhaitez que le document cXML comprenne des notes jointes à la commande fournisseur dans Supply Chain Management. Le texte de la pièce jointe est inclus dans les commentaires d’en-tête du message de commande fournisseur. Pour plus d’informations sur la manière dont le système sélectionne et traite ces pièces jointes, consultez la section [Joindre des notes à une commande fournisseur](#attach-po-notes).
- **CLEANAMP** – Définissez cette propriété sur _TRUE_ si vous recevez un message d’erreur lorsque vous essayez de faire un PunchOut à un fournisseur et que l’URL de retour du fournisseur contient des esperluettes mal encodées (\&).
- **PUNCHOUTTZ** – Définissez cette propriété sur _TRUE_ si le fournisseur avec lequel vous travaillez utilise la norme de l’Organisation internationale de normalisation (ISO) 8601 pour effectuer une validation spécifique de la date/heure du message de demande PunchOut. Supply Chain Management utilise la date du temps universel coordonné (UTC) dans le message **PunchOutSetupRequest**. Par conséquent, lorsque vous définissez cette propriété sur _TRUE_, *+00:00* est ajouté au format date / heure.
- **WMSADDRESSID** - Définissez cette propriété sur _TRUE_ pour utiliser le numéro de magasin sur l’en-tête de la commande fournisseur comme valeur d’**addressID** dans l’adresse de **Destinataire** de la demande de commande fournisseur envoyée au fournisseur. Si vous définissez une valeur pour la propriété **FIXEDSHIPADDRESSID**, cette valeur-là a la priorité sur cette valeur-ci. Par conséquent, vous devez utiliser l’une ou l’autre des propriétés pour définir la valeur **addressID** dans l’adresse de **Destinataire** du document.
- **PUNCHOUTSHIPTOUSER** - Cette propriété fonctionne avec la propriété **PUNCHOUTSHIPTO**. Si **PUNCHOUTSHIPTO** est réglée sur _TRUE_, l’adresse de la personne morale est récupérée. Si **PUNCHOUTSHIPTOUSER** est définie sur _TRUE_, l’adresse principale de l’utilisateur PunchOut est utilisée à la place de l’adresse de l’entité légale.

### <a name="activate-the-external-catalog"></a>Activer le catalogue externe

Lorsque vous avez terminé de configurer toutes les propriétés et de configurer d’autres paramètres pour votre catalogue externe, revenez au FastTab **Général** de la page **Catalogues externes** et définissez l’option **Active** sur *Oui*.

### <a name="attach-notes-to-a-purchase-order"></a><a name="attach-po-notes"></a>Joindre des notes à une commande fournisseur

Comme mentionné dans la section [Définir les propriétés de commande](#set-order-properties), si vous souhaitez que votre cXML livré inclut le texte des notes jointes à la commande fournisseur et / ou aux enregistrements du fournisseur concernés, vous pouvez définir la propriété **POCOMMENTS** et / ou **VENDCOMMENTS** sur _TRUE_ dans la configuration du catalogue externe. Cette section fournit plus de détails sur la manière dont le système sélectionne et traite ces pièces jointes, si vous les utilisez.

Pour définir les types de notes que le système recherchera, accédez à **Approvisionnements \> Paramétrage \> Écrans \> À partir du paramétrage**. Puis, sur l’onglet **Commande fournisseur**, définissez le champ **Inclure les documents de type** sur le type de note que vous souhaitez pouvoir inclure. Seules les notes textuelles seront incluses, pas les pièces jointes.

![Page Paramétrage d’écran.](media/cxml-form-setup.png "Page Paramétrage d’écran")

Les pièces jointes seront incluses avec une commande fournisseur uniquement si leur champ **Type** est défini sur la valeur que vous sélectionnez dans le champ **Inclure les documents de type**, et si leur champ **Restriction** est défini sur _Externe_. Pour créer, afficher ou modifier les pièces jointes d’une commande fournisseur, accédez à **Approvisionnements \> Toutes les commandes fournisseur**, sélectionnez ou créez une commande fournisseur, puis sélectionnez le bouton **Pièces jointes** (symbole de trombone) dans le coin supérieur droit.

![Note jointe qui est configurée pour être envoyée à un fournisseur.](media/cxml-note-to-vendor.png "Note jointe qui est configurée pour être envoyée à un fournisseur")

## <a name="view-the-cxml-cart-message-log-for-external-catalog-punchout"></a><a name="message-log"></a>Afficher le journal des messages des paniers cXML pour le catalogue externe PunchOut

Lorsque vous définissez le champ **Type de protocole Punchout** sur _cXML_ pour un catalogue externe, le système capturera un journal des messages des paniers qui reviennent des fournisseurs. Ce journal peut être utilisé pour le dépannage et à d’autres fins de données.

Pour ouvrir le journal d’un catalogue externe, sélectionnez le catalogue approprié, puis, dans le volet Actions, sélectionnez **Journal des messages des paniers cXML**. La page **Journal des messages des paniers cXML** affiche une liste des paniers qui ont été retournés, le code XML associé à ces paniers et les lignes qui ont été créées sur la demande d’achat associée.

![Page du journal des messages des paniers cXML.](media/cxml-cart-message-log.png "Page du journal des messages des paniers cXML")

## <a name="set-the-extrinsic-elements-for-external-catalog-punchout"></a>Définir les éléments extrinsèques pour le catalogue externe PunchOut

Lorsque vous définissez le champ **Type de protocole Punchout** sur *cXML* pour un catalogue externe, vous pouvez ajouter des éléments extrinsèques personnalisés qui seront insérés au bon endroit dans le message XML de demande.

Pour ajouter des éléments extrinsèques à un catalogue externe, procédez comme suit.

1. Allez dans **Approvisionnements \> Catalogues \> Catalogues externes**.
1. Sélectionnez le catalogue approprié.
1. Sur le FastTab **Format de message**, dans la section **Extrinsèques**, sélectionnez **Ajouter** pour ajouter une ligne à la grille pour chaque élément extrinsèque que vous souhaitez inclure. Sur chaque ligne, définissez les champs suivants :

    - **Nom** – Entrez un nom pour l’élément. Cette valeur deviendra la valeur de l’attribut de **Nom** pour l’élément XML **Extrinsèque** créé par chaque ligne. Habituellement, vous travaillerez avec votre fournisseur pour convenir du nom de chaque élément extrinsèque.
    - **Valeur** - Sélectionnez une valeur pour l’élément. Cette valeur deviendra la valeur de l’élément XML créé par chaque ligne. Les valeurs disponibles sont les suivantes :

        - **Nom d’utilisateur** – Utilisez le nom de l’utilisateur qui effectue le PunchOut. Ce nom est le nom de connexion pour Supply Chain Management.
        - **E-mail de l’utilisateur** – Utilisez l’adresse e-mail de l’utilisateur qui effectue le PunchOut. Cette adresse est l’adresse que l’utilisateur a définie sur l’onglet **Compte** de la page **Options utilisateur**.
        - **Valeur aléatoire** - Utilisez une valeur aléatoire unique.
        - **Nom complet de l’utilisateur** - Utilisez le nom complet de la personne de contact associée à l’utilisateur qui accède au catalogue externe.
        - **Prénom** - Utilisez le prénom de la personne de contact associée à l’utilisateur qui accède au catalogue externe.
        - **Nom** - Utilisez le nom de famille de la personne de contact associée à l’utilisateur qui accède au catalogue externe.
        - **Numéro de téléphone** - Utilisez le numéro de téléphone principal de la personne de contact associée à l’utilisateur qui accède au catalogue externe.

![Paramètres des éléments extrinsèques.](media/cxml-extrinsics.png "Paramètres des éléments extrinsèques")

L’utilisateur ou l’administrateur ne verra pas les éléments extrinsèques, car ils ne sont ajoutés que lorsque l’utilisateur effectue un PunchOut. Ils seront automatiquement insérés entre les éléments **BuyerCookie** et **BrowserFromPost** dans le message de demande de configuration cXML. Par conséquent, vous n’avez pas à les définir manuellement dans le XML lorsque vous configurez le catalogue externe.

![Éléments extrinsèques ajoutés au XML.](media/cxml-extrinsics-xml.png "Éléments extrinsèques ajoutés au XML")

## <a name="create-and-process-a-purchase-order"></a><a name="create-po"></a>Créer et traiter une commande fournisseur

Lorsque vous créez une commande fournisseur pour un fournisseur, celle-ci hérite du paramètre de l’option **Envoyer une commande fournisseur via cXML** de ce fournisseur. Cependant, le paramètre reste disponible sur le FastTab **Paramétrage** dans la vue **Entête** de la commande fournisseur, afin que vous puissiez le modifier ultérieurement si nécessaire.

![Commande fournisseur configurée pour utiliser cXML.](media/cxml-purchase-order.png "Commande fournisseur configurée pour utiliser cXML")

Lorsque vous créez une commande fournisseur à partir d’une demande d’achat provenant d’un flux PunchOut, tous les détails de ligne requis sont renseignés. Vous pouvez ensuite ajouter manuellement des lignes de commande fournisseur ou les copier à partir d’autres commandes fournisseur. Assurez-vous de définir tous les champs obligatoires. Ces champs obligatoires incluent le numéro de référence externe, qui est le numéro de fournisseur qui sera utilisé dans le message cXML.

![Exemple de numéro de référence externe.](media/cxml-line-details.png "Exemple de numéro de référence externe")

Lorsque vous avez terminé de remplir tous les détails de la commande fournisseur, assurez-vous de la confirmer. Aucun message n’est envoyé tant que la commande fournisseur n’est pas confirmée. Pour confirmer la commande fournisseur, dans le volet Actions, sous l’onglet **Achats**, dans le groupe **Actions**, cliquez sur **Confirmer**. 

Une fois la commande fournisseur confirmée, vous pouvez afficher le statut de la confirmation via les journaux **Confirmations des commandes fournisseur**. Dans le volet Actions, sous l’onglet **Achats**, dans le groupe **Journaux**, cliquez sur **Confirmations des commandes fournisseur**.

Chaque commande fournisseur peut avoir de nombreuses confirmations. Chaque confirmation est marquée d’un numéro incrémentiel. Dans l’illustration suivante, la commande fournisseur est *00000275*, et la confirmation est *00000275-1*. Cette numérotation reflète la fonctionnalité standard de Supply Chain Management, dans laquelle les modifications d’une commande fournisseur, et par conséquent le type de message cXML qui doit être envoyé au fournisseur, sont identifiées en fonction de la confirmation. Comme le montre l’illustration, la page **Confirmations des commandes fournisseur** comprend également les champs **Statut d’envoi de la commande** et **Statut du fournisseur de la demande de commande**. Pour plus d’informations sur les différentes valeurs de statut que vous pouvez voir sur cette page, consultez la section [Surveiller les demandes de commande fournisseur](#monitor-po-requests) plus loin dans cette rubrique.

![Page Confirmations de commande fournisseur.](media/cxml-po-confirmations.png "Page Confirmations de commande fournisseur")

Pour afficher plus d’informations sur le document, sélectionnez **Demande de commande fournisseur** au-dessus de la grille.

La page **Demande de commande fournisseur** comprend deux grilles. La grille dans la partie supérieure de la page contient un enregistrement de chaque commande fournisseur marquée pour l’envoi. La grille sur l’onglet **Historique des demandes de commande fournisseur** dans la partie inférieure de la page peut avoir plusieurs enregistrements pour la commande fournisseur sélectionnée, pour indiquer le statut de chaque confirmation. L’illustration suivante montre la commande fournisseur 00000275 dans la grille supérieure et le document 00000275-1 dans la grille sur l’onglet **Historique des demandes de commande fournisseur**.

![Page Demande de commande fournisseur.](media/cxml-po-request.png "Page Demande de commande fournisseur")

Si le traitement par lots est configuré et en cours d’exécution, le document sera envoyé. Vous pouvez afficher le changement de statut une fois le document envoyé. Dans l’illustration suivante, le champ **Statut d’envoi de la commande** est défini sur _Envoyé_. Le champ **Statut du fournisseur de la demande de commande** est défini sur _Reçu_ pour indiquer que le fournisseur a reçu le document, qu’il a pu le lire et le stocker dans son système. La grille sur l’onglet **Historique des demandes de commande fournisseur** affiche l’heure à laquelle le document a été envoyé. Pour plus d’informations sur les différentes valeurs de statut que vous pouvez voir sur cette page, consultez la section [Surveiller les demandes de commande fournisseur](#monitor-po-requests).

![Messages de statut sur la page Demande de commande fournisseur.](media/cxml-po-request-2.png "Messages de statut sur la page Demande de commande fournisseur")

## <a name="schedule-the-purchase-order-request-batch-job"></a><a name="po-batch"></a>Planifier le traitement par lots de demande de commande fournisseur

Pour activer le traitement par lots pour l’envoi des demandes de commande fournisseur, accédez à **Approvisionnement \> Paramétrage \> Gestion cXML \> Demande de commande fournisseur**, puis, dans le volet Actions, sur l’onglet **Demande de commande fournisseur**, dans le groupe **Traitement par lots**, sélectionnez **Envoyer le travail** pour ouvrir la boîte de dialogue **Préparer et envoyer une demande d’achat**. Vous pouvez utiliser cette boîte de dialogue pour configurer la récurrence, comme vous le faites habituellement pour les traitements par lots dans Supply Chain Management. Sélectionnez un intervalle en fonction du volume de vos commandes. Bien que vous puissiez exécuter le traitement par lots toutes les minutes, il est probablement préférable d’envoyer des lots tout au long de la journée ouvrable, en fonction des fenêtres de réception de commande qui correspondent aux horaires de vos fournisseurs.

Par exemple, votre fournisseur a une politique qui stipule que toutes les commandes reçues pour 13 h seront expédiées le même jour. Dans ce cas, vous devrez peut-être exécuter le traitement par lots seulement quelques fois au cours de la matinée pour communiquer les commandes que vous avez. Les commandes restantes seront ensuite envoyées le lendemain. Cette décision est une décision purement commerciale. Vous pouvez la réexaminer et définir les paramètres en conséquence.

Le processus recherchera les documents de demande de commande fournisseur dont le statut est *En attente*. Si vous avez une commande que vous devez envoyer immédiatement à un fournisseur, vous pouvez sélectionner **Envoyer le travail** et définir l’option **Traitement par lots** sur *Non*.

## <a name="monitor-purchase-order-requests"></a><a name="monitor-po-requests"></a>Surveiller les demandes de commande fournisseur

### <a name="view-the-status-of-a-purchase-order"></a>Permet d’afficher le statut d’une commande fournisseur

Lorsque les commandes pouvant être envoyées via cXML sont confirmées, elles passent au statut _En attente_. Comme décrit dans la section [Créer et traiter une commande fournisseur](#create-po), vous pouvez afficher le statut de la commande fournisseur sur la page **Demande de commande fournisseur**. Chaque demande de commande fournisseur peut avoir l’un des statuts, selon ses paramètres et ses données. Cette section décrit les différents types de statut et les valeurs qu’ils peuvent avoir. Ces informations peuvent vous aider à gérer les problèmes et à comprendre le statut de vos commandes fournisseur.

![Statut de la commande fournisseur sur la page Demande de commande fournisseur.](media/cxml-monitor-po-request.png "Statut de la commande fournisseur sur la page Demande de commande fournisseur")

La grille dans la partie supérieure de la page **Demande de commande fournisseur** peut afficher les valeurs de statut suivantes :

- **Statut d’envoi de la commande** – Ce champ peut avoir l’une des valeurs suivantes :

    - **En attente** - Le document attend d’être envoyé.
    - **Envoyé** - Le document a été envoyé.
    - **Arrêté** - Le document a été marqué comme _Arrêté_ avant qu’il ne soit envoyé. (Pour marquer un document comme _Arrêté_, sélectionnez **Arrêter** sur le volet Actions de la page **Demande d’achat**.)
    - **Archive** - Le document a été vidé. (Pour vider un document, sélectionnez **Vider** sur le volet Actions de la page **Demande d’achat**.)

- **Statut du fournisseur de la demande de commande** – Ce champ peut avoir l’une des valeurs suivantes :

    - **En attente** - Le document attend d’être envoyé.
    - **Reçu** - Le document a fait l’objet d’un accusé de réception par le fournisseur. Vous pouvez consulter le message XML détaillé renvoyé par le fournisseur en sélectionnant l’onglet **XML de réponse** dans la partie inférieure de la page.
    - **Erreur** - Le document a été envoyé au fournisseur, mais une erreur s’est produite. Vous pouvez consulter le message d’erreur en sélectionnant l’onglet **XML de réponse** dans la partie inférieure de la page.

La grille sur l’onglet **Historique des demandes de commande fournisseur** dans la partie inférieure de la page **Demande de commande fournisseur** peut afficher les valeurs suivantes :

- **Type de demande de commande** – Ce champ peut avoir l’une des valeurs suivantes :

    - **Nouveau** - La ligne est marquée comme nouvelle immédiatement après la confirmation de la commande fournisseur.
    - **Mise à jour** - Si une confirmation a déjà été envoyée et a fait l’objet d’un accusé de réception par le fournisseur, la prochaine confirmation sera marquée comme _Mise à jour_. Les mises à jour ne seront envoyées que si l’option **Envoyer les mises à jour de la demande d’achat** est définie sur *Oui* dans les [paramètres cXML globaux](#cxml-parameters).
    - **Suppression** - Si une confirmation a déjà été envoyée et a fait l’objet d’un accusé de réception par le fournisseur, mais que la commande fournisseur est annulée, la confirmation en attente sera marquée comme _Suppression_. Les suppressions ne seront envoyées que si l’option **Envoyer les suppression de la demande d’achat** est définie sur *Oui* dans les [paramètres cXML globaux](#cxml-parameters).

- **Heure de demande** - L’heure à laquelle la confirmation de commande a été créée. Vous pouvez comparer l’heure de la demande avec l’heure du statut de la commande pour déterminer le temps entre la confirmation et l’accusé de réception du fournisseur.
- **Statut d’envoi de la commande** - Ce champ est le même que le champ **Statut d’envoi de la commande** dans la partie supérieure de la page. Il est répété ici pour faciliter l’affichage du statut au niveau de la confirmation. Si le champ **Type de demande de commande** est défini sur *Nouveau*, et la commande fournisseur est reconfirmée avant l’envoi d’une confirmation, le champ **Statut d’envoi de la commande** est défini sur *Archive*.
- **Heure du statut de la commande** - L’heure de la dernière mise à jour de l’enregistrement de l’historique des demandes de commande fournisseur. (Les mises à jour incluent les changements de statut.)
- **Statut du fournisseur de la demande de commande** - Ce champ est le même que le champ **Statut du fournisseur de la demande de commande** dans la partie supérieure de la page. Il est répété ici pour faciliter l’affichage du statut au niveau de la confirmation.
- **Heure de renvoi** - L’heure à laquelle l’enregistrement a été envoyé de nouveau.
- **Nombre de renvois** - Le nombre de fois que l’enregistrement a été envoyé de nouveau. Un nombre élevé indique plusieurs échecs et peut donc indiquer un problème avec la configuration de vos données ou la configuration des données de votre fournisseur.

### <a name="view-the-xml-for-a-purchase-order-request-message"></a>Afficher le code XML d’un message de demande de commande fournisseur

Pour afficher le code XML du message de demande de commande fournisseur, sélectionnez l’onglet **Texte XML de demande** en bas de la page **Demande de commande fournisseur**. Les informations de cet onglet peuvent être utiles lors des tests ou de la validation des erreurs. Pour faciliter la lecture des informations, vous pouvez les afficher sous forme de message formaté. Copiez le contenu de l’onglet dans un fichier texte, puis affichez-le dans un éditeur XML.

![Onglet Texte XML de demande.](media/cxml-request-xml-text.png "Onglet Texte XML de demande")

### <a name="view-the-details-of-the-vendor-response"></a>Afficher les détails de la réponse du fournisseur

Pour afficher le contenu d’un accusé de réception ou d’une réponse d’erreur du fournisseur, sélectionnez l’onglet **Réponse XML** onglet en bas de la page **Demande de commande fournisseur**.

![Onglet Réponse XML.](media/cxml-response-xml.png "Onglet Réponse XML")

## <a name="additional-resources"></a>Ressources supplémentaires

- [Paramétrer un catalogue externe pour PunchOut e-procurement](set-up-external-catalog-for-punchout.md)
- [Utiliser des catalogues externes pour PunchOut eProcurement](use-external-catalogs-for-punchout.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]