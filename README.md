# Introduction
With Mozilla Firefox 57, many addons are no longer usable.
With the new WebExtensions, no modifications to the UI are possible but CSS lets you edit the elements.
This repository contains a few ways in which old features of addons can be restored.

# How it works
With a file **userChrome.css** inside your browser profile you can modify the UI of firefox.

To find the browser profile folder type in the address field **about:support** to open the information site from firefox.
Search for **profile folder** (german: Profilverzeichnis) and click the button **Open folder**.

If you are inside this profile folder, check the existence of the subfolder **chrome**. Create if not exists.
Create the file **userChrome.css** inside **chrome**.

Finally add the CSS parts from this page you want.
You need to restart firefox to get the changes work.

# Customizations
## Unread, pending tab

    #TabsToolbar #tabbrowser-tabs .tabbrowser-tab[pending] .tab-content, #TabsToolbar #tabbrowser-tabs .tabbrowser-tab[unread] .tab-content {
        color: red !important;
        font-style: italic !important;
    }

-> https://developer.mozilla.org/en-US/docs/Mozilla/Tech/XUL/tab

## Tabs under main toolbar and bookmarks toolbar

    #TabsToolbar #tabbrowser-tabs {
        background-color: var(--toolbar-bgcolor) !important;
        background-image: var(--toolbar-bgimage) !important;
    }

    #TabsToolbar #tabbrowser-tabs .tabbrowser-tab .tab-content {
        color: #000 !important;
    }

    #TabsToolbar #tabbrowser-tabs .tabbrowser-tab[pending] .tab-content .tab-label-container .tab-text, #TabsToolbar #tabbrowser-tabs .tabbrowser-tab[unread] .tab-content .tab-label-container .tab-text {
        color: #f00 !important;
        font-style: italic !important;
    }

-> https://support.mozilla.org/de/questions/1185426

# How do I change the style myself?
To get the CSS classes from the elements you need to activate the **broeser tools**.
1. Open **Development tools** (F12 or CTRL+SHIFT+I)
2. Click on the right side the setting icon
3. Go th the extended section
4. Enable browser chrome and add-on debugging toolboxes
5. Enable remote debugging
6. Open with CTRL+ALT+SHIFT+I the **browser tools**

Now you can like the normal **Development tools** inspect the browser elements.

