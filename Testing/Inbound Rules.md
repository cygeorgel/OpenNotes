# Inbound Rules

## Inbound Rule  creation/edition view :

![inbound](https://storage.gra.cloud.ovh.net/v1/AUTH_9c30d35f284f44b2bda08609e7c19f33/cyrille_public/20241017051045_PSDfq85Ua79iCu5yfjkhpTSAKQgQl0tSn3Z4XZn2cnsxRfpAhGPwJTuboT8P2c3PU4vCx0ecgjhwPFBq.png)


On the view where the user create/edit a new inbound rule:

Could you replace "Host" by PBX

Could you replace "Name" by "Nom de la règle entrante"

Could you replace "Type" by "Type de resource attachée à la  règle entrante".

Could you replace "Numéro" by "Ressource attachée à la règle entrante".

Could you replace "Type de destination par défaut" by "Type de destination par défaut en dehors des heures d'ouverture"

Could you replace "Numéro de destination" by "Destination par défaut en dehors des heures d'ouverture"

Those 2 values "Type" and "Destination" being linked one to each other, I would like to see them either on the same line or on the same column. My preference being for same line.

Same for the 2 values "Type de destination par défaut en dehors des heures d'ouverture" and "Destination par défaut en dehors des heures d'ouverture". My preference being for same line

My suggestion would be to have the PBX and the rule name, then the two others.

When a field in not filled out, could you put the message in French : "Veuillez compléter ce champ"

All the messages should now refer to "inbound rule" instead of "call queue", especially when successfully creating a rule : "Règle entrante enregistrée avec succès"

The user do not understand from this view, that he will be redirected to another view to define the slots and days. So I would like to add this text at the bottom of the form : "Une fois la règle entrante créée, vous serez redirigé vers un second formulaire vous permettant de configurer les plages horaires et les jours exceptionnels lui correspondant."

Also : 

If a resource is already attached to an existing inbound rule, it should not be available here. The best option should be to show it but make it impossible to select. Concertation with Thomas probably needed on this  point, in order to see how we do the filter.

**Please note:**

An item I forgot : are we right to make the rule name mandatory? I think it makes sense, but then we should show it with a star, like for the other elements.
## Inbound rule configuration view

First of all, here in the index :

![](https://storage.gra.cloud.ovh.net/v1/AUTH_9c30d35f284f44b2bda08609e7c19f33/cyrille_public/20241024122914_2RYFH30wqfuugRgUbMHgpXKv3sH1vinNOvmdMx7hM2Z5Mym3nT9OS4J5fYvsMHPMpWJxeMQvxiVqyO9f.png)

In order to match the names,  could we have the titles as : 
-  "Nom de la règle"
- "Active" (feminine form)
- "Type de ressource"
- "Ressource"

Check errors with some parameters.

Check if all values are correctly saved.

In the header here, could you use the resource type, "type de ressource attachée  à la règle entrante", for example "803 (File d'attente)"

![](https://storage.gra.cloud.ovh.net/v1/AUTH_9c30d35f284f44b2bda08609e7c19f33/cyrille_public/20241024124007_JOzlqR77oBdEpmoVeBk4yVdFcbwSr3KNZPsVnxFZB3Y71jx8UdukAZgY8Q0b9iyHHplgRLaPuX1Efm8M.png)











