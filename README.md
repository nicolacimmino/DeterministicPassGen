DeterministicPassGen
====================

## What this is

A simple Chrome extension that is meant more as an exercise than a complete tool. It demonstrates how to create a basic Chrome extension, grab the current tab URL and exctract the domain from it. It also shows how to alter the user clipboard content.

## What this is NOT

An high security tool that can replace all your passwords. If your current password is 'guessme' in all your accounts this might actually better the situation, I cannot guarantee though that it is safe. 

## How it works

Once the extension is installed you should get a padlock symbol by the address bar. You click on the padlock and type a generic master password and the extension will place in your clipboard a password that is unique for the domain of the website of the current tab. All you need to do is to CTRL-V it in the password field of your website. As long as you type the same master password and you are on the same website you will get the same password generated (hence the 'deterministic' in the name).


![Extension](https://raw.github.com/nicolacimmino/DeterministicPassGen/master/ScreenShot1.png)


## Is it safe(er)?

If the biggest risk is, as it often happens, that the database of a service provider is leaked then this provides better secuirity than same password on every site as you get a different password per web site (but still you have to remember only one master password). It also generates very long passwords that are not going to be in any rainbow table used by hackers to find hashed passwords.

Please remember that if you lose the master password there is no way to generate the derived passwords and that actally changing every website password to the generated one means that if you find yourself on a machine where the extension is not available you won't be able to get the password.

Keeping the above in mind this can be a viable solution to keep every web site password different while having to remember only one password.

## Possible improvements

I have left this exercise as it is since I wasn't interested in perfecting it further, my focus being just to understand how Chrome extensions work. One idea to make things better could be to generate the password based on the typed master password and another long sequence that could be stored in the browser local storage, so the user needs to enter it only once (a sort of certificate). Additionally rather than just concatenating what goes into the hash it would be safer to use an HMAC-256 for the hasing (http://en.wikipedia.org/wiki/Hmac) which is more suitable than hash of the concatenated values for this purpose.


## Installation

Copy all the content of the src folder to a local folder, go to Chrome menu and under "Tools" open "Extensions". Here you will have an option to load an unpacked extension, choose that and browse to the folder where the code is. You are done. You should have the extension loaded as in the screenshot below.


![Extension](https://raw.github.com/nicolacimmino/DeterministicPassGen/master/ScreenShot0.png)
