---
title: Intl.DateTimeFormat.prototype.formatRange()
slug: Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat/formatRange
translation_of: Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat/formatRange
original_slug: Web/JavaScript/Reference/Objets_globaux/Intl/DateTimeFormat/formatRange
browser-compat: javascript.builtins.Intl.DateTimeFormat.formatRange
---
{{JSRef}}

La méthode **`Intl.DateTimeFormat.prototype.formatRange()`** permet de formater un intervalle de dates de la façon la plus concise en fonction de la **`locale`** et des **`options`** fournies lors de l'initialisation de l'objet [`Intl.DateTimeFormat`](/fr/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat).

{{EmbedInteractiveExample("pages/js/intl-datetimeformat-prototype-formatrange.html","taller")}}

## Syntaxe

```js
formatRange(dateDébut, dateFin)
```

## Exemples

### Utilisation simple de `formatRange()`

Cette méthode reçoit comme arguments deux objets [`Date`](/fr/docs/Web/JavaScript/Reference/Global_Objects/Date) et renvoie l'intervalle de la façon la plus concise possible (selon les options fournies lors de l'instanciation du formateur [`Intl.DateTimeFormat`](/fr/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat)).

```js
let date1 = new Date(Date.UTC(2007, 0, 10, 10, 0, 0));
let date2 = new Date(Date.UTC(2007, 0, 10, 11, 0, 0));
let date3 = new Date(Date.UTC(2007, 0, 20, 10, 0, 0));
// > 'Wed, 10 Jan 2007 10:00:00 GMT'
// > 'Wed, 10 Jan 2007 11:00:00 GMT'
// > 'Sat, 20 Jan 2007 10:00:00 GMT'

let fmt1 = new Intl.DateTimeFormat("en", {
    year: '2-digit',
    month: 'numeric',
    day: 'numeric',
    hour: 'numeric',
    minute: 'numeric'
});
console.log(fmt1.format(date1));
console.log(fmt1.formatRange(date1, date2));
console.log(fmt1.formatRange(date1, date3));
// > '1/10/07, 10:00 AM'
// > '1/10/07, 10:00 – 11:00 AM'
// > '1/10/07, 10:00 AM – 1/20/07, 10:00 AM'

let fmt2 = new Intl.DateTimeFormat("en", {
    year: 'numeric',
    month: 'short',
    day: 'numeric'
});
console.log(fmt2.format(date1));
console.log(fmt2.formatRange(date1, date2));
console.log(fmt2.formatRange(date1, date3));
// > 'Jan 10, 2007'
// > 'Jan 10, 2007'
// > 'Jan 10 – 20, 2007'
```

## Spécifications

{{Specifications}}

## Compatibilité des navigateurs

{{Compat}}

## Voir aussi

- [`Intl.DateTimeFormat`](/fr/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat)