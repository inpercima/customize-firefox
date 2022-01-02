# Customizations for version 61+

## pending tabs

![tab-pending](https://github.com/inpercima/customize-firefox/blob/master/images/tab-unread-pending.png)

```css
#TabsToolbar tab[pending] .tab-label {
    color: red !important;
    font-style: italic !important;
}
```

### pending, blinking tabs

![tab-pending-blinking](https://github.com/inpercima/customize-firefox/blob/master/images/tab-unread-pending-blinking.gif)

```css
#TabsToolbar tab[pending] .tab-label {
    animation: blinker 1s linear infinite;
}

@keyframes blinker {
    50% { opacity: 0; }
}
```

### busy tabs

```css
#TabsToolbar tab[busy] .tab-label {
    color: red !important;
    font-style: italic !important;
}
```

### unread tabs, works with [https://addons.mozilla.org/en-US/firefox/addon/tab-flag/](https://addons.mozilla.org/en-US/firefox/addon/tab-flag/) only

```css
#TabsToolbar tab[titlechanged] {
    color: red !important;
    font-style: italic !important;
}
```

### unread, bliking tabs, works with [https://addons.mozilla.org/en-US/firefox/addon/tab-flag/](https://addons.mozilla.org/en-US/firefox/addon/tab-flag/) only

```css
#TabsToolbar tab[titlechanged] {
    animation: blinker 1s linear infinite;
}

@keyframes blinker {
    50% { opacity: 0; }
}
```
