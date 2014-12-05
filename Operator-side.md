# Data Info API (Operators)

## This Document
This document will detail a route to implement the Data Info API on the Operator side. This will look at issues, likely questions, a brief architecture and other related items.

### Each Operator is Different
We understand that each operator is different and any system given below will not be compatible will all operators. Saying this, operators should feel free to use this information as a guideline on how such a system could work, and also should feel free to suggest edits where needed by issuing a Pull Request. 

## APIs
This project's goal is to develop an API for use on web applications and operating systems. For this to work a number of APIs will need to be developed which will integrate with mobile network operator systems. Below is a description of each.

 **Web APIs:**
Allows a web application to query the current status of the data connection through the navigator object.
	 
**Device API:**
Allows native applications to query the current status of the data connection see p [Windows 8 Networking](http://msdn.microsoft.com/en-gb/library/windows/apps/windows.networking.connectivity.aspx) for an example.

**Carrier API:**
Allows the browser or Native OS to access information about the cellular subscribers data allowance and current connection via an authenticated request.

Note: Web apis could happen, but a device api is easier

## Issues
As stated above every operator is different, so a number of hurdles may need to be jumped to achieve this goal. Saying this, the Data Info API will standardise the APIs syntax and expected functionality, but not it's implementation. Therefore, each operator could implement their end in a different way. 

Invisioned issues are listed below to help create an API which can achieve this goal.

__Billing System Issues:__
* __Operator Billing Systems__: are often highly bespoke and do not necessarily have the capabilities to work out a live snapshot of the data plan usage.
* __Complexity:__ Billing systems are often quite segregated in the IT infrastructure of the operator therefore finding a way to them could be complex and adding the server side capability could take some time 
* __Security:__ Operators must make sure that any route to the billing system is safe from attacks (e.g. DDoS)
* __Account Types and Separate Billing Systems:__ There can be separate billing systems for pre-pay and post-pay customers. 
There are EU controls on roaming data price/ volume caps which can also come into play.
* __Bill shock:__ Need to make sure the user’s bill then matches the costs which are showing on their device as an outcome of the Data Info API. 

__Legal Issues:__
* __Legal__: Some countries might think the information about plans/ balances is protected by data protection (i.e. knowing you only have a pre-pay account might make you a higher credit risk).

__Device Based Issues:__
* Which device:__ In certain use cases e.g. Personal hotspot, MiFi devices where the application could be running on a device with its own SIM but using a (private or shared) mobile data connection with a different SIM. So if you run the query should you get results for which device?

__Time Base Issues:__
* __Delays:__ There is often a five minute delay for Data Plan information.
  * __Roaming:__ Could be more instantaneous if the user is roaming, depends on the foreign carrier. Some will be up to date, some just send a CSV three days later!
  * __Type of Roaming__: international roaming versus US roaming

## Data Plan Types
There are many types of Data Plans which need to be considered. Below is a non-exhaustive list (trying to become exhaustive!):
* Pre-pay
* Post-pay
* Shared Data Plans
* Unlimited data
* Zero-Rating

For each plan above the designers should also consider __international  roaming__ and __within country roaming__ which can occur for each plan listed above.  

### Authenticate the customer against the device 
How do we do this?
oath could work
sms could also work
silent sms on ffos

### Operator FAQ
Operators are likely to receieve a number of questions related to this API and how it works. Below is a list of the expected questions and some answers
* __How does Authentication work?:__
* __Sharing user's data is against our privacy guidelines. How does the Data Info API ensure this?:__ The Data Info API is only interested in returning the user's Data Plan information back to the user or the operating system they are using. Exposure to other parties only includes:
 * What is the user's current connection bandwidth. Right now, if the user is on an 3G connection, we always indicate that it's a 3G connection to apps. However if the user's connection speed has been downgraded due to exceeding monthly data limits and the carrier effectively only allows transmission at 2G speed, we'd like to tell applications that the device is currently using 2G connection. Other forms of downgrades unrelated to the user's plan (for example a temporarily overloaded network) would not affect what we want to return. I.e. there's no information about when this connection speed might change. Nor do we plan to tell websites that the user is on a downgraded 3G connection. We simply plan to tell them that the user is on a 2G connection.
 * We have debated exposing the fact that the user is not on an unlimited data plan. I.e. expose the fact that the user is paying *something* per transferred byte. We don't plan to expose how much the user is paying, or what the various limits of the plan are. Just that it isn't free. This to enable websites to ask the user if it's ok before transferring a large file, like a video.


