--- 
title: "Configurer les destinations pour la gestion des états électroniques (ER)"
description: "Cette procédure illustre le paramétrage et l'utilisation de différentes destinations pour les composants de sortie de génération d'états électroniques (ER), tels qu'un dossier ou un fichier."
author: NickSelin
manager: AnnBe
ms.date: 10/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 88927a220246d11e48b210eb5648d7e7c2a7cef8
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="configure-destinations-for-electronic-reporting-er"></a>Configurer les destinations pour la gestion des états électroniques (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure illustre le paramétrage et l'utilisation de différentes destinations pour les composants de sortie de génération d'états électroniques (ER), tels qu'un dossier ou un fichier. La société fictive de démonstration utilisée pour créer cette procédure est DEMF. L'Allemagne est le pays\région de l'adresse principale de l'entité juridique, toutefois, vous pouvez utiliser n'importe quelle entité juridique pour cette procédure. 

Le format utilisé dans cet exemple est Virement ISO20022, mais vous pouvez utiliser n'importe quel format que vous avez déjà importé. Notez que cette procédure est un exemple de paramétrage d'un fichier unique et d'une destination unique. Vous trouverez plus d'informations sur la gestion des destinations d'états électroniques dans l'aide de Dynamics 365 for Finance and Operations.

1. Allez dans Administration d'organisation > Génération d'états électroniques > Destination des états électroniques.
2. Cliquez sur Nouveau pour créer un nouvel ensemble de destination pour un format.
3. Dans le champ Référence, sélectionnez un format pour lequel vous souhaitez configurer des destinations.
    * Si vous n'avez pas de valeur à sélectionner, cela signifie que vous n'avez importé aucune configuration de format des états électroniques. Vous devez importer une configuration de format avant de définir des destinations.  
4. Cliquez sur Nouveau pour créer une destination de fichier.
    * Notez que vous pouvez créer une destination de fichier pour chaque composant de sortie du même format, tel qu'un dossier ou un fichier. Vous pourrez activer ou désactiver des destinations séparément dans les paramètres.  
5. Entrez le nom convivial du composant de sortie dans le champ Nom.
    * Il est recommandé d'utiliser des noms explicites, tels que « Fichier de paiement « ou « État de contrôle ». Ces noms sont présentés aux utilisateurs au moment de l'exécution de la configuration avec les paramètres de destination.  
6. Dans le nom de fichier, sélectionnez un fichier ou un dossier spécifique au format.
7. Cliquez sur Paramètres.
8. Sélectionnez Oui dans le champ Activé.
    * La case à cocher Activé sur chaque onglet active et désactive chaque destination séparément. Dans cet exemple, vous activerez l'envoi d'un fichier de sortie à un destinataire du message lorsque le fichier est généré.  
9. Cliquez sur Modifier pour paramétrer les destinataires de l'e-mail.
10. Cliquez sur Ajouter.
11. Cliquez sur E-mail de gestion de l'impression.
12. Sélectionnez une option dans le champ Source du message électronique.
    * Vous pouvez sélectionner différents types de sources de message électronique, par exemple un type de client ou de fournisseur. Cela définit le type d'argument qui est renvoyé par la formule Compte source de l'e-mail. La formule Compte source de l'e-mail, décrite dans une étape suivante, est l'emplacement où vous liez la source de l'e-mail. Sélectionnez Fournisseur si votre formule renvoie un compte fournisseur. Utilisez Fournisseur si vous utilisez l'exemple de configuration de virement ISO 20022.  
13. Cliquez sur le bouton Liaison de la source du message électronique.
14. Dans la formule, entrez une référence spécifique au document au type de partie que vous avez sélectionné précédemment.
    * Au lieu de taper, vous pouvez rechercher un nœud de source de données qui représente le compte de partie, puis cliquer sur le bouton Ajouter une source de données pour mettre la formule à jour. Par exemple, si vous utilisez la configuration de virement bancaire ISO 20022, le nœud représentant un compte fournisseur est : $PaymentsForCoveringLetter'.Creditor.Identification.SourceID. Sinon, entrez une valeur de chaîne, par exemple « DE-001 », pour enregistrer une formule.  
15. Cliquez sur Enregistrer.
16. Fermez la page.
17. Cliquez sur Modifier pour configurer les détails du contact pour la partie.
18. Sélectionnez Oui dans le champ Contact principal.
    * Vous pouvez utiliser différentes options pour indiquer le type de contact de la partie à utiliser comme adresse e-mail pour cette destination. Nous utilisons le contact principal dans cet exemple.  
19. Cliquez sur OK.
20. Cliquez sur OK.
21. Tapez une valeur dans le champ Objet.
22. Cliquez sur OK.


