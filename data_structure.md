## Types of data logged by togetherjs

1.  cursar-update
2.  idle-status
3.  chat (chat.js)
<pre>
        text: msg.text,
        date: Date.now(),
        peerId: msg.peer.id,
        messageId: msg.messageId
</pre>
4.  key-down
5.  form-focus
6.  scroll-update

Currenly, all of this data is just logged into Logger, and can be viewed in the server log. This data is temporarily stored in user's cache(chrome's storage.tab variable), and once the session is over(when the user closes togetherjs), the data is lost.

### Goal:

To store the data in a mongodb/mysql database.

MongoDB - Structure:
<pre>
Collection -> chat
{
        {
                text: msg.text,
                date: Date.now(),
                peerId: msg.peer.id,
                messageId: msg.messageId 
        },
        {
                text: msg.text,
                date: Date.now(),
                peerId: msg.peer.id,
                messageId: msg.messageId 
        }...
}
</pre>