---
title: Approbations des factures mobiles
description: "Les capacités déplacement dans Microsoft Dynamics 365 pour les opérations permettent expériences déplacement d&quot;une conception d&quot;utilisateur d&quot;entreprise. Pour les scénarios avancés, la plateforme permet également les développeurs étendre les capacités lors de leur désirent. La manière la plus effective d&quot;en savoir que certains nouveaux concepts sur le portable est de passer par le processus de concevoir certains scénarios. Cette rubrique est prévue pour fournir une approche aisé à concevoir les scénarios portables en prenant des approbations de facture fournisseur du portable comme dossier d&quot;utilisation. Cette rubrique doit vous aider à créer d&quot;autres variations de scénarios et peut également être appliquée à d&quot;autres scénarios non liés aux factures fournisseur."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 30229c0d24aed0bd927993b9af76b32d9bb073ee
ms.lasthandoff: 03/31/2017


---

# <a name="mobile-invoice-approvals"></a>Approbations des factures mobiles

Les capacités déplacement dans Microsoft Dynamics 365 pour les opérations permettent expériences déplacement d'une conception d'utilisateur d'entreprise. Pour les scénarios avancés, la plateforme permet également les développeurs étendre les capacités lors de leur désirent. La manière la plus effective d'en savoir que certains nouveaux concepts sur le portable est de passer par le processus de concevoir certains scénarios. Cette rubrique est prévue pour fournir une approche aisé à concevoir les scénarios portables en prenant des approbations de facture fournisseur du portable comme dossier d'utilisation. Cette rubrique doit vous aider à créer d'autres variations de scénarios et peut également être appliquée à d'autres scénarios non liés aux factures fournisseur.

<a name="prerequisites"></a>Conditions préalables
-------------

| Logiciel requis                                                                                            | description ;                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Pré- lecture portable manuels                                                                                |(/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform.md)                                                                                                  |
| Dynamics 365 pour les opérations                                                                             | Un environnement avec Microsoft Dynamics 365 pour la version 1611 d'opérations et Microsoft Dynamics pour la mise à jour 3 de plateforme Opérations (novembre 2016)                   |
| Installez la Base de connaissances 3204341 de correction.                                                                              | L'enregistreur de tâches peut à tort enregistrer deux commandes de clôture pour les boîtes déroulantes cela est inclus dans Dynamics 365 pour la mise à jour 3 (novembre 2016 la mise à jour) de plateforme d'opération |
| Installez la Base de connaissances 3207800 de correction.                                                                              | Ce correctif active des pièces jointes à afficher sur le client portable cela est inclus dans Dynamics 365 pour la mise à jour 3 (novembre 2016 mise à jour) de plateforme d'opération.           |
| Installez la Base de connaissances 3208224 de correction.                                                                              | Code d'application pour l'application mobile approbations de facture fournisseur que celle-ci est inclus dans l'application Microsoft Dynamics AX 7.0.1 (mai 2016).                          |
| Android ou un (ou un périphérique Windows ayant l'application mobile ont installé pour Dynamics 365 pour les opérations | Recherche de l'application dans le magasin adéquat d'application.                                                                                                                     |

## <a name="introduction"></a>Introduction
Les approbations portables pour les factures fournisseur requièrent les trois correctifs mentionnés dans la section « conditions préalables ». Ces correctifs ne présentent pas un espace de travail pour les approbations des factures. Pour connaître ce qui est un espace de travail dans le contexte de portable, lisez le Manuel mobile qui est mentionné dans la section « conditions préalables ». L'espace de travail de l'approbation des factures doit être défini. 

Chaque organisation orchestre et définit son processus commercial pour les factures fournisseur différemment. Avant conçu une expérience portable pour les approbations de facture fournisseur, vous devez prendre en compte les aspects suivants du processus entreprise. L'idée est d'utiliser ces repères point si possible pour optimiser l'expérience utilisateur dans le périphérique.

-   Les champs de l'en-tête de facture l'utilisateur souhaitera-il voir dans l'expérience mobile, et dans quel ordre ?
-   Les champs des lignes de facture l'utilisateur souhaitera-il voir dans l'expérience mobile, et dans quel ordre ?
-   Combien de lignes de facture y a -t-elle dans une facture ? Application de la règle 80-20 ici, et l'optimisation pour le 80 %.
-   Les utilisateurs souhaiteront-ils afficher les répartitions comptables (codage de facture) de l'périphérique mobile au cours de les révisions ? Si la réponse à la question est Oui, tenez compte des questions suivantes :
    -   Combien de répartitions comptables (prix global, taxes, les frais, fractionnements, etc.) y a -t-elle pour une ligne de facture ? Là aussi, appliquez la règle 80-20.
    -   Les factures ont-elles également les répartitions comptables dans l'en-tête de facture ? Dans ce cas, ces répartitions comptables doivent -elles être disponibles dans le périphérique ?

> [!NOTE]
> Cette rubrique explique ne pas comment modifier les répartitions comptables, car cette fonctionnalité n'est actuellement pas prise en charge pour les scénarios portable.

-   Les utilisateurs souhaiteront-ils afficher les pièces jointes pour la facture sur le périphérique ?

La conception de l'expérience portable pour les approbations des factures peut varier, selon les réponses à ces questions. Le but est d'optimiser l'expérience utilisateur pour le processus entreprise sur le portable dans une organisation. Dans le reste de cette rubrique, nous regarderons deux variations de scénario basés sur les réponses aux questions précédantes. 

En général, lorsque vous travaillez avec le Concepteur mobile, vérifiez « pour être sorti » les modifications pour empêcher perdre des mises à jour.

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a>Conception d'un scénario simple d'approbation des factures pour Contoso
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribut du scénario</th>
<th>Répondre</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Les champs de l'en-tête de facture l'utilisateur souhaitera-il voir dans l'expérience mobile, et dans quel ordre ?</td>
<td><ol>
<li>Nom du fournisseur</li>
<li>Total de la facture</li>
<li>Compte de facturation</li>
<li>Numéro de facture</li>
<li>Date de facture</li>
<li>Description de la facture</li>
<li>Date d'échéance</li>
<li>Devise de facturation</li>
</ol></td>
</tr>
<tr class="even">
<td>Les champs des lignes de facture l'utilisateur souhaitera-il voir dans l'expérience mobile, et dans quel ordre ?</td>
<td><ol>
<li>Catégorie d'approvisionnement</li>
<li>Quantité</li>
<li>Prix unitaire</li>
<li>Montant net de ligne</li>
<li>Montant des honoraires</li>
</ol></td>
</tr>
<tr class="odd">
<td>Combien de lignes de facture y a -t-elle dans une facture ? Application de la règle 80-20 ici, et l'optimisation pour le 80 %.</td>
<td>1</td>
</tr>
<tr class="even">
<td>Les utilisateurs souhaiteront-ils afficher les répartitions comptables (codage de facture) de l'périphérique mobile au cours de les révisions ?</td>
<td>Oui</td>
</tr>
<tr class="odd">
<td>Combien de répartitions comptables (prix global, taxes, les frais, etc.) y a -t-elle pour une ligne de facture ? Là aussi, appliquez la règle 80-20.</td>
<td>Prix global : Taxe 2 : Facture 0 : 0</td>
</tr>
<tr class="even">
<td>Les factures ont-elles également les répartitions comptables dans l'en-tête de facture ? Dans ce cas, ces répartitions comptables doivent -elles être disponibles dans le périphérique ?</td>
<td>Non utilisé</td>
</tr>
<tr class="odd">
<td>Les utilisateurs souhaiteront-ils afficher les pièces jointes pour la facture sur le périphérique ?</td>
<td>Oui</td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a>Créer un espace de travail

1.  Dans un navigateur, Dynamics en cours 365 pour les opérations, et chèque dans.
2.  Après avoir signé dans, ajoutez ** &mode=mobile ** à l'adresse comme indiqué dans l'exemple suivant, et actualiser la page : https://yoururl/?cmp=usmf&mi=DefaultDashboard**&mode=mobile**&lt;&gt;
3.  Cliquez sur ** des paramètres ** (vitesse) en appuyant sur la gauche de la page, puis sur ** application mobile **. Le Concepteur mobile d'application doit afficher ainsi que les élements enregistreur de tâches.
4.  Cliquez sur ** ajoutez ** pour créer un nouvel espace de travail. Pour cet exemple, nommez l'espace de travail ** mes approbations **.
5.  Entrez une description.
6.  Sélectionnez une couleur d'espace de travail. La couleur de l'espace de travail est utilisée pour le style général des expériences de la mobilité de cet espace de travail.
7.  Sélectionnez une icône de l'espace de travail.
8.  Cliquez sur ** fait **
9.  Cliquez sur ** publiez l'espace de travail ** pour enregistrer les modifications

### <a name="vendor-invoices-assigned-to-me"></a>Factures fournisseur qui me sont affectées

La première page portable que vous devez configurer est la liste des factures affectées à l'utilisateur pour révision. Pour concevoir cette page mobile, utilisez ** VendMobileInvoiceAssignedToMeListPage ** page dans Dynamics 365 pour les opérations. Avant de pouvoir exécuter cette procédure, assurez-vous qu'au moins une facture fournisseur vous est affectée à la révision, et que la ligne de facture a les deux répartitions. Ce paramétrage correspond aux exigences pour ce scénario.

1.  Dans Dynamics 365 pour l'URL d'opérations, remplacez le nom de l'option de menu par ** VendMobileInvoiceAssignedToMeListPage ** pour ouvrir la version portable ** Factures fournisseur affectées à -moi ** de la page de liste dans ** Achats ** le module. Selon le nombre de factures que vous avez dans votre système qui vous est affecté, cette page affiche les factures. Pour trouver une facture spécifique, vous pouvez utiliser le filtre à gauche. Toutefois, nous ne l'avons pas besoin d'une facture spécifique pour cet exemple. Nous vous besoin juste d'une certaine facture affectée à vous ce qui va vous permettre de concevoir la page portable. Les nouvelles pages disponibles doivent être désignées spécifiquement pour développer les scénarios déplacement pour la facture fournisseur. Par conséquent, vous devez utiliser ces pages. L'URL doit ressembler à l'adresse suivante, et une fois que vous l'avez entré, la page affichée dans l'illustration doit paraître : https://yourURL/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile&lt;&gt;[factures fournisseur en attente![affectées à -moi page (]. /media/mobile-invoice-approvals01-1024x281.png)](. /media/mobile-invoice-approvals01.png)
2.  Clique sur ** des paramètres ** le bouton (de vitesse) dans la gauche de la page, puis sur ** l'application mobile **
3.  Sélectionnez l'espace de travail et cliquez sur ** modifiez **
4.  Cliquez sur ** ajoutez la page ** pour créer la première page portable.
5.  Entrez un nom, par exemple ** mes factures fournisseur **, et une description, par exemple ** des factures fournisseur affectées à -moi pour la révision **.
6.  Click **Done**.
7.  Dans le Concepteur mobile, sous ** champs ** l'onglet, cliquez sur ** sélectionnez les champs **. Les colonnes de la page de liste doivent ressembler à l'illustration suivante. [colonnes![sur les factures fournisseur en attente affectées à -moi page (]. /media/mobile-invoice-approvals02-1024x117.png)](. /media/mobile-invoice-approvals02.png)
8.  Ajoutez les colonnes voulues de la page de liste à afficher aux utilisateurs de la page portable. Ordre dans lequel vous ajoutez est l'ordre dans lequel les champs à afficher pour l'utilisateur. Vous ne pouvez modifier de classer les champs sont en resélectionnant tous les champs. Selon la configuration requise pour ce scénario, les huit champs suivants sont nécessaires. Toutefois, certains utilisateurs peuvent prendre en considération huit champs trop d'informations pour avoir sur un périphérique mobile. Par conséquent, il affiche uniquement les champs principaux dans la vue portable de liste. Les champs restants s'affichent dans l'affichage détaillé que nous concevrons ultérieurement. Pour maintenant, nous ajouterons les champs suivants. Cliquez sur le signe plus (**+**) dans les colonnes à ajouter à la page portable.
    1.  Nom du fournisseur
    2.  Total de la facture
    3.  Compte de facturation
    4.  Numéro de facture
    5.  Date de facture

    Une fois que les champs soient ajoutés, la page portable doit ressembler à l'illustration suivante. [la page![après les champs sont ajoutées] (. /media/mobile-invoice-approvals03.png)](. /media/mobile-invoice-approvals03.png)
9.  Vous devez également ajouter les colonnes suivantes maintenant, de manière à ce que nous puissions activer les actions de workflow ultérieurement.
    1.  Tâche complète d'afficher
    2.  Tâche de délégué d'afficher
    3.  Tâche de rappel d'afficher
    4.  Tâche d'écart d'afficher
    5.  Tâche d'exécution de la demande d'afficher
    6.  Permet d'afficher renvoient la tâche

10. Cliquez sur ** fait ** à quitter mode d'édition.
11. Cliquez sur ** arrière ** puis ** fait ** quitter l'espace de travail
12. Cliquez sur ** publiez l'espace de travail ** pour enregistrer votre travail.
13. Activez ** le total de la facture affichée sur les factures en attente d'une liste ** dans l'écran Paramètres des achats sous ** facture **. Notez que, uniquement en activant ce paramètre, les totaux de la facture sont calculées pour être affichés dans la page de liste en attente des factures fournisseur. Il s'agit d'une nouvelle capacité dans le cadre de le correctif logiciel 3208224 de condition préalable.

### <a name="vendor-invoice-details"></a>Détails de facture fournisseur

Pour déterminer la page de détails de facture pour le mobile, utilisez ** VendMobileInvoiceHeaderDetails ** page dans Dynamics 365 pour les opérations. Notez que, en fonction de le nombre de factures que vous avez dans votre système, des affiches de cette page la facture la plus ancienne (la facture qui a été créée préalablement). Pour trouver une facture spécifique, vous pouvez utiliser le filtre à gauche. Toutefois, nous ne l'avons pas besoin d'une facture spécifique pour cet exemple. Nous vous besoin juste de certaines données de factures afin que nous puissions concevoir la page portable. [page de workflow d'![] (. /media/mobile-invoice-approvals04-1024x425.png)](. /media/mobile-invoice-approvals04.png)

1.  Dans Dynamics 365 pour l'URL d'opérations, remplacez le nom de l'option de menu par ** VendMobileInvoiceHeaderDetails ** pour ouvrir l'écran
2.  Ouvrez le Concepteur mobile du ** des paramètres ** bouton (de vitesse).
3.  Cliquez sur ** modifiez ** se pour bouton commencer à modifier le mode de l'espace de travail.
4.  Sélectionnez ** mes factures fournisseur ** FRx créé précédemment, puis sur ** modifiez **.
5.  Sous ** des champs ** l'onglet, cliquez sur ** grille ** l'en-tête de colonne.
6.  Cliquez sur ** propriétés ** &gt; ** ajoutez la page **. ** Remarque : ** Lorsque vous cliquez sur ** grille ** l'en-tête et ajoutez une page, la relation avec la page de détails est établie automatiquement.
7.  Entrez un titre de la page, comme ** les détails de la facture **, et une description, par exemple ** en-tête de facture de vue et détails de ligne **.
8.  Cliquez sur ** sélectionnez les champs **. Notez que, l'ordre dans lequel vous ajoutez est l'ordre dans lequel les champs à afficher pour l'utilisateur. Vous ne pouvez modifier de classer les champs sont en resélectionnant tous les champs.
9.  Ajoutez les champs suivants de l'en-tête, selon les besoins pour ce cas :
    1.  Nom du fournisseur
    2.  Total de la facture
    3.  Compte de facturation
    4.  Numéro de facture
    5.  Date de facture
    6.  Description de la facture
    7.  Date d'échéance
    8.  Devise de facturation

10. Ajoutez les champs suivants lignes de grille dans la page :
    1.  Catégorie d'approvisionnement
    2.  Quantité
    3.  Prix unitaire
    4.  Montant net de ligne
    5.  Montant des honoraires

11. Une fois l'ensemble des champs des deux étapes précédentes ont été ajoutés, cliquez sur ** fait **. La page doit ressembler à l'illustration suivante. [![Page after fields are added](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)
12. Cliquez sur ** fait ** à quitter mode d'édition.
13. Cliquez sur ** arrière ** puis ** fait ** quitter l'espace de travail
14. Cliquez sur ** publiez l'espace de travail ** pour enregistrer votre travail

### <a name="workflow-actions"></a>Actions de workflow

Pour ajouter des actions de workflow, procédez ** VendMobileInvoiceHeaderDetails ** page dans Dynamics 365 pour les opérations. Pour ouvrir cette page, remplacez le nom de l'option de menu de l'URL, comme le avez créé précédemment vous. Ouvrez le Concepteur mobile du ** des paramètres ** bouton (de vitesse). Procédez comme suit pour ajouter des actions de workflow dans la page de détails.

1.  Cliquez sur ** modifiez ** se pour bouton commencer à modifier le mode de l'espace de travail.
2.  Sélectionnez ** les détails de la facture ** FRx créé précédemment, puis sur ** modifiez **.
3.  Sous ** actions ** l'onglet, cliquez sur ** ajoutez l'action **.
4.  Entrez le titre d'action, par exemple ** approuver **, et une description, par exemple ** facture d'approuver **. Notez que le titre d'action que vous entrez ici devient le nom de l'action affiché pour l'utilisateur de l'application mobile.
5.  Click **Done**.
6.  Cliquez sur ** sélectionnez les champs **.
7.  Passez via le processus de workflow sur ** VendMobileInvoiceHeaderDetails ** la page, puis complétez l'action que vous avez souhaité enregistrer. Assurez-vous que vous entrez des commentaires de workflow lors de ce processus, afin qu'un champ de commentaires soit également inclus dans l'expérience portable.
8.  Une fois l'action de workflow soit exécutée, cliquez sur ** fait ** pour exécuter la tâche de champs de sélection.
9.  Cliquez sur ** fait ** à quitter mode d'édition.
10. Cliquez sur ** arrière ** puis ** fait ** quitter l'espace de travail
11. Cliquez sur ** publiez l'espace de travail ** pour enregistrer votre travail
12. Répétez les étapes 3 à 11 pour enregistrer toutes les actions voulues de workflow. Notez cela, elle est un besoin pour que les factures qui vous sont affectées dans un état pour rendre les actions de workflow disponibles à que vous allez créer pour.
13. Ouvrez le Bloc-notes ou Microsoft Visual Studio, et collez le code suivant. Enregistrez le fichier sous forme de fichier .js. Ce code effectué deux événements :
    1.  Il masque les colonnes de workflow supplémentaires liées que nous avons ajoutées plus haut dans la page de liste portable. Nous vous ajouté les colonnes afin que la candidature a que les informations dans le contexte et puisse effectuer l'étape suivante.
    2.  Selon l'étape de workflow actif, elle s'applique la logique pour afficher uniquement les actions.

Notez que, le nom des pages et d'autres contrôles dans le code de JS doivent être identiques de l'espace de travail.

1.  principale de fonction (metadataService, dataService, cacheService, $q) {retour {appInit : (e) (appMetadata) {contrôles de masquer de //qui doivent figurer, mais metadataService.configureControl non visible (« Mon-fournisseur- factures « , « ShowAccept » {, masqué : rectifiez}) ;                metadataService.configureControl (« Mon-fournisseur- factures « , « ShowApprove » {, masqué : rectifiez}) ;                metadataService.configureControl (« Mon-fournisseur- factures « , « ShowReject » {, masqué : rectifiez}) ;                metadataService.configureControl (« Mon-fournisseur- factures « , « ShowDelegate » {, masqué : rectifiez}) ;                metadataService.configureControl (« Mon-fournisseur- factures « , « ShowRequestChange » {, masqué : rectifiez}) ;              metadataService.configureControl (« Mon-fournisseur- factures « , « ShowRecall » {, masqué : rectifiez}) ;                metadataService.configureControl (« Mon-fournisseur- factures « , « ShowComplete » {, masqué : rectifiez}) ;            metadataService.configureControl (« Mon-fournisseur- factures « , « ShowResubmit » {, masqué : rectifiez}) ;            }, pageInit : (e) (pageMetadata, param) {si (La détails de == de pageMetadata.Name ") {metadataService.configureAction étape de workflow d'actions à afficher sur ///workflow de masquer selon (« acceptez, » {visible : rectifiez}) ;                    metadataService.configureAction (« approuver, » {visible : rectifiez}) ;                    metadataService.configureAction (« écart, » {visible : rectifiez}) ;                    metadataService.configureAction (« délégué, » {visible : rectifiez}) ;                    metadataService.configureAction (« Demande- modification, » {visible : rectifiez}) ;                    metadataService.configureAction (« Rappeler » {, visible : rectifiez}) ;                    metadataService.configureAction (« , complétez » {visible : rectifiez}) ;                    metadataService.configureAction (« retournez, » {visible : rectifiez}) ;

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                       var showRejectControl = Boolean(rejectControl == 1);
                      var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                     metadataService.configureAction('Resubmit', { visible: showResubmitControl });
                   }
                 },
           };
        }

2.  Téléchargez le fichier de code à l'espace de travail en sélectionnant ** logique ** l'onglet
3.  Cliquez sur ** fait ** à quitter mode d'édition.
4.  Cliquez sur ** arrière ** puis ** fait ** quitter l'espace de travail
5.  Cliquez sur ** publiez l'espace de travail ** pour enregistrer votre travail

### <a name="vendor-invoice-attachments"></a>Documents joints de facture fournisseur

1.  Clique sur ** des paramètres ** le bouton (de vitesse) dans la gauche de la page, puis sur ** l'application mobile **
2.  Cliquez sur ** modifiez ** se pour bouton commencer à modifier le mode de l'espace de travail.
3.  Sélectionnez ** les détails de la facture ** FRx créé précédemment, puis sur ** modifiez **.
4.  Définissez ** gestion des documents ** l'option ** Oui ** comme suit. ** Remarque : ** S'il n'existe aucune condition pour les pièces jointes à afficher sous l'périphérique mobile, vous pouvez laisser par cette option défini ** Non **, qui est le paramètre par défaut.
5.  [docmanagement d'![] (. /media/docmanagement-216x300.png)](. /media/docmanagement.png)
6.  Cliquez sur ** fait ** à quitter mode d'édition.
7.  Cliquez sur ** arrière ** puis ** fait ** quitter l'espace de travail
8.  Cliquez sur ** publiez l'espace de travail ** pour enregistrer votre travail

### <a name="vendor-invoice-line-distributions"></a>Les distributions de la ligne de facture fournisseur

Les exigences pour ce scénario de confirmer qu'il figure uniquement les distributions niveau de la ligne, et qu'une facture a toujours une seule ligne. Comme ce scénario est unique, l'expérience utilisateur sous l'périphérique mobile doit également être suffisants simple que l'utilisateur ne doit pas descendre plusieurs niveaux afficher les répartitions. Les factures fournisseur dans Dynamics 365 pour les opérations incluent l'option pour afficher toutes les répartitions de l'en-tête de facture. Est cette expérience de ce que nous avons besoin pour le scénario portable. Par conséquent, il emploierons ** VendMobileInvoiceAllDistributionTree ** la page permet de concevoir cette partie du scénario portable. 

> [!NOTE] 
> Connaître les besoins nous vous aide à définir les page spécifique à utiliser et comment exactement optimiser l'expérience de la mobilité pour l'utilisateur lorsqu'il concevons le scénario. Dans le deuxième cas, nous utilisons une page différente pour afficher les répartitions, car les exigences pour ce scénario diffèrent.

1.  Dans l'URL, remplacez le nom de l'option de menu, comme vous avez effectué avant. La page qui apparaît doit ressembler à l'illustration suivante. [![toute la page des distributions] (. /media/mobile-invoice-approvals06.png)](. /media/mobile-invoice-approvals06.png)
2.  Ouvrez le Concepteur mobile du ** des paramètres ** bouton (de vitesse).
3.  Cliquez sur ** modifiez ** se pour bouton commencer à modifier le mode de l'espace de travail. ** Remarque : ** Vous obtenez que deux nouvelles pages ont été créées automatiquement. Le système crée ces pages, si vous avez activé la gestion des documents dans la section précédente. Vous pouvez ignorer ces nouvelles pages.
4.  Cliquez sur ** ajoutez la page **.
5.  Entrez un titre de la page, comme ** comptabilité de vue **, et une description, par exemple ** vue pour la facture **.
6.  Click **Done**.
7.  Sous ** des champs ** l'onglet, cliquez sur ** sélectionnez les champs **, sélectionnez les champs suivants de la page des distributions, puis sur ** fait ** :
    1.  Montant
    2.  Devise
    3.  Compte général

> [!NOTE] 
> Il ne l'avons pas sélectionné ** description ** la colonne de la grille des distributions, car les exigences pour ce scénario ont confirmé le prix global est le seul montant qu'il figure les répartitions. Par conséquent, l'utilisateur ne sont pas d'un autre champ pour déterminer le montant de type que la distribution est destiné. Toutefois, au prochain scénario, nous ** ** utilisons ces informations, car les exigences pour ce scénario spécifient que l'autre montant de types sont les répartitions (par exemple, taxe).
8.  Cliquez sur ** fait ** à quitter mode d'édition.
9.  Cliquez sur ** arrière ** puis ** fait ** quitter l'espace de travail
10. Cliquez sur ** publiez l'espace de travail ** pour enregistrer votre travail

** Remarque : ** ** Comptabilité de vue ** la page portable n'est actuellement pas liée aux pages mobiles l'une des que nous avons conçues jusqu'à présent. L'utilisateur doit pouvoir accéder à ** comptabilité de vue ** à la page ** les détails de la facture ** de la page sur un périphérique mobile, nous devons fournir la navigation ** les détails de la facture ** de la page ** comptabilité de vue ** à la page. Il établissons cette navigation à l'aide de la logique supplémentaire via le Javascript.

1.  Ouvrez le fichier de .js créé précédemment, et ajouter des lignes qui sont en surbrillance dans le code suivant. Ce code effectué deux événements :
    1.  Il permet de garantir que les utilisateurs ne peuvent pas accéder directement à partir de l'espace de travail ** comptabilité de vue ** à la page.
    2.  Il crée un contrôle de navigation ** les détails de la facture ** de la page ** comptabilité de vue ** à la page.

> [!NOTE] 
> Nom des pages et d'autres contrôles dans le code de JS doit être identique de l'espace de travail.

1.  principale de fonction (metadataService, dataService, cacheService, $q) {retour {appInit : (e) (appMetadata) {contrôles de masquer de //qui doivent figurer, mais metadataService.configureControl non visible (« Mon-fournisseur- factures « , « ShowAccept » {, masqué : rectifiez}) ;                metadataService.configureControl (« Mon-fournisseur- factures « , « ShowApprove » {, masqué : rectifiez}) ;                metadataService.configureControl (« Mon-fournisseur- factures « , « ShowReject » {, masqué : rectifiez}) ;                metadataService.configureControl (« Mon-fournisseur- factures « , « ShowDelegate » {, masqué : rectifiez}) ;                metadataService.configureControl (« Mon-fournisseur- factures « , « ShowRequestChange » {, masqué : rectifiez}) ;              metadataService.configureControl (« Mon-fournisseur- factures « , « ShowRecall » {, masqué : rectifiez}) ;                metadataService.configureControl (« Mon-fournisseur- factures « , « ShowComplete » {, masqué : rectifiez}) ;            metadataService.configureControl (« Mon-fournisseur- factures « , « ShowResubmit » {, masqué : rectifiez}) ;                La Masquer de //pagine Non applicable pour la navigation metadataService.hideNavigation (« Vue- comptabilité ") racine ;                //Link pour afficher la comptabilité metadataService.addLink (« La détails « , « Vue- comptabilité « , « Vue-comptabilité-NAV- contrôle « , « comptabilité de vue », remplies) ;            }, pageInit : (e) (pageMetadata, param) {si (La détails de == de pageMetadata.Name ") {metadataService.configureAction étape de workflow d'actions à afficher sur ///workflow de masquer selon (« acceptez, » {visible : rectifiez}) ;                    metadataService.configureAction (« approuver, » {visible : rectifiez}) ;                    metadataService.configureAction (« écart, » {visible : rectifiez}) ;                    metadataService.configureAction (« délégué, » {visible : rectifiez}) ;                    metadataService.configureAction (« Demande- modification, » {visible : rectifiez}) ;                    metadataService.configureAction (« Rappeler » {, visible : rectifiez}) ;                    metadataService.configureAction (« , complétez » {visible : rectifiez}) ;                    metadataService.configureAction (« retournez, » {visible : rectifiez}) ;

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                     var showRejectControl = Boolean(rejectControl == 1);
                       var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                       metadataService.configureAction('Resubmit', { visible: showResubmitControl });
        }
                 },
           };
        }

2.  Téléchargez le fichier de code à l'espace de travail en sélectionnant ** logique ** l'onglet pour remplacer le code précédent
3.  Cliquez sur ** fait ** à quitter mode d'édition.
4.  Cliquez sur ** arrière ** puis ** fait ** quitter l'espace de travail
5.  Cliquez sur ** publiez l'espace de travail ** pour enregistrer votre travail

### <a name="validation"></a>Contrôle

Dans votre périphérique mobile, ouvrez l'application, puis connectez-vous à votre Dynamics 365 pour l'instance d'opérations. Assurez-vous que vous vous connectez à la société dans laquelle les factures fournisseur vous sont affectées à la révision. Normalement effectuer les actions suivantes :

-   Voir ** mes approbations ** l'espace de travail.
-   Forez dans ** mes approbations ** l'espace de travail et voir ** mes factures fournisseur ** la page.
-   Forez dans ** mes factures fournisseur ** FRx et voir la liste des factures qui vous sont affectées.
-   Forez dans l'une des factures, puis consultez les détails et les détails de la ligne d'en-tête de facture.
-   Dans les détails de page, voir le lien vers les pièces jointes, puis utilisez ce lien pour accéder à la liste des pièces jointes et afficher les pièces jointes.
-   Dans les détails de page, voir le lien ** comptabilité de vue ** à la page, puis utilisez ce lien pour accéder à la page des distributions et d'afficher les répartitions.
-   Dans les détails de page, cliquez sur ** des actions ** le menu vers le bas, et d'effectuer des actions de workflow qui s'appliquent à l'étape de workflow.

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a>Conception d'un scénario complexe d'approbation des factures pour Fabrikam
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribut du scénario</th>
<th>Répondre</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Les champs de l'en-tête de facture l'utilisateur souhaitera-il voir dans l'expérience mobile, et dans quel ordre ?</td>
<td><ol>
<li>Nom du fournisseur</li>
<li>Montant de la facture</li>
<li>Compte de facturation</li>
<li>Numéro de facture</li>
<li>Date de facture</li>
<li>Description de la facture</li>
<li>Date d'échéance</li>
<li>Devise de facturation</li>
</ol></td>
</tr>
<tr class="even">
<td>Les champs des lignes de facture l'utilisateur souhaitera-il voir dans l'expérience mobile, et dans quel ordre ?</td>
<td><ol>
<li>Catégorie d'approvisionnement</li>
<li>Quantité</li>
<li>Prix unitaire</li>
<li>Montant net de ligne</li>
<li>Montant des honoraires</li>
</ol></td>
</tr>
<tr class="odd">
<td>Combien de lignes de facture y a -t-elle dans une facture ? Application de la règle 80-20 ici, et l'optimisation pour le 80 %.</td>
<td>5</td>
</tr>
<tr class="even">
<td>Les utilisateurs souhaiteront-ils afficher les répartitions comptables (codage de facture) de l'périphérique mobile au cours de les révisions ?</td>
<td>Oui</td>
</tr>
<tr class="odd">
<td>Combien de répartitions comptables (prix global, taxes, les frais, etc.) y a -t-elle pour une ligne de facture ? Là aussi, appliquez la règle 80-20.</td>
<td>Prix global : Taxe 2 : 2 Frais : 2</td>
</tr>
<tr class="even">
<td>Les factures ont-elles également les répartitions comptables dans l'en-tête de facture ? Dans ce cas, ces répartitions comptables doivent -elles être disponibles dans le périphérique ?</td>
<td>Non utilisé</td>
</tr>
<tr class="odd">
<td>Les utilisateurs souhaiteront-ils afficher les pièces jointes pour la facture sur le périphérique ?</td>
<td>Oui</td>
</tr>
</tbody>
</table>

### <a name="exercise"></a>Exercice

Les modifications suivantes peuvent être effectuées pour le scénario 1, selon les exigences du scénario 2. Cette section comme exercice que vous pouvez effectuer pour en savoir des fins.

1.  Comme autres lignes de facture sont attendues dans le scénario 2, les modifications suivantes dans la conception aideront à optimiser l'expérience utilisateur sous l'périphérique mobile :
    1.  Au lieu des lignes de facture affichée dans la page de détails (comme dans le scénario 1), utilisateur peut choisir d'afficher des lignes sur une page distincte portable.
    2.  Comme plusieurs lignes de facture est prévue dans ce scénario, si ** VendMobileInvoiceAllDistributionTree ** La page est utilisée pour concevoir la page des distributions pour le portable (comme dans scénario 1), il peut être embrouillant pour que l'utilisateur corrèle des lignes {{avec:to}} les répartitions. Utilisez, par conséquent ** VendMobileInvoiceLineDistributionTree ** la page permet de concevoir la page des répartitions.
    3.  Idéalement, les distributions doivent être affichées dans le contexte d'une ligne de facture dans ce cas. Par conséquent, veillez l'utilisateur peut forer dans une ligne pour afficher la page des répartitions. Utilisez la capacité de lien vers la page d'établir l'extraction, comme vous avez effectué pour l'en-tête et les pages de détails dans le scénario 1.

2.  Comme plus d'un type de montant est prévu sur les distributions dans le scénario 2 (taxes, les frais, etc.), il est utile pour afficher la description du type de montant. (Nous vous omis ces informations dans le scénario 1).

## <a name="conclusion"></a>Conclusion
Plate-forme portable et les capacités d'application permettent de concevoir des scénarios mobiles qui sont optimisés pour une base d'utilisateur dans une organisation. Selon les exemples inclus dans cette rubrique, vous pouvez tester d'autres variations et créer les différentes expériences qui répondent à une exigence spécifique.


