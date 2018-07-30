# bigelowdemo
D1.1. EOMB node:
As an EOMB, user must supply the data about attributes: field/category of industry/service; data of business’s activities; expected Enterprise value...
In DD, it was built for a shortened version of above attributes and included some parameters behalf of them:
D1.1.1.First group of attributes: identity 
<Party>: user declares this node is EOM Business (EOMB node)
<Name>: It may be secret in reality, but in demo, it’s public for testing easily
D1.1.2 Second group of attributes: abilities 
<Field>: user chooses which industry field this EOMB is
<Profitability>: the profitable number
<Capital>: the capital requirements
D1.1.3 Third group of attributes: expectations 
<Value>: the expected value that business offers. Similar <Name>, <value>may be secret in reality, but in demo, it’s public for testing

D1.2. IN node: investors node
In demo, all investor types were behalf of one type node. User supply the informations for attributes of IN node
D1.2.1.First group: identities 
<Party>: IN node
<Name>: public for testing easily
D1.2.2 Second group of attributes: abilities 
<Value>: declares the possible value that investor can accept
D1.2.3 Third group of attributes: expectations 
<Field>: chooses the field of EOMB that investor interests 
<Profitability>: the profitable number of EOMB that investor expects
<Capital>: the capital requirements of EOMB that investor expects

Can see that the ‘abilities’ attribute on EOMB node is the ‘expectations’ attribute on IN node then swapped, ‘abilities’ on IN node is the ‘expectations’ on EOMB node. DD presented a basic mechanism between buyers and sellers, this node’s supply will be compared with other node’s demand if the same <field>.
When DD executing, smart contract will do the comparison for each node that’s running it
when a EOMB-node encounters IN-node that have the same <field> , ‘abilities’ of this node will be compared with ‘expectations’ of other node and vice-versa.
Then report the difference of attributes between each node, 
e.g the <Value> in ‘abilities’ of IN-node is lower than <Value> in ‘expectations’ of EOMB-node
When IN-node or EOMB-node encounters the node like itself (IN-IN buyer-buyer,EOMB-EOMB seller-seller), smart-contract will ignore the comparison, continue ignoring when a IN-node encounters EOMB-node but not same <field> (e.g retail vs transportation, seller can’t sell what buyer unwanted)

D.1.3. The Report
D1.3.1.The report in EOMB-node presents all IN-nodes that are same <field> with it. The list of IN-nodes is sorted by higher <Value>. Any IN-Nodes that chaffer highest <value> will be on top. (In full version, the rank would be sorted by some different priority criteria)
The report also presents the comparison of each attribute between EOMB and IN, that helps to evaluate the similarities between the two parties.(in full version, they will be public or hidden depend on Bigelow’s strategy)

D1.3.2.The report in IN-node
The report in IN-node presents all EOMB-nodes that are same <field> with it and the comparison of each attribute between EOMB and IN, (in demo, they are public to test). 
On each result-Line of reported EOMB, there is a notification on the rank of current IN-node where is it in EOMB’s positive investors list. In demo, if current IN-node is one of two investors that are topping in which EOMB report, the notification is ‘you are in top 2 of positive investors ranked in “that” EOMB’s list’
In full version, the notification would be ‘you are in top 100’ or top 200, top 50 depends on the tactic.
Investors can rely on reports to adjust their chaffered value (reorder smart contract) for increasing their posibility to own the business they desire.
