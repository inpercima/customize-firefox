# Customizations for version 57-60

## Tabs under toolbar and bookmarks

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
#TabsToolbar .tabbrowser-tabs {
    background-color: var(--toolbar-bgcolor) !important;
    background-image: var(--toolbar-bgimage) !important;
}

/* color of tabs */
#TabsToolbar .tabbrowser-tabs .tabbrowser-tab .tab-content {
    color: #000 !important;
}
```

## Unread, pending tabs

[Reference](https://developer.mozilla.org/en-US/docs/Mozilla/Tech/XUL/tab)

![tab-unread-pending](https://github.com/inpercima/customize-firefox/blob/master/images/tab-unread-pending.png)

```css
#TabsToolbar .tabbrowser-tabs .tabbrowser-tab[pending] .tab-content, #TabsToolbar .tabbrowser-tabs .tabbrowser-tab[unread] .tab-content {
    color: red !important;
    font-style: italic !important;
}
```

## Unread, pending, blinking tabs

![tab-unread-pending-blinking](https://github.com/inpercima/customize-firefox/blob/master/images/tab-unread-pending-blinking.gif)

```css
#TabsToolbar .tabbrowser-tabs .tabbrowser-tab[pending] .tab-content, #TabsToolbar .tabbrowser-tabs .tabbrowser-tab[unread] .tab-content {
    animation: blinker 1s linear infinite;
}

@keyframes blinker {
    50% { opacity: 0; }
}
```
