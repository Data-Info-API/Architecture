# Use Cases

## This Document
This document details use cases for the Data Info API.

## Indicate to the user why they cannot access data
Right now it's really hard for the user to know if they aren't able to access the internet because they don't have "enough bars", or if it is because they have consumed their allowed amount of data. The device could instead indicate to the user "no connection as your prepaid account is empty. You have to buy more or wait until X in order to get more data access...". This could both reduces the number of customer-service related phone calls, and presents an opportunity to upsell.

### Throttling Case
The same thing could of course be done if the user is throttled rather than have their connection cut off. I.e. the device could display to the user something to the extent of "your internet is slow because X. Do Y in order to fix it".

## Off Peak Update / Download
The user may want to allow app updates on mobile networks. A mobile network data could "cost" more during peak hours than on non-peak hours. The operating system could use this information to allow / disallow app updates during peak hours.  Likewise the operating system should know if the concept of peak/off-peak is not applicable for the user, user's tarriff or mobile network  in question.

## Throttling for streaming in youtube
A user attempts to stream content from a content streaming site such as youtube or netflix. The user is alerted that they:

* may not be able to watch the entire video as they do not have the required data allowance left
* cannot watch any of the video as they do not have any data allowance left
* informs the user of what they can do to mediate this (wait till a new date or buy more data plus click through to the operator page to buy more).

## Zero Rating
Zero rating information could be more clearly displayed to the user allowing them to view or make choices about apps.

* the app should be able to know whether the data it is consuming is zero-rated (and display an appropriate alert to the user)
