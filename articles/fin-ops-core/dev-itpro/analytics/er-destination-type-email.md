---
title: Type de destination pour l’envoi d’états électroniques par e-mail
description: Cette rubrique explique comment configurer une destination d’e-mail pour chaque composant DOSSIER ou FICHIER d’un format de gestion des états électroniques.
author: NickSelin
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: dc89e7ff43e5df358f6d41bd295e981c883085bc
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2021
ms.locfileid: "7595201"
---
# <a name="email-er-destination-type"></a>Type de destination pour l’envoi d’états électroniques par e-mail

[!include [banner](../includes/banner.md)]

Lors de l’exécution d’un format de la génération d’états électronique (ER), un ou plusieurs documents sortants peuvent être générés. Les composants de format **Dossier** ou **Fichier** sont utilisés dans les formats ER pour spécifier la structure des documents sortants. Vous pouvez configurer une destination d’e-mail pour ces types de composants afin d’envoyer des documents sortants sous forme de pièces jointes à un e-mail.

Vous pouvez configurer une destination d’e-mail pour chaque composant **Dossier** ou **Fichier** d’un format ER. Dans ce cas, **chaque document sortant est envoyé par e-mail individuellement**. En fonction de ce paramètre de destination, un document généré est remis en tant que pièce jointe d’un e-mail. 

> [!NOTE]
> Si aucun document n’est généré, car l’expression **Activée** du composant **Fichier** pertinent a été configuré pour renvoyer une valeur booléenne **Faux**, aucun e-mail n’est envoyé, même si une destination d’e-mail est configurée et activée pour le composant.

Vous pouvez aussi [grouper](#grouping) de nombreux composants **Dossier** ou **Fichier** ensemble, puis configurer une destination d’e-mail pour tous les composants du groupe. Dans ce cas, tous les documents sortants générés par des composants appartenant au groupe **sont envoyés sous forme de pièces jointes multiples d’un même e-mail**. En fonction de ce paramètre de destination, chaque document généré est remis en tant que pièce jointe d’un seul e-mail.

> [!NOTE]
> Si au moins un document est généré par un composant **Fichier** dans un groupe de composants, un e-mail est envoyé. Si aucun document n’est généré par des groupés composants, car l’expression **Activée** de chaque composant **Fichier** pertinent a été configuré pour renvoyer une valeur booléenne **Faux**, aucun e-mail n’est envoyé, même si une destination d’e-mail est configurée et activée pour le groupe de composants.
>
> **E-mail** est la seule destination pouvant être configurée pour un groupe de composants. Pour remettre un document envoyé par e-mail en fonction du paramètre de destination de l’e-mail d’un groupe, ajoutez un autre enregistrement de destination, sélectionnez le composant souhaité, puis configurez une autre destination pour cet enregistrement.

Plusieurs groupes de composants peuvent être configurés pour une configuration de format ER unique. De cette manière, vous pouvez configurer une destination d’e-mail pour chaque groupe de composants et une destination d’e-mail pour chaque composant.

## <a name="enable-an-email-destination"></a>Activer une destination de l’e-mail

Pour envoyer un ou plusieurs fichiers de sortie par e-mail, procédez comme suit.

1. Sur la page **Destination de la gestion des états électroniques**, dans le raccourci **Destination du fichier**, sélectionnez un composant ou un groupe de composants dans la grille.
2. Sélectionnez **Paramètres**, puis, dans la boîte de dialogue **Paramètres de destination**, dans l’onglet **E-mail**, définissez l’option **Activé** sur **Oui**.

[![Définition de l’option Activé sur Oui pour une destination d'e-mail.](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)

## <a name="configure-an-email-destination"></a>Configurer une destination d’e-mail

### <a name="email-content"></a>Contenu de l'e-mail

Vous pouvez modifier l'objet et le corps du message électronique.

Dans le champ **Objet**, saisissez le texte de l'objet de l'e-mail qui doit apparaître dans le champ objet d'un message électronique généré lors de l'exécution. Dans le champ **Corps**, saisissez le texte du corps de l'e-mail qui doit apparaître dans le champ corps d'un message électronique. Vous pouvez paramétrer un texte constant pour l’objet et le corps du courrier électronique, ou vous pouvez utiliser des [formules](er-formula-language.md) de gestion des états électroniques pour créer dynamiquement le texte du courrier électronique lors de l'exécution. La formule configurée doit renvoyer une valeur de type [Chaîne](er-formula-supported-data-types-primitive.md#string).

Le corps de votre email est composé au format TEXTE ou HTML, selon le client de messagerie. Vous pouvez utiliser n’importe quelle mise en page, style et image de marque pris en charge par le format HTML et les feuilles de style en cascade en ligne (CSS).

> [!NOTE]
> Les clients de messagerie imposent des restrictions de mise en page et de style qui pourraient nécessiter des ajustements du HTML et du CSS que vous utilisez pour le corps du message. Nous vous recommandons de vous familiariser avec les meilleures pratiques de création de code HTML que les clients de messagerie les plus populaires prendront en charge.
>
> Utilisez le codage correct pour implémenter un retour chariot, en fonction de la mise en forme du corps. Pour plus d'informations, voir la définition du type de données [Chaîne](er-formula-supported-data-types-primitive.md#string).

### <a name="email-addresses"></a>Adresses e-mail

Vous pouvez spécifier l’expéditeur et les destinataires de l’e-mail. Par défaut, l'e-mail est envoyé au nom de l’utilisateur actuel. Pour spécifier un autre expéditeur d’e-mail, vous devez configurer le champ **De**.

> [!NOTE]
> Lorsqu’une destination de courrier électronique est configurée, le champ **De** n’est visible que pour les utilisateurs qui ont le privilège de sécurité `ERFormatDestinationSenderEmailConfigure` **Configurer l’adresse e-mail de l’expéditeur pour les destinations au format ER**.
>
> Lorsqu’une destination de courrier électronique est proposée pour modification au moment de l’[exécution](electronic-reporting-destinations.md#security-considerations), le champ **De** n’est visible que pour les utilisateurs qui ont le privilège de sécurité `ERFormatDestinationSenderEmailMaintain` **Gérer l’adresse e-mail de l’expéditeur pour la destination au format ER**.
>
> Lorsque le champ **De** est configuré pour utiliser une adresse e-mail autre que celle de l’utilisateur actuel, l’autorisation **Envoyer en tant que** ou **Envoyer pour le compte de** doit être correctement [définie](/microsoft-365/solutions/allow-members-to-send-as-or-send-on-behalf-of-group) à l’avance. Sinon, l’exception suivante est générée au moment de l’exécution : « Impossible d’envoyer l’e-mail en tant que \<from email account\> depuis le compte \<current user account\>, veuillez vérifier les autorisations « Envoyer en tant que » sur le \<from email account\>. »

Vous pouvez configurer le champ **De** pour renvoyer plusieurs adresses e-mail. Dans ce cas, la première adresse de la liste est utilisée comme adresse d’expéditeur de courrier électronique.

Pour spécifier les destinataires des e-mails, vous devez configurer les champs **À** et **Cc** (facultatifs).

Vous pouvez configurer les adresses électroniques pour les états électroniques de deux manières. La configuration peut être effectuée de la même manière que pour la fonction Gestion de l’impression, ou vous pouvez résoudre une adresse e-mail en utilisant une référence directe à la configuration ER par le biais d’une formule.

## <a name="email-address-types"></a>Types d’adresses électroniques

Si vous sélectionnez **Modifier** à côté du champ **De**, **À** ou **Cc** dans la boîte de dialogue **Paramètres de destination**, la boîte de dialogue **E-mail de**, **E-mail à** ou **Copie de l’e-mail** appropriée apparaît. Là, vous pouvez configurer l’expéditeur et les destinataires de l’e-mail. Sélectionnez **Ajouter**, puis sélectionnez le type d’adresse électronique à utiliser. Deux types sont actuellement pris en charge : **E-mail de configuration de l’impression** et **E-mail de configuration**.

[![Sélection du type d’adresse e-mail.](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)

### <a name="print-management-email"></a>E-mail de gestion de l'impression

Si vous sélectionnez **E-mail de gestion de l’impression** comme type d’adresse e-mail, vous pouvez saisir des adresses e-mail fixes dans la boîte de dialogue **E-mail de**, **E-mail à** ou **Copie de l’e-mail** en définissant les champs suivants :

- Sélectionnez le champ **Source du message électronique**, puis **Aucune**.
- Dans le champ **Adresses e-mail supplémentaires, séparées par ";"**, entrez les adresses e-mail fixes.

Vous pouvez également obtenir des adresses électroniques à partir des coordonnées du tiers pour lequel vous générez un document sortant. Pour utiliser des adresses électroniques non fixes dans el champ **Source de l’e-mail**, vous devez sélectionner le [rôle](../../fin-ops/organization-administration/overview-global-address-book.md#party-roles) du tiers pour une destination de fichier. Les rôles suivants sont pris en charge :

- Client
- Fournisseur
- Prosp
- Contact
- Concurrent
- Collaborateur
- Candidat
- Fournisseur potentiel
- Fournisseur non autorisé
- Entité juridique

Par exemple, pour configurer une destination de courrier électronique pour un format ER utilisé pour traiter les paiements fournisseur, sélectionnez le rôle **Fournisseur**.

Après avoir sélectionné le rôle souhaité, sélectionnez le bouton **Lier** (symbole de chaîne) à côté du champ **Compte source de messagerie** pour ouvrir la page [Concepteur de formule](general-electronic-reporting-formula-designer.md). Vous pouvez ensuite utiliser cette page pour configurer une formule qui renvoie, au moment de l’exécution, le numéro de compte de la partie affectée au rôle configuré du document traité à la destination de l’e-mail.

> [!NOTE]
> Les formules sont spécifiques à la configuration de l’état électronique.

Sur la page **Concepteur de formule**, dans le champ **Formule**, entrez une référence spécifique au document à un rôle pris en charge. Au lieu de taper la référence, dans le volet **Source de données**, recherchez et sélectionnez le nœud de source de données qui représente un compte du rôle configuré, puis sélectionnez **Ajouter une source de données** pour mettre à jour la formule. Par exemple, si vous configurez la destination de l’e-mail pour la configuration **Transfert de crédit ISO 20022** utilisée pour traiter les paiements fournisseur, le nœud qui représente un compte fournisseur est `'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.

![Configuration d’un compte source de messagerie.](./media/er_destinations-emaildefineaddresssource.gif)

Si les numéros de compte du rôle configuré sont uniques pour toute l’instance de Microsoft Dynamics 365 Finance, le champ **Entreprise de la source de l’e-mail** dans la boîte de dialogue **Envoyer à** peut rester vide.

Sinon, vous pourriez avoir une situation où différents tiers dans le [Carnet d’adresses global](../../fin-ops/organization-administration/overview-global-address-book.md) ont été enregistrés dans différentes sociétés ([entités juridiques](../../fin-ops/organization-administration/organizations-organizational-hierarchies.md#legal-entities)) de telle manière qu’ils utilisent tous le même numéro de compte pour remplir le rôle configuré. Dans ce cas, les numéros de compte du rôle configuré ne sont pas uniques pour l’ensemble de l’instance Finance. Par conséquent, pour sélectionner explicitement un tiers, vous ne pouvez pas spécifier uniquement un numéro de compte. Vous devez également spécifier la société dans laquelle le tiers a été enregistré pour remplir le rôle configuré. Sélectionnez le rôle souhaité, sélectionnez le bouton **Lier** (symbole de chaîne) à côté du champ **Société de la source de messagerie** dans la boîte de dialogue **E-mail à** pour ouvrir la page [Concepteur de formule](general-electronic-reporting-formula-designer.md). Vous pouvez ensuite utiliser cette page pour configurer une formule qui renvoie, au moment de l’exécution, le code de la société dont la source souhaitée doit se trouver dans le périmètre.

> [!TIP]
> Si vous devez utiliser le code société pour exécuter un format ER, mais que le format ER ne fournit aucune source de données à partir de laquelle le code société peut être obtenu, configurez la formule `GetCurrentCompany()` en utilisant la fonction ER [GETCURRENTCOMPANY](er-functions-other-getcurrentcompany.md) intégrée.

> [!NOTE]
> Les formules sont spécifiques à la configuration de l’état électronique.

Pour spécifier le type d’adresses e-mail à utiliser lors du runtime, dans la boîte de dialogue **E-mail à**, sélectionnez **Modifier** à côté du champ **À** pour ouvrir la boîte de dialogue déroulante **Attribuer une adresse e-mail**. Définissez ensuite les champs suivants :

- Dans le champ **Objet**, sélectionnez les objets souhaités. Seules les adresses e-mail des objets sélectionnés provenant des contacts du tiers détecté seront utilisées.
- Définissez l’option **Contact principal** pour **Oui** pour utiliser une adresse e-mail configurée pour le tiers détecté comme adresse e-mail principale.

> [!NOTE]
> Si des objectifs sont sélectionnés dans le champ **Objectif** et que l’option **Contact principal** est définie sur **Oui** en même temps, chaque e-mail qui satisfait au moins un critère configuré sera utilisé lors de l’exécution.

### <a name="configuration-email"></a>E-mail de configuration

Sélectionnez **E-mail de configuration** comme type d’adresse e-mail si la configuration que vous utilisez a un nœud dans les sources de données qui renvoie une seule adresse e-mail ou plusieurs adresses e-mail séparées par des points-virgules (;). Vous pouvez utiliser les [sources de données](general-electronic-reporting.md#FormatComponentOutbound) et les [fonctions](er-formula-language.md#Functions) dans le concepteur de formule pour obtenir une adresse e-mail correctement mise en forme ou des adresses e-mail correctement mises en forme séparées par des points-virgules. Par exemple, si vous utilisez la configuration **Transfert de crédit ISO 20022**, le nœud qui représente l’adresse e-mail principale d’un fournisseur à partir des coordonnées du fournisseur auquel la lettre explicative doit être envoyée est `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.

[![Configuration d’une source d’adresse e-mail.](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)

## <a name="group-format-components"></a><a id="grouping"></a>Grouper les composants de format

Pour regrouper les composants de format, sur la page **Destination des rapports électroniques**, sur le raccourci **Destination du fichier**, sélectionnez les composants dans la grille, puis **Grouper**.

**E-mail** est la seule destination précédemment configurée qui est encore disponible pour les composants sélectionnés. Aucune autre destination précédemment configurée n’est disponible, car elle est considérée comme non prise en charge pour un groupe de composants. Vous serez informé de ces changements le cas échéant.

L’enregistrement que vous avez précédemment ajouté est considéré comme l’en-tête du groupe créé. Cet enregistrement d’en-tête contient les paramètres de destination des e-mails pour le groupe. Les autres enregistrements sont des membres du groupe qui utiliseront les paramètres de destination des e-mails de l’enregistrement d’en-tête du groupe.

Pour dissocier des composants de format, sur le raccourci **Destination du fichier**, sélectionnez un enregistrement qui appartient au groupe, puis sélectionnez **Dissocier**.

- Si vous sélectionnez un enregistrement d’en-tête, l’ensemble du groupe sera dissocié.
- Si vous sélectionnez un enregistrement de membre et qu’il s’agit du dernier enregistrement de membre d’un groupe, l’ensemble du groupe sera dissocié.
- Si vous sélectionnez un enregistrement de membre qui n’est pas le dernier enregistrement de membre d’un groupe, cet enregistrement sera exclu du groupe actuel.

L’illustration suivante montre la structure d’un format ER qui a été configuré pour produire un fichier sortant compressé contenant une note de lettre de recouvrement et les factures client appropriées au format PDF.

[![Structure d’un format ER qui génère des documents sortants.](./media/ER_Destinations-Email-Grouping1.png)](./media/ER_Destinations-Email-Grouping1.png)

L’illustration suivante montre le processus, comme décrit dans cette rubrique, de regroupement de composants individuels et d’activation de la destination de l’**E-mail** du nouveau groupe, afin qu’une note de lettre de recouvrement soit envoyée avec les factures client appropriées sous forme de pièces jointes à un e-mail.

[![Regrouper des composants individuels et activer la destination de l’e-mail.](./media/ER_Destinations-Email-Grouping2.gif)](./media/ER_Destinations-Email-Grouping2.gif)

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d'ensemble des états électroniques](general-electronic-reporting.md)
- [Destinations pour la gestion des états électroniques](electronic-reporting-destinations.md)
- [Concepteur de formule dans les états électroniques (ER)](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
