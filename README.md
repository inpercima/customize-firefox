# Introduction
With Mozilla Firefox 57 many addons are no longer usable.
The new addon mechanism of WebExtensions disallow modifications to the UI.
I used addons like [Tab Mix Plus](https://addons.mozilla.org/de/firefox/addon/tab-mix-plus/) to modify the tabbar.

Due to the fact that many addons are no longer or not yet available I have searched for methods to allow minimal changes myself.
This repository contains a few features of old addons.

# How does it work?
The changes are made with CSS.
You can modify the UI with the following procedure:

1. Find your profile folder

   Type in the address field **about:support** of the toolbar to open the information from firefox.
   Search for **profile folder** (german: Profilverzeichnis) and click the button **Open folder**.

2. Check and/or create chrome folder

   If you are inside this profile folder, check the existence of the subfolder **chrome**.
   Create if not exists.

3. Create file userChrome.css

   Create the file **userChrome.css** inside the **chrome** folder.
   With this file inside your browser profile you can modify the UI of firefox.

4. Add modifications

   Finally add the CSS parts from this page you want.
   You need to restart firefox to get the changes work.

# Customizations

## Unread, pending tabs
[Source](https://developer.mozilla.org/en-US/docs/Mozilla/Tech/XUL/tab)
![](https://github.com/inpercima/customize-firefox/blob/master/images/tab-unread-pending.png)

```css
#TabsToolbar #tabbrowser-tabs .tabbrowser-tab[pending] .tab-content, #TabsToolbar #tabbrowser-tabs .tabbrowser-tab[unread] .tab-content {
    color: red !important;
    font-style: italic !important;
}
```

## Tabs under toolbar and bookmarks
[Source](https://support.mozilla.org/de/questions/1185426)
![](https://github.com/inpercima/customize-firefox/blob/master/images/tab-bottom.png)

```css
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
```

# How can I change the style myself?
If you want to create your own changes you can use Mozilla Firefox extensions.
You can explore the browser as well as explore web pages.

1. Open the **Development tools** (F12 or Ctrl+Shift+I)
2. Click on the the setting icon on the right side
3. Go to the extended section
4. Enable browser chrome and add-on debugging toolboxes
5. Enable remote debugging
6. Open the **browser tools** with Ctrl+Alt+Shift+I

Now you can like the normal **Development tools** inspect the browser elements.
