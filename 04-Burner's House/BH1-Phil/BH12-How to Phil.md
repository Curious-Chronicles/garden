---
type: work
index: BH12
tags: work, how-to, phil
created: <%+ tp.file.creation_date("dddd Do MMMM YYYY") %>
updated: <%+ tp.file.last_modified_date("dddd Do MMMM YYYY") %>
---
Related: 
- {{related to}}

Tickets: 
- [Add Truepill response in the comment section](https://phildotus.atlassian.net/browse/FFE-302)

----

# How to test Copay for Truepill

1.  Go to test file: `tests/truepill_api_test.go`
2. Start your CAPI
3. Create an order, to one of the truepill PP location. 
4. Now remove the `xx` in front of `Testxxx` func for func `xxTestCopayRequest`
5. Put the rxID from the newly created order. 
6. Before you start test debug, make sure you have a debugger placed on `https://github.com/phil-inc/capi/blob/2a8189a6fd13875720cf07358205e60351eb6d5c/service/partners/truepill/copay_request.go#L133`
7. Launch the test debug. 
8. At the debugger location, copy the RequestID. 
9. Go to test file again and search for `xxTestHandleCopay` and put that RequestID there. 
10. Start the test debugger again. 
11. Now go to OPS Dash, you will see the copay commit there.


