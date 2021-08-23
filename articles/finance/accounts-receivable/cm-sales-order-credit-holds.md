---
title: Blocages de crédit pour les commandes client
description: Cette rubrique décrit le paramétrage des règles utilisées pour placer une commande client en attente de crédit.
author: JodiChristiansen
ms.date: 07/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 14cafa69e75d7e8a0f08fb385a8c364c0162da1ec609a4e0b3cad6178ec3f716
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723965"
---
# <a name="credit-holds-for-sales-orders"></a>Blocages de crédit pour les commandes client
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cette rubrique décrit le paramétrage des règles utilisées pour placer une commande client en attente de crédit. Les règles de blocage de la gestion des crédits peuvent s’appliquer à un client individuel ou à un groupe de clients. Les règles de blocage définissent les réponses aux circonstances suivantes :

1. Nombre de jours de retard
2. Statuts des comptes
3. Conditions de paiement
4. Limite de crédit expirée
5. Montant en retard
6. Montant de la commande client
7. Portion de crédit disponible utilisée

De plus, deux paramètres contrôlent des scénarios supplémentaires qui bloqueront une commande client

1. Modification des modalités de paiement
2. Modification des remises de règlement

## <a name="set-up-blocking-rules-and-exclusion-rules"></a>Paramétrer des règles de blocage et des règles d’exclusion

Lorsqu’un client initie une transaction de vente, les informations sur la commande client sont examinées par rapport à un ensemble de règles de blocage qui guident la décision d’accorder ou non un crédit au client et permettent à la vente de progresser. Vous pouvez également définir des exclusions qui remplaceront les règles de blocage et permettront de traiter une commande client. Vous pouvez configurer des règles de blocage et des règles d’exclusion sur la page **Gestion des crédits > Paramétrer > Paramétrage de la gestion des crédits > Règles de blocage**.

À partir de la version 10.0.21, les règles de blocage dans la gestion des crédits ont été repensées de la manière suivante, pour offrir plus de flexibilité :

- Les demandes d'extensibilité ont été activées, afin que vous puissiez créer vos propres règles de blocage.
- La case à cocher **Lancer la commande client** est désormais disponible pour toutes les règles de blocage. Auparavant, elle n'était disponible que pour la règle de blocage des commandes client. Lorsque cette case est cochée, la règle d'exclusion libère la commande client sans tenir compte des autres règles pouvant bloquer les commandes client. Cette case à cocher n'est disponible que pour le type de règle **Exclusion**.

### <a name="days-overdue"></a>Jours de retard

Ouvrez l’onglet **Jours de retard** si la règle de blocage s’applique au client avec une ou plusieurs factures en souffrance depuis un certain nombre de jours.
1. Sélectionnez la plage de clients pour laquelle cette règle est **Valide pour**.
   - Sélectionnez **Table** si la règle s’applique à un client spécifique.
   - Sélectionnez **Groupe** si la règle est appliquée au niveau du groupe de clients. 
   - Sélectionnez **Tous** si la règle s’applique à tous les clients.
2. Lorsque vous avez spécifié la plage, vous devez spécifier le **Compte/groupe** qui sera utilisé dans la plage.
   - Pour la plage **Table**, la recherche fournira une liste de clients à sélectionner. 
   - Sélectionnez un **Groupe** si la règle s’applique à un groupe de crédit client.
   - Sélectionnez **Tous** si la règle s’applique à tous les clients. 
3. Sélectionnez **Groupe de risque** pour utiliser des critères pour appliquer un blocage de gestion du crédit sur les clients qui sont regroupés par un ensemble commun de facteurs, tels que leurs notations Dun et Bradstreet, le nombre d’années d’activité, le nombre d’années qu’ils ont été votre client, etc.  
4. Permet de sélectionner le type de règle que vous paramétrez. L’option **Blocage** créera une règle qui bloque une commande. L’option **Exclusion** créera une règle qui exclura une autre règle du blocage d’une commande. 
5. Sélectionnez **Type de valeur**. L’entrée par défaut est un nombre fixe de jours. Si vous créez une exclusion, vous pouvez spécifier un nombre fixe de jours ou un montant à la place. 
6. Entrez le nombre de jours **En retard** qui sera autorisé pour la règle de blocage sélectionnée avant qu’une commande ne soit placée en attente de gestion du crédit pour examen. Le nombre de jours de retard représente un nombre supplémentaire de jours de grâce qui s’ajoutent au nombre de jours au-delà de la date d’échéance du paiement que la facture peut avoir avant qu’elle ne soit considérée comme en retard. Si vous avez spécifié le **Type de valeur** comme montant pour une exclusion, entrez ensuite un montant et une devise pour ce montant.

### <a name="account-status"></a>Statut du compte

Ouvrez l’onglet **Statut du compte** si la règle de blocage s’applique à un client avec le statut de compte sélectionné.
1. Permet de sélectionner le type de règle que vous paramétrez.  **Blocage** crée une règle qui bloque une commande. **Exclusion** crée une règle qui exclura une règle du blocage d’une commande. 
2. Sélectionnez le **Statut du compte** qui entraînera la mise en attente d’une commande client ou son exclusion.

### <a name="terms-of-payment"></a>Conditions de paiement

Sélectionnez **Modalités de paiement** si la règle de blocage s’applique au délai de paiement sélectionné.
1. Permet de sélectionner le type de règle que vous paramétrez.  **Blocage** crée une règle qui bloque une commande. **Exclusion** crée une règle qui exclura une règle du blocage d’une commande. 
2. Sélectionnez les **Modalités de paiement** qui entraîneront la mise en attente d’une commande client ou son exclusion.

### <a name="credit-limit-expired"></a>Limite de crédit expirée

Ouvrez l’onglet **Limite de crédit expirée** si la règle de blocage s’applique aux clients dont les limites de crédit ont expiré.
1. Sélectionnez la plage de clients pour laquelle cette règle est **Valide pour**.
   - Sélectionnez **Table** si la règle s’applique à un client spécifique.
   - Sélectionnez **Groupe** si la règle est appliquée au niveau du groupe Client. 
   - Sélectionnez **Tous** si la règle s’applique à tous les clients.
2. Une fois que vous avez spécifié la plage, vous devez spécifier le **Compte/groupe** utilisé dans la plage.
   - Pour la plage **Table**, la recherche fournira une liste de clients dans laquelle sélectionner. 
   - Sélectionnez un **Groupe** si la règle s’applique à un groupe de gestion de crédit client.
   - Sélectionnez **Tous** si la règle s’applique à tous les clients. 
3. Sélectionner un **Groupe de risques** pour limiter davantage la liste des clients qui seront placés en attente de gestion de crédit. 
4. Permet de sélectionner le type de règle que vous paramétrez. 
   - Sélectionnez **Blocage** pour créer une règle qui bloque une commande. 
   - Sélectionnez **Exclusion** pour créer une règle qui exclura une autre règle du blocage d’une commande. 
5. Entrez la valeur **Jours limite de crédit expirée** pour la règle de blocage sélectionnée avant qu’une commande ne soit placée en attente de gestion des crédits. Le nombre de jours de retard représente des jours de grâce supplémentaires qui s’ajoutent au nombre de jours d’expiration de la limite de crédit.

### <a name="overdue-amount"></a>Montant en retard

Ouvrez l’onglet **Montant en retard** si la règle de blocage s’applique aux clients ayant des montants en retard.
1. Sélectionnez la plage de clients pour laquelle cette règle est **Valide pour**.
   - Sélectionnez **Table** si la règle s’applique à un client spécifique.
   - Sélectionnez **Groupe** si la règle est appliquée au niveau du groupe Client. 
   - Sélectionnez **Tous** si la règle s’applique à tous les clients.
2. Une fois que vous avez spécifié la plage, vous devez spécifier le **Compte/groupe** utilisé dans la plage.
   - Pour la plage **Table**, la recherche fournira une recherche par client. 
   - Sélectionnez un **Groupe** si la règle s’applique à un groupe de gestion de crédit client.
   - Sélectionnez **Tous** si la règle s’applique à tous les clients. 
3. Sélectionnez un **Groupe de risques** si vous souhaitez limiter davantage la liste des clients en attente de gestion de crédit. 
4. Permet de sélectionner le type de règle que vous paramétrez. 
   - Sélectionnez **Blocage** pour créer une règle qui bloque une commande. 
   - Sélectionnez **Exclusion** pour créer une règle qui exclura une autre règle du blocage d’une commande. 
5. Entrez la valeur **Montant en retard** pour la règle de blocage sélectionnée avant qu’une commande ne soit placée en attente de gestion des crédits pour examen. 
6. Sélectionnez le **Type de valeur** qui définit le type de valeur qui sera utilisé pour tester également combien de la limite de crédit a été utilisée. Les règles de blocage et les règles d'exclusion autorisent un pourcentage uniquement pour **Montant en souffrance**. Le seuil se rapporte à la limite de crédit.
7. Entrez la valeur **Seuil de limite de crédit** de la règle sélectionnée avant qu’un client ne soit mis en attente pour la gestion du crédit. Il peut s’agir d’un montant ou d’un pourcentage basé sur le type de valeur sélectionné dans le type de valeur.
8. La règle vérifie que le **Montant en retard** est dépassé et le **Seuil de limite de crédit** est dépassé. 

### <a name="sales-order"></a>Commande client 

Sélectionnez **Commande client** si la règle de blocage s’applique à la valeur de la commande client.
1. Sélectionnez la plage de clients pour laquelle cette règle est **Valide pour**.
   - Sélectionnez **Table** si la règle s’applique à un client spécifique.
   - Sélectionnez **Groupe** si la règle est appliquée au niveau du groupe Client. 
   - Sélectionnez **Tous** si la règle s’applique à tous les clients.
2. Une fois que vous avez spécifié la plage, vous devez spécifier le **Compte/groupe** utilisé dans la plage.
   - Pour la plage **Table**, la recherche fournira une recherche par client. 
   - Sélectionnez un **Groupe** si la règle s’applique à un groupe de gestion de crédit client.
   - Sélectionnez **Tous** si la règle s’applique à tous les clients. 
3. Sélectionnez un **Groupe de risques** si vous souhaitez limiter davantage la liste des clients en attente de gestion de crédit. 
4. Permet de sélectionner le type de règle que vous paramétrez.  
   - Sélectionnez **Blocage** pour créer une règle qui bloque une commande. 
   - Sélectionnez **Exclusion** pour créer une règle qui exclura une autre règle du blocage d’une commande. 
5. Entrez la valeur **Montant de la commande client** pour la règle de blocage sélectionnée avant qu’une commande ne soit placée en attente de gestion des crédits. 

### <a name="credit-limit-used"></a>Limite de crédit utilisée

Sélectionnez **Limite de crédit utilisée** si la règle de blocage s’applique au montant de limite de crédit client utilisé.
1. Sélectionnez la plage de clients pour laquelle cette règle est **Valide pour**.
   - Sélectionnez **Table** si la règle s’applique à un client spécifique.
   - Sélectionnez **Groupe** si la règle est appliquée au niveau du groupe Client. 
   - Sélectionnez **Tous** si la règle s’applique à tous les clients.
2. Une fois que vous avez spécifié la plage, vous devez spécifier le **Compte/groupe** utilisé dans la plage.
   - Pour la plage **Table**, la recherche fournira une recherche par client. 
   - Sélectionnez un **Groupe** si la règle s’applique à un groupe de gestion de crédit client.
   - Sélectionnez **Tous** si la règle s’applique à tous les clients. 
3. Sélectionnez un **Groupe de risques** si vous souhaitez limiter davantage la liste des clients en attente de gestion de crédit. 
4. Permet de sélectionner le type de règle que vous paramétrez.
   - Sélectionnez **Blocage** pour créer une règle qui bloque une commande. 
   - Sélectionnez **Exclusion** pour créer une règle qui exclura une autre règle du blocage d’une commande. 
5. Sélectionnez la valeur **Seuil ouvert** qui définit le pourcentage de la limite de crédit qui bloquera la commande client. Si la valeur d’une commande augmente le montant de la limite de crédit utilisée au-dessus du pourcentage, la commande sera mise en attente. 

## <a name="put-a-sales-order-on-hold-based-on-other-criteria"></a>Mettre une commande client en attente sur la base d’autres critères
  
### <a name="rank-payment-terms"></a>Classer les conditions de paiement  

Vous pouvez forcer l’exécution des règles de contrôle du crédit lorsque les conditions de paiement sont modifiées. Vous devez classer les modalités de paiement et leur attribuer une valeur de classement. Si vous remplacez les modalités de paiement de la commande par des modalités de paiement qui sont classées plus haut que les anciennes, la commande sera envoyée à la gestion du crédit et devra être approuvée.

Vous pouvez configurer le classement des modalités de paiement sur la page **Gestion des crédits > Paramétrer > Paramétrage de la gestion des crédits > Classer les modalités de paiement**.

1. Sélectionnez le champ **Modalités de paiement** à classer ; lorsque vous sélectionnez une modalité, la description s’affiche dans le champ **Description**.
2. Sélectionnez le rang de la modalité dans le champ **Rang**. Les valeurs sont toutes relatives les unes aux autres afin que vous puissiez utiliser 1,2,3 ou 10,20,30. Vous pouvez également utiliser la même valeur pour la plupart des modalités de paiement afin que seulement une ou deux modalités de paiement déclenchent la vérification du crédit.

### <a name="rank-settlement-discounts"></a>Classer les remises de règlement   

Vous pouvez forcer l’exécution des règles de contrôle du crédit lorsque les remises de règlement sont modifiées. Vous devez classer les remises de règlement et leur attribuer une valeur de classement. Si vous remplacez les remises de règlement de la commande par des remises de règlement qui sont classées plus haut que les anciennes, la commande sera envoyée à la gestion du crédit et devra être approuvée.

Vous pouvez configurer le classement des modalités de paiement sur la page **Gestion des crédits > Paramétrer > Paramétrage de la gestion des crédits > Classer les remises de règlement**.

1. Sélectionnez l’**Escompte de règlement** que vous souhaitez classer. La **Description** de l’escompte de règlement sera affichée.
2. Sélectionnez la valeur **Rang**. Les valeurs sont toutes relatives les unes aux autres afin que vous puissiez utiliser 1,2,3 ou 10,20,30. Vous pouvez également utiliser la même valeur pour la plupart des remises de règlement afin que seulement une ou deux remises de règlement déclenchent la vérification du crédit.

## <a name="sequence-the-application-of-rules"></a>Ordonner l’application des règles

Les règles sont exécutées dans un ordre spécifique que vous modifiez en fonction des besoins de votre organisation. 

- Une instance des règles d’exclusion de commande client vous permet de remplacer toutes les règles susceptibles de bloquer une commande client. Créez une règle d’exclusion de commande client et marquez l’option **Lancer le prélèvement des commandes client**. La commande ne sera pas mise en attente si cette règle d’exclusion est vraie, et aucune autre règle ne sera cochée.
- Les règles de blocage peuvent mettre la commande en attente.
- Les règles d’exclusion sont exécutées après les règles de blocage. Les règles d’exclusion n’affecteront que la règle sur laquelle elles sont définies. 
- Les règles de blocage et d’exclusion sont exécutées dans Table, puis Groupe, puis Toute commande. En raison de cet ordre de traitement, il est possible d’avoir une règle de blocage au niveau Toute qui ne sera pas exécuté car une règle d’exclusion au niveau de la table ou du groupe est exécutée.
- Les exclusions ne remplacent pas la règle de blocage si elles sont au même niveau. Par exemple, une règle d’exclusion au niveau du groupe ne remplacera pas la règle de blocage au niveau du groupe. Vous n’aurez pas besoin de configurer des exclusions au niveau Toute, sauf comme indiqué ci-dessus avec la seule instance de la règle d’exclusion de commande client. 

Le comportement de la règle **Limite de crédit utilisée** changera en fonction du réglage du paramètre **Vérifier la limite de crédit pour la commande client** trouvé dans le formulaire des paramètres de crédit et de recouvrement.
- Si le paramètre est défini sur Non, la règle de limite de crédit utilisée ne sera pas exécutée.
- Si le paramètre est défini sur Oui et que **Message en cas de dépassement de la limite de crédit** est défini sur avertissement, vous recevrez un avertissement lorsque la limite de crédit est dépassée. Les règles **Limite de crédit utilisée** seront exécutées pour voir si vous avez des règles que vous souhaitez exécuter. Cependant, pour ce scénario, vous n’ajouteriez normalement aucune règle.
- Si le paramètre est défini sur Oui et que **Message en cas de dépassement de la limite de crédit** est défini sur erreur, la limite de crédit sera vérifiée et la commande sera mise en attente si la limite de crédit est dépassée. En outre, les règles **Limite de crédit utilisée** seront exécutées pour voir si d’autres règles devraient être exécutées. Un message d’erreur ne s’affichera pas, mais le motif de blocage **Dépassement de la limite de crédit** sera affiché. 

## <a name="settings-that-will-change-the-way-an-order-is-placed-on-hold"></a>Paramètres qui changeront la façon dont une commande est mise en attente

Les commandes peuvent être exclues de la gestion du crédit même si des règles sont en place. 

- Si vous modifiez les paramètres **Exclure le client de la gestion du crédit** dans **Tous les clients> sélectionnez un client> raccourci Crédit et relances** sur **Oui**, alors aucune commande pour ce client ne sera traitée
- Si vous modifiez la valeur **Exclure de la gestion du crédit** sur l’**en-tête des commandes client** dans le **raccourci de gestion des crédits** sur **Oui**, alors les règles de gestion du crédit ne seront pas traitées. Ce réglage ne peut être effectué que par le commis au crédit ou le gestionnaire de crédit.

## <a name="processing-orders-on-hold-using-the-credit-management-hold-list"></a>Traitement des commandes en attente à l’aide de la liste de blocage de gestion des crédits

La liste de blocage de la gestion du crédit permet aux gestionnaires du crédit de visualiser toutes les commandes client qui ont été mises en attente et leur permet de supprimer les blocages lorsque les problèmes de crédit ont été atténués. La page **Liste d’attente pour la gestion des crédits** affiche toutes les commandes client qui ont été mises en attente. Vous pouvez afficher la liste d’attente sur la page **Tous les crédits sont bloqués** (**Gestion du crédit > Liste de blocage de la gestion du crédit > Tous les blocages de crédit**).
Les commandes client de toutes les entités juridiques sont envoyées à la même liste de gestion des crédits, offrant une vue centralisée de toutes les transactions qui nécessitent une attention particulière. Les utilisateurs ne verront que les informations pour les entités juridiques auxquelles ils ont accès.

Une commande client peut être placée dans la liste d’attente pour les raisons suivantes :
1. Le client a une facture en souffrance depuis un nombre de jours spécifié. 
2. La commande a un statut de compte spécifique.
3. La commande a des modalités de paiement spécifiques.
4. Le client a une limite de crédit expirée.
5. Le client a un montant en souffrance et a utilisé un pourcentage spécifié de sa limite de crédit
6. La commande client dépasse un certain montant.
7. Le client a dépassé un certain pourcentage de sa limite de crédit.
8. Les modalités de paiement diffèrent des conditions de paiement par défaut pour le client.
9. Les remises de règlement diffèrent de la remise de règlement par défaut pour le client.

Le motif de blocage est affiché pour chaque commande client dans la liste de blocage. S’il y a plus d’un motif pour la suspension, la raison apparaîtra comme **Plusieurs**. Vous pouvez utiliser le menu **Motifs de blocage** dans le volet Actions pour afficher tous les motifs pour lesquels la commande client a été mise en attente. Vous pouvez également consulter les **Motifs de blocage** dans un récapitulatif.

### <a name="releasing-orders-from-the-hold-list-for-processing"></a>Validation des commandes de la liste d’attente pour traitement

Lorsque vous avez recherché les motifs de la suspension et que vous les avez atténuées, vous pouvez libérer les commandes client pour un traitement ultérieur.

1) Sélectionnez une ligne dans la liste d’attente. Vous pouvez libérer plusieurs commandes en sélectionnant plusieurs lignes.
2) Sélectionnez un **Motif de libération** pour la commande qui a été sélectionnée pour la libération.  
3) Entrez la **Date de révision** pour chaque commande qui a été sélectionnée pour la libération.  
4) Sélectionnez le menu **Libération** dans le volet Actions pour libérer une commande. Ce menu ne sera disponible qu’après avoir sélectionné les transactions. L’utilisateur se voit proposer deux options :
   - Sélectionner **Avec validation** pour supprimer la mise en attente et publier le document en utilisant le même processus de publication que celui utilisé lors de sa mise en attente. Par exemple, si la confirmation de commande client était mise en attente, la confirmation de commande client serait terminée après la libération. Le formulaire de validation de la commande client sera affiché permettant à l’utilisateur de poster la confirmation.
   - Sélectionner **Sans validation** pour supprimer le blocage sans effectuer de traitement supplémentaire. La commande client peut être postée manuellement.

### <a name="rejecting-orders-in-the-hold-list"></a>Rejeter des commandes dans la liste d’attente
Vous pouvez utiliser le menu **Rejeter** dans le volet Actions pour refuser une commande client
1. Sélectionnez une ligne dans la liste d’attente. Vous pouvez libérer plusieurs commandes en sélectionnant plusieurs lignes.
2. La commande sera supprimée de la liste de blocage et l’en-tête de la commande client sera mis à jour pour indiquer que la commande a été rejetée.

### <a name="automatically-releasing-credit-management-holds"></a>Libération automatique des blocages de gestion du crédit
Les commandes client sont placées dans la liste de blocage en fonction des règles de blocage. Cependant, certaines raisons des blocages peuvent changer au fil du temps si la commande client reste dans la liste des blocages pendant un certain temps. Par exemple, un client peut payer sa facture, libérant ainsi sa limite de crédit. 

Vous pouvez utiliser le menu **Évaluer pour libération** pour consulter les commandes client dans la liste de blocage et les libérer automatiquement si le motif du blocage a été atténué.
1.  Sélectionnez le menu **Évaluer pour libération**
2.  Sélectionnez **Traiter les règles de blocage** pour revoir toutes les commandes client. Sélectionnez **Traiter les règles de blocage pour les lignes sélectionnées** pour revoir uniquement les lignes que vous avez sélectionnées.
3. Un curseur apparaîtra pour vous permettre de sélectionner un seul client. Laissez le menu déroulant client vide pour tous les clients. 
4. Lorsque vous cliquez sur OK, le processus est exécuté en arrière-plan et vous pouvez continuer à travailler sur d’autres tâches. Si vous sélectionnez le traitement par lots avant de cliquer sur OK, le processus s’exécute en lot lorsque vous cliquez sur OK. Le traitement des commandes en attente dans la liste peut prendre un certain temps. Utilisez donc Actualiser pour mettre à jour le statut des commandes. 
5.  Si un motif de blocage n’est plus applicable pour une commande, le motif de blocage sera considéré comme n’étant plus valide et vous ne verrez plus de coche à côté du motif lorsque vous afficherez les motifs de blocage.
6.  Si tous les motifs de blocage sont supprimés, un nouveau motif, **Prêt pour libération**, est ajouté à la liste des motifs de blocage. La commande client peut être libérée automatiquement.
7.  Si le paramètre **Libérer automatiquement** dans l’onglet **Crédits et recouvrements > Paramétrer > Paramètres de crédits et recouvrements > Crédits > Libération automatique** est défini sur **Avec validation**, vous serez invité à valider à l’aide du formulaire de validation du document qui a été bloqué.
8.  Si le paramètre **Libérer automatiquement** dans l’onglet **Crédits et recouvrements > Paramétrer > Paramètres de crédits et recouvrements > Crédits > Libération automatique** est défini sur **Sans validation**, vous devez valider la commande manuellement.

### <a name="credit-management-approval-workflow"></a>Workflow d’approbation de la gestion des crédits

Vous pouvez également créer **Workflows de gestion de crédit** pour contrôler le déblocage des crédits. Une fois que vous avez configuré le flux de travail à l’aide de la page **Gestion des crédits > Paramétrer > Workflows de gestion des crédits**, les commandes marquées pour la libération ou le rejet seront envoyées au workflow où elles doivent être approuvées avant d’être libérées ou rejetées. 

Si vous incluez les tâches de libération avec validation ou de libération sans validation dans votre workflow, l’approbation du workflow libérera également la commande client. Cependant, en cas d’échec du processus de libération en raison d’informations de configuration manquantes ou d’autres causes, vous devrez rappeler la commande client à partir du workflow, résoudre le problème à l’origine de l’échec, puis soumettre à nouveau la commande au workflow.

Si vous n’incluez pas les tâches de libération avec validation ou de libération sans validation dans votre workflow, le processus d’approbation de workflow vous permettra simplement de libérer manuellement la commande client une fois l’approbation terminée.

### <a name="forced-credit-hold"></a>Retenue de crédit forcée  
  
Parfois, les commandes client doivent être bloquées même si la commande ne répond pas aux critères des règles de blocage. Par exemple, un gestionnaire de crédit peut être informé d’un problème non lié au crédit avec le client et décider de suspendre manuellement les commandes immédiatement jusqu’à ce que le problème soit résolu. Vous pouvez forcer manuellement la suspension d’une commande client si cette situation se produit.

1. Ouvrez la commande client que vous souhaitez mettre en attente.  
2. Sélectionnez **Forcer le blocage du crédit** dans l’onglet **Gestion de crédit** sur le volet Actions **Gestion de crédit**.
3. Sélectionnez un **Motif du blocage forcé**.
4. Cliquez sur **OK.** La commande client sera renvoyée dans la liste de blocage de la gestion des crédits.

Vous pouvez également forcer la suspension de plusieurs commandes à l’aide de la page **Gestion des crédits > Tâches périodiques > Forcer le blocage des crédits**. Par exemple, vous pouvez placer toutes les commandes client en attente pour un client spécifique.
1. Sélectionnez le **Motif du blocage forcé**. 
2. Cliquez sur **Dossiers à inclure** pour sélectionner les commandes client à mettre en attente. 
3. Cliquez sur **OK** pour traiter les commandes client sélectionnées.

Les commandes client qui ont été suspendues de force ne peuvent pas être traitées avec le workflow.

#### <a name="releasing-orders-that-were-added-to-the-credit-management-hold-list-with-a-forced-credit-hold"></a>Libération des commandes qui ont été ajoutées à la liste de blocage de la gestion des crédits avec un blocage forcé des crédits
Les commandes client qui ont un motif de blocage forcé ne peuvent pas être libérées automatiquement. Si la commande client a été suspendue de force et que vous avez utilisé un processus qui libère automatiquement les commandes client, la commande client s’affiche comme **Prête pour libération** et reste dans la liste d’attente. Vous devez utiliser le menu **Libération** pour libérer la commande.
 
## <a name="free-text-invoices-orders-and-project-invoice-support-in-credit-management"></a>Prise en charge des factures financières, des commandes et des factures de projet dans la gestion des crédits 
La gestion des crédits ne peut actuellement être utilisée que pour les commandes client. Les factures financières, les commandes au point de vente et les commandes au centre d’appels utiliseront les limites de crédit temporaires et les assurances/garanties que vous ajoutez pour ajuster la limite de crédit. Ils n’utiliseront pas les règles de blocage et ne seront pas placés dans la liste de blocage en cas de problème avec la limite de crédit.

Il n’y a pas de prise en charge des factures de projet dans la gestion du crédit.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
