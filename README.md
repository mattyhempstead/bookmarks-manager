# Bookmarks Manager
Just writing this as a possible bookmarks manager project to make in the future.

I'm somewhat reluctant to use a regular bookmarks with its own backend that stores all my links.
This is due to
 - Security Concerns
   - I likely will store private links that I don't want people having access to, and this has a risk of being hacked.
   - Even if encrypted, you would have to really convince me this is not a concern (and that a future bug/exploit won't allow circumvention - e.g. hackers getting full control over servers)
 - Reliability
   - I don't want to have any downtime while you are pushing new updates that I don't care about
   - I *definitely* don't want to permanently lose my bookmarks if the server experiences a data loss
 - Cross Platform Fallback
   - I want to be able to use my bookmarks normally if the extension stops working or I use a platform that doesn't support it.
 - Other stuff probably


Chrome already syncs the backend to gmail accounts which imo is a great UX.

The data that is synced is a folder tree, where the files are "bookmarks" in the form of a name (string) and url (string).

If we imagine the URLs as key-value pairs, we could actually represent the bookmarks bar as a JSON object.

If we create a bookmarks folder, say `.metadata`, we could use this folder to store any data related to our bookmarks extension.
This data would be synced automatically across google accounts, and would not get in the way when you are using the fallback which is the default bookmarks bar since you can just hide that folder.

Given this, we could now build a new view to the bookmarks bar that contains whatever we want (better UI, notes/tags attached to bookmarks, search, new objects entirely) that requires no backend.

A good start would just be a simple "tagging" system to the existing bookmarks bar that lets you easily search bookmarks.
The tagging data would be stored in our `.metadata` folder and would then work seamlessly with the existing bookmarks syncing mechanism.


There is probably a limit to the number of bookmarks (maybe 100k), but that is probably unlikely and can be addressed later (if reached, we could spin up a server just for the 80:20 feature).


Maybe this already exists, and maybe I would still come up with an excuse to not use it mostly bc I just wanna make my own as a project.

