This is a zero_push module and also modified Mongooseim  version of https://github.com/ZeroPush/mod_zeropush  


# mod_zeropush (Mongooseim)
Mongooseim Module for sending push notifications via ZeroPush

mod_zeropush sends an API request to ZeroPush when a message is sent to an offline user.

The notification contains the following URI-encoded payload:

{
    "auth_token": "{config-auth_token}",
    "channel": "{recipient-jid}",
    "alert": "{chat-message-body}",
    "badge": "+1",
    "sound": "{config-sound}",
    "info": {
        "from": "{sender-jid}"
    }
}


How to compile erl file to get mod_zeropush.beam  :

Make sure you have erlang installed on the machine you are building from

1) Clone latest Mongooseim from github 
2) Place mod_zero_push.erl file in Mongooseim source code path <Mongooseim>apps/ejabberd/src/
3) <Mongooseim> sudo make 


If you dont have souce repository and installed Mongooseim from executable file 

Copy the *.beam files from the ebin directory to the location where the other modules are for your server( mail to me i.aadi07@gmail.com to get  beam file )

Add the configuration from below


Configuration

in ejabberd.cfg

{mod_zeropush, [
    {sound, "default"},
    {auth_token, "your-auth-token"},
    {post_url, "https://api.zeropush.com/broadcast"}
]}
