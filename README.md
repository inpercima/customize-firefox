# customize-firefox

[![MIT license](https://img.shields.io/badge/license-MIT-blue.svg)](./LICENSE.md)

With Mozilla Firefox 57 many addons are no longer usable.
The new addon mechanism of WebExtensions disallow modifications to the UI.
I used addons like [Tab Mix Plus](https://addons.mozilla.org/de/firefox/addon/tab-mix-plus/) to modify the tabbar.
I have searched for methods to allow minimal changes to the UI myself.
This repository contains a few features of old addons.

## How does it work

The changes are made with CSS.
You can modify the UI with the following procedure:

1. Find your profile folder

   Type in the address field of the toolbar **about:support** to open the information from firefox.
   Search for **profile folder** (german: Profilverzeichnis) and click the button **Open folder**.

2. Check for the chrome folder

   If you are inside your profile folder, check the existence of the subfolder **chrome**.
   Create if not exists.

3. Create file userChrome.css

   Create the file **userChrome.css** inside the **chrome** folder.
   With this file inside your browser profile you can modify the UI of firefox.

4. Add modifications

   Finally add the CSS parts from this page you want.
   You need to restart firefox to get the changes work.

## Customizations

### small bookmarks without loosing text

![bookmark-small](https://github.com/inpercima/customize-firefox/blob/master/images/bookmark-small.png)

```css
.bookmark-item .toolbarbutton-text {
    display: none !important;
}
```

### Tabs under toolbar and bookmarks

[Reference](https://support.mozilla.org/de/questions/1185426)

![tab-bottom](https://github.com/inpercima/customize-firefox/blob/master/images/tab-bottom.png)

```css
/* place nav-bar first */
#nav-bar {
    -moz-box-ordinal-group: 1 !important;
    border-top-width: 0 !important;
    margin-top: 0 !important;
}

/* place bookmarks second */
#PersonalToolbar {
    -moz-box-ordinal-group: 2 !important;
}

/* place tabs third */
#TabsToolbar {
    -moz-box-ordinal-group: 3 !important;
}

/* correct margin on moving tabs */
#TabsToolbar[movingtab] > .tabbrowser-tabs {
    padding-bottom: 0 !important;
    margin-bottom: 0 !important;
}

#TabsToolbar[movingtab] {
    padding-bottom: 0 !important;
}

/* background of tabbar */
#TabsToolbar #tabbrowser-tabs {
    background-color: var(--toolbar-bgcolor) !important;
    background-image: var(--toolbar-bgimage) !important;
}

/* color of tabs */
#TabsToolbar #tabbrowser-tabs .tabbrowser-tab .tab-content {
    color: #000 !important;
}
```

### Unread, pending tabs

[Reference](https://developer.mozilla.org/en-US/docs/Mozilla/Tech/XUL/tab)

![tab-unread-pending](https://github.com/inpercima/customize-firefox/blob/master/images/tab-unread-pending.png)

```css
#TabsToolbar #tabbrowser-tabs .tabbrowser-tab[pending] .tab-content, #TabsToolbar #tabbrowser-tabs .tabbrowser-tab[unread] .tab-content {
    color: red !important;
    font-style: italic !important;
}
```

### Unread, pending, blinking tabs

![tab-unread-pending-blinking](https://github.com/inpercima/customize-firefox/blob/master/images/tab-unread-pending-blinking.gif)

```css
#TabsToolbar #tabbrowser-tabs .tabbrowser-tab[pending] .tab-content, #TabsToolbar #tabbrowser-tabs .tabbrowser-tab[unread] .tab-content {
    animation: blinker 1s linear infinite;
}

@keyframes blinker {
    50% { opacity: 0; }
}
```

## How can I change the style myself

If you want to create your own changes you can use Mozilla Firefox extensions.
You can explore the browser as well as explore web pages.

Described for version 61+

1. Open the **Development tools** (F12 or Ctrl+Shift+I)
2. Click on 'Customize Tools and get help' button on the right side (button with three dots)
3. Click on 'Settings'
4. Go to the extended section
5. Enable **browser chrome and add-on debugging toolboxes** and **remote debugging**
6. Open the **browser tools** with Ctrl+Alt+Shift+I

Now you can like the normal **Development tools** inspect the browser ui elements.
