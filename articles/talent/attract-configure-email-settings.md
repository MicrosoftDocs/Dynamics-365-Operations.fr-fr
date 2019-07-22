---
title: Configurer les paramètres d'e-mail dans Microsoft Dynamics 365 for Talent - Attract
description: Cette rubrique explique comment configurer les paramètres des e-mails envoyés par Microsoft Dynamics 365 for Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 360937b807ea149edb2f16ad6799d74791d599b5
ms.sourcegitcommit: a6b32be10b6eb6340f8f68261bf62d0202c03dd1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/05/2019
ms.locfileid: "1729779"
---
# <a name="configure-email-settings-in-microsoft-dynamics-365-for-talent---attract"></a>Configurer les paramètres d'e-mail dans Microsoft Dynamics 365 for Talent - Attract
[!include[banner](../includes/banner.md)]

Votre marque est un gage de confiance et vous aide à établir la relation avec les candidats avant même qu'ils ne postulent à vos offres d'emploi. Une perception de marque positive attire les meilleurs talents et augmente la fidélité des employés en place. Microsoft Dynamics 365 for Talent : Attract vous permet de configurer les e-mails pour qu'ils reflètent la marque de votre société. Par conséquent, vous pouvez offrir une expérience cohérente aux candidats au fil de leur progression dans le processus de candidature.

Attract vous permet d'exécuter les actions suivantes :

- Configurer les paramètres d'e-mail afin d'utiliser le compte de service de messagerie Microsoft Exchange de votre société. Ainsi, les candidats savent que les e-mails proviennent de votre société. Par exemple, vous pouvez configurer les paramètres afin que les candidats reçoivent des e-mails de `recruiting@contoso.com` au lieu de `contoso@microsoft.com`.
- Créer une personnalisation cohérente pour toutes les communications par e-mail, en définissant un en-tête et un pied de page globaux pour tous les modèles d'e-mails. 

> [!NOTE]
> Pour configurer Attract afin qu'il utilise le compte de service de messagerie de votre société pour envoyer les e-mails, vous avez besoin du module complémentaire Recrutement complet.

## <a name="connect-an-email-service-account"></a>Connecter un compte de service de messagerie

En connectant le compte de service de messagerie de votre société, vous pouvez créer une expérience de messagerie à l'image de votre marque pour les candidats à vos offres d'emploi. Si vous ne connectez pas le compte de votre société, Attract utilise le compte de service de messagerie à l'image de marque de Microsoft par défaut.

1. Sélectionnez **Paramètres** (le symbole d'engrenage) dans le coin supérieur droit, puis sélectionnez **Centre d'administration**.
2. Dans l'onglet **Paramètres d'e-mail**, sous **Comptes de service de messagerie**, sélectionnez **Connecter un compte de société**.

    ![Connexion du compte du service de messagerie de votre société dans Attract](./media/attract-admin-email-service-accounts.png)

    Pour plus d'informations sur la création d'un compte e-mail partagé, voir [Boîtes de réception partagées dans Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes).

3. Dans la fenêtre de connexion Microsoft, connectez-vous à l'aide de vos informations d'identification d'entreprise.
4. Si vous n'avez pas encore été paramétré de compte de service de messagerie, ou si vous souhaitez en ajouter un nouveau, sélectionnez **Ajouter un nouveau compte de service**, puis entrez vos informations de messagerie. Si vous avez déjà configuré le compte de service de messagerie à utiliser, sélectionnez-le.

Lorsque votre compte de service de messagerie est correctement configuré, vous le voyez répertorié sous **Comptes de service de messagerie**.

## <a name="disconnect-an-email-service-account"></a>Déconnecter un compte de service de messagerie

Si vous souhaitez cesser d'utiliser le domaine de votre société dans vos communications par e-mail dans Attract, vous pouvez déconnecter un compte de service de messagerie.

1. Sélectionnez **Paramètres** (le symbole d'engrenage) dans le coin supérieur droit, puis sélectionnez **Centre d'administration**.
2. Dans l'onglet **Paramètres d'e-mail**, sous **Comptes de service de messagerie**, sélectionnez le bouton **Plus** (trois points verticaux) en regard du compte de service de messagerie que vous souhaitez déconnecter.
3. Sélectionnez **Déconnecter le compte de messagerie**.

    ![Déconnexion du compte du service de messagerie de votre société](./media/attract-admin-disconnect-email-account.png)

4. Lorsque vous êtes invité à confirmer l'opération, sélectionnez **Déconnecter**.

    ![Conformation de la déconnexion du compte du service de messagerie de votre société](./media/attract-admin-email-confirm-disconnect.png)

Si vous ne connectez pas d'autre compte de service de messagerie, les e-mails envoyés à partir d'Attract utiliseront compte de service de messagerie à l'image de marque de Microsoft par défaut.

## <a name="configure-email-template-settings"></a>Configurer les paramètres de modèle d'e-mail

Vous pouvez charger une image du logo de votre société et d'autres informations comme en-tête de marque pour vos e-mail. Vous pouvez également fournir des liens vers votre politique de confidentialité et vos conditions d'utilisation dans les pieds de page d'e-mail.

> [!NOTE]
> Vous devez respecter toutes les lois applicables de votre pays ou de votre région, ainsi que celles du pays ou de la région qui régissent le destinataire de l'e-mail. Ces lois comprennent les réglementations anti-courrier indésirable.

1. Sélectionnez **Paramètres** (le symbole d'engrenage) dans le coin supérieur droit, puis sélectionnez **Centre d'administration**.
2. Dans l'onglet **Paramètres d'e-mail**, sous **Paramètres du modèle d'e-mail**, faites glisser l'image que vous souhaitez utiliser comme en-tête d'e-mail dans la zone d'image, ou cliquez sur la zone d'image pour rechercher le fichier. Pour remplacer une image existante, vous devez d'abord sélectionner **Supprimer** en regard de celle-ci. L'image doit être un fichier au format JPEG, JPG, PNG, ou SVG. La taille recommandée d'image est comprise entre 25 et 800 pixels de large, et entre 25 et 150 pixels de haut. La taille maximale de fichier pour l'en-tête est de 1 méga-octet (Mo).

    ![Ajouter une image à l'en-tête d'e-mail de votre société](./media/attract-admin-email-header.png)

3. Sous **Votre politique de confidentialité pour les communications**, indiquez un lien vers la politique de confidentialité de votre société. Sous **Vos conditions générales pour les communications**, indiquez un lien vers les conditions d'utilisation de votre société.

    ![Ajouter des liens vers la politique de confidentialité et les conditions d'utilisation de votre société dans le pied de page d'e-mail](./media/attract-admin-email-footer.png)

4. Sélectionnez **Enregistrer** pour enregistrer vos paramètres de modèle d'e-mail.
