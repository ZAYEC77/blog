###Привабливий ефект гортання для jQuery UI Tabs
Ефект гортання досягається за допомогою простого використання callback-а `beforeActivate`:

```js
jQuery('#registration-wizard').tabs({
    beforeActivate: function(event, ui) {
        var tabs = jQuery(this),
            isNext = (ui.newTab.index() < tabs.tabs('option', 'active'));
        tabs.tabs({
            show: {
                effect: 'slide',
                direction: isNext ? 'right' : 'left',
                duration: 400
            },
            hide: {
                effect: 'slide',
                direction: !isNext ? 'right' : 'left',
                duration: 400
            }
        });
    }
});
```
