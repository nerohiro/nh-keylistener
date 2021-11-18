# nh-keylistener
A basic Key listener for RedM

# Information
I made this when i first found out that there was no RegisterKeyMapping available for RedM, so until there is, this resource will help you optimize your framework by using it as a wrapper to prevent having multiple loops throughout your resources, instead just relying on the events it sends to process the information.

As i find more keys to add with proper names I'll update this resource.

# Setup
It's pretty simple, once you drop the nh-keylistener resource into your resources folder just make sure you put

`ensure nh-keylistener`

in your server.cfg.

and placing the corrisponding event in any resource you would like to use it on. very simple and efficient!

# Examples
Here is an example of how I used this to reduce the resource usage of my scenes script, without having these loops running on multiple resources, it might have a decently high usage, but will save that usage from your other resources. (my usage is about 0.08ms~)
```
RegisterNetEvent("nh-keylistener:keyPressed", function(eKeyPress)
    if eKeyPress == "DEL" then
        DeleteScene()
    elseif eKeyPress == "RIGHTBRACKET" then
        HideScenes()
    end
end)

RegisterNetEvent("nh-keylistener:keyReleased", function(eKeyPress)
    if eKeyPress ~= "HOME" then return end
    CreateScene()
end)

```
# Known Bugs
No Known Issues

# Support
Feel free to report any issues you have in the GitHub [Issues](https://github.com/nerohiro/nh-keylistener/issues)

if you wish to add something to it, do a pull request on the github [Pull Requests](https://github.com/nerohiro/nh-keylistener/pulls)


