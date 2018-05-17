# Firefox password field focus bug
This extension contains a popup with a single password input field set to autofocus.

## Why
When a password field is set to focus, Firefox automatically closes the popup.

## Where
This issue is reproducable on Ubuntu 18.04 LTS using Firefox versions:
- Firefox Quantum 60.0 (64-bit)
- Firefox Nightly 62.0a1 (2018-05-16) (64-bit)


## How to test 
1. Clone this repo
2. Open `about:debugging`
3. Enable add-on debugging
4. Click `Load Temporary Add-on` and select the cloned `manifest.json`
5. Click the newly added extension in your toolbar. 

## Expect results
The popup should open and focus the password field, allowing users to input a password. 

## Actual results
One of two things generally happen:
1. The popup never opens.
2. The popup opens but doesn't allow input or focus of the password field and then closes automatically.

## Taking it a step further
Disabling `ui.popup.disable_autohide` in `about:config` allows the popup to stay open long enough for a user to manually focus the password field. Once focused the password field appears to accept input normally. However, this is clearly not a viable workaround to this bug. 