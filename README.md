SMS Gateway API XML Configuration
================================

This is an XML configuration file for sending SMS messages using the SMS Gateway Hub API.

File Structure
--------------

The XML file consists of two main sections:

* `<Account>`: Contains API key, sender ID, and other account settings.
* `<Messages>`: Contains a list of SMS messages to be sent.

Requirements
--------------

* xmltodict
* requests

Elements
---------

### `<Account>`

* `<APIKey>`: Instead of the username and password you can use the API KEY https://www.smsgatewayhub.com/Panel/WebAPI/APICodes.aspx for authentication of account.
* `<SenderId>`: Approved sender id(6 characters string only).
* `<Channel>`: The channel to use for sending SMS messages (e.g., Message channel Promotional=1 or Transactional=2).
* `<EntityId>`: Your entity ID.
* `<DCS>`: The data coding scheme to use (e.g., 0 for plain text and Set 8 for unicode sms).
* `<FlashSms>`: Flash message immediate display (Default is 0 for normal sms, Set 1 for immediate display)
* `<Route>`: Pass the route id in this parameter to route the message. Click Here for more information regarding your routeid.

### `<Messages>`

* `<Message>`: A single SMS message to be sent.
	+ `<Number>`: Recipient mobile number (pass with (,) comma seprated if need to send on more then one number).
	+ `<Text>`: The message content.
	+ `<DltTemplateId>`: The DLT template ID (optional).

Example
-------

Here is an example XML file:
```xml
<SmsQueue>
    <Account>
        <APIKey>6f9XXXXXXX</APIKey>
        <SenderId>XXXXXX</SenderId>
        <Channel>2</Channel>
        <EntityId>13011XXXXXXXX</EntityId>
        <DCS>0</DCS>
        <FlashSms>0</FlashSms>
        <Route>1</Route>
    </Account>
    <Messages>
        <Message>
            <Number>9144XXXXXX</Number>
            <Text>XXXXXXXX</Text>
            <DltTemplateId>130716XXXXXXXXX</DltTemplateId>
        </Message>
    </Messages>
</SmsQueue>
